# RRNN-RESPEL (Español)
Para la predicción de la generación de desechos eléctricos y electrónicos (2021-2025) de acuerdo a su comportamiento registrado por el IDEAM en la Bases Animizadas (2015-2020); se realiza la investigación en 4 pasos

1. Entendimiento de los datos, mapeo de campos, identificación de las principales ciudades COL y Códigos CIIU.
2. Limpieza, filtrado y categorización de las bases anonimizadas (2015-2020) para su posterior uso en la predicción.
3. Predicción por medio de regresión lineal, por departamento, municipio y actividad económica.
4. Predicción por medio de red neuronal (RRNN), por departamento y municipio
5. Entendimiento de los datos por medio de gráficos.

# RESUMEN
Este código en Python está diseñado para realizar tareas de machine learning utilizando redes neuronales para predecir datos basados en series temporales. A continuación se detallan las funciones de cada parte del código:

Carga de datos (Dataloading):

En primer lugar, se carga un archivo CSV llamado 'DEPARTAMENTO_GrpConsolidado.csv' utilizando pandas.
Se crea una copia de los datos originales.
Se elimina la columna 'DEPARTAMENTO' y se configura la columna 'ANIO' como índice, luego se formatea como tipo de datos de fecha y tiempo y se ordenan los datos por índice.
División de datos (Datasplitting):

Los datos se dividen en conjuntos de entrenamiento y prueba basados en la cantidad de días especificados para el entrenamiento.
Los datos se dividen adicionalmente en entradas y salidas para los modelos de entrenamiento y validación.
Los datos de entrada se remodelan para que sean tridimensionales para poder ser procesados por la red neuronal.
Diseño, entrenamiento y predicción de la red neuronal feedforward (FeedforwardNeuronalNetworkdesign, trainingandpredicting):

Se define una función para crear un modelo secuencial de red neuronal que consiste en capas densas con función de activación 'tanh', se aplana la salida y se agrega una capa densa final.
El modelo se compila con la función de pérdida 'mean_absolute_error' y la optimización 'Adam', utilizando métricas de error cuadrático medio ('mse') y error porcentual absoluto medio ('mape').
El modelo se entrena utilizando el conjunto de datos de entrenamiento con un número específico de épocas y tamaño de lote definidos por 'PASOS', y se valida con el conjunto de datos de validación.
Después del entrenamiento, se calcula el promedio del 'mse' y 'mape' de todas las épocas y se agregan a listas para su análisis.
Finalmente, se utilizan los datos de validación para hacer predicciones con el modelo entrenado.

![image](https://github.com/user-attachments/assets/ca59e69a-b40a-46cf-99ce-5d510de4272e)
