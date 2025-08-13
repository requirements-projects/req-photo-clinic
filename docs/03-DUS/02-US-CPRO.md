# Módulo: Gestão de Prontuários (CPRO)

## Histórias de Usuário

- [[US-CPRO-001] Registrar anotação clínica](#us-cpro-001-registrar-anotação-clínica)
- [[US-CPRO-002] Consultar histórico do prontuário](#us-cpro-002-consultar-histórico-do-prontuário)
- [[US-CPRO-003] Editar anotação com rastreabilidade](#us-cpro-003-editar-anotação-com-rastreabilidade)

---

## [US-CPRO-001] Registrar anotação clínica

**Como** um Profissional de Saúde,
**Eu quero** criar uma nova anotação no prontuário de um paciente durante ou após uma consulta,
**Para que** eu possa registrar informações clínicas importantes, como a evolução do tratamento e observações.

### Critérios de Aceitação
1.  **Dado que** estou no perfil de um paciente,
    **Quando** eu crio uma nova anotação com texto e salvo,
    **Então** a anotação é associada ao paciente, ao meu usuário e à data/hora atual, e aparece no topo do histórico.

### Referências
- **RF:** CPRO-001

---

## [US-CPRO-002] Consultar histórico do prontuário

**Como** um Profissional de Saúde,
**Eu quero** visualizar o histórico completo de anotações de um paciente em ordem cronológica,
**Para que** eu possa ter uma visão completa do seu histórico clínico para tomar decisões informadas.

### Critérios de Aceitação
1.  **Dado que** abro o prontuário de um paciente,
    **Quando** a tela carrega,
    **Então** o sistema exibe uma lista de todas as anotações em ordem cronológica decrescente (a mais recente primeiro).

### Referências
- **RF:** CPRO-002

---

## [US-CPRO-003] Editar anotação com rastreabilidade

**Como** um Profissional de Saúde,
**Eu quero** editar uma anotação que fiz anteriormente para corrigir um erro ou adicionar informações,
**Para que** o prontuário se mantenha preciso, mas sem perder a integridade do registro original.

### Critérios de Aceitação
1.  **Dado que** estou visualizando uma anotação que eu criei,
    **Quando** eu edito o texto e salvo,
    **Então** a anotação é atualizada e o sistema registra um log de auditoria com a data, o usuário e a alteração realizada.

### Referências
- **RF:** CPRO-003
