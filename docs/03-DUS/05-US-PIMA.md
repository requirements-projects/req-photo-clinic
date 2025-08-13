# Módulo: Processamento de Imagens (PIMA)

## Histórias de Usuário

- [[US-PIMA-001] Criar colagem de antes e depois](#us-pima-001-criar-colagem-de-antes-e-depois)
- [[US-PIMA-002] Salvar colagem no histórico do paciente](#us-pima-002-salvar-colagem-no-histórico-do-paciente)

---

## [US-PIMA-001] Criar colagem de antes e depois

**Como** um Profissional de Saúde,
**Eu quero** criar uma colagem lado a lado com duas imagens selecionadas (antes e depois),
**Para que** eu possa ilustrar de forma clara e objetiva a evolução do tratamento para o paciente.

### Critérios de Aceitação
1.  **Dado que** eu selecionei duas imagens da galeria,
    **Quando** eu acesso a ferramenta de colagem,
    **Então** o sistema exibe as duas imagens lado a lado, com legendas como "Antes" e "Depois".

### Referências
- **RF:** PIMA-002

---

## [US-PIMA-002] Salvar colagem no histórico do paciente

**Como** um Profissional de Saúde,
**Eu quero** salvar a colagem gerada na galeria de imagens do paciente,
**Para que** ela fique registrada no histórico e possa ser facilmente consultada no futuro.

### Critérios de Aceitação
1.  **Dado que** criei uma colagem,
    **Quando** eu clico em "Salvar",
    **Então** a imagem da colagem é salva como um novo item na galeria do paciente, com uma identificação de que é uma colagem.

### Referências
- **RF:** PIMA-003
