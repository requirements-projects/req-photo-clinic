# Documento de Qualificação de Escopo e Requisitos (DQER) - Sugestão

## 1. Propósito deste Documento

Este documento tem como finalidade estabelecer formalmente o escopo e os requisitos do sistema PhotoClinic, a partir do alinhamento entre a visão do projeto (conforme o Termo de Abertura) e as funcionalidades técnicas necessárias para atender às necessidades dos usuários.
Ele garante que todas as partes envolvidas compartilhem um entendimento comum sobre o que será construído, em que termos e com quais critérios de aceitação, possibilitando rastreabilidade ao longo de todo o ciclo de vida do projeto.

## 2. Público-alvo deste Documento

Este documento destina-se a desenvolvedores, designers, testadores e gestores envolvidos no projeto, bem como stakeholders que necessitem entender o escopo funcional e técnico do sistema.

## 3. Introdução

A aplicação PhotoClinic é uma **solução móvel** voltada para clínicas de estética e consultórios médicos, cujo propósito é padronizar, organizar e manter a integridade dos registros fotográficos de seus pacientes, com fins estéticos, legais e comerciais. A solução visa substituir a utilização da galeria de fotos padrão dos dispositivos móveis por um ambiente dedicado, seguro e organizado.

**Inspirado no funcionamento e nas falhas observadas no app PhotoDoc, o sistema visa oferecer uma experiência aprimorada, com maior precisão, segurança de dados e foco na usabilidade clínica.**

## 4. Objetivos do Sistema
Desenvolver um aplicativo móvel que permita a captura, organização, sincronização e comparação de imagens clínicas de pacientes, com foco na padronização visual e na segurança da informação.

- Criar álbuns individuais de pacientes com organização cronológica;
- Registrar e organizar imagens de pacientes em sessões estéticas, com padronização visual (molduras, posicionamento, iluminação, modo fantasma);
- Permitir criação de colagens para comparação "antes e depois";
- Armazenar imagens exclusivamente em ambiente seguro, fora da galeria do celular;
- Proteger a integridade dos dados (sigilo, backup e controle de acesso);
- Gerar colagens e relatórios para fins clínicos, de marketing e documentação;
- Garantir rastreabilidade de alterações e registros fotográficos;
- Atender normas éticas, legais e técnicas sobre o uso de imagem em ambientes clínicos.

## 5. Perfis de Usuário

| Perfil                               | Descrição                                                                   | Acesso                                          |
| ------------------------------------ | --------------------------------------------------------------------------- | ----------------------------------------------- |
| **Profissional de Estética**         | Responsável pela captura de imagens na sala de procedimentos.               | Câmera, molduras, modo fantasma, colagens.      |
| **Médico(a)**                        | Utiliza as imagens para demonstrar evolução ao paciente durante a consulta. | Visualização de álbuns e colagens, comparações. |
| **Administrador Clínico** *(futuro)* | Gerencia permissões, pacientes e exportações de imagens.                    | Acesso completo.                                |
| **Paciente** *(indiretamente)*       | Sujeito dos dados, visualiza imagens com mediação do profissional.          | Nenhum acesso direto ao sistema.                |

## 6. Problemáticas Identificadas

| Stakeholder/Persona        | Problema                                                           | Solução Proposta                                              |
|----------------------------|--------------------------------------------------------------------|------------------------------------------------------------|
| Profissionais de Estética  | Desorganização das fotos na galeria padrão do celular               | Ambiente dedicado com organização por paciente e procedimento |
| Médicos e Pacientes        | Dificuldade em comparar precisamente o antes e depois de tratamentos | Modo fantasma e ferramentas de colagem                        |
| Administradores de Clínica | Risco de vazamento de dados sensíveis (LGPD)                         | Armazenamento seguro, criptografado e com controle de acesso  |
| Profissionais de Estética  | Inconsistência no enquadramento das fotos                           | Sistema de molduras padronizadas para diferentes partes do corpo |
| Equipe Multidisciplinar    | Falta de sincronização entre dispositivos da mesma clínica          | Sistema de sincronização segura entre dispositivos autorizados |

