### Funcionalidade: Cadastro de Usuário

- **Diagrama de Classes**: Envolve as classes:

  - `Usuario`: contém os atributos `email` e `senha`.

  - `RepositorioUsuario`: responsável por armazenar os dados dos usuários no banco (Airtable).

  - `Autenticador`: valida os campos e garante que as senhas sejam confirmadas corretamente antes de enviar.

- **Modelo C4 (Container)**: A funcionalidade faz parte do container **Aplicativo Mobile**, que se comunica com o **Banco de Dados (Airtable)** para registrar novos usuários.

- **Modelo C4 (Componente)**: Utiliza a tela `TelaCadastro`, onde o usuário insere seus dados. Os blocos do Thunkable processam os inputs e enviam para o Airtable.

### Funcionalidade: Login de Usuário

- **Diagrama de Classes**: Envolve as classes:

  - `Usuario`: representa os dados inseridos (email e senha).

  - `RepositorioUsuario`: realiza a busca no banco para comparar com os dados inseridos.

  - `Autenticador`: valida se os dados existem no Airtable e autoriza o acesso.

- **Modelo C4 (Container)**: A funcionalidade está no container **Aplicativo Mobile**, que consulta o **Banco de Dados (Airtable)** para autenticar o usuário.

- **Modelo C4 (Componente)**: Utiliza a tela `TelaLogin`, que compara os dados digitados com o que está no Airtable usando blocos de verificação no Thunkable.

### Funcionalidade: Visualizar Alertas Meteorológicos

- **Diagrama de Classes**: Envolve as classes:

  - `Aviso`: representa os dados dos alertas, com atributos como `nivel`, `resumo` e `data`.

  - `RepositorioAviso`: responsável por buscar os alertas no banco Airtable.

- **Modelo C4 (Container)**: A funcionalidade está no container **Aplicativo Mobile**, que se conecta ao **Banco de Dados (Airtable)** para listar os avisos.

- **Modelo C4 (Componente)**: Utiliza a tela `TelaAvisos`, com um `Data Viewer List` vinculado à tabela "Alertas Meteorológicos", exibindo os dados automaticamente.

### Funcionalidade: Visualizar Dados Climáticos e Nível do Rio

- **Diagrama de Classes**: Envolve as classes:

  - `Clima`: contém os atributos `vento`, `precipitacao` e `temperatura`.

  - `NivelRio`: contém os atributos `local`, `nivel` e `dataAtualizacao`.

  - `RepositorioClima` e `RepositorioNivelRio`: responsáveis por buscar os dados nas fontes externas (API, Airtable ou base simulada).

- **Modelo C4 (Container)**: A funcionalidade faz parte do container **Aplicativo Mobile**, que se comunica com o container **Banco de Dados (Airtable)** ou uma **API Externa** para obter os dados atualizados.

- **Modelo C4 (Componente)**: Utiliza a tela `TelaClimaRio`, que consome os dados de clima e nível do rio. Essa tela é composta por campos de texto e ícones dinâmicos, e pode ser atualizada manual ou automaticamente.

