# Documento de User Stories (DUS)

## 1. Propósito deste Documento
Este documento organiza e detalha as histórias de usuário derivadas dos requisitos funcionais e das problemáticas identificadas no DQER. Ele visa alinhar expectativas funcionais de forma clara e compreensível para todas as partes envolvidas no desenvolvimento.

## 2. Público-alvo
Este documento destina-se a desenvolvedores, analistas, product owners, designers e qualquer stakeholder envolvido no processo de construção da solução.

## 3. Estrutura da User Story

> Cada user story deve conter:
> - ID (formato: US-[SIGLA]-[NÚMERO])
> - Título breve
> - Descrição no formato "Como [persona], quero [ação] para [benefício]"
> - Critérios de aceitação
> - Notas técnicas
> - Referências ao DQER (requisitos relacionados)
> - Problema resolvido

## 4. Domínios e Módulos do Sistema

As user stories do sistema estão organizadas por módulos, seguindo a mesma estrutura do DQER. Cada módulo possui seu próprio documento de user stories com informações específicas sobre seu contexto e funcionalidades.

### 4.1. Segurança

Este domínio abrange a segurança e auditoria do sistema, incluindo autenticação, autorização, log de atividades e prevenção a fraudes.

| #   | Seção                             | Descrição                                         | Detalhamento do módulo                          |
|-----|-----------------------------------|---------------------------------------------------|-------------------------------------------------|
| 1   | Auditoria de dados                | Relatório de ações de usuários no sistema         | [Auditoria de Dados](01-Auditoria-dados.md)     |
| 2   | Controle de Acesso e Permissões   | Gestão de permissões e perfis                     | [RBAC](02-RBAC.md)                              |
| 3   | Prevenção de Fraudes e Validações | Mecanismos de segurança e validação de operações  | [Prevenção de Fraudes](11-Prevencao-fraudes.md) |

### 4.2. Infraestrutura da Fazenda

Este domínio abrange o mapeamento e gestão da estrutura física da fazenda e das pessoas que nela atuam.

| #   | Seção               | Descrição                                                            | Detalhamento do módulo          |
|-----|---------------------|----------------------------------------------------------------------|---------------------------------|
| 1   | Infraestrutura      | Gestão da estrutura física da fazenda, pastos, retiros e instalações | [Fazenda](03-Fazenda.md)        |
| 2   | Membros de Fazendas | Gestão de funcionários, colaboradores e seus perfis                  | [Membros](04-Membros-fazenda.md) |

### 4.3. Insumos

Este domínio abrange o controle de insumos e equipamentos utilizados na operação da fazenda.

| #   | Seção             | Descrição                                      | Detalhamento do módulo           |
|-----|-------------------|------------------------------------------------|----------------------------------|
| 1   | Fornecedores      | Gestão de fornecedores de insumos e serviços   | [Fornecedores](05-Fornecedores.md) |
| 2   | Gestão de Estoque | Controle de entrada, saída e saldo de insumos  | [Estoque](06-Estoque.md)         |
| 3   | Maquinários       | Inventário e controle de maquinário da fazenda         | [Maquinário](07-Maquinario.md)   |
| 4   | Fábrica de Ração  | Formulação, produção e distribuição de rações personalizadas | [Fábrica de Ração](07-Fabrica-de-racao.md) |

### 4.4. Gestão de Rebanho

Este domínio abrange o controle e gestão do rebanho, incluindo manejo, reprodução e saúde animal.

| #   | Seção                | Descrição                                               | Detalhamento do módulo                       |
|-----|----------------------|---------------------------------------------------------|----------------------------------------------|
| 1   | Manejo de Rebanho    | Controle de movimentações e agrupamentos de animais     | [Manejo de Rebanho](05-Manejo-de-rebanho.md) |
| 2   | Controle Reprodutivo | Gerenciamento do ciclo reprodutivo do rebanho           | [Reprodutivo](07-Reprodutivo.md)             |
| 3   | Controle Sanitário   | Gerenciamento de ações sanitárias aplicadas ao rebanho  | [Sanitário](07-Sanitario.md)                 |

### 4.5. Operação

Este domínio abrange a gestão das operações diárias da fazenda, incluindo planejamento de rotinas e atividades.

| #   | Seção                | Descrição                                          | Detalhamento do módulo                    |
|-----|----------------------|----------------------------------------------------|-------------------------------------------|
| 1   | Plano de Rotina      | Planejamento de rotinas operacionais estruturadas  | [Plano de Rotina](08-Plano-de-rotinas.md) |
| 2   | Gestão de Atividades | Gerenciamento de tarefas diárias e recorrentes     | [Atividades](09-Atividade.md)             |

### 4.6. Financeiro

Este domínio abrange o gerenciamento financeiro da operação pecuária.

| #   | Seção      | Descrição                                     | Detalhamento do módulo         |
|-----|------------|-----------------------------------------------|--------------------------------|
| 1   | Financeiro | Gerenciamento financeiro da operação pecuária | [Financeiro](10-Financeiro.md) |

### 4.7. Ferramentas de Plataforma

Este domínio abrange funcionalidades transversais que permeiam todo o sistema.

| #   | Seção                       | Descrição                                                | Detalhamento do módulo              |
|-----|-----------------------------|----------------------------------------------------------|-------------------------------------|
| 1   | Plataformas e Sincronização | Gestão de plataformas web/mobile e sincronização offline | [Plataformas](11-Platforms-sync.md) |
| 2   | Backoffice                  | Funcionalidades administrativas para gestão da plataforma, incluindo gestão de clientes, planos de assinatura e configurações do sistema. | [Backoffice](12-Backoffice.md)                |

## 5. Observações Finais

> As user stories foram derivadas dos requisitos funcionais, não-funcionais e regras de negócio definidos no DQER.  
> Cada módulo contém user stories focadas na resolução dos problemas identificados no contexto do sistema BoiView.  
> A implementação deve priorizar as histórias de acordo com as necessidades de negócio e dependências técnicas.  
> Cada user story deve ser validada com stakeholders relevantes antes e após sua implementação.
