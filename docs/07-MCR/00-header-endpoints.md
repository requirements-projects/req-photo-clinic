# API - Documentação de Endpoints

## 1. Introdução

Este documento descreve os padrões e convenções utilizados nos endpoints da API REST. A API é projetada seguindo os princípios de uma arquitetura com ênfase em segurança, auditabilidade e controle de acesso baseado em papéis (RBAC).

## 2. Visão Geral da API

| Atributo      | Valor                                   |
|---------------|----------------------------------------|
| URL Base      | https://api.project.com/v1             |
| Versão        | v1                                     |
| Content-Type  | application/json                        |
| Autenticação  | JWT Bearer Token                        |

## 3. Convenções

### 3.1. Requisições e Autenticação

- Todas as requisições devem incluir o cabeçalho `Authorization: Bearer {token}` (exceto endpoints de autenticação)
- Requisições com corpo devem usar o formato JSON e incluir o cabeçalho `Content-Type: application/json`
- Timestamps são enviados e recebidos em formato ISO 8601 (UTC): `YYYY-MM-DDTHH:mm:ss.sssZ`
- UUIDs são utilizados como identificadores únicos de recursos

### 3.2. Respostas

- Respostas bem-sucedidas retornam códigos HTTP na faixa 2xx
- Erros retornam códigos HTTP apropriados (4xx para erros de cliente, 5xx para erros de servidor)
- Respostas paginadas seguem o formato:
  ```json
  {
    "data": [...],
    "pagination": {
      "page": 1,
      "pageSize": 20,
      "totalPages": 10,
      "totalItems": 195
    }
  }
  ```

### 3.3. Erros

Códigos de erro seguem o formato:
```json
{
  "code": "ERROR_CODE",
  "message": "Descrição do erro",
  "details": { ... } // Opcional
}
```

### 3.4. Versionamento

- A versão da API é especificada na URL (`/v1/`)
- Mudanças incompatíveis resultam em uma nova versão da API
- Versões antigas são mantidas por um período de transição

### 3.5. Padrão de URLs

- Recursos são nomeados usando substantivos no plural: `/farms`, `/users`, `/livestock`
- Sub-recursos são acessados via recursos pai: `/farms/{id}/members`
- Operações especiais são expressas como verbos após o recurso: `/users/{id}/activate`
- Filtros, ordenação e paginação são aplicados via parâmetros de query

### 3.6. Métodos HTTP

| Método | Uso Comum                                        |
|--------|--------------------------------------------------|  
| GET    | Recuperar recursos ou coleções                    |
| POST   | Criar novos recursos ou acionar operações especiais |
| PUT    | Atualizar recursos inteiros (substituição)          |
| PATCH  | Atualizar recursos parcialmente                   |
| DELETE | Remover ou inativar recursos                      |

## 4. Paginação, Filtros e Ordenação

### 4.1. Paginação

| Parâmetro | Descrição                                     |
|-----------|-------------------------------------------------|  
| page      | Número da página (baseado em 1, padrão: 1)     |
| pageSize  | Itens por página (padrão: 20, máximo: 100)      |

### 4.2. Filtros Comuns

| Parâmetro    | Exemplo                   | Descrição                                |
|--------------|---------------------------|------------------------------------------|
| search       | search=fazenda           | Busca de texto em campos relevantes      |
| status       | status=active            | Filtra por status do recurso             |
| createdAfter | createdAfter=2025-01-15  | Recursos criados após a data             |
| createdBefore| createdBefore=2025-07-01 | Recursos criados antes da data           |

### 4.3. Ordenação

| Parâmetro    | Exemplo                | Descrição                                 |
|--------------|-----------------------|--------------------------------------------|  
| sortBy       | sortBy=createdAt      | Campo para ordenação                       |
| sortOrder    | sortOrder=desc        | Direção da ordenação (asc/desc, padrão: asc) |

## 5. Segurança e Boas Práticas

### 5.1. Autenticação e Autorização

- JWT (JSON Web Tokens) são usados para autenticação
- Tokens contêm claims para identificação e permissões do usuário
- Tokens têm tempo de vida limitado e mecanismo de refresh
- Autorização baseada em papéis (RBAC) controla o acesso a recursos

### 5.2. Proteções de Segurança

1. **Rate Limiting**: Limites de requisições para endpoints sensíveis
2. **Token Blacklisting**: Tokens invalidados são armazenados em blacklist
3. **Validação de Input**: Dados de entrada são validados em formato e conteúdo
4. **Proteção CSRF**: Tokens anti-CSRF para operações sensíveis
5. **Monitoramento**: Detecção de padrões de uso anômalos

### 5.3. Operação Offline

1. **Sincronização Bidirecional**: Suporte para criar/modificar dados offline
2. **Resolução de Conflitos**: Estratégias definidas para resolver conflitos de dados
3. **Timestamp de Origem**: Preservação do timestamp original das operações
4. **Priorização de Sincronização**: Dados críticos são sincronizados primeiro

## 6. Catálogo de Erros

| Código                      | HTTP Status | Descrição                                               |
|-----------------------------|-------------|--------------------------------------------------------|
| `AUTH_INVALID_CREDENTIALS`  | 401         | Credenciais inválidas (usuário/senha incorretos)        |
| `AUTH_ACCOUNT_LOCKED`       | 403         | Conta temporariamente bloqueada por tentativas inválidas |
| `AUTH_TOKEN_EXPIRED`        | 401         | Token JWT expirado                                      |
| `AUTH_TOKEN_INVALID`        | 401         | Token JWT inválido ou mal-formado                       |
| `AUTH_TOKEN_REVOKED`        | 401         | Token JWT foi revogado explicitamente                   |
| `RBAC_INSUFFICIENT_PERMISSIONS` | 403    | Usuário não possui permissão para a operação solicitada |
| `RESOURCE_NOT_FOUND`        | 404         | Recurso solicitado não encontrado                       |
| `VALIDATION_ERROR`          | 422         | Falha na validação dos dados fornecidos                 |
| `RATE_LIMIT_EXCEEDED`       | 429         | Limite de requisições excedido                          |
| `CONFLICT_ERROR`            | 409         | Conflito na operação (e.g., violação de regra de negócio) |
| `SERVER_ERROR`              | 500         | Erro interno do servidor                                |
| `SERVICE_UNAVAILABLE`       | 503         | Serviço temporariamente indisponível                    |
| `SYNC_CONFLICT`             | 409         | Conflito durante sincronização de dados offline         |
