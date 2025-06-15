# 🧠 Arquitetura Tecnológica do Sistema

Este documento descreve a estrutura tecnológica utilizada no sistema, com foco nas camadas funcionais e ferramentas associadas. A arquitetura busca equilíbrio entre flexibilidade, acessibilidade e robustez, integrando soluções de baixo código com tecnologias escaláveis.

---

<img src=https://github.com/IAGOx46/ESI-TP1/blob/main/images/image.png>

---

## 🧱 Camada 1 – **Frontend (Interface com o Usuário)**

### 📋 Descrição:
Essa camada é responsável pela interação direta com o usuário final. A proposta inclui soluções multiplataforma (mobile e web), com foco em acessibilidade, responsividade e facilidade de uso.

### 🛠️ Tecnologias Utilizadas:
- **React Native** – Framework para apps nativos com JavaScript.
- **Flutter** – Toolkit da Google baseado em Dart, ideal para interfaces fluidas.
- **Thunkable** – Plataforma low-code para construção rápida de apps móveis.
- **Dart** – Linguagem usada no Flutter, com foco em performance e UI.

### 🧩 Objetivo:
Oferecer interfaces visuais intuitivas, acessíveis tanto para usuários técnicos quanto leigos, como Lucas (Persona 1).

---

## ⚙️ Camada 2 – **Backend (Lógica do Sistema)**

### 📋 Descrição:
Essa camada processa a lógica de negócio, integra dados e serviços, e serve como ponte entre a interface e o armazenamento.

### 🛠️ Tecnologias Utilizadas:
- **Node.js** – Ambiente JavaScript para desenvolvimento assíncrono e rápido.
- **JavaScript** – Linguagem de suporte ao Node.js.
- **C# e .NET** – Alternativa robusta para sistemas baseados em Windows.
- **API REST** – Padrão de comunicação entre o frontend e o backend.
- **Thunkable Cloud** – Backend visual da plataforma Thunkable.

### 🧩 Objetivo:
Fornecer dados e processar requisições com estabilidade e escalabilidade. Adequado ao trabalho técnico de Carla e à manutenção feita por Marcos.

---

## 🗃️ Camada 3 – **Banco de Dados (Armazenamento)**

### 📋 Descrição:
O sistema precisa de armazenamento estruturado, capaz de lidar tanto com grandes volumes quanto com soluções leves e de rápida integração.

### 🛠️ Tecnologias Utilizadas:
- **PostgreSQL / TimescaleDB** – Banco relacional robusto, ideal para séries temporais (chuvas, nível de rios).
- **SQL** – Linguagem de consulta padrão.
- **Airtable** – Banco de dados visual e colaborativo.
- **Google Sheets** – Armazenamento leve e acessível para contextos simples.

### 🧩 Objetivo:
Oferecer diferentes níveis de armazenamento, de acordo com o contexto (baixo custo e alta acessibilidade para Lucas; precisão técnica para Carla).

---

## 🔐 Camada 4 – **Autenticação**

### 📋 Descrição:
Mecanismos que controlam o acesso ao sistema de acordo com o tipo de usuário e permissões específicas.

### 🛠️ Tecnologias Utilizadas:
- **OAuth 2.0** – Padrão seguro de autenticação.
- **Firebase Authentication** – Solução de autenticação rápida e escalável.
- **Thunkable Auth** – Autenticação nativa para apps criados no Thunkable.

### 🧩 Objetivo:
Garantir segurança, simplicidade no login e integração com plataformas existentes.

---

## ☁️ Camada 5 – **Deploy e Infraestrutura**

### 📋 Descrição:
Conjunto de ferramentas para publicação, hospedagem, gerenciamento e manutenção do sistema e seus serviços.

### 🛠️ Tecnologias Utilizadas:
- **Gerador de APK (Android)** – Criação de arquivos instaláveis diretamente.
- **Publicação para App Store / Google Play** – Distribuição oficial dos aplicativos.
- **AWS (EC2 / Lambda)** – Infraestrutura escalável e baseada em nuvem.
- **Google Cloud / Firebase** – Hospedagem, notificações e backend como serviço.

### 🧩 Objetivo:
Viabilizar a publicação, escalabilidade e manutenção constante do sistema, permitindo que Marcos administre a plataforma de forma eficiente.

---

## 🎨 Cores do Diagrama

- 🟩 **Funcional Técnica**: linguagens, frameworks, interfaces e lógica.
- 🟨 **Infraestrutura**: bancos de dados, autenticação, servidores, publicação.

---

# 🧰 Tabela de Tecnologias Utilizadas (Tech Table)

Esta tabela resume as principais tecnologias adotadas para o desenvolvimento do sistema, organizadas por camadas arquiteturais. Cada tecnologia foi escolhida com base em sua compatibilidade com plataformas no-code, facilidade de integração e escalabilidade.

---

<img src=https://github.com/IAGOx46/ESI-TP1/blob/main/images/Captura%20de%20tela%202025-06-14%20230959.png>

---

## 🧱 Camada: Frontend

- **Tecnologia:** Thunkable  
- **Justificativa:** Plataforma no-code com suporte _cross-platform_ (Android e iOS). Permite criar interfaces gráficas e interações com facilidade, sem necessidade de codificação avançada.

---

## ⚙️ Camada: Backend

- **Tecnologia:** Thunkable Cloud, API REST  
- **Justificativa:** Integração com serviços externos via REST, possibilitando o consumo dinâmico de dados meteorológicos em tempo real. O Thunkable Cloud viabiliza lógica de backend mesmo em ambiente no-code.

---

## 🗃️ Camada: Banco de Dados

- **Tecnologia:** Google Sheets, Airtable  
- **Justificativa:** Soluções acessíveis e visuais, integradas diretamente ao Thunkable. Permitem armazenar e consultar dados estruturados com agilidade, ideal para MVPs e protótipos rápidos.

---

## 🔐 Camada: Autenticação

- **Tecnologia:** OAuth 2.0  
- **Justificativa:** Padrão amplamente adotado que oferece segurança e escalabilidade no controle de acesso ao sistema. Compatível com diversos serviços de terceiros (Google, Facebook, etc).

---

## ☁️ Camada: Deploy

- **Tecnologia:** Thunkable (APK/IPA Generator), Publicação na App Store / Play Store  
- **Justificativa:** Geração fácil de aplicativos instaláveis (APK/IPA) e publicação direta nas principais lojas de aplicativos, facilitando a distribuição ao público final.

---

