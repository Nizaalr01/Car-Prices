# Informe de Análisis de Datos: Predicción de Precios de Automóviles en el Mercado Estadounidense
## Niza Alvarado Rendón 
A01367547

## Introducción
En este informe, se presenta un análisis exhaustivo de datos realizado para ayudar a una empresa automovilística china a comprender los factores que influyen en el precio de los automóviles en el mercado estadounidense. El objetivo principal es identificar variables significativas y desarrollar un modelo de regresión lineal para predecir los precios de los automóviles en función de estas variables. El análisis abarca desde la exploración inicial de datos hasta la validación de supuestos y la interpretación de resultados.

# Análisis Exploratorio de Datos de Automóviles

## Exploración de Datos

### Medidas Estadísticas

Las variables cuantitativas muestran distintos niveles de dispersión y agrupamiento de datos. La variable "wheelbase" muestra una dispersión baja en relación con la media y datos agrupados alrededor de ella. En "carlength", aunque existe un rango amplio de longitudes, la mayoría se sitúa cerca de la media debido a su bajo coeficiente de variación. Similarmente, "carwidth" y "carheight" tienen datos agrupados alrededor de la media y baja dispersión. "Curbweight" muestra una dispersión moderada con un rango amplio. "Enginesize" y "horsepower" presentan alta variabilidad y rango amplio. "Stroke" tiene baja variación y la mayoría de valores cercanos a la media. "Compressionratio" muestra alta variación y amplio rango. "Peakrpm" tiene baja dispersión y datos agrupados alrededor de la media, con un rango definido.

### Frecuencias

La frecuencia de la variable "CarName" destaca porque su limpieza es esencial para retener solo los nombres de las compañías. Asimismo, "symboling" muestra que el 32% de los automóviles tiene una calificación de riesgo normal/neutro. "Fueltype" tiene una moda de gas (90%) en comparación con el diesel. En "carbody", el sedan es el más frecuente (46%), seguido por hatchback (34%). "Drivewheel" revela que la tracción delantera es la más común, seguida de la trasera. También, "Enginelocation" muestra que el 98% de los autos tiene el motor en la parte delantera. En "enginetype", el 72% son motores OHC. Finalmente, "cylindernumber" indica que la mayoría de los vehículos tienen cuatro cilindros.

### Histograma

Se observa que la mayoría de las variables presentan una asimetría hacia la derecha, por tanto, una distribución positiva. Esta característica es común debido a la presencia de valores atípicos que son menos frecuentes pero tienen un impacto significativo en la distribución. Sin embargo, la variable "stroke" muestra una asimetría negativa.


### Heatmap de Correlación

En relación al precio, se destacan correlaciones positivas fuertes con las variables curbweight, enginesize y horsepower. Por el contrario, citympg y highwaympg muestran correlaciones negativas notables. Las dimensiones físicas del vehículo, como carlength, carwidth y curbweight, también influyen positivamente en los precios. En contraste, wheelbase, stroke y compressionratio tienen correlaciones menos pronunciadas con el precio, lo que sugiere que su impacto podría ser menos directo en la determinación de los precios.

