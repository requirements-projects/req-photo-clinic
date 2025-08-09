# Documento de Especificação de Histórias de Usuário (DUS) - Domínio de Registro Fotográfico

Este documento detalha as histórias de usuário para o **Domínio de Registro Fotográfico** do sistema **PhotoClinic**. Ele traduz requisitos funcionais (referenciados no RQSD) em narrativas centradas no usuário para orientar a equipe de desenvolvimento.

---

## [US-RF-001] Capturar Foto de Paciente

**Como** Profissional de Clínica Estética,  
**Quero** capturar uma foto do paciente diretamente no aplicativo,  
**Para** documentar visualmente a situação atual antes ou após um procedimento.

### Detalhes
- Deve permitir captura com a câmera do dispositivo.
- Disponibilizar molduras padronizadas conforme o procedimento.
- Salvar automaticamente a foto no registro do paciente.
- Exibir pré-visualização para confirmação antes de salvar.

### Critérios de Aceitação
**Dado** que estou na tela de captura,  
**Quando** tiro a foto e confirmo,  
**Então** a imagem é salva no registro do paciente com data, hora e profissional responsável.

### Referências
- RF: RF001, RF002  
- RN: RN001

### Problema(s) Resolvido(s)
- Padroniza e organiza registros fotográficos.
- Evita perda de informações visuais importantes.

---

## [US-RF-002] Aplicar Modo Fantasma na Captura

**Como** Profissional de Clínica Estética,  
**Quero** aplicar o modo fantasma durante a captura da foto,  
**Para** alinhar imagens antes e depois de procedimentos de forma precisa.

### Detalhes
- Sobrepor a imagem anterior do paciente como camada semi-transparente.
- Permitir ajuste de opacidade da sobreposição.
- Garantir alinhamento entre capturas.

### Critérios de Aceitação
**Dado** que selecionei o modo fantasma,  
**Quando** posiciono o paciente e ajusto a câmera,  
**Então** vejo a sobreposição da foto anterior e posso capturar a nova com o mesmo enquadramento.

### Referências
- RF: RF003

### Problema(s) Resolvido(s)
- Facilita comparação visual de resultados.
- Aumenta precisão na documentação fotográfica.

---

## [US-RF-003] Criar Colagem de Fotos

**Como** Profissional de Clínica Estética,  
**Quero** criar colagens com fotos do paciente,  
**Para** apresentar comparativos antes e depois de procedimentos.

### Detalhes
- Selecionar múltiplas fotos do paciente.
- Disponibilizar modelos prontos de colagem (2, 3 ou 4 imagens).
- Exportar colagem em formato padrão (JPEG/PNG) para impressão ou envio.

### Critérios de Aceitação
**Dado** que selecionei as fotos e o modelo,  
**Quando** confirmo a criação da colagem,  
**Então** o sistema gera a imagem final e salva no registro do paciente.

### Referências
- RF: RF004

### Problema(s) Resolvido(s)
- Facilita apresentação visual de resultados.
- Padroniza materiais de acompanhamento e marketing.

---

## [US-RF-004] Sincronizar Fotos entre Dispositivos

**Como** Profissional de Clínica Estética,  
**Quero** sincronizar fotos e registros entre diferentes dispositivos,  
**Para** acessar as imagens em qualquer aparelho autorizado.

### Detalhes
- Sincronização segura via nuvem.
- Respeitar regras de privacidade e consentimento do paciente.
- Permitir uso offline, com envio automático quando a conexão estiver disponível.

### Critérios de Aceitação
**Dado** que capturei fotos em um dispositivo,  
**Quando** a conexão for restabelecida,  
**Então** as imagens são enviadas para a nuvem e ficam disponíveis nos demais dispositivos autorizados.

### Referências
- RF: RF005  
- RN: RN002

### Problema(s) Solucionado(s)
- Garante disponibilidade das fotos para todos os profissionais da clínica.
- Evita perda de registros por falha no dispositivo.
