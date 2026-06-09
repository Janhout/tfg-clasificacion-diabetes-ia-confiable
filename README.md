# TFG – Clasificación multiclase de diabetes con cuantificación de la incertidumbre

## Descripción

Este repositorio contiene el código y los artefactos experimentales correspondientes al Trabajo de Fin de Grado (TFG) centrado en el desarrollo de un sistema de clasificación multiclase para la predicción de distintos estadios de la diabetes.

Además del entrenamiento de modelos de aprendizaje automático, se incorporan técnicas de cuantificación de la incertidumbre basadas en Predicción Conforme, con el objetivo de evaluar no solo el rendimiento del modelo, sino también la fiabilidad de sus predicciones.

---

## Metodología

El trabajo se organiza en dos fases principales:

### 1. Análisis exploratorio y modelado

- Análisis exploratorio de los datos (EDA)
- Preprocesamiento de variables
- Entrenamiento de modelos de clasificación:
  - Regresión Logística
  - K-Nearest Neighbors
  - Random Forest
  - XGBoost
- Optimización de hiperparámetros mediante Optuna
- Evaluación mediante métricas:
  - Accuracy
  - Balanced Accuracy
  - F1-score
  - LogLoss

---

### 2. Cuantificación de la incertidumbre mediante Predicción Conforme

Se aplican métodos orientados a la generación de conjuntos de predicción:

- Inductive Conformal Prediction (ICP)
- Mondrian Conformal Prediction
- Adaptive Prediction Sets (APS)
- Regularized Adaptive Prediction Sets (RAPS)

Asimismo, se aplica calibración de la probabilidad mediante:

- Venn-Abers

Evaluación mediante:

- Cobertura
- Cardinalidad de los conjuntos de predicción
- Brier Score
- LogLoss
- Diagramas de fiabilidad

---

## Estructura del repositorio

``` 
TFG/
│
├── 01_EDA_y_Entrenamiento.ipynb
├── 02_Prediccion_Conforme.ipynb
│
│
├── data/diabetes_dataset.csv
│
├── artefactos/
│   ├── pipe_final.joblib
│   ├── datasets_splits.joblib
│   ├── resultados_modelos.joblib
│   └── ...
│
├── requirements_01_EDA_y_Entrenamiento.txt
├── requirements_02_Prediccion_Conforme.txt
│
└── README.md
``` 

## Notebooks

El repositorio incluye dos notebooks principales diseñados para reproducir el análisis completo:

1. `01_EDA_y_Entrenamiento.ipynb`: realiza el análisis exploratorio, preprocesamiento, entrenamiento y evaluación de modelos.
2. `02_Prediccion_Conforme.ipynb`: aplica técnicas de cuantificación de la incertidumbre utilizando los artefactos generados en el notebook anterior.

---

## Instalación

Se proporcionan dos archivos de dependencias, uno por cada notebook del proyecto.

### Notebook 1 – EDA y entrenamiento

```bash
pip install -r requirements_01_EDA_y_Entrenamiento.txt
```

### Notebook 2 – Predicción Conforme

```bash
pip install -r requirements_02_Prediccion_Conforme.txt
```

## Ejecución
Para reproducir los resultados:

Ejecutar:

- 01_EDA_y_Entrenamiento.ipynb

A continuación:

- 02_Prediccion_Conforme.ipynb

El primer notebook genera y almacena los artefactos del proceso de modelado, incluyendo el modelo final, los datos particionados y los resultados de evaluación. El segundo notebook utiliza estos artefactos para realizar el análisis de incertidumbre, generando resultados adicionales que permiten evaluar el comportamiento del modelo.

## Artefactos
Durante el proceso de entrenamiento se generan y almacenan los siguientes elementos:

- Modelo final entrenado (pipe_final.joblib)
- Conjuntos de datos particionados (datasets_splits.joblib)
- Codificador de etiquetas (label_encoder.joblib)
- Matrices de confusión (matriz_confusion_*.joblib)
- Parámetros de los modelos (parametros_modelos.json)
- Resultados de evaluación en CV (resultados_modelos_cv.joblib)
- Resultados de evaluación sobre el conjunto de test del modelo seleccionado (resultados_final_test.joblib)
- Resultados de Predicción Conforme (resultados_finales_cp.joblib)
- Datos de diagramas de fiabilidad (diagramas_fiabilidad.joblib)

Estos artefactos permiten analizar los resultados obtenidos y reproducir el flujo experimental sin necesidad de ejecutar nuevamente los notebooks.

## Reproducibilidad
Los archivos de dependencias se han construido a partir del entorno utilizado, incluyendo únicamente las librerías necesarias junto con sus versiones específicas.
Esto garantiza la reproducibilidad del sistema sin incluir dependencias innecesarias.

## Datos
El conjunto de datos utilizado está disponible públicamente en Kaggle:
https://www.kaggle.com/datasets/mohankrishnathalla/diabetes-health-indicators-dataset
Licencia: CC0 (uso libre).
