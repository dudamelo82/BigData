eja bem-vindo aos laboratórios de **Big Data**.  
Este repositório foi desenvolvido para a prática das ferramentas utilizadas nesse ecossistema.

No cenário atual de **Tecnologia da Informação e Comunicação (TIC)**, enfrentamos o desafio de armazenar e gerenciar quantidades massivas de dados — mais de **2,5 quintilhões de bytes** gerados diariamente por redes sociais, transações financeiras, sensores IoT e dispositivos conectados à internet.  

O conceito de Big Data surge em resposta a essa demanda, sendo caracterizado não apenas pelo **grande Volume**, mas também pela **Velocidade** com que os dados são gerados e processados, pela **Variedade** de formatos e fontes, pela **Veracidade** das informações e, finalmente, pelo potencial **Valor** que podem agregar quando analisados corretamente.  

Nesse contexto, as ferramentas de Big Data e os sistemas gerenciadores de bancos de dados **NoSQL (Not-only SQL)** emergem como soluções otimizadas para lidar com esses desafios.

---

## 📖 Sumário
- [BigData 🚀](#bigdata-)
  - [📖 Sumário](#-sumário)
  - [🎯 Objetivo](#-objetivo)
  - [🛠 Stack Tecnológica](#-stack-tecnológica)
  - [📂 Estrutura do Repositório](#-estrutura-do-repositório)
  - [⚡ Guia Rápido de Instalação](#-guia-rápido-de-instalação)
    - [1) Clone o projeto](#1-clone-o-projeto)
    - [2) Suba os containers](#2-suba-os-containers)
    - [3) Acesse os serviços](#3-acesse-os-serviços)
  - [📓 Uso dos Notebooks](#-uso-dos-notebooks)
  - [🗄 Banco de Dados MongoDB](#-banco-de-dados-mongodb)
  - [✅ Boas Práticas](#-boas-práticas)
  - [🖼 Imagens e Diagramas](#-imagens-e-diagramas)
    - [Exemplo — Arquitetura do Ambiente](#exemplo--arquitetura-do-ambiente)
    - [Exemplo — Jupyter em execução](#exemplo--jupyter-em-execução)
  - [🤝 Contribuindo](#-contribuindo)
  - [📜 Licença](#-licença)

---

## 🎯 Objetivo
Este projeto foi criado para servir como um **ambiente de estudos em Big Data**, facilitando:
- Execução de **notebooks interativos** para análise e manipulação de dados.
- Criação de pipelines simples de ingestão, transformação e armazenamento.
- Exploração de bancos NoSQL (**MongoDB**) aplicados a cenários de Big Data.

---

## 🛠 Stack Tecnológica
- **Docker** + **Docker Compose** — orquestração e isolamento do ambiente.  
- **Jupyter Lab** — desenvolvimento e testes em notebooks.  
- **MongoDB** — banco de dados NoSQL para persistência.  
- **Python 3.11+** — base para scripts e bibliotecas de análise.

---

## 📂 Estrutura do Repositório
```

BigData/
├─ jupyter/           # Notebooks de análise e exemplos práticos
├─ mongodb/           # Configurações, seeds e scripts para MongoDB
├─ docs/              # (opcional) Documentação estendida
├─ assets/            # Imagens e diagramas usados no README
├─ docker-compose.yml # Orquestração dos serviços
├─ requirements.txt   # Dependências Python
└─ README.md          # Este documento

````

---

## ⚡ Guia Rápido de Instalação

### 1) Clone o projeto
```bash
git clone https://github.com/dudamelo82/BigData.git
cd BigData
````

### 2) Suba os containers

```bash
docker compose up -d
```

### 3) Acesse os serviços

* **Jupyter Lab**: URL e token aparecem no log

  ```bash
  docker compose logs jupyter -f
  ```
* **MongoDB**: disponível em `mongodb://localhost:27017`

---

## 📓 Uso dos Notebooks

1. Acesse o Jupyter Lab (link nos logs do container).
2. Abra um dos notebooks na pasta `jupyter/`.
3. Execute as células em sequência.

> **Dica:** mantenha os outputs limpos ao versionar (`Kernel > Restart & Clear Output`).

---

## 🗄 Banco de Dados MongoDB

* Conexão via variável de ambiente `MONGODB_URI`.
* Exemplo em Python:

```python
from pymongo import MongoClient

client = MongoClient("mongodb://localhost:27017")
db = client["bigdata"]
col = db["leituras"]
```

* Scripts auxiliares estão em `mongodb/`.

---

## ✅ Boas Práticas

* Não versione credenciais (use `.env`).
* Dados grandes devem ficar fora do Git — prefira amostras pequenas para testes.
* Estruture datasets em:

  ```
  data/
  ├─ raw/        # Dados brutos
  ├─ staging/    # Dados transformados
  └─ processed/  # Dados prontos para análise
  ```



## 🤝 Contribuindo

1. Faça um fork do projeto.
2. Crie uma branch: `git checkout -b feature/minha-feature`.
3. Commit suas alterações: `git commit -m 'feat: adiciona minha feature'`.
4. Envie para o fork: `git push origin feature/minha-feature`.
5. Abra um Pull Request.

---
