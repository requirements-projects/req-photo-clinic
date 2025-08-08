# Módulo de Cadastro de Paciente
- **Sigla:** CGP
- **Status:**
  -

- **Implementação:**
  - ✅ Backend
  - ⬜ Frontend
  - ⬜ Mobile
  - ⬜ Backoffice

> **Legenda:** ⬜ Pendente | ✅ Realizado | ⚠️ Ponto de atenção | ❌ Não se aplica

## Descrição
O módulo Cadastro e Gestão de Pacientes é responsável por gerenciar todas as informações cadastrais e administrativas dos pacientes, garantindo a integridade, segurança e disponibilidade dos dados para utilização em outros módulos do sistema. Envolve o registro inicial, atualização, consulta e inativação de pacientes, assegurando a conformidade com normas de proteção de dados e regulamentações do setor de saúde.


## Escopo Inicial


## Funcionalidades
- **Cadastro de Paciente:** Inclusão manual com dados básicos e complementares;       
- **Gestão de Dados Cadastrais:** Edição, atualização e exclusão de registros;
- **Histórico do Paciente:** Registro de interações, atendimentos e modificações;
- **Armazenamento de Documentos:** Upload e gestão de arquivos vinculados ao paciente;
- **Assinatura de Termos:** Assinatura digital de consentimento, autorização e responsabilidade;
- **Consulta Rápida:** Pesquisa por nome, documento ou outros identificadores.



## Requisitos Funcionais


- **RF-CGP-001:** Cadastro de pacientes com campos obrigatórios
  - **Descrição:** O sistema deve permitir o cadastro de pacientes com campos obrigatórios: Nome completo, CPF, Data de nascimento, Sexo, Telefone e E-mail.
  - **Critério de aceitação:** Cadastro deve ser salvo apenas se todos os campos obrigatórios estiverem preenchidos e o CPF for válido.
  - **Prioridade:** Alta


- **RF-CGP-002:** Edição de informações cadastrais
  - **Descrição:** O sistema deve permitir a edição das informações cadastrais do paciente, registrando histórico de alterações.
  - **Critério de aceitação:** Alterações devem ser salvas e associadas ao usuário que realizou a modificação.
  - **Prioridade:** Alta


- **RF-CGP-003:** Busca de pacientes por múltiplos filtros
  - **Descrição:** O sistema deve permitir a busca de pacientes por múltiplos filtros (nome, CPF, telefone, e-mail).
  - **Critério de aceitação:** Pesquisa deve retornar resultados correspondentes aos filtros aplicados.
  - **Prioridade:** Alta


- **RF-CGP-004:** Inativação de pacientes
  - **Descrição:** O sistema deve permitir a inativação de pacientes, impedindo novos registros ou edições.
  - **Critério de aceitação:** Pacientes inativados devem ser exibidos em consultas, mas não podem ser vinculados a novos atendimentos.
- **Prioridade:** Média


- **RF-CGP-005:** Reativação de pacientes
  - **Descrição:** O sistema deve permitir a reativação de pacientes inativados.    
    - **Critério de aceitação:** Após a reativação, paciente volta a ser elegível para novos atendimentos.
    - **Prioridade:** Média


- **RF-CGP-006:** Upload e gestão de arquivos vinculados ao paciente
    - **Descrição:** O sistema deve permitir o upload e gestão de arquivos vinculados ao paciente.
    - **Critério de aceitação:** Arquivos devem ser associados ao paciente e exibidos em consultas.
    - **Prioridade:** Média


- **RF-CGP-007:** Assinatura digital de documentos
  - **Descrição:** O sistema deve permitir a assinatura digital de consentimento, autorização e responsabilidade.
  - **Critério de aceitação:** Assinaturas devem ser registradas e associadas ao paciente.
  - **Prioridade:** Média


- **RF-CGP-008:** Exportação de dados de pacientes
  - **Descrição:** O sistema deve permitir a exportação de dados de pacientes em formatos padrão (CSV, PDF, JSON).
  - **Critério de aceitação:** Exportação deve ser realizada em formatos padrão e segmentados por múltiplos critérios.
  - **Prioridade:** Média


- **RF-CGP-009:** Relatórios customizáveis
  - **Descrição:** O sistema deve permitir a geração de relatórios customizáveis com base nos dados de pacientes, com opções de agendamento e distribuição automática.
  - **Critério de aceitação:** Relatórios podem ser exportados em formatos padrão (CSV, PDF, JSON), segmentados por múltiplos critérios, e distribuídos automaticamente por e-mail ou integração com sistemas externos.
  - **Prioridade:** Média
 



## Requisitos Não Funcionais

**RNF-CGP-001:** Tempo de Resposta para Cadastro e Consulta de Pacientes
- **Descrição:** O tempo de resposta para cadastro e consulta de pacientes deve ser inferior a 2 segundos em condições normais de operação.
- **Critério de aceitação:** Resposta inferior a 2 segundos para consultas padrão com até 1 milhão de registros; indexação avançada para pesquisas complexas com suporte a partição de dados por período.
- **Prioridade:** Alta

**RNF-CGP-002:**  Conformidade com a LGPDO sistema deve estar em conformidade com a LGPD.
- **Descrição:** O sistema deve estar em conformidade com a LGPD.
- **Critério de aceitação:**Implementação de controles para consentimento de uso de dados, anonimização quando aplicável e registro de logs de acesso a dados pessoais.
- **Prioridade:** Alta 



## Regras de Negócio

- **RN-CGP-001:** Não é permitido cadastrar dois pacientes com o mesmo CPF.
  - **Descrição:** Antes de inserir um novo paciente, o sistema deve verificar duplicidade no banco de dados considerando o CPF. Caso encontrado, retornar mensagem de erro.     
  - **Prioridade:** Alta

- **RN-CGP-002:** Pacientes inativados não podem ter informações alteradas, exceto para fins legais.
  - **Descrição:** Antes de alterar um paciente inativado, o sistema deve verificar se o registro é válido. Caso encontrado, retornar mensagem de erro.  
  - **Prioridade:** Média

- **RN-CGP-003:** Todos os registros devem ser auditáveis, contendo data, hora e usuário responsável por cada alteração.
  - **Descrição:**      
  - **Prioridade:** Média


## Critérios de Aceitação

- O cadastro só será salvo se todos os campos obrigatórios forem preenchidos e validados.
- Alterações devem manter histórico completo e não podem ser apagadas.
- Filtros de busca devem retornar resultados consistentes e rápidos.
- Inativação impede qualquer ação que envolva novos registros para o paciente.
- Todas as ações relevantes de usuários são registradas com detalhes mínimos (quem, quando, o quê, onde, como).


## Dependências

- Módulo de Segurança (para controle de acesso e permissões)
- Módulo de Auditoria de Dados (para registro de alterações)
- Módulo de Notificações (para envio de alertas)
- Banco de dados de pacientes.
- Serviço de autenticação e controle de acesso.


## Integrações

- Integração com módulo de autenticação (para registro de usuário responsável pelas alterações).
- Integração com módulo de auditoria (para rastreio de alterações).

## Riscos Relacionados a Requisitos

- Risco de inconsistência de dados caso não haja validação de CPF.
- Risco de violação de dados caso criptografia não seja aplicada corretamente.  


## Ações Críticas do Sistema

- Exclusão lógica de pacientes (inativação).
- Edição de dados sensíveis (CPF, data de nascimento).

## Indicadores Possíveis


## Oportunidades de Escopos Futuros
