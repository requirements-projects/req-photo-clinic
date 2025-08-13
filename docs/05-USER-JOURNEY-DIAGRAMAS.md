# Diagramas de Atividade das Jornadas do Usuário - PhotoClinic

Este documento complementa o arquivo de jornadas do usuário, apresentando diagramas de atividade detalhados para cada jornada, incluindo fluxos principais, edge-cases e sugestões de melhorias.

---

## 1. Jornada de Cadastro e Gestão de Pacientes

```mermaid
flowchart TD
    Start([Início]) --> A1[Recepcionista acessa o sistema]
    A1 --> Decision1{Ação necessária?}
    Decision1 -->|Novo Paciente| B1[Acessar tela de cadastro]
    B1 --> B2[Preencher dados do paciente\nUS-CPAC-001]
    B2 --> B3{CPF já existe?}
    B3 -->|Sim| B4[Mostrar erro\ne impedir cadastro]
    B4 --> B1
    B3 -->|Não| B5[Salvar dados\ndo paciente]
    B5 --> B6[Exibir perfil\ndo paciente]
    B6 --> End
    Decision1 -->|Buscar Paciente| C1[Acessar campo de busca]
    C1 --> C2[Digitar nome, CPF\nou telefone\nUS-CPAC-002]
    C2 --> C3[Sistema busca\ne exibe resultados]
    C3 --> C4{Paciente\nencontrado?}
    C4 -->|Não| C5[Exibir 'Não encontrado']
    C5 --> C1
    C4 -->|Sim| C6[Selecionar paciente\nda lista]
    C6 --> C7[Exibir perfil\ndo paciente]
    C7 --> End
    Decision1 -->|Editar Paciente| D1[Buscar e selecionar\npaciente]
    D1 --> D2[Acessar função\nde edição\nUS-CPAC-003]
    D2 --> D3[Modificar dados]
    D3 --> D4[Sistema registra log\nde alteração]
    D4 --> D5[Salvar alterações]
    D5 --> End
    Decision1 -->|Inativar Paciente| E1[Administrador busca\npaciente]
    E1 --> E2[Verificar histórico\ndo paciente]
    E2 --> E3[Selecionar função\nde inativação\nUS-CPAC-004]
    E3 --> E4[Confirmar inativação]
    E4 --> E5[Sistema atualiza\nstatus para INATIVO]
    E5 --> End
    Decision1 -->|Exportar Dados| F1[Administrador busca\npaciente]
    F1 --> F2[Selecionar função\nde exportação\nUS-CPAC-005]
    F2 --> F3[Sistema gera\narquivo PDF]
    F3 --> F4[Salvar PDF\nlocalmente]
    F4 --> End
    Decision1 -->|Reativar Paciente| G1[Administrador busca\npaciente inativo]
    G1 --> G2[Selecionar função\nde reativação]
    G2 --> G3[Confirmar reativação]
    G3 --> G4[Sistema atualiza\nstatus para ATIVO]
    G4 --> End
    End([Fim])
```

---

## 2. Jornada de Documentação Clínica

```mermaid
flowchart TD
    Start([Início]) --> A1[Profissional acessa\nperfil do paciente]
    A1 --> Decision1{Ação necessária?}
    Decision1 -->|Criar Anotação| B1[Acessar prontuário]
    B1 --> B2[Selecionar 'Nova Anotação'\nUS-CPRO-001]
    B2 --> B3[Escrever conteúdo\nda anotação]
    B3 --> B4[Salvar anotação]
    B4 --> B5[Sistema vincula anotação ao\npaciente, profissional e data/hora]
    B5 --> End
    Decision1 -->|Consultar Histórico| C1[Acessar prontuário]
    C1 --> C2[Sistema exibe histórico\nem ordem cronológica\nUS-CPRO-002]
    C2 --> C3[Profissional analisa\nanotações anteriores]
    C3 --> C4{Informação\nsuficiente?}
    C4 -->|Não| C5[Filtrar ou\nbuscar anotações]
    C5 --> C3
    C4 -->|Sim| End
    Decision1 -->|Editar Anotação| D1[Acessar prontuário]
    D1 --> D2[Localizar anotação\na ser editada]
    D2 --> D3{Anotação é do\nprofissional?}
    D3 -->|Não| D4[Sistema exibe\nmensagem de erro]
    D4 --> End
    D3 -->|Sim| D5[Editar texto\nUS-CPRO-003]
    D5 --> D6[Sistema armazena\nversão original]
    D6 --> D7[Sistema registra log\nde auditoria]
    D7 --> D8[Salvar alterações]
    D8 --> End
    Decision1 -->|Buscar por Período| E1[Acessar prontuário]
    E1 --> E2[Selecionar filtro\nde datas]
    E2 --> E3[Sistema exibe anotações\ndo período selecionado]
    E3 --> End
    Decision1 -->|Verificar Edições| F1[Acessar prontuário]
    F1 --> F2[Selecionar anotação]
    F2 --> F3[Visualizar histórico\nde edições]
    F3 --> F4[Sistema exibe todas\nas versões anteriores]
    F4 --> End
    End([Fim])
```