## 7. Domínios e Módulos do Sistema

### 7.1. Domínio de Gestão de Pacientes
*Objetivo: Gerenciar os dados e registros de todos os pacientes da clínica.*

| # | Módulo | Sigla | Descrição | Detalhamento |
|--|--|--|---|---|
|7.1.1| **Cadastro de Paciente** | CPAC | Responsável pelo registro, edição e consulta dos dados dos pacientes. | [Cadastro de Paciente](./7.1.1-CPAC.md) |
|7.1.2| **Gestão de Prontuários**| CPRO | Centraliza as informações clínicas não-fotográficas dos pacientes. | [Gestão de Prontuários](./7.1.2-CPRO.md) |


### 7.2. Domínio de Registro Fotográfico
*Objetivo: Gerenciar todo o ciclo de vida das fotografias clínicas.*

| # | Módulo | Sigla | Descrição | Detalhamento |
|--|--|--|--|--|
|7.2.1| **Histórico Clínico Fotográfico**| HCF | Gerencia as imagens dos pacientes. | [Histórico Clínico Fotográfico](./7.2.1-HCF.md) |
|7.2.2| **Captura de Imagens** | CIM | Interface de captura com suporte a molduras e modo fantasma. | [Captura de Imagens](./7.2.2-CIM.md) |
|7.2.3| **Processamento de Imagens** | PIMA | Criação de colagens, ajustes e comparativos visuais. | [Processamento de Imagens](./7.2.3-PIMA.md) |

### 7.3. Domínio de Infraestrutura
*Objetivo: Fornecer os serviços de base para a aplicação.*

| # | Módulo | Sigla | Descrição | Detalhamento |
|--|--|---|---|---|
|7.3.1| **Sincronização** | SYNC | Mantém os dados sincronizados entre diferentes dispositivos. | [Sincronização](./7.3.1-SYNC.md) |
|7.3.2| **Armazenamento** | STOR | Gerenciamento do armazenamento seguro das imagens e dados em nuvem. | [Armazenamento](./7.3.2-STOR.md) |
|7.3.3| **Backup e Recuperação** | BACK | Garante a segurança e disponibilidade dos dados. | [Backup e Recuperação](./7.3.3-BACK.md) |

### 7.4. Domínio de Experiência do Usuário
*Objetivo: Fornecer interfaces e fluxos otimizados para diferentes perfis de usuários.*

| # | Módulo | Sigla | Descrição | Detalhamento |
|--|--|---|---|---|
|7.4.1| **Interface de Fotografia** | UIFOT | Otimizada para profissionais que realizam a captura de imagens. | [Interface de Fotografia](./7.4.1-UIFOT.md) |
|7.4.2| **Interface de Consulta** | UICON | Dedicada à visualização e análise durante o atendimento médico. | [Interface de Consulta](./7.4.2-UICON.md) |

## 8. Integrações e Dependências

### 8.1. Integrações Internas
- O módulo de Captura de Imagens se integra com o Modo Fantasma para permitir comparações precisas.
- O módulo de Processamento de Imagem se integra com a Galeria do Paciente para selecionar e organizar fotos.
- O módulo de Sincronização se integra com todos os outros para garantir consistência de dados entre dispositivos.

### 8.2. Dependências Externas
- Sistema operacional iOS (inicial) com suporte à câmera de alta resolução.
- Serviço de armazenamento em nuvem para backup e sincronização.

## 9. Anexos e Referências

- TAP (Termo de Abertura do Projeto)
- Análise do aplicativo concorrente PhotoDoc
- Protótipos de interface de usuário (a serem desenvolvidos)
- Legislação LGPD aplicável ao armazenamento de dados biométricos
