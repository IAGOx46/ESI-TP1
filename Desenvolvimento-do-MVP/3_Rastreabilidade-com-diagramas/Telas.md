# 🔍 Rastreabilidade das Funcionalidades — Sistema Banzeiro

---

## ✅ Funcionalidade: Cadastro de Usuário

**📘 Diagrama de Classes:**  
Envolve as seguintes classes:

- `Usuario`: contém os atributos `email` e `senha`.
- `RepositorioUsuario`: responsável por armazenar os dados dos usuários no banco (Airtable).
- `Autenticador`: valida os campos e garante que as senhas sejam confirmadas corretamente antes de enviar.

**📦 Modelo C4 (Container):**  
Faz parte do container **Aplicativo Mobile**, que se comunica com o **Banco de Dados (Airtable)** para registrar novos usuários.

**🧩 Modelo C4 (Componente):**  
Utiliza a tela `TelaCadastro`, onde o usuário insere seus dados. Os blocos do Thunkable processam os inputs e enviam para o Airtable.

---

## ✅ Funcionalidade: Login de Usuário

**📘 Diagrama de Classes:**  
Envolve as seguintes classes:

- `Usuario`: representa os dados inseridos (`email` e `senha`).
- `RepositorioUsuario`: realiza a busca no banco para comparar com os dados inseridos.
- `Autenticador`: valida se os dados existem no Airtable e autoriza o acesso.

**📦 Modelo C4 (Container):**  
Faz parte do container **Aplicativo Mobile**, que consulta o **Banco de Dados (Airtable)** para autenticar o usuário.

**🧩 Modelo C4 (Componente):**  
Utiliza a tela `TelaLogin`, que compara os dados digitados com os dados do banco usando blocos de verificação do Thunkable.

---

## ✅ Funcionalidade: Visualizar Alertas Meteorológicos

**📘 Diagrama de Classes:**  
Envolve as seguintes classes:

- `Aviso`: representa os dados dos alertas, com atributos como `nivel`, `resumo` e `data`.
- `RepositorioAviso`: responsável por buscar os alertas no banco Airtable.

**📦 Modelo C4 (Container):**  
Faz parte do container **Aplicativo Mobile**, que se conecta ao **Banco de Dados (Airtable)** para exibir os avisos.

**🧩 Modelo C4 (Componente):**  
Utiliza a tela `TelaAvisos`, que usa o componente `Data Viewer List` vinculado à tabela "Alertas Meteorológicos".

---

## ✅ Funcionalidade: Visualizar Dados Climáticos e Nível do Rio

**📘 Diagrama de Classes:**  
Envolve as seguintes classes:

- `Clima`: atributos `vento`, `precipitacao` e `temperatura`.
- `NivelRio`: atributos `local`, `nivel` e `dataAtualizacao`.
- `RepositorioClima` e `RepositorioNivelRio`: responsáveis por buscar os dados nas fontes externas (API, Airtable ou simulador).

**📦 Modelo C4 (Container):**  
Faz parte do container **Aplicativo Mobile**, que se comunica com o **Banco de Dados (Airtable)** ou uma **API externa**.

**🧩 Modelo C4 (Componente):**  
Utiliza a tela `TelaClimaRio`, composta por campos de texto e ícones. Os dados são carregados dinamicamente.

---
