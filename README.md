## 🧠 Predição de Doença Cardíaca com Machine Learning  
**Aluno:** Cauê Reis
**Disciplina:** Inteligência Artificial e Aprendizado de Máquina Supervisionado  

---

## 📌 Sobre o Projeto

Este repositório contém o projeto final da disciplina de **IA e Aprendizado de Máquina Supervisionado**, cujo objetivo é construir e comparar diferentes modelos de classificação para prever a presença de **doença cardíaca** com base em atributos clínicos.

O trabalho envolve:

- Análise exploratória inicial do dataset  
- Tratamento e padronização dos dados  
- Construção de múltiplos modelos supervisionados  
- Comparação de métricas  
- Seleção do melhor classificador  
- Salvamento do modelo final em **pickle (.pkl)**  

---

## 🗂️ Dataset

O dataset contém informações clínicas como:

- Idade  
- Sexo  
- Pressão arterial  
- Colesterol  
- Freq. cardíaca máxima  
- Tipo de dor no peito  
- Eletrocardiograma em repouso  
- Inclinação do segmento ST  
- Indicadores binários sobre esforço físico  
- Presença ou não da doença cardíaca (variável alvo)

---

## 🔧 Processamento dos Dados

As etapas principais incluem:

- Remoção de valores inválidos (`RestingBP == 0`)
- Imputação inteligente para colunas com valores faltantes
- Codificação de variáveis categóricas (One-Hot Encoding)
- Padronização de variáveis numéricas (StandardScaler)
- Separação das colunas em **numéricas** e **categóricas**

---

## 🤖 Modelos Treinados

Foram avaliados os seguintes modelos:

- **Logistic Regression**  
- **Random Forest**  
- **Gradient Boosting**  
- **SVM com kernel RBF**  
- **KNN**

Cada modelo foi construído usando um **Pipeline**, contendo:

- Preprocessamento automático  
- Modelo escolhido  
- Métricas de avaliação  

---

## 📊 Métricas de Avaliação

As principais métricas calculadas foram:

- **Accuracy**
- **F1-score**
- **ROC-AUC**
- **Precisão e Recall por classe**
- **Matriz de confusão**

O foco está na classe **1** (pacientes com doença cardíaca), por ser mais crucial clinicamente.

---

## 🏆 Melhor Modelo

Após comparação completa, o modelo com melhor desempenho foi:

# ⭐ **SVM-RBF**

### Destaques:
- **ROC-AUC = 0.943**  
- **F1 = 0.900**  
- Excelente sensibilidade na classe positiva (**R1 = 0.922**)

O modelo é, portanto, o mais adequado para aplicações de predição de risco cardíaco neste dataset.

---

## 💾 Salvando e Carregando o Modelo

O melhor modelo é salvo em formato pickle:

```python
joblib.dump(modelo, "modelo_SVM-RBF.pkl")
```

Para carregar posteriormente:

```python
modelo = joblib.load("modelo_SVM-RBF.pkl")
```

---

## 📁 Arquivos do Repositório

- `notebook.ipynb` — Notebook principal do projeto  
- `comparacao_modelos.csv` — Tabela com métricas de todos os modelos  
- `modelo_*.pkl` — Modelos treinados  
- `README.md` — Este arquivo  

---

## 🚀 Como Executar

1. Instale as dependências necessárias:  
   ```bash
   pip install scikit-learn joblib
   ```

2. Abra o notebook:  
   ```bash
   jupyter notebook
   ```

3. Execute todas as células, incluindo a parte de comparação de modelos e salvamento do melhor classificador.

---
