# 🦠 Flu Shot Learning — Prevendo Vacinação H1N1 e Sazonal  
**Projeto de Machine Learning | Competição DivenData**

Este projeto tem como objetivo prever a probabilidade de uma pessoa ter tomado as vacinas **H1N1** e **Sazonal**, utilizando técnicas completas de Data Science aplicadas ao dataset disponibilizado pela competição da **DivenData**.

---

## 🎯 Objetivo do Projeto

Construir um pipeline de Machine Learning capaz de:

- Realizar limpeza e tratamento dos dados  
- Criar novas variáveis relevantes (feature engineering)  
- Selecionar os melhores atributos para cada previsão  
- Testar diferentes modelos  
- Ajustar hiperparâmetros (hyperparameter tuning)  
- Construir predições finais  
- Gerar o arquivo oficial de submissão no formato solicitado pela DivenData

---

## 📂 Estrutura do Projeto

├── data/

│ ├── train_set.csv

│ ├── test_set_features.csv

│ └── submission_format.csv

├── notebooks/

│ └── flu_shot_learning.ipynb

├── README.md

└── requirements.txt


---

## 🧹 Preparação dos Dados

As etapas de transformação incluíram:

### ✔ Tratamento de valores ausentes  
- Mediana para variáveis numéricas  
- Moda para variáveis categóricas  

### ✔ Conversão de tipos  

### ✔ Criação de novas features
- `family_size`  
- `education_level_num`  
- `health_behaviors_score`  
- `risk_awareness_score`  
- `opinion_gap`

### ✔ Normalização e Padronização  
- `StandardScaler` para variáveis de percepção  
- `MinMaxScaler` para variáveis contínuas  

### ✔ Codificação categórica  
- One-hot encoding (`get_dummies`)  

---

## 🔎 Seleção de Features

A seleção foi realizada utilizando:

- Random Forest  
- LightGBM  
- ExtraTrees  
- Ranking por importância de features  
- Validação cruzada  

Isso gerou dois conjuntos finais:

- **Features para prever H1N1**  
- **Features para prever Vacina Sazonal**

---

## 🤖 Modelos Testados

Foram testados e comparados:

- **Logistic Regression**  
- **Random Forest**  
- **LightGBM (modelo final escolhido)**  

O LightGBM apresentou o melhor desempenho geral.

---

## 🔧 Tuning de Hiperparâmetros

Utilizado:

```python
RandomizedSearchCV(
    estimator=LGBMClassifier(),
    param_distributions=param_grid,
    n_iter=50,
    scoring='roc_auc',
    cv=5,
    random_state=42
)
```

🏆 Resultados Obtidos
| 🔬 Modelo | 🦠 H1N1 (AUC) | 🤧 Gripe Sazonal (AUC) |
|----------|--------------|------------------------|
| Logistic Regression | 0.8447 | 0.8436 |
| Random Forest | 0.8075 | 0.8061|
| LightGBM | 0.8448 | 0.8475 |


📈 Tecnologias Utilizadas

Python

Pandas / NumPy

Scikit-Learn

LightGBM

Matplotlib / Seaborn

Jupyter Notebook

👨‍💻 Autor

Tiago Barros
Estudante de Big Data | Cientista de Dados em formação

FATEC Ipiranga · São Paulo, Brasil
