# Módulo: Cadastro de Paciente (CPAC)

## Histórias de Usuário

- [[US-CPAC-001] Cadastrar novo paciente](#us-cpac-001-cadastrar-novo-paciente)
- [[US-CPAC-002] Buscar por um paciente](#us-cpac-002-buscar-por-um-paciente)
- [[US-CPAC-003] Editar dados de um paciente](#us-cpac-003-editar-dados-de-um-paciente)
- [[US-CPAC-004] Inativar um paciente](#us-cpac-004-inativar-um-paciente)
- [[US-CPAC-005] Exportar dados do paciente](#us-cpac-005-exportar-dados-do-paciente)

---

## [US-CPAC-001] Cadastrar novo paciente

**Como** uma Recepcionista,
**Eu quero** registrar um novo paciente no sistema com suas informações essenciais (nome, CPF, contato),
**Para que** ele possa ser identificado e ter seu histórico clínico iniciado.

### Detalhes
- O formulário deve validar a unicidade do CPF para evitar pacientes duplicados.
- Campos como nome completo, CPF e telefone são obrigatórios.

### Critérios de Aceitação
1.  **Dado que** estou na tela de cadastro,
    **Quando** preencho todos os campos obrigatórios com dados válidos e salvo,
    **Então** o paciente é criado com sucesso e seu perfil é exibido.
2.  **Dado que** tento cadastrar um paciente com um CPF já existente,
    **Quando** tento salvar,
    **Então** o sistema exibe uma mensagem de erro e impede o cadastro.

### Referências
- **RF:** CPAC-001

---

## [US-CPAC-002] Buscar por um paciente

**Como** uma Recepcionista ou Profissional de Saúde,
**Eu quero** buscar por um paciente usando seu nome, CPF ou telefone,
**Para que** eu possa acessar rapidamente seu cadastro e prontuário.

### Critérios de Aceitação
1.  **Dado que** estou na tela de busca,
    **Quando** digito o nome ou CPF de um paciente existente e busco,
    **Então** o sistema exibe uma lista de resultados correspondentes.

### Referências
- **RF:** CPAC-003

---

## [US-CPAC-003] Editar dados de um paciente

**Como** uma Recepcionista,
**Eu quero** editar as informações cadastrais de um paciente existente,
**Para que** os dados do paciente se mantenham sempre atualizados.

### Critérios de Aceitação
1.  **Dado que** estou no perfil de um paciente,
    **Quando** altero uma informação (ex: telefone) e salvo,
    **Então** a alteração é registrada e o sistema mantém um log de quem e quando a modificação foi feita.

### Referências
- **RF:** CPAC-002

---

## [US-CPAC-004] Inativar um paciente

**Como** um Administrador do Sistema,
**Eu quero** inativar o cadastro de um paciente que não utiliza mais os serviços,
**Para que** ele não apareça em buscas ativas, mas seu histórico seja preservado por questões legais.

### Critérios de Aceitação
1.  **Dado que** um paciente está inativo,
    **Quando** uma recepcionista tenta agendar um novo atendimento para ele,
    **Então** o sistema deve impedir a ação e informar o status do paciente.

### Referências
- **RF:** CPAC-004

---

## [US-CPAC-005] Exportar dados do paciente

**Como** um Administrador do Sistema,
**Eu quero** exportar os dados cadastrais completos de um paciente em formato PDF,
**Para que** eu possa atender a uma solicitação do titular dos dados, conforme a LGPD.

### Critérios de Aceitação
1.  **Dado que** estou no perfil de um paciente,
    **Quando** clico na opção de exportar,
    **Então** o sistema gera um arquivo PDF com todos os dados cadastrais do paciente.

### Referências
- **RF:** CPAC-006
