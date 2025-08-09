# Documento de Qualificação de Escopo e Requisitos (DQER)

## 1. Propósito deste Documento

Este documento tem como finalidade estabelecer formalmente o escopo e os requisitos do sistema PhotoClinic, a partir do alinhamento entre a visão do projeto (conforme o Termo de Abertura) e as funcionalidades técnicas observadas em soluções de mercado, especialmente o aplicativo PhotoDoc.
Ele garante que todas as partes envolvidas compartilhem um entendimento comum sobre o que será construído, em que termos e com quais critérios de aceitação, possibilitando rastreabilidade ao longo de todo o ciclo de vida do projeto.

## 2. Público-alvo deste Documento

???

## 3. Introdução

A aplicação PhotoClinic é uma ** solução móvel ** voltada para clínicas de estética e consultórios médicos, cujo propósito é padronizar, organizar e manter a integridade dos registros fotográficos de seus pacientes, com fins estéticos, legais e comerciais e  substituir a utilização da galeria de fotos padrão dos dispositivos móveis por um ambiente dedicado, seguro e organizado.

**Inspirado no funcionamento e nas falhas observadas no app PhotoDoc, o sistema visa oferecer uma experiência aprimorada, com maior precisão, segurança de dados e foco na usabilidade clínica.**

## 4. Objetivos do Sistema
Desenvolver um aplicativo móvel que permita a captura, organização, sincronização e comparação de imagens clínicas de pacientes, com foco na padronização visual e na segurança da informação.

- Criar álbuns individuais de pacientes com organização cronológica;
- Registrar e organizar imagens de pacientes em sessões estéticas, com padronização visual (molduras, posicionamento, iluminação, modo fantasma).
- Permitir criação de colagens para comparação “antes e depois”;
- Armazenar imagens exclusivamente em ambiente seguro, fora da galeria do celular;
- Proteger a integridade dos dados (sigilo, backup e controle de acesso);
- Gerar colagens e relatórios para fins clínicos, de marketing e documentação;
- Garantir rastreabilidade de alterações e registros fotográfico;
- Atender normas éticas, legais e técnicas sobre o uso de imagem em ambientes clínicos.



## 5. Perfis de Usuário


| Perfil                               | Descrição                                                                   | Acesso                                          |
| ------------------------------------ | --------------------------------------------------------------------------- | ----------------------------------------------- |
| **Profissional de Estética**         | Responsável pela captura de imagens na sala de procedimentos.               | Câmera, molduras, modo fantasma, colagens.      |
| **Médico(a)**                        | Utiliza as imagens para demonstrar evolução ao paciente durante a consulta. | Visualização de álbuns e colagens, comparações. |
| **Administrador Clínico** *(futuro)* | Gerencia permissões, pacientes e exportações de imagens.                    | Acesso completo.                                |
| **Paciente** *(indiretamente)*       | Sujeito dos dados, visualiza imagens com mediação do profissional.          | Nenhum acesso direto ao sistema.                |





## 6. Problemáticas Identificadas



| Stakeholder/Persona                                       | Problema                                                                                | Conflitos                                                                                | Observações                                                                     |
| --------------------------------------------------------- | --------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| Profissional de estética                                  | Dificuldade em capturar fotos com qualidade e alinhamento consistentes                  | Perda de tempo com repetição de fotos, frustração com resultados inconsistentes          | Necessidade de molduras e guias de alinhamento (modo fantasma)                  |
| Dono da clínica                                           | Ausência de padronização entre os registros de diferentes profissionais                 | Dificuldade em manter controle de qualidade e comparação de resultados                   | Necessário centralizar e padronizar o processo fotográfico                      |
| Paciente/cliente                                          | Desconfiança quanto à veracidade de antes e depois                                      | Sensação de insegurança sobre os resultados entregues                                    | Importância de fotos com integridade e coerência visual                         |
| Profissional de marketing                                 | Fotos desalinhadas e com baixa qualidade comprometem campanhas de divulgação            | Impossibilidade de usar registros nos materiais institucionais                           | Necessário recurso de colagem e tratamento visual para uso em mídia             |
| TI da clínica                                             | Falta de controle sobre dispositivos e armazenamento das imagens                        | Risco de vazamento de dados, duplicidade e dificuldade de integração com outros sistemas | Importância de sincronização, criptografia e integração com sistemas existentes |
| Auditorias clínicas/regulatórias                          | Impossibilidade de rastrear histórico fotográfico com confiabilidade técnica e temporal | Não conformidade com exigências éticas, contratuais ou legais                            | Importância de metadados, data/hora automática e controle de versão             |




## 7. Domínios e Módulos do Sistema

Os domínios do sistema representam áreas funcionais organizadas para atender às necessidades específicas da clínica estética, agrupando módulos que compartilham objetivos semelhantes e funcionalidades interdependentes.

### 7.1. Domínio de Cadastro e Gestão de Pacientes

Gerenciar informações pessoais, clínicas e fotográficas dos pacientes.


