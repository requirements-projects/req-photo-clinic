# Módulo: Captura de Imagens (CIM)

## Histórias de Usuário

- [[US-CIM-001] Capturar foto com guia de alinhamento](#us-cim-001-capturar-foto-com-guia-de-alinhamento)
- [[US-CIM-002] Capturar foto usando modo fantasma](#us-cim-002-capturar-foto-usando-modo-fantasma)
- [[US-CIM-003] Salvar foto segura no prontuário](#us-cim-003-salvar-foto-segura-no-prontuário)

---

## [US-CIM-001] Capturar foto com guia de alinhamento

**Como** um Profissional de Saúde,
**Eu quero** usar molduras (guias) sobre a câmera para padronizar o ângulo e a distância da foto,
**Para que** as imagens de antes e depois sejam consistentes e comparáveis.

### Critérios de Aceitação
1.  **Dado que** estou na tela da câmera,
    **Quando** eu seleciono uma moldura (ex: "Face Frontal"),
    **Então** a moldura aparece sobre a imagem da câmera para me guiar.

### Referências
- **RF:** CIM-002

---

## [US-CIM-002] Capturar foto usando modo fantasma

**Como** um Profissional de Saúde,
**Eu quero** sobrepor uma foto anterior (modo fantasma) na tela da câmera ao tirar uma nova foto,
**Para que** eu possa replicar exatamente o mesmo enquadramento da foto de referência.

### Critérios de Aceitação
1.  **Dado que** selecionei uma foto de referência na galeria,
    **Quando** ativo o modo fantasma na câmera,
    **Então** a foto de referência é exibida com transparência sobre a imagem ao vivo da câmera.

### Referências
- **RF:** CIM-003

---

## [US-CIM-003] Salvar foto segura no prontuário

**Como** um Profissional de Saúde,
**Eu quero** que a foto capturada seja salva automaticamente e de forma segura no prontuário do paciente selecionado,
**Para que** eu tenha a garantia de que a imagem está corretamente associada e protegida.

### Critérios de Aceitação
1.  **Dado que** capturei uma foto para um paciente,
    **Quando** a foto é salva,
    **Então** ela aparece imediatamente na galeria daquele paciente e não é salva na galeria pública do dispositivo.

### Referências
- **RF:** CIM-004
