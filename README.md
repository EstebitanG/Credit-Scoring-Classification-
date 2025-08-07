# Credit Scoring Classification
Este proyecto forma parte de mi portfolio de Data Analytics y Data Science, donde se usa el lenguaje de programación Python aplicando técnicas estadísticas y de Machine Learning para clasificar el comportamiento crediticio de personas según variables sociodemográficas y comportamiento pasado.

# Descripción General 
Este proyecto busca clasificar personas en 3 categorías: 'Poor', 'Standard' y 'Good', las cuales describen el comportamiento crediticio de una persona en base a distintas variables (tanto numéricas como categóricas) asociadas al comportamiento de crédito actual y variables sociodemográficas. En este caso, los datos disponibles correspondían a datos de panel (información de los mismos clientes a través del tiempo) lo que permitía aprender comportamiento crediticio pasado, para luego procesar la información y clasificar nuevamente a estos clientes considerando los cambios en las variables mencionadas.

Los datos fueron sacados del sitio web [Kaggle](https://www.kaggle.com/datasets/parisrohan/credit-score-classification).

Primeramente se realizó la importación de los archivos csv a Python (train y test), para luego proceder con el preprocesamiento de los datos (limpieza y reordenamiento de la información), principalmente usando la librería Pandas, siendo este paso el mayor desafío del proyecto. Al tener ambos dataframes preprocesados correctamente, se exploran las proporciones de las clases de entrenamiento y se aplica la técnica SMOTE dado el desbalance de clases, de manera de no sesgar el entrenamiento de los modelos. Luego de ello, se entrenan diversos modelos de clasificación: Regresión Logística Multiclase, Naive Bayes, Árboles de Decisión, RandomForest, XGBoost, LGBM y KNN, cada modelo con sus potencialidades y limitaciones. Se interpretan las métricas de clasificación, haciendo énfasis principalmente en Accuracy y la Matriz de Confusión, de manera de comparar el rendimiento de cada modelo. Finalmente, se exporta un csv con las predicciones finales que entrega cada modelo, junto con la clasificación antigua del cliente para estudiar su evolución.

Para este proyecto se utilizó principalmente Python para cumplir con la ruta de analista y científico de datos, desde la importación de la información, su procesamiento, aplicación de modelos y exportación de la clasificación.

<img width="427" alt="Portada" src="https://github.com/user-attachments/assets/fc01f8cf-ff5b-4c84-be81-7ab1eb0e484b" />

