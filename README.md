Este proyecto se basa en las redes neuronales recurrentes para predecir el nivel de una estación limnigráfica a partir de variables meteorológicas: Humedad, Temperatura, Viento, Precipitación y Presión.

Se presenta un caso para las estación de nivel de la Quebrada el Chocho y la estación meteorológica Cedepro 500 metros aguas arriba. Estaciones ubicadas al suroccidente de Medellín, Antioquia, Colombia. En la siguiente imágen se presenta la ubicación de las estaciones.
![alt text](https://github.com/MateoParra/DischargePrediction/blob/master/Images/Localizacion.png)

Se muestran dos notebooks de ajuste de datos, estos tienen herramientas para pasar la serie de tiempo minutal a horario y agregación de variables a una matriz comparando las fechas de los datos.

Se prueban los modelos RNN, LSTM y GRU incluyendo y sin incluir la serie de tiempo de nivel de la quebrada con 9 tiempos hacia atrás, en promedio se alcanza un MSE de 0.009 y 0.019 incluyendo y sin incluir respectivamente el nivel del agua.
Se observa que la simulación de la variabilidad y la tendencia es buena, los mínimos se simulan medianamente y los máximos no se simulan bien.
En este sentido se aplican los modelos para predecir 3,6 y 12 tiempos hacia atrás en todos se observa en general un mejor desempeño del modelo LSTM.
Se crea una arquitectura Encoder-Decoder, en general los modelos se desempeñan igual en los pasos. Es por esto que se realiza una modelación incluyendo el nivel del agua con RNN. En este caso se ve que la serie de tiempo se ajusta mejor y balanceado los máximos y los mínimos siendo los predichos superiores.
