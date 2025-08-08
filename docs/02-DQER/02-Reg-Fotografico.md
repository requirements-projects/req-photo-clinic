# Módulo de Registro Fotográfico
- **Sigla:** RF
- **Status:**
  -

- **Implementação:**
  - ✅ Backend
  - ⬜ Frontend
  - ⬜ Mobile
  - ⬜ Backoffice

> **Legenda:** ⬜ Pendente | ✅ Realizado | ⚠️ Ponto de atenção | ❌ Não se aplica

## Descrição
O módulo de Registro Fotográfico é responsável pela captura, edição, organização e armazenamento das imagens clínicas dos pacientes, garantindo padronização na qualidade, alinhamento e documentação visual dos tratamentos estéticos realizados.

## Escopo Inicial
- Captura de fotos com molduras padronizadas.
- Sobreposição de imagem anterior (modo fantasma) para alinhamento.
- Edição básica de imagens (corte, brilho, contraste, anotações).
- Organização e categorização das imagens.
- Criação de colagens para comparação visual.

## Funcionalidades
- Captura de imagens com molduras padronizadas e feedback de enquadramento.
- Sobreposição de imagens anteriores para alinhamento visual (modo fantasma).
- Ferramentas básicas de edição de imagens (corte, brilho, contraste, anotações).
- Organização das imagens por paciente, data e procedimento estético.
- Criação e exportação de colagens comparativas.
- Compartilhamento das imagens e colagens via formatos padrão e canais autorizados.

## Requisitos Funcionais

**RF-RF-001:** Captura de imagens com moldura padronizada
- **Descrição:** O sistema deve permitir capturar fotos aplicando molduras visuais para garantir padronização no enquadramento.
- **Critério de aceitação:** Moldura aplicada corretamente e visível na imagem capturada.
- **Prioridade:** Alta

**RF-RF-002:** Seleção de molduras pré-definidas por área anatômica
- **Descrição:** Molduras devem estar categorizadas por região anatômica, com fácil seleção antes da captura.
- **Critério de aceitação:** O usuário consegue alterar a moldura rapidamente e a captura respeita o padrão selecionado.
- **Prioridade:** Alta

**RF-RF-003:**  Feedback em tempo real sobre enquadramento
- **Descrição:** O sistema avalia posicionamento com base em alinhamento, distância e escala para garantir enquadramento correto.
- **Critério de aceitação:** O feedback visual deve ser instantâneo e claro, permitindo correção antes da captura.
- **Prioridade:** Alta

**RF-RF-004:** Ajuste manual da moldura na tela
- **Descrição:** Usuário pode mover e redimensionar a moldura para se adequar à necessidade do atendimento.
- **Critério de aceitação:** Ajustes manuais são salvos para aquela sessão e refletem na captura final.
- **Prioridade:** Média

**RF-RF-005:** Registro de metadados da captura
- **Descrição:** Sistema deve registrar tipo de moldura, posição da câmera, zoom, data e hora da foto.
- **Critério de aceitação:** Metadados estão disponíveis para consulta e relatório.
- **Prioridade:** Média

**RF-RF-006:** Sobreposição em modo fantasma para alinhamento
- **Descrição:** O sistema deve permitir sobrepor a última imagem capturada para facilitar o alinhamento exato da nova foto.
- **Critério de aceitação:** A sobreposição deve ser ajustável e permitir transparência para facilitar o alinhamento.
- **Prioridade:** Alta

**RF-RF-007:** Ferramentas básicas de edição
- **Descrição:** O sistema deve disponibilizar ferramentas para cortar, ajustar brilho, contraste e incluir anotações visuais (setas, texto, círculos).
- **Critério de aceitação:** Alterações devem ser aplicadas e salvas corretamente, mantendo a imagem original preservada.
- **Prioridade:** Média

**RF-RF-008:** Organização das imagens
- **Descrição:** O sistema deve organizar as fotos por paciente, data e tipo de procedimento.
- **Critério de aceitação:** Fotos devem ser facilmente pesquisáveis e filtradas conforme esses critérios.
- **Prioridade:** Alta

**RF-RF-009:** Criação de colagens comparativas
- **Descrição:** O sistema deve permitir criar colagens com múltiplas fotos para comparação visual lado a lado, sobreposição ou sequência.
- **Critério de aceitação:** Colagens geradas corretamente e exportáveis em formatos padrão.
- **Prioridade:** Média

