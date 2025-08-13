# Módulo: Armazenamento (STOR)

## Histórias de Usuário

- [[US-STOR-001] Garantir armazenamento seguro de dados](#us-stor-001-garantir-armazenamento-seguro-de-dados)
- [[US-STOR-002] Acessar dados de qualquer dispositivo autorizado](#us-stor-002-acessar-dados-de-qualquer-dispositivo-autorizado)
- [[US-STOR-003] Manter fotos do paciente privadas](#us-stor-003-manter-fotos-do-paciente-privadas)

---

## [US-STOR-001] Garantir armazenamento seguro de dados

**Como** um Administrador do Sistema,
**Eu quero** que todos os dados de pacientes, especialmente as fotos, sejam armazenados com criptografia tanto no dispositivo quanto no servidor em nuvem,
**Para que** os dados sensíveis dos pacientes estejam protegidos contra acessos não autorizados.

### Critérios de Aceitação
1.  **Dado que** uma nova foto é capturada,
    **Quando** ela é salva,
    **Então** o arquivo da foto é criptografado antes de ser gravado no disco local ou enviado para a nuvem.

### Referências
- **RF:** STOR-002

---

## [US-STOR-002] Acessar dados de qualquer dispositivo autorizado

**Como** um Profissional de Saúde,
**Eu quero** poder acessar os prontuários e fotos dos meus pacientes a partir de qualquer dispositivo da clínica (tablet, computador de mesa) onde eu esteja logado,
**Para que** eu tenha flexibilidade para trabalhar em diferentes salas de atendimento.

### Critérios de Aceitação
1.  **Dado que** eu estou logado no sistema em um novo dispositivo autorizado,
    **Quando** eu pesquiso por um paciente,
    **Então** o sistema busca e exibe os dados mais recentes do paciente, sincronizados a partir do servidor central.

### Referências
- **RF:** STOR-003

---

## [US-STOR-003] Manter fotos do paciente privadas

**Como** um Profissional de Saúde,
**Eu quero** que as fotos tiradas com o aplicativo não apareçam na galeria de fotos pessoal do meu celular,
**Para que** a privacidade do paciente seja mantida e para evitar misturar fotos pessoais com as de trabalho.

### Critérios de Aceitação
1.  **Dado que** eu tirei uma foto usando o aplicativo FotoClinic,
    **Quando** eu abro a galeria de fotos padrão do meu celular (ex: Google Fotos, Rolo da Câmera),
    **Então** a foto do paciente não deve estar visível lá.

### Referências
- **RF:** STOR-001
