# Trabajo Fin de Máster: Uso de Algoritmos de Machine Learning para Identificar Anomalías en Transferencias Financieras Digitales
Se desarrolla un sistema de detección de fraudes en transacciones financieras digitales, combinando algoritmos supervisados, técnicas de rebalanceo y estrategias de ensamblado.

# Objetivo general del trabajo
Implementar modelos convencionales de Machine Learning para la identificación de anomalías en transferencias financieras digitales, con el propósito de optimizar la capacidad de recuperación (recall), comparando diferentes configuraciones con y sin técnicas de balanceo.

# Dataset
- Fuente: Credit Card Fraud Detection (Kaggle, 2018).
- Registros: 284,807 transacciones, con solo 0.17% de fraudes.
- Características: Datos anonimizados mediante PCA. Se incluyen `Time`, `Amount` y `Class`, y se añade una variable `Hour` para análisis temporal.

# Modelos y técnicas
- Modelos supervisados: KNN, Random Forest, XGBoost y LightGBM.
- Rebalanceo: SMOTE (90-10% y 95-5%), class_weight, scale_pos_weight.
- Optimización de LightGBM: Grid Search con validación cruzada.
- Ensamblado: VotingClassifier con votación suave, ponderada según el F1-score de cada modelo.

# Resultados destacados
- Mejor modelo: LightGBM con Grid Search sin SMOTE — F1-score: 88.8%, Recall: 84.6%, Precision: 93.5%.
- Ensemble: VotingClassifier (KNN sin SMOTE + RF con SMOTE 95%-5% + XGB con SMOTE 95%-5%), F1-score: 86.3%.
- SMOTE mejora el recall en algunos modelos, pero puede degradar la precisión en algoritmos sensibles como KNN.
- La estrategia de rebalanceo óptima depende del modelo y requiere ajuste cuidadoso.

# Recomendaciones y trabajos futuros

- Incluir modelos no supervisados como autoencoders y HMM.
- Incorporar variables contextuales: canal, geolocalización, frecuencia de uso, etc.
- Evaluar el sistema en entornos de streaming y con datos reales.
- Utilizar SHAP y LIME para fortalecer la interpretabilidad.
- Extender el sistema a otros tipos de fraude (préstamos, suplantación de identidad, etc).
