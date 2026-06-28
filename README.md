# 🚀 Banco API Performance Tests

## 📌 Introdução

Este repositório contém a suíte de testes de performance para a API do Banco, utilizando a ferramenta **K6**. O objetivo é validar a resiliência, escalabilidade e tempo de resposta dos endpoints críticos da aplicação, sob diferentes cargas de usuários simulados.

Os testes são escritos em **JavaScript** e seguem boas práticas de organização, reutilização de código e parametrização via variáveis de ambiente.

---

## 🛠 Tecnologias utilizadas

- **[K6](https://k6.io/)** – Ferramenta open-source para testes de carga e performance.
- **JavaScript** – Linguagem utilizada para escrever os scripts de teste.
- **Node.js** (opcional) – Para gerenciamento de pacotes e execução de scripts auxiliares.
- **Git** – Controle de versionamento.

---

## 📂 Estrutura do repositório
banco-api-performance/
├── congig/
│ ├── config.local.json # Arquivo de configuração
├── fixtures/
│ ├── postLogin.json # Dados de login
├── helpers/
│ ├── autenticacao.js # Auxiliar para obter token em endpoints que utilizam autenticacao
├── tests/
│ ├── login.test.js # Testes endpoint de login
│ ├── transferencias.test.js # Testes endpoint de transferências
├── utils/ 
├── variaveis.js # Variáveis de ambiente
├── .gitignore
└── README.md # Este arquivo

## 🎯 Objetivo de cada grupo de arquivos

| Pasta/Arquivo       | Objetivo |
|---------------------|----------|
| `tests/`            | Contém os scripts de teste organizados por endpoint. |
| `helpers/`          | Funções compartilhadas entre os testes. |
| `config/`           | Configuração. |
| `fixtures/`         | Dados utilizados. |
| `utils`             | Modelo para definir variáveis de ambiente necessárias. |

---

## ⚙️ Modo de instalação
Pré-requisitos

É necessário possuir instalado:

Node.js
npm
K6

Caso ainda não possua o K6 instalado, consulte a documentação oficial:

https://grafana.com/docs/k6/latest/set-up/install-k6/

Clonando o projeto
git clone https://github.com/kafilipe/banco-api-performance.git

Entre na pasta do projeto:

cd banco-api-performance

Instale as dependências:

npm install

---

## ▶️ Modo de execução
Execução padrão (com variável de ambiente)
Para rodar um teste específico, utilize o comando:

k6 run tests/smoke-test.js -e BASE_URL=$BASE_URL

---

## 📊 Acompanhamento do relatório em tempo real e exportação
O K6 permite a geração de um dashboard web interativo e a exportação automática do relatório em HTML, utilizando variáveis de ambiente próprias da ferramenta.

Exemplo de comando com dashboard e exportação:
K6_WEB_DASHBOARD=true \
K6_WEB_DASHBOARD_EXPORT=html-report.html \
k6 run tests/load-test.js -e BASE_URL=$BASE_URL

Autor: Karina Filipe
Repositório: banco-api-performance
