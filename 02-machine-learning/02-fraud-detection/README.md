# 🛡️ Credit Card Fraud Detection using Machine Learning

### XGBoost (UnderSampling vs SMOTE) vs Neural Networks

![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB?logo=python&logoColor=white)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Machine%20Learning-F7931E?logo=scikitlearn&logoColor=white)
![XGBoost](https://img.shields.io/badge/XGBoost-Gradient%20Boosting-success)
![TensorFlow](https://img.shields.io/badge/TensorFlow-Deep%20Learning-FF6F00)
![SMOTE](https://img.shields.io/badge/SMOTE-Class%20Balancing-blue)
![EDA](https://img.shields.io/badge/EDA-Exploratory%20Data%20Analysis-orange)
![Classification](https://img.shields.io/badge/Machine%20Learning-Classification-blue)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

---

# 📌 Descripción del Proyecto

Este proyecto consiste en el desarrollo de modelos de Machine Learning para la detección de fraude en transacciones con tarjetas de crédito.

Se implementaron distintas estrategias para abordar el fuerte desbalance de clases presente en el dataset, comparando múltiples técnicas de balanceo y diferentes algoritmos de clasificación.

El objetivo principal fue construir un sistema capaz de identificar transacciones fraudulentas minimizando la cantidad de falsas alarmas y maximizando la capacidad de detección.

---

# 🎯 Objetivos del Proyecto

- Analizar un dataset altamente desbalanceado de fraude financiero.
- Implementar técnicas de balanceo de clases.
- Comparar diferentes estrategias de entrenamiento.
- Evaluar modelos mediante métricas adecuadas para problemas desbalanceados.
- Comparar modelos basados en árboles y redes neuronales.
- Seleccionar la mejor solución para detección de fraude.

---

# 📊 Dataset

## Fuente

Credit Card Fraud Detection Dataset

## Variable Objetivo

```text
Class
0 = Transacción legítima
1 = Transacción fraudulenta
```

## Características del Dataset

- Más de 280.000 transacciones.
- Variables anonimizadas mediante PCA.
- Variables Time y Amount.
- Problema altamente desbalanceado.
- Solo aproximadamente 0.17% de las observaciones corresponden a fraude.

---

# 📈 Resumen del Problema

La detección de fraude financiero representa uno de los principales desafíos dentro del sector bancario y de pagos digitales.

Los sistemas tradicionales basados en reglas suelen generar una gran cantidad de falsos positivos o perder eventos de fraude importantes.

Por ello, Machine Learning permite construir modelos capaces de identificar patrones complejos asociados a transacciones fraudulentas.

---

# 🔍 Análisis Exploratorio de Datos (EDA)

Se realizó un análisis exploratorio para comprender la estructura del dataset:

### Actividades realizadas

- Análisis de la variable objetivo.
- Evaluación del desbalance de clases.
- Verificación de valores faltantes.
- Distribución de variables.
- Matriz de correlación.
- Identificación de patrones relevantes.

### Principales Hallazgos

- El dataset presenta un desbalance extremo.
- Las transacciones fraudulentas representan menos del 1% del total.
- Algunas variables presentan relaciones importantes con la variable objetivo.

---

# ⚙️ Preparación de Datos

## División del Dataset

Se utilizó una estrategia de separación en:

- Training Set
- Validation Set
- Test Set

Esto permitió realizar selección de modelos sin contaminar la evaluación final.

---

# ⚖️ Balanceo de Clases

Debido al fuerte desbalance del dataset se implementaron tres estrategias:

## 1. UnderSampling

Reducción de la clase mayoritaria para equilibrar el conjunto de entrenamiento.

### Ventajas

- Entrenamiento rápido.
- Dataset balanceado.

### Desventajas

- Pérdida significativa de información.

---

## 2. SMOTE (5000 / 5000)

Generación sintética de ejemplos de fraude hasta alcanzar una distribución balanceada controlada.

---

## 3. SMOTE Full

Generación sintética utilizando toda la información disponible de la clase minoritaria.

Esta estrategia produjo los mejores resultados.

---

# 🤖 Modelos Entrenados

## Modelo 1

### XGBoost + UnderSampling

Primer modelo de referencia para evaluar el efecto del balanceo mediante reducción de la clase mayoritaria.

---

## Modelo 2

### XGBoost + SMOTE (5000/5000)

Modelo entrenado utilizando una estrategia de balanceo sintético moderada.

---

## Modelo 3

### XGBoost + SMOTE Full

Modelo entrenado utilizando la estrategia de balanceo más completa.

---

## Modelo 4

### Red Neuronal Multicapa

Arquitectura Deep Learning desarrollada para comparar su desempeño frente a los modelos basados en árboles.

---

# 📏 Métricas Utilizadas

Dado el fuerte desbalance de clases, se utilizaron múltiples métricas de evaluación:

- Accuracy
- Precision
- Recall
- F1 Score
- Specificity
- ROC Curve
- ROC-AUC
- Precision-Recall Curve
- Average Precision (AP)

---

# 📊 Comparación de Modelos

| Modelo | AP | ROC-AUC |
|----------|----------|----------|
| XGBoost UnderSampling | 0.60 | 0.97 |
| XGBoost SMOTE (5000/5000) | 0.78 | 0.99 |
| XGBoost SMOTE Full | **0.86** | **0.98** |
| Red Neuronal | 0.75 | 0.97 |

---

# 📈 Curvas Precision-Recall

![Precision Recall Curve](images/pr_curve_comparison.png)

### Interpretación

La métrica Average Precision (AP) mostró diferencias importantes entre los modelos.

El modelo XGBoost entrenado con SMOTE Full obtuvo el mejor desempeño, manteniendo una precisión elevada incluso para altos niveles de recall.

Esto resulta especialmente relevante en problemas de fraude debido al fuerte desbalance de clases.

---

# 📉 Curvas ROC

![ROC Curve](images/roc_curve_comparison.png)

### Interpretación

Todos los modelos presentaron una excelente capacidad de discriminación.

Sin embargo, la métrica ROC-AUC resultó menos sensible para distinguir el impacto real del balanceo de clases.

Por esta razón se complementó con el análisis mediante Precision-Recall.

---

# 🏆 Modelo Ganador

## XGBoost + SMOTE Full

### Resultados Finales

| Métrica | Valor |
|----------|----------|
| Average Precision (AP) | **0.86** |
| ROC-AUC | **0.98** |

### Razones de Selección

- Mejor Average Precision.
- Excelente ROC-AUC.
- Menor cantidad de falsos positivos.
- Mejor equilibrio entre Precision y Recall.
- Mayor robustez frente al desbalance de clases.

---

# 📋 Conclusiones

Los resultados demostraron que las estrategias de balanceo tienen un impacto significativo en el desempeño de los modelos de detección de fraude.

### Hallazgos principales

- UnderSampling produjo una pérdida importante de información.
- Los modelos entrenados con SMOTE superaron ampliamente al UnderSampling.
- La Red Neuronal mostró buen desempeño general, pero fue superada por XGBoost.
- XGBoost combinado con SMOTE Full obtuvo el mejor equilibrio entre capacidad de detección y reducción de falsas alarmas.

En consecuencia, el modelo seleccionado para despliegue sería **XGBoost + SMOTE Full**.

---

# 🛠️ Tecnologías Utilizadas

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-Learn
- XGBoost
- Imbalanced-Learn (SMOTE)
- TensorFlow / Keras
- Jupyter Notebook
- Git
- GitHub

---

# 💼 Competencias Demostradas

## Data Science

- Exploratory Data Analysis (EDA)
- Feature Analysis
- Data Preprocessing
- Class Imbalance Handling

## Machine Learning

- Binary Classification
- Fraud Detection
- Ensemble Learning
- Gradient Boosting
- Neural Networks

## Model Evaluation

- Precision
- Recall
- F1 Score
- Specificity
- ROC-AUC
- Precision-Recall Analysis
- Average Precision

---

# 🎓 Aplicaciones

Este proyecto es representativo de problemas reales en:

- FinTech
- Bancos
- Sistemas de Pago
- Gestión de Riesgo
- Detección de Fraude
- Ciberseguridad Financiera

---

## 👨‍💻 Autor

**Jhorman David Bernal Tapias**  
Biochemical Engineering Student | Data Science & Machine Learning Portfolio

Proyecto desarrollado con fines educativos y de portafolio profesional.