**RF-RF-010:** Exportação e compartilhamento
- **Descrição:** O sistema deve permitir exportar imagens e colagens em PDF, JPEG e outros formatos, e compartilhá-las via e-mail, WhatsApp, etc.
- **Critério de aceitação:** Arquivos exportados devem manter qualidade adequada e serem compatíveis com os meios de compartilhamento.
- **Prioridade:** Média



## Requisitos Não Funcionais

**RNF-RF-001:** Tempo de resposta para edição e visualização
- **Descrição:** O sistema deve responder às operações de edição e visualização em até 3 segundos para imagens padrão.
- **Critério de aceitação:** A edição e visualização de imagens devem ocorrer dentro do tempo limite mesmo com banco de dados de até 500 mil fotos.
- **Prioridade:** Alta

**RNF-RF-002:** Armazenamento seguro das imagens
- **Descrição:** Todas as imagens devem ser armazenadas criptografadas em repouso e protegidas em trânsito.
- **Critério de aceitação:** As imagens armazenadas e transferidas devem usar criptografia conforme padrões de segurança vigentes.
- **Prioridade:** Alta

**RNF-RF-003:** Compatibilidade com dispositivos móveis
- **Descrição:** O módulo deve funcionar corretamente em dispositivos móveis com diferentes resoluções de tela.
- **Critério de aceitação:** As funcionalidades devem estar disponíveis e operantes em dispositivos iOS e Android.
- **Prioridade:** Média



## Regras de Negócio

- **RN-RF-001:** Todas as imagens devem ser vinculadas ao paciente correspondente.
    - **Descrição:** Nenhuma imagem pode ser salva sem associação clara ao paciente para garantir rastreabilidade.
    - **Prioridade:** Alta

- **RN-RF-002:** Imagens originais não podem ser apagadas ou alteradas diretamente.
    - **Descrição:** Alterações devem ser feitas em cópias para preservar histórico visual.
    - **Prioridade:** Alta

- **RN-RF-003:** Colagens só podem ser criadas a partir de imagens aprovadas pelo profissional responsável.
    - **Descrição:** Garantir que somente fotos validadas possam ser usadas para documentação oficial.
    - **Prioridade:** Média

- **RN-RF-001:** A moldura deve corresponder ao padrão definido para cada região anatômica e não pode ser removida durante a captura, salvo ajuste manual autorizado.
    - **Descrição:** Isso garante padronização e comparabilidade entre sessões.
    - **Prioridade:** Alta

- **RN-RF-002:** O sistema deve validar o enquadramento com base na moldura antes de permitir a captura da imagem.
    - **Descrição:** Se o paciente não estiver corretamente enquadrado, o sistema deve impedir a captura e exibir mensagem orientativa.
    - **Prioridade:** Alta

- **RN-RF-003:** Em casos de ajuste manual da moldura, a nova configuração deve ser registrada e vinculada à sessão fotográfica.
    - **Descrição:** Para rastreabilidade e possíveis auditorias clínicas.
    - **Prioridade:** Média

- **RN-RF-004:** O feedback visual de enquadramento correto deve ser exibido apenas quando todos os critérios mínimos de alinhamento e escala forem atendidos.
    - **Descrição:** Minimiza erros e fotos com baixa qualidade para acompanhamento clínico.
    - **Prioridade:** Alta


## Critérios de Aceitação

- Captura de imagem com moldura aplicada e visível.
- Sobreposição em modo fantasma funcionando com ajuste de transparência.
- Ferramentas de edição aplicam alterações sem perder a imagem original.
- Organização das fotos permite pesquisa rápida por paciente, data e procedimento.
- Colagens são geradas e exportadas corretamente em múltiplos formatos.
- Compartilhamento é funcional via e-mail e apps de mensagens.


## Dependências

- Módulo de Cadastro e Gestão de Pacientes (para vinculação das fotos).
- Módulo de Relatórios (para exportação e geração de históricos).



## Integrações

- Integração com biblioteca de edição de imagens (externa ou interna).
- Integração com serviços de armazenamento seguro em nuvem.

## Riscos Relacionados a Requisitos

- Risco de perda de qualidade da imagem durante exportação ou edição.
- Risco de desorganização das imagens se não houver controle rigoroso de vinculação.


## Ações Críticas do Sistema

- Remoção ou alteração de imagens vinculadas a pacientes.
- Exportação e compartilhamento de dados sensíveis.


## Indicadores Possíveis


## Oportunidades de Escopos Futuros
- Integração com IA para reconhecimento automático de área tratada.
- Ferramentas avançadas de edição, como remoção de imperfeições.