---

## 3. Jornada de Captura e Organização de Imagens

```mermaid
flowchart TD
    Start([Início]) --> A1[Profissional acessa\nperfil do paciente]
    A1 --> A2[Seleciona opção\nde captura de imagens]
    A2 --> Decision1{O que fazer?}
    Decision1 -->|Capturar com Guia| B1[Abrir interface da câmera\nUS-UIFOT-001]
    B1 --> B2[Sistema exibe nome\ndo paciente\nUS-UIFOT-003]
    B2 --> B3[Selecionar guia\nde alinhamento\nUS-CIM-001]
    B3 --> B4[Sistema sobrepõe\nguia na câmera]
    B4 --> B5[Capturar foto]
    B5 --> B6[Sistema salva foto\nno prontuário\nUS-CIM-003]
    B6 --> B7[Exibir visualização\nda foto capturada]
    B7 --> Decision2{Capturar mais?}
    Decision2 -->|Sim| B1
    Decision2 -->|Não| End
    Decision1 -->|Modo Fantasma| C1[Abrir galeria do paciente\nUS-HCF-001]
    C1 --> C2[Selecionar foto\nde referência]
    C2 --> C3[Abrir câmera com\nmodo fantasma\nUS-UIFOT-002]
    C3 --> C4[Sistema sobrepõe\nfoto anterior com\ntransparência\nUS-CIM-002]
    C4 --> C5[Alinhar ângulo e\ndistância]
    C5 --> C6[Capturar nova foto]
    C6 --> C7[Sistema salva foto\nno prontuário]
    C7 --> End
    Decision1 -->|Ver Galeria| D1[Acessar galeria\ndo paciente\nUS-HCF-001]
    D1 --> D2[Sistema exibe fotos\nem ordem cronológica]
    D2 --> D3[Profissional navega\nentre as fotos]
    D3 --> D4{Ação na foto?}
    D4 -->|Ver Detalhes| D5[Abrir foto em\ntela cheia]
    D5 --> D3
    D4 -->|Selecionar| D6[Marcar foto\npara colagem]
    D6 --> D3
    D4 -->|Nenhuma| End
    Decision1 -->|Categorizar| E1[Selecionar foto]
    E1 --> E2[Atribuir categoria\nà imagem]
    E2 --> E3[Sistema atualiza\nmetadados da foto]
    E3 --> End
    B5 -->|Erro| F1[Sistema exibe\nmensagem de erro]
    F1 --> F2[Opções de solução]
    F2 --> F3{Tentar novamente?}
    F3 -->|Sim| B1
    F3 -->|Não| End
    End([Fim])
```

---

## 4. Jornada de Processamento e Apresentação de Resultados

