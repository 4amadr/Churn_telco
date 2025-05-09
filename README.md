# churn_telco

## Project Organization

```
├── LICENSE
├── Makefile           <- Makefile with commands like `make data` or `make train`
├── README.md          <- The top-level README for developers using this project.
├── data
│   ├── external       <- Data from third party sources.
│   ├── interim        <- Intermediate data that has been transformed.
│   ├── processed      <- The final, canonical data sets for modeling.
│   └── raw            <- The original, immutable data dump.
│
├── docs               <- A default Sphinx project; see sphinx-doc.org for details
│
├── models             <- Trained and serialized models, model predictions, or model summaries
│
├── notebooks          <- Jupyter notebooks. Naming convention is a number (for ordering),
│                         the creator's initials, and a short `-` delimited description, e.g.
│                         `1.0-jqp-initial-data-exploration`.
│
├── references         <- Data dictionaries, manuals, and all other explanatory materials.
│
├── reports            <- Generated analysis as HTML, PDF, LaTeX, etc.
│   └── figures        <- Generated graphics and figures to be used in reporting
│
├── requirements.txt   <- The requirements file for reproducing the analysis environment, e.g.
│                         generated with `pip freeze > requirements.txt`
│
├── setup.py           <- makes project pip installable (pip install -e .) so src can be imported
├── src                <- Source code for use in this project.
│   ├── __init__.py    <- Makes src a Python module
│   ├── data           <- Scripts to download or generate data
│   │   └── make_dataset.py
│   ├── features       <- Scripts to turn raw data into features for modeling
│   │   └── build_features.py
│   ├── models         <- Scripts to train models and then use trained models to make predictions
│   │   ├── predict_model.py
│   │   └── train_model.py
│   └── visualization  <- Scripts to create exploratory and results oriented visualizations
│       └── visualize.py
│
└── tox.ini            <- tox file with settings for running tox; see tox.readthedocs.io
```

<small>Project based on the <a target="_blank" href="https://drivendata.github.io/cookiecutter-data-science/">cookiecutter data science project template</a>. #cookiecutterdatascience</small>

## 📊 Projeto de Análise de Churn — Telco

Este projeto simula um cenário real em que atuamos como analistas de dados contratados pela empresa americana **Telco**, com a missão de **reduzir em 15% o índice de churn (cancelamentos de clientes)** em um período de 3 meses, por meio de campanhas personalizadas.

A análise foi realizada com base em um dataset fornecido pela companhia. Durante a exploração inicial dos dados, notamos que a coluna `Churn Reason` possuía muitos valores nulos (NaN), os quais foram interpretados como clientes que preferiram não fornecer feedback — algo que também pode indicar insatisfação.

Para manter o foco em clientes com feedback claro, os valores nulos foram substituídos por "No opinion", e foi criado um DataFrame filtrado com **1869 clientes com feedback definido**. O objetivo é aplicar análises e estratégias direcionadas para **reduzir o churn em pelo menos 280 clientes**.

## Análise Focada em Clientes Insatisfeitos com o Atendimento ao Cliente (SAC)

Durante a análise dos motivos de cancelamento, identificamos que o fator mais recorrente entre os clientes que deram feedback foi relacionado ao atendimento ao cliente (SAC), especificamente à "Attitude of support person".

### Principais insights:
- Churn Score médio: **82,04** (risco elevado de cancelamento).
- **163 clientes** com score acima de 70.
- Tempo médio de contrato: **18,75 meses**.
- Pagamento mensal médio: **$73**.
- CLTV médio: **$4164**.

Melhorar o atendimento ao cliente é uma estratégia crítica de retenção e preservação de receita.

## Análise de Clientes que Reclamaram da Velocidade da Internet

### Principais achados:
- Churn Score médio: **85,34** (ainda mais alto que SAC).
- **166 clientes** com score acima de 70.
- Tempo médio de contrato: **19,65 meses**.
- Pagamento mensal: **$74,98**.
- CLTV médio: **$4127**.

É urgente melhorar a infraestrutura de rede e divulgar os avanços como diferencial competitivo.

## Clientes que Alegaram Melhor Oferecimento de Dados pela Concorrência

### Principais insights:
- Churn Score médio: **84,69**.
- **135 clientes** com score ≥ 70.
- Tempo como cliente: **18,61 meses**.
- Pagamento mensal: **$76,91**.
- CLTV médio: **$4215**.

Recomenda-se reavaliar os planos de dados e personalizar ofertas conforme perfis de uso.

## 📊 Interpretação dos Clusters

Foram identificados **3 grupos principais** de clientes:

### 🧩 Cluster 0: "Conservadores"
- Contrato médio: **~30 meses**.
- Gasto mensal: **~R$21**.
- Estratégia: Upgrades com descontos e pacotes vantajosos.

### 👑 Cluster 1: "Fidelidade Premium"
- Tempo de contrato: **~55 meses**.
- Gasto mensal: **~R$84**.
- Estratégia: Programa de fidelidade, vantagens exclusivas.

... (continuação omitida por brevidade)