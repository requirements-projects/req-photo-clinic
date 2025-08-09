# Documento de Histórias de Usuário (DUS)

## 1. Propósito
Este documento traduz os requisitos do sistema PhotoClinic, detalhados no DQER, em Histórias de Usuário (User Stories). Seu objetivo é fornecer uma visão clara e centrada no usuário sobre as funcionalidades a serem desenvolvidas, garantindo que a equipe de desenvolvimento compreenda o valor de cada entrega sob a ótica de quem utilizará o sistema.

## 2. Perfis de Usuário (Personas)
As histórias de usuário são contadas a partir da perspectiva de diferentes perfis que interagem com o sistema:

- **Recepcionista:** Responsável pelo primeiro contato com o paciente, agendamentos e gestão de dados cadastrais.
- **Profissional de Saúde:** O usuário principal do sistema (médico, esteticista, etc.), responsável por toda a jornada clínica, desde a captura de imagens e anotações em prontuário até a apresentação dos resultados.
- **Administrador do Sistema:** Perfil técnico com acesso a configurações avançadas, gestão de usuários e extração de dados para conformidade com a LGPD.

## 3. Estrutura da História de Usuário
Cada história de usuário seguirá o formato padrão abaixo para garantir consistência e clareza:

- **ID:** Um identificador único no formato `[US-SIGLA-NÚMERO]`.
- **Título:** Um resumo curto e direto da história.
- **Descrição:** No formato clássico: **Como** `[perfil de usuário]`, **Eu quero** `[realizar uma ação]`, **Para que** `[eu obtenha um benefício]`.
- **Critérios de Aceitação:** Condições específicas que a funcionalidade deve atender para ser considerada concluída.
- **Referências:** Vínculo com os Requisitos Funcionais (RFs) correspondentes no DQER.

## 4. Domínios e Módulos
As histórias estão agrupadas por módulos, refletindo a arquitetura definida no DQER.

### 4.1. Domínio de Gestão (DG)
| # | Módulo | Sigla | Detalhamento |
|---|---|---|---|
| 1.1 | Cadastro de Paciente | CPAC | [Histórias de Usuário](./01-US-CPAC.md) |
| 1.2 | Gestão de Prontuários | CPRO | [Histórias de Usuário](./02-US-CPRO.md) |

### 4.2. Domínio de Registro Fotográfico (DRF)
| # | Módulo | Sigla | Detalhamento |
|---|---|---|---|
| 2.1 | Histórico Clínico Fotográfico | HCF | [Histórias de Usuário](./03-US-HCF.md) |
| 2.2 | Captura de Imagens | CIM | [Histórias de Usuário](./04-US-CIM.md) |
| 2.3 | Processamento de Imagens | PIMA | [Histórias de Usuário](./05-US-PIMA.md) |

### 4.3. Domínio de Infraestrutura (DI)
| # | Módulo | Sigla | Detalhamento |
|---|---|---|---|
| 3.1 | Sincronização | SYNC | [Histórias de Usuário](./06-US-SYNC.md) |
| 3.2 | Armazenamento | STOR | [Histórias de Usuário](./07-US-STOR.md) |
| 3.3 | Backup e Recuperação | BACK | [Histórias de Usuário](./08-US-BACK.md) |

### 4.4. Domínio de Experiência do Usuário (DUX)
| # | Módulo | Sigla | Detalhamento |
|---|---|---|---|
| 4.1 | Interface de Fotografia | UIFOT | [Histórias de Usuário](./09-US-UIFOT.md) |
| 4.2 | Interface de Consulta | UICON | [Histórias de Usuário](./10-US-UICON.md) |

## 5. Observações Finais
- Cada história de usuário deve ser validada com os stakeholders antes do início do desenvolvimento.
- A priorização das histórias deve levar em conta o valor de negócio, as dependências técnicas e as necessidades dos usuários.
