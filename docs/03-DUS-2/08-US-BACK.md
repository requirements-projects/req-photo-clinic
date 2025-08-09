# Módulo: Backup e Recuperação (BACK)

## Histórias de Usuário

- [[US-BACK-001] Garantir backup automático e regular](#us-back-001-garantir-backup-automático-e-regular)
- [[US-BACK-002] Restaurar dados em caso de falha](#us-back-002-restaurar-dados-em-caso-de-falha)

---

## [US-BACK-001] Garantir backup automático e regular

**Como** um Administrador do Sistema,
**Eu quero** que o sistema realize backups automáticos e diários de todo o banco de dados,
**Para que** possamos nos recuperar de uma eventual perda de dados (ex: falha de hardware) com o mínimo de impacto.

### Critérios de Aceitação
1.  **Dado que** o sistema está em operação,
    **Quando** chega o horário agendado para o backup (ex: toda madrugada),
    **Então** um backup completo dos dados é gerado e armazenado em um local seguro e geograficamente distinto.

### Referências
- **RF:** BACK-001

---

## [US-BACK-002] Restaurar dados em caso de falha

**Como** um Administrador do Sistema,
**Eu quero** ter um procedimento claro e testado para restaurar os dados a partir do último backup bem-sucedido,
**Para que** o sistema possa voltar a operar rapidamente após um incidente crítico.

### Critérios de Aceitação
1.  **Dado que** ocorreu uma falha que corrompeu o banco de dados principal,
    **Quando** eu aciono o procedimento de restauração,
    **Então** o sistema é restaurado ao estado do último backup válido dentro do tempo de recuperação (RTO) definido.

### Referências
- **RF:** BACK-003
