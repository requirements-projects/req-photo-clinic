# Módulo de Gestão de Tratamentos
- **Sigla:** GT
- **Status:**
  -

- **Implementação:**
  - ✅ Backend
  - ⬜ Frontend
  - ⬜ Mobile
  - ⬜ Backoffice

> **Legenda:** ⬜ Pendente | ✅ Realizado | ⚠️ Ponto de atenção | ❌ Não se aplica

## Descrição
O módulo de Gestão de Tratamentos é responsável por organizar e documentar todos os procedimentos e etapas realizados em cada paciente, possibilitando o acompanhamento detalhado da evolução clínica, o registro dos produtos utilizados e o planejamento das sessões futuras conforme protocolos estabelecidos.

## Escopo Inicial
- Registro e associação de imagens e informações em cada etapa do tratamento.
- Cadastro e controle dos produtos aplicados em cada fase.
- Organização e agendamento das sessões conforme protocolos definidos.
- Registro da evolução clínica com base em fotos, observações e colagens.

## Funcionalidades
- Registro das etapas do tratamento com vinculação de imagens.
- Controle de produtos utilizados em cada etapa.
- Planejamento e organização das sessões futuras.
- Registro da evolução clínica visual e descritiva.

## Requisitos Funcionais

- **RF-GT-001:** Registro de etapas do tratamento
  - **Descrição:** O sistema deve permitir registrar e associar imagens e informações específicas a cada fase do tratamento realizado no paciente.
  - **Critério de aceitação:** Cada etapa deve estar vinculada ao paciente e ao tratamento correspondente, com imagens acessíveis.
  - **Prioridade:** Alta

- **RF-GT-002:** Controle de produtos utilizados
  - **Descrição:** O sistema deve registrar os produtos aplicados em cada etapa do tratamento, incluindo quantidade, lote e validade.
  - **Critério de aceitação:** Produtos registrados devem estar acessíveis para consulta e relatórios.
  - **Prioridade:** Média

- **RF-GT-003:** Agendamento das sessões de tratamento
  - **Descrição:** O sistema deve permitir organizar e planejar as sessões futuras baseadas nos protocolos definidos para cada tipo de tratamento.
  - **Critério de aceitação:** Sessões devem ser visualizadas em agenda e vinculadas ao paciente.
  - **Prioridade:** Média

- **RF-GT-004:** Registro da evolução clínica
  - **Descrição:** O sistema deve permitir registrar a evolução clínica do paciente com base em fotos, colagens e observações clínicas detalhadas.
  - **Critério de aceitação:** A evolução deve ser acessível em formato cronológico e visual.
  - **Prioridade:** Alta

## Requisitos Não Funcionais

- **RNF-GT-001:** Desempenho na consulta e registro
  - **Descrição:** O sistema deve garantir tempo de resposta inferior a 3 segundos para consultas e registros de tratamento, mesmo com grande volume de dados.
  - **Critério de aceitação:** Tempo de resposta consistente em cenários de uso padrão.
  - **Prioridade:** Alta

- **RNF-GT-002:** Segurança dos dados clínicos
  - **Descrição:** Dados de tratamento devem ser armazenados com criptografia e acessíveis apenas a usuários autorizados.
  - **Critério de aceitação:** Conformidade com LGPD e controle de acesso ativo.
  - **Prioridade:** Alta

## Regras de Negócio

- **RN-GT-001:** Cada etapa do tratamento deve ser vinculada obrigatoriamente a um paciente e a um protocolo aprovado.
  - **Descrição:** Garante rastreabilidade e padronização nos registros clínicos.
  - **Prioridade:** Alta

- **RN-GT-002:** Produtos utilizados devem estar registrados no estoque antes de serem aplicados no tratamento.
  - **Descrição:** Evita uso de produtos não autorizados ou não cadastrados.
  - **Prioridade:** Média

- **RN-GT-003:** Evolução clínica deve ser registrada obrigatoriamente após cada sessão.
  - **Descrição:** Permite acompanhamento detalhado e histórico completo do tratamento.
  - **Prioridade:** Alta

## Critérios de Aceitação

- Registro de etapas e produtos vinculado corretamente ao paciente.
- Sessões agendadas visíveis e modificáveis na agenda.
- Evolução clínica acessível em formato visual e textual.
- Segurança e performance conforme requisitos.

## Dependências

- Módulo de Cadastro e Gestão de Pacientes (para vinculação dos tratamentos).
- Módulo de Registro Fotográfico (para imagens associadas).
- Módulo de Estoque (para controle de produtos).

## Integrações

- Integração com agenda do sistema para gerenciamento de sessões.
- Integração com módulo de estoque para controle de produtos usados.
- Integração com módulos de relatórios para geração de históricos.

## Riscos Relacionados a Requisitos

- Risco de dados incompletos se o registro das etapas ou produtos não for obrigatório.
- Risco de inconsistência se produtos não forem validados no estoque.

## Ações Críticas do Sistema

- Alteração e exclusão de registros de tratamento.
- Controle rigoroso do uso e descarte de produtos.

## Indicadores Possíveis

- Número de tratamentos realizados por período.
- Evolução média dos pacientes por tipo de tratamento.
- Consumo de produtos por tratamento.

## Oportunidades de Escopos Futuros

- Alertas automáticos para próximas sessões ou reavaliações.
- Análise preditiva da evolução clínica com base em dados históricos.
- Integração com dispositivos médicos para coleta automática de dados.