![image](https://github.com/Nizaalr01/Car-Prices/assets/61805853/4a3d7120-e538-4235-95fc-dd584908b3b2)


## Selección de Variables Significativas

Se utilizaron criterios específicos para seleccionar las variables que se incluirían en el modelo de regresión. Las variables seleccionadas fueron curbweight, horsepower, carlength, enginesize, CarName, wheelbase. Estas variables fueron consideradas significativas debido a su importancia en la predicción del precio de los automóviles, así como a sus altos valores de correlación en el heatmap de correlación.

Los resultados del ANOVA y correlacion, pueden interpretarse de la siguiente manera:

###### CarName
Se seleccionó esta variable porque representa la marca o el nombre del automóvil. Su alta significación estadística (p < 2e-16) indica que la marca del automóvil tiene un efecto significativo en el precio. Esto tiene sentido, ya que las marcas de automóviles a menudo están asociadas con la calidad, la reputación y la percepción de valor, lo que puede influir en el precio.

###### carlength: 
Esta variable se eligió debido a su alta significación estadística (p = 6.07e-14). La longitud del automóvil puede influir en su precio, ya que los automóviles más largos a menudo tienen características adicionales o espacio interior, lo que puede aumentar su precio.

###### curbweight: 
Se seleccionó esta variable porque también muestra alta significación estadística (p = 2.24e-07). El peso en vacío del automóvil (curbweight) puede estar relacionado con la calidad de construcción y la cantidad de material utilizado en la fabricación del vehículo, lo que afecta el precio.

###### enginetype: 
A pesar de que hay varias categorías en esta variable, se eligió debido a su significación estadística (p = 3.97e-05). El tipo de motor puede influir en el rendimiento y la eficiencia del automóvil, lo que, a su vez, puede afectar el precio.

###### wheelbase: 
Esta variable también se seleccionó debido a su significación estadística (p = 0.00548). La distancia entre ejes (wheelbase) puede estar relacionada con la estabilidad y el espacio interior del automóvil, lo que influye en el precio.

###### horsepower: 
La variable "horsepower" también se incluyó en el modelo debido a su significación estadística (p = 0.04790 *). La potencia del motor es un factor crítico que influye en el rendimiento de un automóvil y, por lo tanto, en su precio.

## Limpieza de Variable CarName

### Limpiar variable CarName

Se realizó una limpieza en la variable CarName para asegurar la consistencia y uniformidad de los nombres de las compañías de automóviles. Esto incluyó la conversión de todos los nombres a minúsculas, la eliminación de cualquier información adicional después de un espacio y la corrección de nombres de compañías comunes que tenían errores tipográficos.

## Manejo de Outliers

### Observación de Valores Atípicos

Se identificaron valores atípicos en varias variables, como carlength, horsepower y precio. Estos valores atípicos fueron considerados en el análisis y se aplicaron técnicas para abordarlos adecuadamente.

### Eliminación de Valores Atípicos

Se procedió a eliminar los valores atípicos identificados en las variables, excepto en la variable precio. Esto se hizo utilizando el método del rango intercuartil (IQR) para determinar los límites superior e inferior de los valores aceptables. Los valores fuera de estos límites fueron excluidos del conjunto de datos.

## Modelo Estadístico
Se utilizó un modelo de regresión lineal para predecir los precios de los automóviles en función de las variables seleccionadas. El modelo proporcionó un coeficiente de determinación (R-cuadrado) de 0.9858, lo que indica un ajuste efectivo del modelo a los datos.

### Interpretación de Coeficientes
En el resumen del modelo de regresión lineal, podemos observar varios detalles importantes. Primero, el valor "Call" muestra que hemos ajustado un modelo de regresión lineal utilizando las variables independientes "curbweight," "horsepower," "carlength," "enginesize," "CarName," y "wheelbase" para predecir el precio de los automóviles.

Respecto a los coeficientes estimados, cada uno tiene su propio significado en relación con la variable objetivo, que es el precio de los automóviles. Por ejemplo, el coeficiente para "curbweight" es positivo (3.514), lo que sugiere que un aumento en el peso del automóvil se asocia con un aumento en el precio, manteniendo las otras variables constantes. El coeficiente para "horsepower" también es positivo (28.879), lo que significa que un mayor caballaje del motor se traduce en un aumento en el precio.

Algunas variables de "CarName" tienen coeficientes positivos significativos, lo que indica que ciertas marcas o modelos específicos tienen un impacto en el precio. Por ejemplo, "CarNamebmw x5" tiene un coeficiente positivo alto (18,309.411), lo que sugiere que los vehículos de esta marca tienden a tener precios más altos. Del mismo modo, "CarNameporsche boxter" y "CarNameporsche cayenne" tienen coeficientes positivos significativos, lo que indica que los automóviles de la marca Porsche también tienen precios más elevados.

Por otro lado, algunas variables, como "carlength," "carnamealfa-romero Quadrifoglio," y "CarNamechevrolet impala," tienen coeficientes que no son estadísticamente significativos, lo que sugiere que su contribución al precio no es significativa en el modelo.

El valor del estadístico F es 24.39, con un p-valor muy bajo, lo que indica que el modelo en su conjunto es estadísticamente significativo. Además, el coeficiente de determinación múltiple (R-cuadrado ajustado) es 0.9454, lo que significa que el modelo explica aproximadamente el 94.54% de la variabilidad en el precio de los automóviles.

En resumen, este análisis de coeficientes y estadísticas del modelo nos proporciona información valiosa sobre cómo las diferentes variables afectan al precio de los automóviles y cuán bien se ajusta el modelo en general.

### Validación de Supuestos
#### Resultados de las Pruebas
Se realizaron pruebas de normalidad para evaluar si los residuos del modelo de regresión seguían una distribución normal. En un modelo de regresión lineal, se asume que los residuos siguen una distribución normal. Para verificar esta suposición, se utilizaron diversas pruebas estadísticas, como la prueba de Shapiro-Wilk. Los resultados de estas pruebas se interpretaron para determinar si los residuos eran normalmente distribuidos.

Los resultados de la prueba de Shapiro-Wilk indican que los residuos no siguen una distribución normal (W = 0.73498, p-value < 2.2e-16). En particular, el valor p obtenido es extremadamente pequeño, lo que lleva a rechazar la hipótesis nula de normalidad. Esto significa que los residuos no se distribuyen de manera gaussiana y, por lo tanto, no cumplen con uno de los supuestos clave de los modelos de regresión lineal.

![image](https://github.com/Nizaalr01/Car-Prices/assets/61805853/74517886-56f6-4eb2-a7b4-ba6bd92f3a99)

![image](https://github.com/Nizaalr01/Car-Prices/assets/61805853/c3936943-edc6-44f2-b78d-c5c5d3694aa5)

El resultado del QQ plot de los residuos sugiere que la distribución de los residuos del modelo de regresión lineal no sigue una distribución normal de manera estricta. Se observa una asimetría negativa, indicando que la cola izquierda de los residuos es más pesada de lo esperado, mientras que la cola derecha es más ligera en comparación con una distribución normal. Esto sugiere cierta desviación de la normalidad en la distribución de los residuos. 

![image](https://github.com/Nizaalr01/Car-Prices/assets/61805853/5d6d08ec-4c96-477b-ade3-82463685a2d5)

Sin embargo, es importante recordar que ningún conjunto de datos es perfectamente normal, y es común que en las colas del gráfico Q-Q los puntos se alejen ligeramente de la línea diagonal.


### Conclusiones
En este análisis exhaustivo de datos de la industria automovilística, se investigaron las relaciones y los factores influyentes en el precio de los automóviles en el mercado estadounidense. Se identificaron variables significativas como curbweight, horsepower, carlength, enginesize, CarName y wheelbase, que mostraron una fuerte correlación con el precio de los vehículos. Un modelo de regresión lineal fue construido para predecir los precios de los automóviles en función de estas variables, y se obtuvo un alto coeficiente de determinación (R-cuadrado) de 0.9858, lo que indica una buena capacidad predictiva. Sin embargo, se observó una desviación de la normalidad en la distribución de los residuos del modelo, lo que sugiere la necesidad de una evaluación más detallada y posibles mejoras en el modelo. En resumen, este análisis proporciona información valiosa para la toma de decisiones en la empresa automovilística china, pero se recomienda un análisis adicional para perfeccionar el modelo y abordar la desviación de la normalidad en los residuos.

###  Anexos

https://drive.google.com/file/d/1xh6eE6OSEQXTl7IX2rGG7__eOESAHsOc/view?usp=drive_link
