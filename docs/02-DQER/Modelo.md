# Módulo 
- **Sigla:** 
- **Status:**
  -

- **Implementação:**
  - ✅ Backend
  - ⬜ Frontend
  - ⬜ Mobile
  - ⬜ Backoffice

> **Legenda:** ⬜ Pendente | ✅ Realizado | ⚠️ Ponto de atenção | ❌ Não se aplica

## Descrição


## Escopo Inicial
- Registro automático de todas as ações relevantes dos usuários

## Funcionalidades
- **descreva a funcionalidade:** 


## Requisitos Funcionais


- **RF-CGP-001:** Cadastro de pacientes com campos obrigatórios
  - **Descrição:** O sistema deve permitir o cadastro de pacientes com campos obrigatórios: Nome completo, CPF, Data de nascimento, Sexo, Telefone e E-mail.
  - **Critério de aceitação:** Cadastro deve ser salvo apenas se todos os campos obrigatórios estiverem preenchidos e o CPF for válido.
  - **Prioridade:** Alta




## Requisitos Não Funcionais

**RNF-CGP-001:** Tempo de Resposta para Cadastro e Consulta de Pacientes
- **Descrição:** O tempo de resposta para cadastro e consulta de pacientes deve ser inferior a 2 segundos em condições normais de operação.
- **Critério de aceitação:** Resposta inferior a 2 segundos para consultas padrão com até 1 milhão de registros; indexação avançada para pesquisas complexas com suporte a partição de dados por período.
- **Prioridade:** Alta




## Regras de Negócio

- **RN-CGP-001:** Não é permitido cadastrar dois pacientes com o mesmo CPF.
  - **Descrição:** Antes de inserir um novo paciente, o sistema deve verificar duplicidade no banco de dados considerando o CPF. Caso encontrado, retornar mensagem de erro.     
  - **Prioridade:** Alta




## Critérios de Aceitação

- O cadastro só será salvo se todos os campos obrigatórios forem preenchidos e validados.


## Dependências

- Módulo de Segurança (para controle de acesso e permissões)



## Integrações

- Integração com módulo de autenticação (para registro de usuário responsável pelas alterações).
- Integração com módulo de auditoria (para rastreio de alterações).

## Riscos Relacionados a Requisitos

- Risco de inconsistência de dados caso não haja validação de CPF.
-


## Ações Críticas do Sistema

- Exclusão lógica de pacientes (inativação).


## Indicadores Possíveis


## Oportunidades de Escopos Futuros
