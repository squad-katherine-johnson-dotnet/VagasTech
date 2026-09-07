# 💼 Plataforma Vagas Tech

Projeto desenvolvido em **squad** como parte do desafio prático final do módulo de **Banco de Dados e Persistência de Dados**, utilizando **C#, ADO.NET, SQLite e SQL**.

## 🎯 Objetivo

Desenvolver o sistema de persistência de dados de uma plataforma de empregos chamada **Vagas Tech**, voltada para conectar empresas que possuem vagas afirmativas a talentos femininos da área de tecnologia.

O projeto tem como objetivo aplicar os conhecimentos de **modelagem de banco de dados, relacionamentos Muitos-para-Muitos (N:N), SQL, CRUD e integração de uma aplicação C# com banco de dados utilizando ADO.NET**.

## 🗄️ Estrutura do Banco de Dados

O banco de dados utilizado no projeto é o **`vagas_tech.db`**, composto por três tabelas:

### 💼 VAGAS

Armazena as informações das oportunidades de emprego:

* `ID_VAGA` — Chave primária;
* `TITULO` — Título da vaga;
* `EMPRESA` — Empresa responsável;
* `SALARIO` — Salário oferecido.

### 👩 CANDIDATAS

Armazena os dados das candidatas:

* `ID_CANDIDATA` — Chave primária;
* `NOME` — Nome da candidata;
* `EMAIL` — E-mail da candidata.

### 📋 CANDIDATURAS

Tabela associativa responsável por relacionar candidatas e vagas:

* `ID_CANDIDATURA` — Chave primária;
* `DATA_ENVIO` — Data e hora da candidatura;
* `ID_VAGA` — Chave estrangeira relacionada à tabela `VAGAS`;
* `ID_CANDIDATA` — Chave estrangeira relacionada à tabela `CANDIDATAS`.

A tabela `CANDIDATURAS` resolve o relacionamento **Muitos-para-Muitos (N:N)** entre candidatas e vagas.

## ⚙️ Funcionalidades

O sistema possui as seguintes operações:

### ➕ Create

* Cadastrar uma vaga;
* Cadastrar uma candidata;
* Enviar uma candidatura.

### 🔎 Read

* Consultar candidaturas utilizando **dois `INNER JOINs`**, exibindo:

  * Nome da candidata;
  * E-mail;
  * Título da vaga;
  * Empresa de destino.

### ✏️ Update

* Atualizar o salário de uma vaga existente.

### 🗑️ Delete

* Cancelar uma candidatura, removendo o registro da tabela `CANDIDATURAS`.

As funcionalidades CRUD são implementadas em C# por meio do pacote **`Microsoft.Data.Sqlite` versão 8.0.11**.

## 🔄 Simulação do Sistema

Durante a integração, o sistema realiza a seguinte jornada:

1. Cadastra a vaga **Engenheira de Dados**, da Empresa Alfa, com salário de **R$ 9.000**.
2. Cadastra a vaga **Analista de BI**, da Empresa Ômega, com salário de **R$ 7.500**.
3. Cadastra a candidata **Mariana Souza**.
4. Realiza a candidatura de Mariana nas duas vagas.
5. Consulta as candidaturas cadastradas.
6. Atualiza o salário da vaga de Engenheira de Dados para **R$ 9.500**.
7. Cancela a candidatura de Mariana para Analista de BI.
8. Realiza uma nova consulta para confirmar que apenas a candidatura para **Engenheira de Dados** permanece ativa.

## 🛠️ Tecnologias utilizadas

* **C#**
* **ADO.NET**
* **SQLite**
* **SQL**
* **Microsoft.Data.Sqlite 8.0.11**
* **Google Colab**
* **DBeaver**
* **GitHub**

## 📦 Entregáveis

O projeto conta com:

* 📓 Notebook do Google Colab (`.ipynb`) contendo o código C#;
* 🗄️ Banco de dados final `vagas_tech.db`;
* 📄 Arquivo `DDL_Criacao.sql` com os comandos utilizados para criação das tabelas;
* 💻 Código da aplicação desenvolvido em C#.

Esses arquivos compõem os principais entregáveis solicitados para o repositório do projeto.

## 🤝 Trabalho em Squad

O desenvolvimento foi realizado de forma colaborativa, envolvendo a criação da estrutura do banco, desenvolvimento das operações CRUD, integração entre C# e SQLite e validação dos dados.

O projeto permitiu colocar em prática conceitos de **banco de dados relacional, persistência de dados, SQL e desenvolvimento em equipe**, desde a criação das tabelas até a validação final dos dados armazenados no banco.
