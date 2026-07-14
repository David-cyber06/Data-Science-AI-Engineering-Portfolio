# 🤖 Customer Churn Prediction using Machine Learning

### Telco Customer Churn Prediction (XGBoost vs Random Forest vs Logistic Regression)

![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB?logo=python\&logoColor=white)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Machine%20Learning-F7931E?logo=scikitlearn\&logoColor=white)
![XGBoost](https://img.shields.io/badge/XGBoost-Gradient%20Boosting-success)
![Random Forest](https://img.shields.io/badge/Random%20Forest-Ensemble%20Learning-green)
![EDA](https://img.shields.io/badge/EDA-Exploratory%20Data%20Analysis-orange)
![Classification](https://img.shields.io/badge/Machine%20Learning-Classification-blue)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)
![License](https://img.shields.io/badge/License-MIT-green)

---

# 📌 Proyecto de Portafolio para Machine Learning y Customer Analytics

Este proyecto fue desarrollado para demostrar competencias en Machine Learning supervisado, clasificación binaria, evaluación de modelos, optimización de hiperparámetros y análisis de retención de clientes.

El objetivo consiste en predecir qué clientes tienen mayor probabilidad de cancelar el servicio (*customer churn*), permitiendo a la empresa implementar estrategias preventivas de retención.

El proyecto parte del dataset previamente limpiado y analizado durante la fase de Exploratory Data Analysis (EDA), enfocándose exclusivamente en el ciclo completo de modelado predictivo.

### Competencias demostradas

✅ Machine Learning Supervisado

✅ Clasificación Binaria

✅ Feature Engineering

✅ Model Evaluation

✅ Hyperparameter Tuning

✅ Cross Validation

✅ Ensemble Learning

✅ XGBoost

✅ Random Forest

✅ Customer Analytics

✅ Business Impact Analysis

---

# 🎯 Resumen Ejecutivo

La pérdida de clientes representa uno de los principales desafíos para empresas de telecomunicaciones y negocios basados en suscripciones.

En este proyecto se desarrollaron múltiples modelos de Machine Learning para identificar clientes con riesgo de abandono utilizando información histórica de comportamiento, facturación y permanencia.

Se evaluaron distintos algoritmos de clasificación y posteriormente se optimizaron los modelos con mejor desempeño mediante GridSearchCV y validación cruzada.

Finalmente, XGBoost obtuvo el mejor rendimiento general, alcanzando un **ROC-AUC de 0.8350 en el conjunto de prueba**, demostrando una buena capacidad para distinguir entre clientes que abandonan el servicio y aquellos que permanecen activos.

---

# 🏢 Problema de Negocio

Retener clientes suele ser considerablemente más económico que adquirir nuevos.

Por esta razón, las empresas buscan responder preguntas como:

* ¿Qué clientes tienen alta probabilidad de abandonar el servicio?
* ¿Cuáles son los principales factores asociados al churn?
* ¿Qué tan preciso puede ser un modelo predictivo?
* ¿Qué segmentos deberían recibir campañas de retención?
* ¿Cómo reducir pérdidas de ingresos futuras?

Este proyecto busca proporcionar una solución basada en Machine Learning para apoyar dichas decisiones.

---

# 📊 Dataset

## Fuente

Telco Customer Churn Dataset

## Variables Analizadas

### Variables Numéricas

* tenure
* MonthlyCharges
* TotalCharges
* SeniorCitizen

### Variables Categóricas

* gender
* Partner
* Dependents
* PhoneService
* MultipleLines
* InternetService
* OnlineSecurity
* OnlineBackup
* DeviceProtection
* TechSupport
* StreamingTV
* StreamingMovies
* Contract
* PaperlessBilling
* PaymentMethod

### Variable Objetivo

```text id="a1f93m"
Churn
0 = Cliente permanece
1 = Cliente abandona
```

---

# 📈 Resultados del Negocio

| KPI                 | Valor   |
| ------------------- | ------- |
| Clientes Analizados | 7,043   |
| Clientes Perdidos   | 1,869   |
| Tasa de Churn       | 26.54%  |
| Tasa de Retención   | 73.46%  |
| Modelos Evaluados   | 6       |
| Mejor Modelo        | XGBoost |
| ROC-AUC Final       | 0.8350  |

---

# 🧠 Metodología de Machine Learning

## 1. Exploración de Datos

Antes del modelado se realizó:

* Análisis exploratorio (EDA)
* Validación de variables
* Identificación de desbalance de clases
* Análisis de distribuciones
* Análisis de correlaciones

---

## 2. Preparación de Datos

Se realizaron los siguientes procesos:

### Variables Numéricas

* Selección de variables relevantes
* Escalamiento cuando fue requerido

### Variables Categóricas

* Codificación mediante pipelines
* Transformación para compatibilidad con modelos

### División de Datos

Se aplicó una estrategia de separación estratificada:

* Train
* Validation
* Test

Garantizando una evaluación robusta del desempeño.

---

## 3. Construcción de Pipelines

Se implementaron pipelines utilizando Scikit-Learn para garantizar reproducibilidad y evitar fuga de información (*data leakage*).

---

## 4. Entrenamiento de Modelos

Se entrenaron y compararon seis algoritmos diferentes:

### K-Nearest Neighbors (KNN)

Modelo basado en proximidad entre observaciones.

### Logistic Regression

Modelo lineal ampliamente utilizado como baseline en clasificación.

### Decision Tree

Modelo interpretable basado en reglas de decisión.

### Support Vector Machine (SVC)

Clasificador basado en hiperplanos de separación.

### Random Forest

Método ensemble basado en múltiples árboles de decisión.

### XGBoost

Algoritmo de Gradient Boosting reconocido por su alto desempeño en problemas tabulares.

---

## 5. Evaluación de Modelos

Los modelos fueron evaluados utilizando:

* Accuracy
* Precision
* Recall
* F1 Score
* Specificity
* ROC Curve
* ROC-AUC

---

# 🏆 Comparación de Modelos

## Modelos Evaluados

| Modelo              | Accuracy (Validation) |
| ------------------- | --------------------- |
| KNN                 | 0.764                 |
| Logistic Regression | 0.825                 |
| Decision Tree       | 0.783                 |
| SVC                 | 0.807                 |
| Random Forest       | 0.800                 |
| XGBoost             | Modelo Final          |

Durante la comparación inicial, Logistic Regression y XGBoost mostraron el mejor equilibrio entre capacidad predictiva y generalización.

---

# 📈 Optimización de Modelos

## Logistic Regression

Se realizó búsqueda de hiperparámetros utilizando:

* GridSearchCV
* Validación Cruzada (5 folds)

### Mejores hiperparámetros

```python id="w94x2n"
{
    "C": 1,
    "penalty": "l1",
    "solver": "saga"
}
```

### Resultado

```text id="e7kq3p"
ROC-AUC TEST = 0.8326
```

---

## XGBoost

Se optimizó mediante GridSearchCV evaluando:

* learning_rate
* max_depth
* n_estimators
* subsample
* colsample_bytree
* reg_alpha
* reg_lambda

### Mejores hiperparámetros

```python id="x82mz4"
{
    "learning_rate": 0.1,
    "max_depth": 3,
    "n_estimators": 100,
    "subsample": 1.0,
    "colsample_bytree": 0.8,
    "reg_alpha": 0.1,
    "reg_lambda": 1
}
```

### Resultado

```text id="h7n1zb"
ROC-AUC TEST = 0.8350
```

---

# 🥇 Modelo Seleccionado

## XGBoost

### Razones de selección

* Mejor ROC-AUC final.
* Excelente capacidad de generalización.
* Buen balance entre sensibilidad y precisión.
* Alto desempeño en datasets tabulares.

### Métrica Principal

| Métrica      | Valor  |
| ------------ | ------ |
| ROC-AUC Test | 0.8350 |

---

# 📊 Flujo del Proyecto

```text id="q82mda"
Datos Limpios
      │
      ▼
Análisis Exploratorio
      │
      ▼
Preparación de Variables
      │
      ▼
Train / Validation / Test
      │
      ▼
Entrenamiento de Modelos
      │
      ▼
Evaluación
      │
      ▼
Optimización de Hiperparámetros
      │
      ▼
Selección del Mejor Modelo
```

---

# ⚙️ Tecnologías Utilizadas

| Tecnología       | Aplicación              |
| ---------------- | ----------------------- |
| Python           | Desarrollo del proyecto |
| Pandas           | Manipulación de datos   |
| NumPy            | Operaciones numéricas   |
| Matplotlib       | Visualización           |
| Seaborn          | Análisis exploratorio   |
| Scikit-Learn     | Machine Learning        |
| XGBoost          | Modelo predictivo       |
| GridSearchCV     | Optimización            |
| Jupyter Notebook | Desarrollo              |
| Git              | Versionamiento          |
| GitHub           | Portafolio profesional  |

---

# 🛠️ Competencias Técnicas Demostradas

## Machine Learning

* Binary Classification
* Model Selection
* Ensemble Learning
* Gradient Boosting
* Random Forest
* Logistic Regression

## Model Evaluation

* ROC Curve
* ROC-AUC
* Precision
* Recall
* F1 Score
* Specificity

## Model Optimization

* Hyperparameter Tuning
* GridSearchCV
* Cross Validation
* Pipeline Construction

## Data Science

* Feature Selection
* Customer Analytics
* Churn Prediction
* Business Insights

---

# 💼 Impacto de Negocio

| Área                | Beneficio                                       |
| ------------------- | ----------------------------------------------- |
| 📈 Marketing        | Identificación de clientes con alto riesgo      |
| 🤝 Customer Success | Intervención temprana para evitar cancelaciones |
| 💰 Finanzas         | Reducción de pérdidas por churn                 |
| 📊 Analytics        | Priorización de campañas de retención           |
| 🏢 Dirección        | Toma de decisiones basada en predicciones       |

---

# 📋 Principales Aprendizajes

Durante el desarrollo de este proyecto se fortalecieron habilidades en:

* Machine Learning Supervisado
* Clasificación Binaria
* Optimización de Modelos
* Cross Validation
* Evaluación de Desempeño
* XGBoost
* Random Forest
* Customer Analytics
* Interpretación de Métricas de Negocio

---

# 🎓 Relevancia para Data Science

La predicción de churn es uno de los casos de uso más comunes y valiosos dentro de Data Science aplicada al negocio.

Por esta razón, este proyecto demuestra competencias fundamentales para roles de:

* Data Analyst
* Junior Data Scientist
* Machine Learning Engineer Intern
* Applied Machine Learning Intern
* Analytics Engineer

---

# 👨‍💻 Autor

**Jhorman David Bernal Tapias**


💻 GitHub: [github.com/David-cyber06]

📧 Correo: [[Jhormandavid2000@gmail.com](mailto:Jhormandavid2000@gmail.com)]

---
