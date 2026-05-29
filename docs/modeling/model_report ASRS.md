# Reporte del Modelo Final
## Proyecto: Clasificación de Problemas en Reportes de Seguridad Aérea (ASRS)
### Rama: `Experimento/-XGBoost`

---

## Resumen Ejecutivo

Se optimizó el modelo XGBoost baseline mediante búsqueda bayesiana de hiperparámetros con Optuna (50 trials), logrando una mejora en Accuracy de 0.7439 a 0.7624. El modelo final quedó registrado en MLflow Model Registry como `asrs_classifier` versión 2 y fue desplegado como REST API en el puerto 8001.

---

## Descripción del Problema

El sistema ASRS de la NASA recopila reportes anónimos de incidentes de aviación. Clasificar manualmente cada reporte según su problema primario (Aircraft, Human Factors, Other) es un proceso lento y susceptible a inconsistencias. El objetivo es automatizar esa clasificación mediante un modelo de machine learning entrenado sobre variables estructuradas de los reportes del año 2006.

---

## Descripción del Modelo

El modelo final es un clasificador **XGBoost** con hiperparámetros optimizados mediante **Optuna**, una librería de optimización bayesiana que explora el espacio de hiperparámetros de forma inteligente, priorizando las regiones más prometedoras en cada trial.

Se exploraron 50 combinaciones de los siguientes hiperparámetros:

| Hiperparámetro | Rango explorado |
|---|---|
| `n_estimators` | 50 – 400 |
| `max_depth` | 3 – 10 |
| `learning_rate` | 0.0001 – 0.3 |
| `subsample` | 0.5 – 1.0 |
| `colsample_bytree` | 0.5 – 1.0 |
| `min_child_weight` | 1 – 10 |
| `gamma` | 0 – 5 |

Cada trial fue registrado como un run independiente en MLflow, permitiendo trazabilidad completa del proceso de optimización.

---

## Evaluación del Modelo

### Comparación baseline vs optimizado

| Métrica | Baseline XGBoost | XGBoost Optimizado |
|---|---|---|
| F1 Macro | 0.7286 | 0.7221 |
| Accuracy | 0.7439 | 0.7624 |

### Interpretación

La optimización mejoró la capacidad general del modelo para clasificar correctamente los reportes, aunque esta mejora no fue uniforme entre clases. La clase **Aircraft** es identificada con alta confianza gracias a sus patrones más distintivos. **Human Factors** sigue siendo la categoría más difícil, con confusiones frecuentes con Aircraft, lo que sugiere que ambas comparten características estructurales similares. La clase **Other** continúa siendo un desafío por el desbalance de clases en el dataset.

---

## Conclusiones y Recomendaciones

El modelo optimizado representa una mejora real en precisión general, pero su principal limitación es el desbalance entre clases. Para iteraciones futuras se recomienda explorar técnicas de manejo de desbalance como SMOTE o ajuste de pesos por clase, así como incorporar variables de texto libre de los reportes mediante NLP, lo que probablemente revelaría patrones más ricos para distinguir entre Human Factors y Aircraft.

El modelo fue registrado en MLflow como `asrs_classifier/2` y validado como REST API, completando el ciclo de vida completo del proyecto.

---

## Referencias

- Dataset: [ASRS — NASA Aviation Safety Reporting System](https://asrs.arc.nasa.gov/search/database.html), reportes del año 2006.
- Optimización: Optuna — búsqueda bayesiana, 50 trials
- Seguimiento de experimentos: MLflow 2.17.1, experimento `ASRS_XGBoost_Optuna`
- Modelo registrado: `asrs_classifier` versión 2
