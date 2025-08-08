# Módulo de Segurança e Acesso
- **Sigla:** SA
- **Status:**
  -

- **Implementação:**
  - ✅ Backend
  - ⬜ Frontend
  - ⬜ Mobile
  - ⬜ Backoffice

> **Legenda:** ⬜ Pendente | ✅ Realizado | ⚠️ Ponto de atenção | ❌ Não se aplica

## Descrição
O módulo de Segurança e Acesso é responsável por garantir a proteção dos dados sensíveis, controlar o acesso dos usuários conforme seus perfis e implementar mecanismos robustos de autenticação, autorização e criptografia, assegurando a conformidade com legislações como a LGPD.

## Escopo Inicial
- Autenticação segura com múltiplos métodos (biometria facial, digital, PIN).
- Controle de permissões por perfil e função.
- Criptografia de dados em trânsito e em repouso.
- Registro e auditoria das tentativas de acesso.
- Gestão de sessões e bloqueio automático por tentativas inválidas.

## Funcionalidades
- Autenticação multifator.
- Controle granular de acesso por perfil.
- Criptografia ponta a ponta dos dados.
- Auditoria detalhada dos acessos e ações críticas.
- Bloqueio automático após tentativas falhas.

## Requisitos Funcionais

- **RF-SA-001:** Implementar autenticação segura com suporte a biometria facial, digital e PIN.
  - **Descrição:** O sistema deve permitir o login do usuário utilizando métodos biométricos e/ou PIN para garantir segurança.
  - **Critério de aceitação:** O usuário consegue autenticar com sucesso usando qualquer método disponível; falhas são registradas.
  - **Prioridade:** Alta

- **RF-SA-002:** Controlar o acesso dos usuários baseado em perfis pré-definidos.
  - **Descrição:** O sistema deve restringir o acesso às funcionalidades conforme o perfil do usuário (ex: administrador, esteticista, auditor).
  - **Critério de aceitação:** Usuários só visualizam e operam recursos autorizados ao seu perfil.
  - **Prioridade:** Alta

- **RF-SA-003:** Criptografar todos os dados sensíveis armazenados e transmitidos.
  - **Descrição:** Os dados armazenados localmente e na nuvem devem ser protegidos por criptografia conforme padrões vigentes.
  - **Critério de aceitação:** Testes comprovam que dados são indecifráveis sem chave adequada.
  - **Prioridade:** Alta

- **RF-SA-004:** Registrar todas as tentativas de acesso, bem-sucedidas ou não.
  - **Descrição:** O sistema deve manter logs detalhados das tentativas de login, incluindo falhas e bloqueios.
  - **Critério de aceitação:** Logs acessíveis para auditoria e análise de segurança.
  - **Prioridade:** Alta

- **RF-SA-005:** Implementar bloqueio automático de usuário após tentativas consecutivas de login inválidas.
  - **Descrição:** Após número configurável de tentativas falhas, o sistema deve bloquear o acesso temporariamente.
  - **Critério de aceitação:** Bloqueio ativo e notificações enviadas ao administrador.
  - **Prioridade:** Alta

## Requisitos Não Funcionais

- **RNF-SA-001:** Tempo de resposta para autenticação deve ser inferior a 2 segundos.
  - **Descrição:** A experiência do usuário não deve ser comprometida pela segurança.
  - **Critério de aceitação:** Autenticações devem ocorrer em até 2 segundos na maioria dos casos.
  - **Prioridade:** Alta

- **RNF-SA-002:** O sistema deve estar em conformidade com a LGPD para proteção dos dados pessoais.
  - **Descrição:** Toda coleta, armazenamento e tratamento de dados devem respeitar a legislação.
  - **Critério de aceitação:** Auditorias confirmam conformidade LGPD.
  - **Prioridade:** Alta

## Regras de Negócio

- **RN-SA-001:** Usuários bloqueados por tentativas inválidas devem ser desbloqueados apenas por administradores.
  - **Descrição:** Bloqueios automáticos só podem ser revertidos manualmente para evitar acessos indevidos.
  - **Prioridade:** Alta

- **RN-SA-002:** Perfis de usuário devem ser revistos e atualizados periodicamente.
  - **Descrição:** As permissões devem ser auditadas para evitar acúmulo indevido de privilégios.
  - **Prioridade:** Média

- **RN-SA-003:** Todas as alterações em perfis e permissões devem ser registradas em log.
  - **Descrição:** Para garantir rastreabilidade e auditoria de mudanças de acesso.
  - **Prioridade:** Alta

## Critérios de Aceitação

- Login seguro com múltiplos métodos biométricos e PIN.
- Controle de acesso rigoroso conforme perfil do usuário.
- Criptografia aplicada em todas as camadas de dados.
- Logs completos das tentativas e alterações de acesso.
- Bloqueio automático funcionando conforme parâmetros configurados.

## Dependências

- Módulo de Cadastro de Usuários para informações e perfis.
- Serviços de criptografia.
- Infraestrutura de auditoria e monitoramento.

## Integrações

- Integração com serviços biométricos nativos dos dispositivos.
- Integração com sistemas de monitoramento e alerta de segurança.

## Riscos Relacionados a Requisitos

- Risco de falhas na autenticação por problemas de hardware (sensor biométrico).
- Risco de vazamento de dados se a criptografia não for corretamente implementada.
- Risco de bloqueios indevidos por ataques de força bruta.

## Ações Críticas do Sistema

- Bloqueio e desbloqueio de usuários.
- Alteração de perfis e permissões.
- Registro e manutenção dos logs de acesso.

## Indicadores Possíveis

- Número de tentativas de login malsucedidas.
- Tempo médio de autenticação.
- Número de usuários bloqueados e desbloqueados.

## Oportunidades de Escopos Futuros

- Implementação de autenticação por tokens externos (OAuth, SAML).
- Integração com sistemas de gerenciamento de identidade corporativa.
- Análise comportamental para detecção de acessos suspeitos.
