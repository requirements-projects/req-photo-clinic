# MCR - Documento de Recursos da API

## Sumário

- [1. Introdução](#1-introdução)
- [2. Visão Geral da API](#2-visão-geral-da-api)
- [3. Convenções e Padrões](#3-convenções-e-padrões)
- [4. Domínio: Gestão de Pacientes](#4-domínio-gestão-de-pacientes)
  - [4.1. Pacientes (`/patients`)](#41-pacientes-patients)
  - [4.2. Prontuários (`/patients/{patientId}/records`)](#42-prontuários-patientspatientidrecords)
- [5. Domínio: Registro Fotográfico](#5-domínio-registro-fotográfico)
  - [5.1. Fotos (`/photos`)](#51-fotos-photos)
  - [5.2. Histórico Fotográfico (`/patients/{patientId}/photos`)](#52-histórico-fotográfico-patientspatientidphotos)
  - [5.3. Colagens (`/collages`)](#53-colagens-collages)
  - [5.4. Categorias de Imagem (`/photo-categories`)](#54-categorias-de-imagem-photo-categories)
- [6. Domínio: Sessões de Tratamento](#6-domínio-sessões-de-tratamento)
  - [6.1. Sessões (`/sessions`)](#61-sessões-sessions)
- [7. Domínio: Infraestrutura](#7-domínio-infraestrutura)
  - [7.1. Autenticação (`/auth/token`)](#71-autenticação-authtoken)
  - [7.2. Dispositivos Autorizados (`/devices`)](#72-dispositivos-autorizados-devices)
  - [7.3. Sincronização (`/sync`)](#73-sincronização-sync)

---

## 1. Introdução

Este documento descreve os recursos e endpoints da API REST do PhotoClinic. A API é projetada seguindo os princípios de uma arquitetura com ênfase em segurança, auditabilidade e controle de acesso baseado em papéis (RBAC).

## 2. Visão Geral da API

| Atributo      | Valor                                   |
|---------------|----------------------------------------|
| URL Base      | https://api.photoclinic.com/v1         |
| Versão        | v1                                     |
| Content-Type  | application/json                        |
| Autenticação  | JWT Bearer Token                        |

## 3. Convenções e Padrões

### 3.1. Autenticação
- Todas as requisições (exceto `/auth/token`) devem incluir o cabeçalho `Authorization: Bearer {token}`.

### 3.2. Formato dos Dados
- Requisições com corpo devem usar o formato JSON e o cabeçalho `Content-Type: application/json`.
- Nomes de campos seguem o padrão `camelCase`.
- Timestamps são representados em formato ISO 8601 (UTC): `YYYY-MM-DDTHH:mm:ss.sssZ`.
- UUIDs são utilizados como identificadores únicos de recursos.

### 3.3. Respostas
- **Sucesso:** Códigos HTTP 2xx.
- **Erros:** Códigos HTTP 4xx (cliente) ou 5xx (servidor).
- **Recurso Único:** O objeto do recurso é retornado diretamente.
- **Listas Paginadas:** A resposta segue o formato:
  ```json
  {
    "count": 123,
    "next": "https://api.photoclinic.com/v1/patients/?page=3",
    "previous": "https://api.photoclinic.com/v1/patients/?page=1",
    "results": [
      { ... },
      { ... }
    ]
  }
  ```

### 3.4. Erros
- Erros de validação de campos retornam um objeto com os campos e seus respectivos erros.
  ```json
  {
    "cpf": ["CPF inválido."]
  }
  ```
- Outros erros seguem o formato:
  ```json
  {
    "detail": "Descrição do erro",
    "code": "CODIGO_DO_ERRO"
  }
  ```

---

## 4. Domínio: Gestão de Pacientes

Recursos para gerenciar o ciclo de vida completo dos pacientes e seus prontuários clínicos.

### 4.1. Pacientes (`/patients`)

#### `GET /patients`
- **Descrição:** Lista todos os pacientes com filtros e paginação.
- **Permissões:** `read:patients`
- **Parâmetros de Query:**
  - `page` (int): Número da página.
  - `pageSize` (int): Itens por página (padrão: 20).
  - `search` (string): Busca por nome ou CPF.
- **Resposta (200 OK):**
  ```json
  {
    "count": 1,
    "next": null,
    "previous": null,
    "results": [
      {
        "id": "uuid-paciente-123",
        "name": "João da Silva",
        "cpf": "123.456.789-00",
        "birthDate": "1985-10-20",
        "createdAt": "2024-01-15T10:00:00Z"
      }
    ]
  }
  ```

#### `GET /patients/{id}`
- **Descrição:** Busca um paciente específico pelo seu ID.
- **Permissões:** `read:patients`
- **Resposta (200 OK):**
  ```json
  {
    "id": "uuid-paciente-123",
    "name": "João da Silva",
    "cpf": "123.456.789-00",
    "birthDate": "1985-10-20",
    "phone": "+5511987654321",
    "email": "joao.silva@example.com",
    "createdAt": "2024-01-15T10:00:00Z",
    "updatedAt": "2024-01-16T09:00:00Z"
  }
  ```

#### `POST /patients`
- **Descrição:** Cria um novo paciente.
- **Permissões:** `create:patients`
- **Corpo da Requisição:**
  ```json
  {
    "name": "Maria Souza",
    "cpf": "111.222.333-44",
    "birthDate": "1990-05-15",
    "phone": "+5511987654321",
    "email": "maria.souza@example.com"
  }
  ```
- **Resposta (201 CREATED):**
  ```json
  {
    "id": "uuid-paciente-456",
    "name": "Maria Souza",
    "cpf": "111.222.333-44",
    "birthDate": "1990-05-15",
    "createdAt": "2024-03-10T14:30:00Z"
  }
  ```

#### `PUT /patients/{id}`
- **Descrição:** Atualiza os dados de um paciente existente.
- **Permissões:** `update:patients`
- **Corpo da Requisição:**
  ```json
  {
    "name": "João da Silva Santos",
    "phone": "+5511999998888",
    "email": "joao.santos@example.com"
  }
  ```
- **Resposta (200 OK):** Retorna o objeto do paciente atualizado.

#### `DELETE /patients/{id}`
- **Descrição:** Inativa um paciente. A inativação é lógica (soft delete).
- **Permissões:** `delete:patients`
- **Resposta (204 NO CONTENT):** Nenhuma resposta no corpo.

### 4.2. Prontuários (`/patients/{patientId}/records`)

Recursos para gerenciar as anotações clínicas no prontuário de um paciente.

#### `GET /patients/{patientId}/records`
- **Descrição:** Lista as anotações do prontuário de um paciente.
- **Permissões:** `read:records`
- **Resposta (200 OK):**
  ```json
  {
    "count": 1,
    "next": null,
    "previous": null,
    "results": [
      {
        "id": "uuid-prontuario-789",
        "patientId": "uuid-paciente-123",
        "notes": "Paciente relata melhora no tratamento...",
        "authorId": "uuid-profissional-abc",
        "createdAt": "2024-02-20T11:00:00Z"
      }
    ]
  }
  ```

#### `POST /patients/{patientId}/records`
- **Descrição:** Adiciona uma nova anotação ao prontuário do paciente.
- **Permissões:** `create:records`
- **Corpo da Requisição:**
  ```json
  {
    "notes": "Nova anotação sobre o progresso do tratamento.",
    "authorId": "uuid-profissional-abc"
  }
  ```
- **Resposta (201 CREATED):**
  ```json
  {
    "id": "uuid-prontuario-999",
    "patientId": "uuid-paciente-123",
    "notes": "Nova anotação sobre o progresso do tratamento.",
    "authorId": "uuid-profissional-abc",
    "createdAt": "2024-03-12T18:00:00Z"
  }
  ```

#### `PUT /patients/{patientId}/records/{recordId}`
- **Descrição:** Atualiza uma anotação clínica existente.
- **Permissões:** `update:records`
- **Corpo da Requisição:**
  ```json
  {
    "notes": "Correção da anotação anterior."
  }
  ```
- **Resposta (200 OK):** Retorna o objeto da anotação atualizada.

#### `DELETE /patients/{patientId}/records/{recordId}`
- **Descrição:** Remove uma anotação clínica.
- **Permissões:** `delete:records`
- **Resposta (204 NO CONTENT):** Nenhuma resposta no corpo.

---

## 5. Domínio: Registro Fotográfico

Recursos para gerenciar o ciclo de vida das fotografias clínicas, incluindo upload, categorização e organização.

### 5.1. Fotos (`/photos`)

#### `POST /photos`
- **Descrição:** Realiza o upload de uma nova foto e a associa a um paciente.
- **Permissões:** `create:photos`
- **Corpo da Requisição (multipart/form-data):**
  - `file`: O arquivo da imagem.
  - `patientId` (string): ID do paciente.
  - `sessionId` (string): ID da sessão de tratamento.
  - `capturedAt` (string): Data/hora da captura (ISO 8601).
- **Resposta (201 CREATED):**
  ```json
  {
    "id": "uuid-foto-abc",
    "patientId": "uuid-paciente-123",
    "url": "https://storage.photoclinic.com/fotos/uuid-foto-abc.jpg",
    "thumbnailUrl": "https://storage.photoclinic.com/fotos/uuid-foto-abc_thumb.jpg",
    "capturedAt": "2024-03-10T15:00:00Z"
  }
  ```

#### `GET /photos/{id}`
- **Descrição:** Busca os metadados de uma foto específica.
- **Permissões:** `read:photos`
- **Resposta (200 OK):** Retorna o objeto da foto.

#### `PUT /photos/{id}`
- **Descrição:** Atualiza os metadados de uma foto (ex: categorias).
- **Permissões:** `update:photos`
- **Corpo da Requisição:**
  ```json
  {
    "categoryIds": ["uuid-categoria-face", "uuid-categoria-perfil"]
  }
  ```
- **Resposta (200 OK):** Retorna o objeto da foto atualizado.

#### `DELETE /photos/{id}`
- **Descrição:** Remove uma foto.
- **Permissões:** `delete:photos`
- **Resposta (204 NO CONTENT):** Nenhuma resposta no corpo.

### 5.2. Histórico Fotográfico (`/patients/{patientId}/photos`)

#### `GET /patients/{patientId}/photos`
- **Descrição:** Retorna a galeria de fotos de um paciente.
- **Permissões:** `read:photos`
- **Resposta (200 OK):**
  ```json
  {
    "count": 1,
    "next": null,
    "previous": null,
    "results": [
      {
        "id": "uuid-foto-abc",
        "url": "https://storage.photoclinic.com/fotos/uuid-foto-abc.jpg",
        "thumbnailUrl": "https://storage.photoclinic.com/fotos/uuid-foto-abc_thumb.jpg",
        "capturedAt": "2024-03-10T15:00:00Z"
      }
    ]
  }
  ```

### 5.3. Colagens (`/collages`)

Recursos para criar e gerenciar colagens de imagens.

#### `POST /collages`
- **Descrição:** Cria uma nova colagem a partir de duas ou mais fotos existentes.
- **Permissões:** `create:collages`
- **Corpo da Requisição:**
  ```json
  {
    "patientId": "uuid-paciente-123",
    "photoIds": [
      "uuid-foto-abc",
      "uuid-foto-def"
    ],
    "layout": "side-by-side",
    "title": "Antes e Depois - Tratamento X"
  }
  ```
- **Resposta (201 CREATED):**
  ```json
  {
    "id": "uuid-colagem-xyz",
    "patientId": "uuid-paciente-123",
    "url": "https://storage.photoclinic.com/colagens/uuid-colagem-xyz.jpg",
    "createdAt": "2024-03-11T10:00:00Z"
  }
  ```

#### `GET /collages/{id}`
- **Descrição:** Busca uma colagem específica pelo ID.
- **Permissões:** `read:collages`
- **Resposta (200 OK):** Retorna o objeto da colagem.

#### `DELETE /collages/{id}`
- **Descrição:** Remove uma colagem.
- **Permissões:** `delete:collages`
- **Resposta (204 NO CONTENT):** Nenhuma resposta no corpo.

---

### 5.4. Categorias de Imagem (`/photo-categories`)

Recursos para gerenciar as categorias (tags) que podem ser aplicadas às fotos.

#### `GET /photo-categories`
- **Descrição:** Lista todas as categorias de imagem disponíveis.
- **Permissões:** `read:photo-categories`
- **Resposta (200 OK):**
  ```json
  {
    "count": 2,
    "results": [
      { "id": "uuid-cat-1", "name": "Face Frontal" },
      { "id": "uuid-cat-2", "name": "Perfil Direito" }
    ]
  }
  ```

#### `POST /photo-categories`
- **Descrição:** Cria uma nova categoria de imagem.
- **Permissões:** `create:photo-categories`
- **Corpo da Requisição:** `{"name": "Nova Categoria"}`
- **Resposta (201 CREATED):** Retorna o objeto da nova categoria.

#### `PUT /photo-categories/{id}`
- **Descrição:** Atualiza o nome de uma categoria.
- **Permissões:** `update:photo-categories`
- **Corpo da Requisição:** `{"name": "Face Frontal Editado"}`
- **Resposta (200 OK):** Retorna o objeto atualizado.

#### `DELETE /photo-categories/{id}`
- **Descrição:** Remove uma categoria de imagem.
- **Permissões:** `delete:photo-categories`
- **Resposta (204 NO CONTENT):** Nenhuma resposta no corpo.

---

## 6. Domínio: Sessões de Tratamento

Recursos para agrupar registros fotográficos e anotações em uma sessão de tratamento específica.

### 6.1. Sessões (`/sessions`)

#### `POST /sessions`
- **Descrição:** Cria uma nova sessão de tratamento para um paciente.
- **Permissões:** `create:sessions`
- **Corpo da Requisição:**
  ```json
  {
    "patientId": "uuid-paciente-123",
    "title": "Sessão de Acompanhamento - Laser",
    "scheduledFor": "2024-04-01T10:00:00Z"
  }
  ```
- **Resposta (201 CREATED):** Retorna o objeto da sessão criada.

#### `GET /patients/{patientId}/sessions`
- **Descrição:** Lista todas as sessões de um paciente.
- **Permissões:** `read:sessions`
- **Resposta (200 OK):** Lista paginada de sessões.

#### `GET /sessions/{id}`
- **Descrição:** Busca uma sessão específica.
- **Permissões:** `read:sessions`
- **Resposta (200 OK):** Retorna o objeto da sessão.

---

## 7. Domínio: Infraestrutura

Recursos relacionados à autenticação, autorização de dispositivos e sincronização de dados.

### 7.1. Autenticação (`/auth/token`)

#### `POST /auth/token`
- **Descrição:** Autentica um usuário e retorna um token JWT.
- **Permissões:** Nenhuma (endpoint público).
- **Corpo da Requisição:**
  ```json
  {
    "username": "profissional@clinic.com",
    "password": "senhaSuperSegura"
  }
  ```
- **Resposta (200 OK):**
  ```json
  {
    "accessToken": "ey...",
    "refreshToken": "ey...",
    "expiresIn": 3600
  }
  ```

### 7.2. Dispositivos Autorizados (`/devices`)

#### `POST /devices/authorize`
- **Descrição:** Solicita a autorização de um novo dispositivo.
- **Permissões:** `authorize:device`
- **Corpo da Requisição:** `{"deviceId": "unique-device-identifier", "deviceName": "iPhone de João"}`
- **Resposta (202 ACCEPTED):** A solicitação foi recebida e aguarda aprovação de um administrador.

#### `GET /devices`
- **Descrição:** Lista todos os dispositivos autorizados e pendentes.
- **Permissões:** `manage:devices`
- **Resposta (200 OK):** Lista de dispositivos com seus status (`authorized`, `pending`).

#### `POST /devices/{id}/approve`
- **Descrição:** Aprova um dispositivo pendente.
- **Permissões:** `manage:devices`
- **Resposta (200 OK):** Retorna o objeto do dispositivo atualizado.

### 7.3. Sincronização (`/sync`)

#### `GET /sync/status`
- **Descrição:** Verifica o estado da fila de sincronização para o dispositivo atual.
- **Permissões:** `sync:data`
- **Resposta (200 OK):**
  ```json
  {
    "pendingItems": 15,
    "lastSyncAt": "2024-03-10T12:00:00Z",
    "status": "pending_upload"
  }
  ```

#### `POST /sync/upload`
- **Descrição:** Envia um lote de dados offline para o servidor.
- **Permissões:** `sync:data`
- **Corpo da Requisição:** Array de ações (criação/atualização de pacientes, fotos, etc.).
- **Resposta (202 ACCEPTED):** O lote foi recebido e está sendo processado.

#### `GET /sync/download`
- **Descrição:** Baixa atualizações do servidor para o dispositivo.
- **Permissões:** `sync:data`
- **Resposta (200 OK):** Array de dados atualizados para o cliente aplicar localmente.
