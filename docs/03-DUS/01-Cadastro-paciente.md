# Documento de User Stories (DUS) - Módulo Cadastro de Paciente (DQER)

Este documento detalha as histórias de usuário para o módulo **Cadastro de Paciente (DQER)**.  
Ele traduz os requisitos funcionais do **Documento de Requisitos e Regras (DRR)** em narrativas centradas no usuário, visando orientar o time de desenvolvimento.

---

## Sumário
- [[US-DQER-001] Cadastrar Paciente](#us-dqer-001---cadastrar-paciente)
- [[US-DQER-002] Editar Dados do Paciente](#us-dqer-002---editar-dados-do-paciente)
- [[US-DQER-003] Consultar Paciente](#us-dqer-003---consultar-paciente)
- [[US-DQER-004] Inativar Paciente](#us-dqer-004---inativar-paciente)
---

## US-DQER-001 - Cadastrar Paciente

**Como** Recepcionista da clínica  
**Quero** registrar um novo paciente no sistema  
**Para que** seus dados pessoais e de contato fiquem armazenados para uso em agendamentos, atendimentos e histórico clínico.

### Detalhes
- Formulário deve conter campos obrigatórios: Nome completo, CPF, Data de nascimento, Telefone, Endereço, E-mail.  
- Deve validar duplicidade por CPF.  
- Campos opcionais: Observações, Indicação (quem indicou o paciente).  
- Ao salvar, gerar um identificador único do paciente.  

### Critérios de Aceitação
- **Dado** que o recepcionista preenche todos os campos obrigatórios  
  **Quando** clicar em "Salvar"  
  **Então** o paciente deve ser criado e listado na base de pacientes.

- **Dado** que um paciente com o mesmo CPF já exista  
  **Quando** tentar cadastrar  
  **Então** o sistema deve exibir mensagem de erro "Paciente já cadastrado".

### Referências
- RF: DQER001

### Problema(s) Resolvido(s)
- Centraliza o cadastro e evita duplicidade de dados.  
- Facilita busca e histórico de atendimento.

---

## US-DQER-002 - Editar Dados do Paciente

**Como** Recepcionista da clínica  
**Quero** atualizar as informações cadastrais de um paciente  
**Para que** os dados estejam sempre corretos e atualizados.

### Detalhes
- Possibilidade de edição apenas por usuários autorizados.  
- Registro de log com data/hora e usuário que realizou a alteração.  

### Critérios de Aceitação
- **Dado** que o usuário tenha permissão de edição  
  **Quando** salvar as alterações  
  **Então** as informações devem ser atualizadas e registradas no histórico de alterações.

### Referências
- RF: DQER002

### Problema(s) Resolvido(s)
- Garante integridade e atualização das informações.

---

## US-DQER-003 - Consultar Paciente

**Como** Profissional ou Recepcionista  
**Quero** buscar um paciente pelo nome, CPF ou telefone  
**Para que** eu possa acessar seu cadastro rapidamente.

### Detalhes
- Deve permitir busca parcial por nome.  
- Resultados ordenados por relevância.  

### Critérios de Aceitação
- **Dado** que o usuário insira parte do nome  
  **Quando** clicar em "Pesquisar"  
  **Então** o sistema retorna todos os pacientes que contenham o termo.

### Referências
- RF: DQER003

### Problema(s) Resolvido(s)
- Otimiza o atendimento e reduz tempo de busca.

---

## US-DQER-004 - Inativar Paciente

**Como** Administrador da clínica  
**Quero** marcar um paciente como inativo  
**Para que** ele não apareça mais nas listagens de agendamento e atendimento, mas mantenha histórico preservado.

### Detalhes
- Deve exigir justificativa para inativação.  
- Paciente inativo não pode ser associado a novos atendimentos.  

### Critérios de Aceitação
- **Dado** que o administrador selecione "Inativar"  
  **Quando** confirmar a ação  
  **Então** o paciente passa para status "Inativo" e sai das listagens.

### Referências
- RF: DQER004

### Problema(s) Resolvido(s)
- Mantém a base limpa e organizada sem perda de histórico.

---