```mermaid
flowchart TD
    Start([Início]) --> A1[Profissional acessa\nperfil do paciente]
    A1 --> A2[Navegar para galeria\nUS-UICON-001]
    A2 --> Decision1{O que fazer?}
    Decision1 -->|Criar Colagem| B1[Selecionar foto 'antes']
    B1 --> B2[Selecionar foto 'depois']
    B2 --> B3[Acessar ferramenta\nde colagem\nUS-PIMA-001]
    B3 --> B4[Sistema gera\nvisualização da colagem]
    B4 --> B5{Layout adequado?}
    B5 -->|Não| B6[Ajustar layout]
    B6 --> B4
    B5 -->|Sim| B7[Adicionar título\ne legenda]
    B7 --> B8[Salvar colagem\nUS-PIMA-002]
    B8 --> B9[Sistema armazena\ncolagem no histórico]
    B9 --> End
    Decision1 -->|Apresentar ao Paciente| C1[Selecionar colagem]
    C1 --> C2[Ativar modo\napresentação\nUS-UICON-002]
    C2 --> C3[Sistema exibe em\ntela cheia]
    C3 --> C4[Profissional explica\nresultados ao paciente]
    C4 --> C5{Mais colagens?}
    C5 -->|Sim| C6[Navegar para\npróxima colagem]
    C6 --> C3
    C5 -->|Não| C7[Sair do modo\napresentação]
    C7 --> End
    Decision1 -->|Navegar Imagens| D1[Sistema exibe\ngaleria organizada]
    D1 --> D2[Profissional filtra\npor data ou tipo]
    D2 --> D3[Visualizar evolução\ndo tratamento]
    D3 --> End
    Decision1 -->|Exportar para Marketing| E1[Selecionar colagem]
    E1 --> E2{Autorização do\npaciente?}
    E2 -->|Não| E3[Exibir aviso\nde restrição]
    E3 --> End
    E2 -->|Sim| E4[Exportar com\nmetadados anonimizados]
    E4 --> E5[Sistema gera\narquivo da colagem]
    E5 --> End
    B8 -->|Erro| F1[Sistema exibe\nmensagem de erro]
    F1 --> F2{Tentar novamente?}
    F2 -->|Sim| B4
    F2 -->|Não| End
    End([Fim])
```

---

## 5. Jornada de Sincronização e Disponibilidade de Dados

```mermaid
flowchart TD
    Start([Início]) --> A1[Profissional utiliza\no aplicativo]
    A1 --> A2[Sistema verifica\nconectividade]
    A2 --> Decision1{Internet\ndisponível?}
    Decision1 -->|Não| B1[Sistema ativa\nmodo offline\nUS-SYNC-001]
    B1 --> B2[Profissional continua\ntrabalho normalmente]
    B2 --> B3[Dados são salvos\nlocalmente]
    B3 --> B4[Sistema monitora\nconectividade]
    B4 --> B5{Conexão\nrestabelecida?}
    B5 -->|Não| B2
    B5 -->|Sim| B6[Sistema inicia\nsincronização\nUS-SYNC-002]
    B6 --> End
    Decision1 -->|Sim| C1[Sistema sincroniza\nem segundo plano]
    C1 --> C2[Sistema busca\natualizações do servidor]
    C2 --> C3[Novos dados de outros\ndispositivos são baixados\nUS-SYNC-003]
    C3 --> C4[Sistema atualiza\ninterface com novos dados]
    C4 --> End
    Start --> D1[Profissional acessa\noutro dispositivo]
    D1 --> D2[Login no sistema]
    D2 --> D3[Sistema verifica\ndispositivo]
    D3 --> D4{Dispositivo\nautorizado?}
    D4 -->|Não| D5[Processo de\nautorização]
    D5 --> D6{Autorizado?}
    D6 -->|Não| End
    D6 -->|Sim| D7[Acesso concedido]
    D4 -->|Sim| D7
    D7 --> D8[Sistema carrega dados\ndo servidor\nUS-STOR-002]
    D8 --> End
    Start --> E1[Sistema processa\ndados sensíveis]
    E1 --> E2[Dados criptografados\nante do armazenamento\nUS-STOR-001]
    E2 --> E3[Imagens isoladas da\ngaleria padrão\nUS-STOR-003]
    E3 --> End
    B6 --> F1{Conflito detectado?}
    F1 -->|Sim| F2[Sistema identifica\nversão mais recente]
    F2 --> F3[Notificar usuário\nsobre conflito]
    F3 --> F4{Resolução\nautomática?}
    F4 -->|Sim| F5[Aplicar regra\nde mesclagem]
    F4 -->|Não| F6[Usuário seleciona\nversão a manter]
    F5 --> End
    F6 --> End
    F1 -->|Não| End
    B6 --> G1{Falha na\nsincronização?}
    G1 -->|Sim| G2[Sistema registra erro]
    G2 --> G3[Adicionar à fila de\nretentativas]
    G3 --> G4[Notificar usuário]
    G4 --> End
    G1 -->|Não| End
    End([Fim])
```

