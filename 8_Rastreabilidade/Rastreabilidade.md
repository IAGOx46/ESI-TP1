**Rastreabilidade com Histórias do Usuário \- Banzeiro**

| História de Usuário | Componentes Envolvidos | Diagramas de Referência |
| ----- | ----- | ----- |
| H1- “Como novo usuário do aplicativo, quero poder criar uma conta para que minhas preferências de configuração sejam salvas e recuperadas automaticamente em futuros acessos.”  |  Autenticador, Gestor de preferências, Banco de Dados |  Containers, Componentes, Classes |
| H10- “Como pescador em uma comunidade ribeirinha no Amazonas, quero receber dados personalizados sobre o clima com base nas minhas atividades locais, para tomar decisões mais seguras e eficientes no meu dia a dia de trabalho.”  |  Gestor de preferências, Personalizador de alertas, API Meteorológica, Banco de Dados |  Contexto, Componentes, Classes |
| H9- “Como, um agricultor de uma comunidade ribeirinha, quero receber atualizações simples e confiáveis sobre o nível dos rios, para me planejar melhor e proteger minha produção e minha locomoção em caso de enchentes.”  |  Coletor de dados hidrológicos, Gerador de alerta, Notificador |  Contexto, Componentes |
| H8 \- “Como administrador do aplicativo, quero que os usuários validem suas contas por meio de autenticação multifator (MFA), para garantir a segurança das contas e prevenir acessos não autorizados.”  |  Autenticador, Módulo MFA, Banco de Dados |  Componentes, Classes |
| H7 \- “Como, morador de uma comunidade ribeirinha, quero ser alertado sobre possíveis tempestades na região, para me proteger e reduzir riscos.”  |  Gerador de alerta, Notificador, API Meteorológica |  Componentes, Contexto |
| H6 \- “Como agricultor, quero ser avisado sobre os dias com zero probabilidade de chuva, para poder planejar minhas atividades na região com mais confiança.”  |  Processador de dados meteorológicos, Gerador de alerta |  Componentes, Classes |
| H5 \- “Como, morador de uma comunidade ribeirinha, quero receber alertas claros e antecipados sobre o nível do rio na minha região, para me preparar com antecedência e evitar prejuízos.”  |  Coletor de dados hidrológicos, Gerador de alerta, Notificador |  Contexto, Componentes |
| H2 \- “Como pesquisadora, quero registrar dados sobre o nível dos rios para garantir uma  informação precisa e segura para os usuários”  |  Coletor de dados hidrológicos, Banco de Dados |  Componentes, Classes |
| H4 \- “Como meteorologista, quero editar textos de alertas para deixá-los mais acessíveis e compreensíveis para todos os públicos, para aumentar a eficácia da comunicação e evitar confusões.”  |  Editor de mensagens, Gerador de alerta, Notificador |  Componentes |
| H3 \- “Como pesquisadora, quero baixar conteúdos do aplicativo(como relatórios, gráficos e registros de eventos climáticos) para acessá-los em situações em que eu estiver em campo, e continuar meu trabalho.” |  Exportador de dados, Gerador de relatórios, Banco de Dados |  Componentes, Classes |

