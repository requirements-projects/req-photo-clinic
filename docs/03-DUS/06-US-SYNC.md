# Módulo: Sincronização (SYNC)

## Histórias de Usuário

- [[US-SYNC-001] Trabalhar offline sem interrupções](#us-sync-001-trabalhar-offline-sem-interrupções)
- [[US-SYNC-002] Sincronizar dados automaticamente](#us-sync-002-sincronizar-dados-automaticamente)
- [[US-SYNC-003] Receber dados de outros dispositivos](#us-sync-003-receber-dados-de-outros-dispositivos)

---

## [US-SYNC-001] Trabalhar offline sem interrupções

**Como** um Profissional de Saúde,
**Eu quero** continuar usando o aplicativo para tirar fotos e fazer anotações mesmo se a clínica estiver sem internet,
**Para que** a minha rotina de atendimento não seja interrompida por problemas de conectividade.

### Critérios de Aceitação
1.  **Dado que** o dispositivo está sem conexão com a internet,
    **Quando** eu capturo uma nova foto ou crio uma anotação no prontuário,
    **Então** os dados são salvos localmente no dispositivo de forma segura.

### Referências
- **RF:** SYNC-003

---

## [US-SYNC-002] Sincronizar dados automaticamente

**Como** um Profissional de Saúde,
**Eu quero** que o aplicativo sincronize automaticamente todos os dados que eu gerei offline assim que a conexão com a internet for restabelecida,
**Para que** eu não precise me preocupar em fazer isso manualmente e tenha a certeza de que os dados estão seguros no servidor central.

### Critérios de Aceitação
1.  **Dado que** existem dados salvos localmente e a internet se torna disponível,
    **Quando** o aplicativo detecta a conexão,
    **Então** ele inicia a sincronização em segundo plano e exibe um indicador visual do status do processo.

### Referências
- **RF:** SYNC-001

---

## [US-SYNC-003] Receber dados de outros dispositivos

**Como** um Profissional de Saúde,
**Eu quero** que meu dispositivo baixe automaticamente as informações mais recentes do servidor,
**Para que** eu possa ver em meu tablet as fotos que um colega tirou em outro dispositivo momentos antes.

### Critérios de Aceitação
1.  **Dado que** um novo dado foi sincronizado por outro dispositivo,
    **Quando** meu dispositivo realiza a sincronização,
    **Então** o novo dado (ex: nova foto) aparece na galeria do paciente no meu dispositivo.

### Referências
- **RF:** SYNC-002