---

## 6. Jornada de Segurança e Recuperação de Dados

```mermaid
flowchart TD
    Start([Início]) --> A1[Sistema em operação]
    A1 --> A2[Verificar horário\nprogramado]
    A2 --> Decision1{Hora do backup?}
    Decision1 -->|Sim| B1[Iniciar processo\nde backup\nUS-BACK-001]
    B1 --> B2[Sistema cria snapshot\ndo banco de dados]
    B2 --> B3[Criptografar dados\nUS-STOR-001]
    B3 --> B4[Transferir para\narmazenamento secundário]
    B4 --> B5{Transferência\nconcluída?}
    B5 -->|Não| B6[Registrar falha]
    B6 --> B7[Notificar administrador]
    B7 --> B8[Agendar nova tentativa]
    B8 --> End
    B5 -->|Sim| B9[Validar integridade\ndo backup]
    B9 --> B10{Backup válido?}
    B10 -->|Não| B6
    B10 -->|Sim| B11[Registrar backup\nbem-sucedido]
    B11 --> B12[Remover backups\nantigos conforme política]
    B12 --> End
    Start --> C1[Ocorrência de falha\nno sistema]
    C1 --> C2[Administrador inicia\nrecuperação\nUS-BACK-002]
    C2 --> C3[Selecionar backup\nmais recente válido]
    C3 --> C4[Iniciar processo\nde restauração]
    C4 --> C5[Sistema desativado\npara manutenção]
    C5 --> C6[Restaurar dados\ndo backup]
    C6 --> C7{Restauração\nconcluída?}
    C7 -->|Não| C8[Registrar erro]
    C8 --> C9[Tentar backup\nalternativo]
    C9 --> C4
    C7 -->|Sim| C10[Verificar integridade\ndos dados]
    C10 --> C11{Dados íntegros?}
    C11 -->|Não| C8
    C11 -->|Sim| C12[Reativar sistema]
    C12 --> C13[Notificar usuários]
    C13 --> End
    Decision1 -->|Não| D1{Solicitação de\nbackup manual?}
    D1 -->|Sim| B1
    D1 -->|Não| A1
    Start --> E1[Administrador inicia\nteste de recuperação]
    E1 --> E2[Criar ambiente\nde teste isolado]
    E2 --> E3[Executar recuperação\nno ambiente de teste]
    E3 --> E4{Teste bem-sucedido?}
    E4 -->|Não| E5[Documentar falhas]
    E5 --> E6[Ajustar procedimentos]
    E6 --> End
    E4 -->|Sim| E7[Documentar sucesso]
    E7 --> End
    End([Fim])
```

---

## 7. Jornada de Experiência do Usuário Otimizada

