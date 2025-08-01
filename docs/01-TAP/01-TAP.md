# Termo de Abertura de Projeto (TAP) - PhotoClinic

## 1. Título do Projeto
PhotoClinic

## 2. Gerente do Projeto
Hugo Seabra (HSB Tech)

## 3. Patrocinadores do Projeto
*   Raquel Oliveira
*   Paulo

## 4. Propósito / Objetivos do Projeto
O objetivo principal do projeto é desenvolver uma aplicação móvel para clínicas de estética, substituindo o uso da galeria de fotos convencional do celular. A ferramenta visa organizar e padronizar o registro fotográfico de pacientes para acompanhamento de tratamentos.

A visão de uso da aplicação se divide em duas frentes principais:
*   **Operação de Fotografia:** Realizada por um profissional que irá registrar as imagens dos pacientes em conformidade com as molduras predefinidas ou com as fotos de sessões anteriores (através do "modo fantasma").
*   **Atendimento Médico:** Realizado no consultório, onde o médico utiliza a aplicação para demonstrar os resultados ao paciente, incluindo a comparação entre fotos de diferentes sessões a partir da segunda visita.

**Objetivos Específicos:**
*   Criar álbuns de fotos individuais para cada paciente.
*   Implementar "molduras" (templates) para guiar o enquadramento correto das fotos.
*   Desenvolver o "modo fantasma" para sobrepor fotos e facilitar a comparação precisa do "antes e depois".
*   Oferecer uma funcionalidade de criação de colagens para visualização comparativa.
*   Prover um ambiente seguro e dedicado para o armazenamento das fotos dos pacientes.

## 5. Justificativa / Caso de Negócio
Atualmente, profissionais de estética utilizam a galeria de fotos do celular, um método desorganizado, que consome armazenamento do dispositivo e não oferece segurança para os dados sensíveis dos pacientes (LGPD).

O principal concorrente, `PhotoDoc`, apresenta falhas técnicas, de segurança e possui um posicionamento de mercado fraco. O projeto PhotoClinic surge como uma oportunidade de entregar uma solução mais robusta, segura e com um forte plano de distribuição e vendas. O valor do projeto está na organização do trabalho do profissional e na possibilidade futura de monetização através da análise de dados agregados para a indústria.

## 6. Premissas
*   A abordagem inicial será focada em um aplicativo móvel (mobile-first).
*   Uma única clínica será utilizada como ambiente de teste para validar a usabilidade e as funcionalidades do MVP.
*   As funcionalidades essenciais do MVP serão baseadas nas funcionalidades-chave do aplicativo `PhotoDoc` (molduras, modo fantasma, colagens).
*   Para a fase de testes, será utilizado um modelo de usuário único, com acesso a todas as funcionalidades em múltiplos dispositivos.

## 7. Restrições
*   O escopo do MVP deve ser enxuto e focado nas funcionalidades essenciais para evitar um "projeto infinito".
*   O plano de monetização e as projeções de volumetria de dados não serão definidos nesta fase inicial.
*   O desenvolvimento inicial será focado na plataforma iOS (nativo) para garantir a melhor performance e integração com a câmera.

## 8. Itens Dentro do Escopo (MVP)
*   Criação de álbuns de pacientes.
*   Funcionalidade de "molduras" para diferentes partes do corpo (rosto, etc.).
*   "Modo Fantasma" para comparação de fotos.
*   Criação de colagens de "antes e depois".
*   Armazenamento das fotos em servidor, sem salvar na galeria do dispositivo.
*   Acesso multi-dispositivo (ex: iPhones e iPads) com um usuário único para a fase de testes.
*   Sincronização de fotos entre dispositivos (ex: a foto tirada na sala de preparação aparece no tablet do consultório médico).

## 9. Itens Fora do Escopo (MVP)
*   Funcionalidade para adicionar anotações (texto ou voz transcrita) em pontos específicos da foto (escopo futuro).
*   Sistema de múltiplos usuários com diferentes papéis e permissões (ex: administrador, médico, fotógrafo).
*   Funcionalidades avançadas de IA para análise de transformações milimétricas.
*   Versão para Android.
*   Versão Web para gerenciamento.
*   Plano de monetização e sistema de assinaturas.
*   Funcionalidades completas de conformidade com a LGPD, como termo de aceite do paciente no app (será feito em papel inicialmente).

## 10. Principais Partes Interessadas (Stakeholders)
*   Paulo (Sponsor / Estrategista de Vendas)
*   Hugo Seabra (Gerente de Projeto / Engenharia de Requisitos)
*   Médicos e profissionais de estética (Usuários Finais)
*   Pacientes (Sujeitos dos dados)

## 11. Principais Entregáveis
* Documento de Termo de Abertura de Projeto (TAP).
* Orçamento e execução de análise de requisitos.
* Documento de Engenharia de Requisitos:
    * Documento de Qualificação e Especificação de Requisitos
    * Documento de Jornada e Estórias do usuário
    * Arquitetura de software dentro do esperado e documentado nos requisitos
    * Documento de modelagem de dados
    * Documento de modelagem de recursos
    * Plano de MVP para guiar o desenvolvimento
* Orçamento para desenvolvimento do MVP

## 12. Riscos Iniciais
*   **Segurança:** Vazamento de fotos de pacientes, que são dados biométricos sensíveis.
*   **Técnico:** Dificuldade em replicar o "modo fantasma" de forma precisa e performática.
*   **Adoção:** Resistência dos profissionais em adotar uma nova ferramenta.
*   **LGPD:** Não conformidade com a lei de proteção de dados, gerando riscos jurídicos.

## 13. Cronograma de Alto Nível / Marcos
*   **Fase 1:** Engenharia de Requisitos e Planejamento do Produto.
*   **Fase 2:** Desenvolvimento do MVP - Módulo de Fotos com Molduras.
*   **Fase 3:** Desenvolvimento do MVP - Módulo de Comparação (Modo Fantasma e Colagens).
*   **Fase 4:** Desenvolvimento do MVP - Módulo de Anotações no Prontuário Visual.
*   **Fase 5:** Testes e Validação na clínica piloto.

## 14. Critérios de Sucesso
*   O aplicativo é capaz de tirar e armazenar fotos de forma organizada e segura.
*   A funcionalidade de "modo fantasma" permite uma comparação precisa do antes e depois, sendo considerada útil pelos profissionais.
*   O aplicativo é estável e não apresenta os mesmos bugs do concorrente (ex: erro de armazenamento).
*   A clínica piloto valida as funcionalidades do MVP como superiores ao método de trabalho atual (galeria do celular).

## 15. Aprovação do Projeto

_____________________________
[Responsável pelo Projeto

_____________________________
[Responsável pelo Projeto 2]
