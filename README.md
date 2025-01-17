Template
==============================

Template do CookieCutter

Project Organization
------------

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
    │   │
    │   ├── data           <- Scripts to download or generate data
    │   │   └── make_dataset.py
    │   │
    │   ├── features       <- Scripts to turn raw data into features for modeling
    │   │   └── build_features.py
    │   │
    │   ├── models         <- Scripts to train models and then use trained models to make
    │   │   │                 predictions
    │   │   ├── predict_model.py
    │   │   └── train_model.py
    │   │
    │   └── visualization  <- Scripts to create exploratory and results oriented visualizations
    │       └── visualize.py
    │
    └── tox.ini            <- tox file with settings for running tox; see tox.readthedocs.io


--------

<p><small>Project based on the <a target="_blank" href="https://drivendata.github.io/cookiecutter-data-science/">cookiecutter data science project template</a>. #cookiecutterdatascience</small></p>



# Projeto
- Projeto de clusterização utilizando K-Means
 - Clusterização de clientes e criação de métricas e procedimentos para avaliar e melhorar a experiência de compra de cliente valiosos.

# Contextualização

Há um risco grande ruptura de clientes que são considerados valiosos para o negócio quando há uma recorrência de experiências negativas comprando na plataforma Olist. Nesse projeto há uma proposta de clusterização de clientes que agregam maior valor para o negócio.

Além disso, a fim de diminuir a probabilidade de ruptura de compras efetuadas pelos clientes de maior valor na plataforma realizou-se uma análise de dados com objetivo de listar os fornecedores e produtos que causam maiores experiencias negativas para os clientes de maior valor para o negócio.

Entende-se como uma experiência negativa a compra de um produto que não corresponde as expectativas do cliente.

# Repositorio

- Clusterização e analise de dados.ipynb - Notebook para EDA e desenvolvimento em ML

# Objetivos:

1) Criar um modelo de agrupamento de clientes a fim de identificar os clientes de maior valor para o negócio;  
2) Aplicar metodos para inferir a avaliação de produtos por fornecedor a a partir da resposta do questionário de avaliação de pedidos;  
3) Entre os clientes de maiores valores realizar o levantar do número de ocorrências de baixas avaliações com a fim de identificar o conjunto agressor produto-fornecedor
4) Otimizar as operações de notificações ao conjunto produtos-fornecedores, propondo uma metodologia para priorização, utilizando, para isso dados de preço unitário de produtos por fornecedor e da relação Frete/distancia cliente-fornecedor;  

 
 # Fonte de dados
 
 https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce
 
# Conclusões resumidas

Os clientes de maior valor para o negócio foram agrupados utilizando o algorítimo KMEANS considerando a frequencia de compra, o numero total de transações e o valor monetário total das transações. O processo de agrupamento foi orientado pelo método de Elbow que retornou 4 agrupamentos, sendo:

0: Clientes que efetuaram uma única compra de baixo valor monetário;
1: Clientes que realizaram mais de uma compra num período espaçado com valor de compra intermediário;
2: Clientes que realizaram mais de uma compra num período espaçado maior e com valor de compra maior em relação ao agrupamento 1;
3: Clientes que efetuaram uma única compra de alto valor monetário;


Os clientes de maior valor foram identificados com os rótulos 2 e 3.

Ao final do projeto, é realizado uma análise de dados robusta, listando-se os fornecedores e produtos que mais causam experiencias negativas aos clientes de maior valor para o negócio. É feita uma recomendação para que hajam notificações priorizando os produtos que:

1) Tiveram menores notas na avaliação;  
2) Tiveram maiores ocorrências de baixa avaliação;  
3) Possui elevado valor unitário, pois quanto maior o valor unitário maior a decepção do cliente;  
4) Possui elevado valor de Frete/Distância cliente-fornecedor uma vez que é maior o custo logistico nessas operações 



# Melhorias, recomendações e gaps do projeto

A da clusterização de clientes e análise de dados proposto nesse projeto é possível aprimorar os algorítimos de recomendação a fim de priorizar fornecedores que possuam produtos equivalentes cuja avaliações de produtos estejam conforme os padrões.

# Stack
Scikit-Learn, Pandas, Numpy, Seaborn, Matplotlib