| # | Seção                             | Descrição                                                                                                                  | Detalhamento do módulo                        |
|---|-----------------------------------|----------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------|
| 7.1.1 | Cadastro de Pacientes             | Permite cadastrar e atualizar dados básicos do paciente: nome, contato, CPF, data de nascimento, foto de perfil, etc.                                                                                                                                               Registro de dados clínicos relevantes (alergias, observações de pele, uso de medicamentos etc.). |  Registros Fotográficos, Módulo de Relatórios
| 7.1.2 | Histórico Clínico Fotográfico     | Armazena e organiza o acervo de imagens e registros visuais por atendimento.                                          | Registros Fotográficos, Agendamentos, e Assinatura de Termos.
| 7.1.3 | Organização por Sessão/Tratamento | Vincula imagens a sessões específicas ou protocolos realizados na clínica.   




### 7.2. Domínio de Registro Fotográfico

Padronizar a captura e armazenamento de fotos antes, durante e após sessões.

| # | Seção               | Descrição                                                                                                                                  | Detalhamento do módulo             |
|---|---------------------|--------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------|
| 7.2.1 | Captura com Moldura | Aplica molduras visuais que padronizam o enquadramento das fotos.                | Edição e Colagem
| 7.2.2 | Modo Fantasma       | Sobreposição da imagem anterior para garantir alinhamento exato na nova captura. | Integra com Captura de Imagens e Galeria
| 7.2.3 | Edição de Imagens   | Recursos básicos de corte, brilho, contraste e anotações visuais.  Aplicação de filtros técnicos               |Integra com Galeria, Colagem e Relatórios
| 7.2.4 | Criação de Colagens | Permite combinar fotos em uma mesma visualização comparativa.| Integra com Galeria de Pacientes e Exportação
| 7.2.5 | Organização de Fotos |  Organização por data, área e tipo de procedimento| Integra com Histórico e Pacientes




### 7.3. Domínio de Edição e Colagem de Imagens

Recursos visuais para comparação e documentação técnica.

| # | Seção             | Descrição                                                                                                                                         | Detalhamento do módulo                     |
|---|-------------------|---------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------|
| 7.3.1 | Exportação e Compartilhamento | Permite salvar colagens e imagens para PDF ou enviar via WhatsApp, e-mail ou outros meios. |Integra com Galeria e Módulo de Relatórios
| 7.3.2 | Catálogo de Casos             | Criação de portfólio clínico, com filtros de pesquisa e visualização organizada.           | Integra com Histórico Fotográfico
| 7.3.3 | Comparação           | Colagens personalizáveis (lado a lado, sobreposição, sequência)           |Integra com Registro Fotográfico
| 7.3.4 | Edição e Anotações         | Anotações básicas (setas, círculos, texto, observações)           |Integra com Imagem e Relatórios




### 7.4. Domínio de Gestão de Tratamentos 

Organização dos procedimentos realizados em cada paciente.

| # | Seção               | Descrição                                                                                                                                          | Detalhamento do módulo                     |
|---|---------------------|----------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------|
| 7.4.1 | Etapas do Tratamento      | Associação de imagens a cada fase do procedimento. |Integra com Galeria e Histórico Clínico|
7.4.2 |Registro de Produtos | Armazena os produtos utilizados em cada etapa.|Integra com Relatórios Clínicos|
7.4.4| Evolução Clínica| Registro de evolução com base em fotos, colagens e observações clínicas.|Integra com Galeria e Relatórios

### 7.5.  Domínio de Administração e Configurações

Personalização do aplicativo conforme a realidade da clínica.

| # | Seção               | Descrição                                                                                                                                          | Detalhamento do módulo                     |
|---|---------------------|----------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------|
| 7.5.1 | Cadastro de Profissionais        | Registro de usuários da clínica (médicos, esteticistas, etc.), com permissões específicas. |Integra com Controle de Acesso
| 7.5.2 | Configurações da Clínica         | Definições de logotipo, nome da clínica, campos obrigatórios, molduras, backups, etc.      |Integra com Personalização e Backup
| 7.5.3 | Sincronização entre Dispositivos | Controle de múltiplos dispositivos com acesso ao mesmo banco de imagens.                   |Integra com Backup e Segurança


### 7.6. Domínio de Segurança e Acesso

Este domínio abrange o gerenciamento financeiro da operação pecuária, incluindo plano de contas, lançamentos e relatórios.

| # | Seção      | Descrição                                                                                                        | Detalhamento do módulo         |
|---|------------|------------------------------------------------------------------------------------------------------------------|--------------------------------|
| 7.6.1 | Autenticação           | Login seguro com biometria facial, digital ou PIN.                                 |Integra com Cadastro de Profissionais
| 7.6.2 | Criptografia de Dados  | Proteção dos dados e imagens localmente e em trânsito.                             |Integra com Backup e Sincronização
| 7.6.3 | Controle de Permissões | Níveis de acesso por perfil de usuário, restrição a determinadas áreas ou funções. |Integra com Administração



## 9. Anexos e Referências

Estes são documentos e materiais de referência que complementam o DQER, fornecendo informações
adicionais sobre o projeto 