```mermaid
flowchart TD
    Start([Início]) --> A1[Usuário acessa\no sistema]
    A1 --> A2[Sistema detecta perfil\nde usuário e contexto]
    A2 --> Decision1{Contexto de uso?}
    Decision1 -->|Captura de Fotos| B1[Carregar interface\nde fotografia]
    B1 --> B2[Exibir controles\nsimples e botões grandes\nUS-UIFOT-001]
    B2 --> B3[Mostrar nome do\npaciente em destaque\nUS-UIFOT-003]
    B3 --> B4[Disponibilizar acesso\nrápido às ferramentas\nUS-UIFOT-002]
    B4 --> B5[Usuário captura\nimagens]
    B5 --> B6[Feedback visual\nimediato]
    B6 --> End
    Decision1 -->|Consulta com Paciente| C1[Carregar interface\nde consulta]
    C1 --> C2[Exibir abas de\nnavegação clara\nUS-UICON-001]
    C2 --> C3[Usuário alterna\nentre seções]
    C3 --> C4{Apresentar\nresultados?}
    C4 -->|Sim| C5[Ativar modo de\napresentação limpo\nUS-UICON-002]
    C5 --> C6[Ocultar elementos\nda interface]
    C6 --> C7[Exibir imagens\nem tela cheia]
    C7 --> End
    C4 -->|Não| End
    Decision1 -->|Novo Dispositivo| D1[Detectar características\ndo dispositivo]
    D1 --> D2[Ajustar layout para\ntamanho da tela]
    D2 --> D3[Otimizar controles\npara tipo de dispositivo]
    D3 --> D4[Aplicar preferências\ndo usuário]
    D4 --> End
    Decision1 -->|Personalização| E1[Usuário acessa\nconfigurações]
    E1 --> E2[Ajustar preferências\nde interface]
    E2 --> E3[Sistema salva\npreferências]
    E3 --> E4[Aplicar mudanças\nà interface]
    E4 --> End
    Decision1 -->|Acessibilidade| F1[Detectar necessidades\nde acessibilidade]
    F1 --> F2[Ativar recursos\nde acessibilidade]
    F2 --> F3[Ajustar contraste\ne tamanho de texto]
    F3 --> F4[Adaptar controles\npara facilitar uso]
    F4 --> End
    End([Fim])
```

---

## Casos de Uso Adicionais

### Recuperação de Conta e Dispositivo

```mermaid
flowchart TD
    Start([Início]) --> A1[Usuário não consegue\nacessar sua conta]
    A1 --> Decision1{Tipo de problema?}
    Decision1 -->|Senha Esquecida| B1[Selecionar 'Esqueci\nminha senha']
    B1 --> B2[Sistema solicita\ne-mail cadastrado]
    B2 --> B3[Sistema envia link\nde recuperação]
    B3 --> B4[Usuário cria nova senha]
    B4 --> B5[Sistema atualiza\ncredenciais]
    B5 --> End
    Decision1 -->|Novo Dispositivo| C1[Tentar login em\nnovo dispositivo]
    C1 --> C2[Sistema detecta\ndispositivo não autorizado]
    C2 --> C3[Sistema solicita\nautenticação adicional]
    C3 --> C4[Administrador aprova\nnovo dispositivo]
    C4 --> C5[Sistema registra\nnovo dispositivo]
    C5 --> End
    Decision1 -->|Conta Bloqueada| D1[Sistema exibe\nmensagem de bloqueio]
    D1 --> D2[Usuário contata\nadministrador]
    D2 --> D3[Administrador verifica\nmotivo do bloqueio]
    D3 --> D4{Desbloquear?}
    D4 -->|Sim| D5[Administrador\ndesbloqueia conta]
    D5 --> D6[Sistema reativa\nconta do usuário]
    D6 --> End
    D4 -->|Não| D7[Manter bloqueio]
    D7 --> End
    End([Fim])
```

### Jornada de Conformidade com a LGPD

```mermaid
flowchart TD
    Start([Início]) --> A1[Paciente solicita\ndireitos de privacidade]
    A1 --> Decision1{Tipo de solicitação?}
    Decision1 -->|Acesso aos Dados| B1[Administrador recebe\nsolicitação]
    B1 --> B2[Verificar identidade\ndo solicitante]
    B2 --> B3[Gerar relatório de\ndados do paciente]
    B3 --> B4[Entregar relatório\nde forma segura]
    B4 --> End
    Decision1 -->|Exclusão de Dados| C1[Administrador recebe\nsolicitação]
    C1 --> C2[Verificar obrigações\nlegais de retenção]
    C2 --> C3{Pode excluir?}
    C3 -->|Não| C4[Informar impedimento\nlegal ao paciente]
    C4 --> End
    C3 -->|Sim| C5[Iniciar processo\nde exclusão]
    C5 --> C6[Remover dados\npessoais]
    C6 --> C7[Documentar exclusão]
    C7 --> End
    Decision1 -->|Portabilidade| D1[Administrador recebe\nsolicitação]
    D1 --> D2[Gerar dados em\nformato estruturado]
    D2 --> D3[Exportar para\nformato padrão]
    D3 --> D4[Entregar arquivo\nao paciente]
    D4 --> End
    End([Fim])
```
