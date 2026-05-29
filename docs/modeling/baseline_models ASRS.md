# Reporte del Modelo Baseline
## Proyecto: Clasificación de Problemas en Reportes de Seguridad Aérea (ASRS)

---

## Descripción del modelo

Se entrenaron tres modelos baseline para clasificar automáticamente el problema primario de reportes de seguridad aérea de la NASA. El objetivo es predecir si un incidente corresponde a **Aircraft**, **Human Factors** u **Other**, a partir de variables estructuradas del reporte.

---

## Variables de entrada

| Feature | Grupo |
|---|---|
| Flight Phase | Aircraft 1 |
| Flight Conditions | Environment |
| Light | Environment |
| Anomaly | Events |
| Contributing Factors | Assessments |
| Result | Events |
| Make Model Name | Aircraft 1 |
| Operating Under FAR Part | Aircraft 1 |
| Detector | Events |

## Variable objetivo

`Primary Problem` — simplificada a 3 clases: **Aircraft**, **Human Factors**, **Other**.

---

## Evaluación del modelo

### Métricas de evaluación

Se utilizaron **F1 Macro** y **Accuracy** como métricas principales. El F1 Macro pondera por igual el desempeño en cada clase, lo que es relevante dado el desbalance entre categorías.

### Resultados de evaluación

| Modelo | F1 Macro | Accuracy |
|---|---|---|
| Random Forest | 0.7095 | 0.7352 |
| Naive Bayes | 0.6958 | 0.7361 |
| **XGBoost** | **0.7286** | **0.7439** |

El mejor modelo baseline fue **XGBoost**, con F1 Macro de 0.7286 y Accuracy de 0.7439.

---

## Análisis de los resultados

El modelo XGBoost demostró ser el más robusto de los tres. La clase **Aircraft** fue la mejor predicha gracias a sus patrones más distintivos en los datos. La clase **Human Factors** presentó mayor dificultad, con confusiones frecuentes con Aircraft, sugiriendo que ambas categorías comparten características estructurales similares en los reportes. La clase **Other** fue prácticamente invisible para todos los modelos debido al desbalance de clases en el dataset.

---

## Conclusiones

XGBoost se selecciona como modelo base para la fase de optimización. El principal desafío identificado es el desbalance entre clases, particularmente la baja representación de la categoría **Other**. Las siguientes etapas incluyen optimización de hiperparámetros con Optuna y estrategias para mejorar el desempeño en clases minoritarias.

---

## Referencias

- Dataset: [ASRS — NASA Aviation Safety Reporting System](https://asrs.arc.nasa.gov/search/database.html), reportes del año 2006.
- Seguimiento de experimentos: MLflow 2.17.1
- Optimización: Optuna
