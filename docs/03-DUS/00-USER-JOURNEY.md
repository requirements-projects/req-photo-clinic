# Jornadas do Usuário - PhotoClinic

Este documento mapeia as principais jornadas do usuário no sistema PhotoClinic, agrupando as histórias de usuário em fluxos coerentes que representam experiências completas dos diferentes perfis de usuário.

## 1. Jornada de Cadastro e Gestão de Pacientes

Esta jornada abrange o processo de registro e manutenção dos dados dos pacientes no sistema.

### Histórias de Usuário Relacionadas:
- **[US-CPAC-001]** Cadastrar novo paciente
- **[US-CPAC-002]** Buscar por um paciente
- **[US-CPAC-003]** Editar dados de um paciente
- **[US-CPAC-004]** Inativar um paciente
- **[US-CPAC-005]** Exportar dados do paciente

### Fluxo da Jornada:
1. A recepcionista cadastra um novo paciente no sistema com seus dados básicos
2. Quando necessário, a recepcionista ou profissional de saúde busca o paciente no sistema
3. A recepcionista atualiza os dados do paciente conforme necessário
4. O administrador pode inativar pacientes que não utilizam mais os serviços
5. O administrador pode exportar os dados do paciente para atender solicitações legais

## 2. Jornada de Documentação Clínica

Esta jornada abrange o processo de registro e consulta de informações textuais no prontuário do paciente.

### Histórias de Usuário Relacionadas:
- **[US-CPRO-001]** Registrar anotação clínica
- **[US-CPRO-002]** Consultar histórico do prontuário
- **[US-CPRO-003]** Editar anotação com rastreabilidade

### Fluxo da Jornada:
1. O profissional de saúde cria uma nova anotação no prontuário durante ou após o atendimento
2. O profissional consulta o histórico completo de anotações para tomar decisões informadas
3. Quando necessário, o profissional edita uma anotação anterior, mantendo o registro de auditoria

## 3. Jornada de Captura e Organização de Imagens

Esta jornada abrange o processo completo de captura, armazenamento e organização de imagens clínicas.

### Histórias de Usuário Relacionadas:
- **[US-CIM-001]** Capturar foto com guia de alinhamento
- **[US-CIM-002]** Capturar foto usando modo fantasma
- **[US-CIM-003]** Salvar foto segura no prontuário
- **[US-HCF-001]** Visualizar galeria de imagens do paciente
- **[US-UIFOT-001]** Ter uma interface de câmera limpa e intuitiva
- **[US-UIFOT-002]** Acessar facilmente as ferramentas da câmera
- **[US-UIFOT-003]** Saber para qual paciente estou tirando a foto

### Fluxo da Jornada:
1. O profissional de saúde seleciona um paciente para capturar imagens
2. Utilizando uma interface intuitiva, o profissional acessa a câmera do aplicativo
3. O profissional seleciona uma guia de alinhamento apropriada para padronizar a captura
4. Para fotos de acompanhamento, o profissional pode usar o modo fantasma para replicar o enquadramento anterior
5. Após a captura, a foto é automaticamente salva de forma segura no prontuário do paciente
6. O profissional pode visualizar a galeria de imagens do paciente organizada cronologicamente

## 4. Jornada de Processamento e Apresentação de Resultados

Esta jornada abrange o processo de criação de comparativos visuais e apresentação dos resultados ao paciente.

### Histórias de Usuário Relacionadas:
- **[US-PIMA-001]** Criar colagem de antes e depois
- **[US-PIMA-002]** Salvar colagem no histórico do paciente
- **[US-UICON-001]** Navegar facilmente pelo perfil do paciente
- **[US-UICON-002]** Apresentar comparação de imagens ao paciente

### Fluxo da Jornada:
1. O profissional de saúde seleciona duas imagens (antes e depois) da galeria do paciente
2. O profissional cria uma colagem lado a lado para ilustrar a evolução do tratamento
3. A colagem é salva no histórico do paciente para consultas futuras
4. Durante a consulta, o profissional navega facilmente entre o prontuário e as fotos
5. O profissional apresenta ao paciente as comparações em um modo de visualização limpo e profissional

## 5. Jornada de Sincronização e Disponibilidade de Dados

Esta jornada abrange o processo de garantir que os dados estejam disponíveis e sincronizados entre diferentes dispositivos.

### Histórias de Usuário Relacionadas:
- **[US-SYNC-001]** Trabalhar offline sem interrupções
- **[US-SYNC-002]** Sincronizar dados automaticamente
- **[US-SYNC-003]** Receber dados de outros dispositivos
- **[US-STOR-001]** Garantir armazenamento seguro de dados
- **[US-STOR-002]** Acessar dados de qualquer dispositivo autorizado
- **[US-STOR-003]** Manter fotos do paciente privadas

### Fluxo da Jornada:
1. O profissional de saúde trabalha normalmente mesmo sem conexão à internet
2. Os dados capturados offline são armazenados localmente de forma segura e criptografada
3. Quando a conexão é restabelecida, o sistema sincroniza automaticamente os dados com o servidor
4. O profissional pode acessar os mesmos dados em qualquer dispositivo autorizado da clínica
5. As fotos dos pacientes são mantidas em um ambiente seguro, sem aparecer na galeria padrão do dispositivo

## 6. Jornada de Segurança e Recuperação de Dados

Esta jornada abrange os processos de garantir a segurança, integridade e recuperabilidade dos dados.

### Histórias de Usuário Relacionadas:
- **[US-BACK-001]** Garantir backup automático e regular
- **[US-BACK-002]** Restaurar dados em caso de falha
- **[US-STOR-001]** Garantir armazenamento seguro de dados

### Fluxo da Jornada:
1. O sistema realiza backups automáticos e regulares de todos os dados
2. Os backups são armazenados de forma segura em locais geograficamente distintos
3. Em caso de falha, o administrador do sistema pode restaurar os dados a partir do último backup válido
4. Todos os dados são armazenados com criptografia para garantir a privacidade e segurança

## 7. Jornada de Experiência do Usuário Otimizada

Esta jornada abrange os aspectos de usabilidade e experiência do usuário em diferentes contextos de uso.

### Histórias de Usuário Relacionadas:
- **[US-UIFOT-001]** Ter uma interface de câmera limpa e intuitiva
- **[US-UIFOT-002]** Acessar facilmente as ferramentas da câmera
- **[US-UIFOT-003]** Saber para qual paciente estou tirando a foto
- **[US-UICON-001]** Navegar facilmente pelo perfil do paciente
- **[US-UICON-002]** Apresentar comparação de imagens ao paciente

### Fluxo da Jornada:
1. O profissional interage com interfaces otimizadas para diferentes contextos (captura de fotos, consulta)
2. As ferramentas essenciais estão facilmente acessíveis, sem menus complexos
3. O contexto do paciente está sempre visível para evitar erros
4. A navegação entre diferentes seções do aplicativo é fluida e intuitiva
5. O modo de apresentação permite mostrar resultados ao paciente de forma profissional
