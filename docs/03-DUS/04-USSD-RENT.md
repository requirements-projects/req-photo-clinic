


# User Story Specification Document (USSD) - Gestão de Regras de Aluguel (RENT) Module

This document details the user stories for the **Gestão de Regras de Aluguel (RENT)** module. It translates functional requirements from the RQSD into actionable, user-centric narratives for the development team.

---

## Summary

- [[US-RENT-001] Cadastrar regra de aluguel individualmente](#us-rent-001-cadastrar-regra-de-aluguel-individualmente)
- [[US-RENT-002] Editar regra de aluguel com nova vigência](#us-rent-002-editar-regra-de-aluguel-com-nova-vigência)
- [[US-RENT-003] Importar regras de aluguel em lote](#us-rent-003-importar-regras-de-aluguel-em-lote)
- [[US-RENT-004] Validar e conferir regras de aluguel](#us-rent-004-validar-e-conferir-regras-de-aluguel)
- [[US-RENT-005] Visualizar lista e detalhes das regras](#us-rent-005-visualizar-lista-e-detalhes-das-regras)
- [[US-RENT-006] Acompanhar indicadores e alertas sobre regras](#us-rent-006-acompanhar-indicadores-e-alertas-sobre-regras)

---

## [US-RENT-001] Cadastrar regra de aluguel individualmente

**As a** Gestor de Energia,  
**I want to** register a new rental rule for one or more UCs,  
**so that** I can definir como o aluguel será calculado a partir de uma determinada data.

### Details
- Formulário deve exibir campos dinamicamente conforme o tipo de regra selecionada.
- Deve conter validação de campos obrigatórios, limites de valor e lógica de vigência.

### Acceptance Criteria
1. **Given** I select a formula type,  
   **when** I fill the required fields and submit,  
   **then** the rule is created and shown in the list.

### References
- **FR:** RENT001

### Problem(s) Solved
- Evita erros de cadastro manual.
- Garante cálculo coerente com os contratos acordados.

---

## [US-RENT-002] Editar regra de aluguel com nova vigência

**As a** Gestor de Energia,  
**I want to** update a rental rule without losing historical records,  
**so that** I can ajustar os valores de aluguel a partir de um novo período.

### Details
- A edição deve gerar uma nova versão com nova vigência.
- A regra anterior deve ser encerrada automaticamente.

### Acceptance Criteria
1. **Given** I open an active rule,  
   **when** I change its values and define a new start date,  
   **then** a new rule version is saved and the previous one ends.

### References
- **FR:** RENT003

### Problem(s) Solved
- Preserva histórico de contratos.
- Garante rastreabilidade da evolução de regras.

---

## [US-RENT-003] Importar regras de aluguel em lote

**As a** Operador Técnico,  
**I want to** import multiple rental rules using a spreadsheet,  
**so that** I can cadastrar regras de forma mais rápida e padronizada.

### Details
- Planilha com modelo oficial deve ser utilizada.
- Feedback linha a linha deve ser exibido no processamento.

### Acceptance Criteria
1. **Given** I upload a valid spreadsheet,  
   **when** I trigger the import,  
   **then** valid rows are saved and invalid ones are flagged with errors.

### References
- **FR:** RENT002

### Problem(s) Solved
- Agiliza grandes volumes de entrada.
- Reduz retrabalho e erros manuais.

---

## [US-RENT-004] Validar e conferir regras de aluguel

**As a** Administrador Cogni,  
**I want to** validate the consistency of all rental rules,  
**so that** I can evitar conflitos de vigência ou valores inválidos.

### Details
- O sistema deve verificar: sobreposição de vigência, valores fora do padrão, UCs sem regra.
- Resultado deve ser apresentado com alertas e sugestões.

### Acceptance Criteria
1. **Given** the validation is triggered,  
   **when** inconsistencies are found,  
   **then** I must see a report with type, affected rule and action suggestion.

### References
- **FR:** RENT005

### Problem(s) Solved
- Garante segurança operacional.
- Reduz falhas no cálculo de aluguel.

---

## [US-RENT-005] Visualizar lista e detalhes das regras

**As a** Gestor de Energia,  
**I want to** see all existing rental rules with filters,  
**so that** I can localizar, revisar ou editar regras facilmente.

### Details
- Lista deve conter status (ativo/inativo), tipo, fórmula aplicada, vigência, UC.
- Permitir ordenação e filtros por período, empresa, tipo.

### Acceptance Criteria
1. **Given** I access the rules list,  
   **when** I apply filters,  
   **then** only matching rules should be shown.

### References
- **FR:** RENT004

### Problem(s) Solved
- Otimiza gestão contínua.
- Apoia diagnóstico de erros e auditorias.

---

## [US-RENT-006] Acompanhar indicadores e alertas sobre regras

**As a** Administrador Cogni,  
**I want to** visualize metrics about rental rules coverage and errors,  
**so that** I can monitorar se o sistema está corretamente parametrizado.

### Details
- Painel com totais de regras por status, tipo, pendências e ausência por UC.
- Alertas visuais de inconsistências.

### Acceptance Criteria
1. **Given** I open the dashboard,  
   **when** the data loads,  
   **then** I must see updated metrics and any active alerts.

### References
- **FR:** RENT006

### Problem(s) Solved
- Oferece visão executiva.
- Facilita atuação preventiva sobre regras faltantes ou inválidas.