# Project Charter - Entendimiento del Negocio
## Predicción del Factor Primario de Incidentes Aéreos

## Objetivo del Proyecto

Desarrollar un modelo de Machine Learning capaz de predecir el factor primario que causó un incidente aéreo ('Primary Problem') a partir de las características contextuales del vuelo registradas en el Aviation Safety Reporting System (ASRS). El modelo permitirá a las autoridades aeronáuticas y operadores identificar de forma anticipada los factores de riesgo más críticos, orientando intervenciones preventivas y mejorando la seguridad aérea.

## Alcance del Proyecto

### Incluye:

- Dataset ASRS con 4,434 registros de incidentes aéreos reportados voluntariamente, con 125 variables organizadas en grupos: Time, Place, Environment, Aircraft 1 & 2, Component, Person 1 & 2, Events, Assessments y Reports.
- Variable objetivo: 'Primary Problem' (Assessments) con 14 categorías: Human Factors (62.7%), Aircraft (13.7%), Ambiguous (8.6%), Procedure (7.2%), Weather (1.7%), entre otras.
- Variables de entrada relevantes identificadas: Flight Phase (Landing, Initial Approach, Final Approach, Takeoff), Flight Conditions (VMC/IMC/Mixed), Human Factors de Person 1 & 2 (Situational Awareness, Communication Breakdown, Training/Qualification), Anomaly (tipo de evento), Contributing Factors / Situations, Make Model Name, Mission, Flight Plan, Operating Under FAR Part, Light, Weather Elements.
- Criterios de éxito: Accuracy >= 75% en clasificación multiclase; F1-score macro >= 0.65 considerando el desbalance de clases; interpretabilidad del modelo mediante SHAP values para validación con expertos en aviación.

### Excluye:

- Predicción de la severidad del accidente o número de víctimas.
- Análisis de texto libre de los campos Narrative y Synopsis (NLP avanzado fuera de alcance en esta fase).
- Integración en tiempo real con sistemas operacionales de aerolíneas o autoridades.
- Registros del Aircraft 2 como fuente primaria de features (se usan como apoyo).
- 
## Metodología

Se utilizará la metodología CRISP-DM (Cross-Industry Standard Process for Data Mining), adaptada al contexto de seguridad aérea. Las etapas incluyen: entendimiento del negocio y carga de datos, preprocesamiento y análisis exploratorio (EDA), ingeniería de características y codificación de variables categóricas multi-valor, modelamiento con algoritmos de clasificación multiclase (Random Forest, XGBoost, LightGBM y Regresión Logística como baseline), manejo de desbalance de clases con SMOTE o class_weight, evaluación con validación cruzada estratificada, e interpretación de resultados con SHAP. El despliegue final consistirá en una API REST que exponga el modelo entrenado.

## Cronograma

| Etapa | Duración Estimada | Fechas |
|------|---------|-------|
| Entendimiento del negocio y carga de datos | 1 semana | del 7 de mayo al 15 de mayo |
| Preprocesamiento, análisis exploratorio | 1 semana | del 16 de mayo al 22 de mayo |
| Modelamiento y extracción de características | 1 semana | del 22 de mayo al 29 de mayo |
| Despliegue, Evaluación y entrega final | 1 semanas | del 29 de mayo al 6 de junio |


## Equipo del Proyecto

- Martin Zorrilla


## Presupuesto

Estimado total: USD 45,000. Distribuido en: infraestructura cloud para entrenamiento (GPU/CPU) USD 8,000; licencias de herramientas de MLOps USD 5,000; horas-hombre del equipo (15 semanas) USD 30,000; consultoría en dominio aeronáutico USD 2,000.

## Stakeholders

- Autoridad de Aviación Civil (AAC): interesada en los factores de riesgo más frecuentes para orientar políticas de seguridad. Espera reportes ejecutivos con hallazgos del modelo.
-  Aerolíneas: buscan identificar patrones de riesgo en sus operaciones. Esperan que el modelo sea integrable en sus sistemas de safety management.
- Equipo de Investigación de Accidentes: utiliza el sistema como herramienta de apoyo para priorizar líneas de investigación. Requiere explicabilidad del modelo.
- Pilotos e Instructores de Vuelo: beneficiarios finales de las mejoras en protocolos de entrenamiento derivadas del análisis.
- 
## Aprobaciones

- Director de Seguridad Operacional — firma y fecha de aprobación del charter.
- Jefe del Equipo de Ciencia de Datos — validación técnica del plan.
- Representante del Stakeholder Principal (AAC) — aceptación del alcance y entregables.
