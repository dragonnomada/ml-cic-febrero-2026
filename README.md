# Curso de Machine Learning

![IPN](https://ipn.mx/assets/files/main/img/template/header/logo-ipn-horizontal.svg)

![CIC](https://www.cic.ipn.mx/img/home/menu/logocic.png)

> Centro de Investigación en Computación
>
> Departamento de Diplomados y Extensión Profesional

---

Alan Badillo Salas (badillosalas@outlook.com)

## Sesión 101 - Martes 27, enero

> Resumen

En esta clase teórica se introdujo el concepto de Aprendizaje Automático, también llamado Aprendizaje Máquina (*Machine Learning*).

Se mostraron dos tipos de aprendizaje, el supervisado, que se basa en entender y modelar el comportamiento de una respuesta a través de las características informativas restantes a las respuestas y el aprendizaje no supervisado que será revisado más adelante.

Se explicó el sentido de las dimensiones de las características informativas que intentan explicar la respuesta mediante un modelo paramétrico, el cuál de ser muy flexible podría sobreajustarse a los datos observados.

Se introduce el concepto de la función de pérdida (*loss funcion*) y el proceso de optimización para encontrar los mejores pesos (parámetros de ajuste) que logren llevar al modelo (una función generalizada) lo más próximo a los datos.

Finalmente, se ejemplifica como un conjunto de datos de características se puede usar para seleccionar una respuesta y las características informativas (covariables).

Mediante el ejemplo del Titanic se ve la necesidad de comprender la naturaleza de los datos, ya sean cualitativos (categóricos) o cuantitativos (numéricos continuos). De donde los datos numéricos discretos podrán ser usados como continuos o como categóricos.

> Video

https://drive.google.com/drive/folders/1to5JhwzKTAcOipkt7PNfdhxqndw2D4lw?usp=share_link

## Sesión 102 - Jueves 29, enero

> Resumen

En esta clase práctica se trabajó sobre la práctica [ML-CIC-IPN-P101](ML-CIC-IPN-P101.pdf).

## Sesión 201 - Martes 3, febrero

> Resumen

En esta clase teórica se mostró la teoría sobre la estructura de un proyecto de *Machine Learning* y las fases para estructurarlo. También se profundizó sobre los métodos visuales para analizar las características individuales y la influencia en la respuesta mediante contrastes numérico-numérico, numérico-categórico, categórico-numérico y categórico-categórico.

> Fases del proyecto

1. **Conjunto de datos** - Continen las características de análisis de forma natural
2. **Características** - poseen una naturaleza numérica (cuantitativa) o categórica (cualitativa)
3. **Respuesta** - Representan la características de mayor costo e influencia que desean ser predichas mediante las demás características informativas
4. **Análisis descriptivo** - Se analizan las características individuales mediante la estadística según su naturaleza y la visualización de datos
5. **Análisis predictivo** - Busca modelar el comportamiento de las respuestas mediante el ajuste de un modelo con la matriz de características y el vector de respuesta dividido en datos de entrenamiento y validación
6. **Resultados** - Condensa los resultados de la validación y la comparación entre los 3 o más modelos propuestos para hacer la predicción

> Gráficas individuales

* **Numéricos** - Las gráficas de caja, densidad y de hoja que visualiza los cuartiles y mínimos y máximos (rangos) totales y relativos, así como los puntos atípicos
* **Categóricos** - Las gráficas de barras (muchas categorías) y dona o pastel (pocas categorías) que muestran los conteos totales y proporciones entre las categorías para determinar las de mayor peso que serán usadas como base

> Gráficas de contraste

* **Respuesta numérica** - La gráfica de puntos si la característica informativa es numérica y la gráfica de caja y hoja si la característica informativa es categórica
* **Respuesta categórica** - La gráfica de densidad segmentada si si la característica informativa es numérica y el mapa de calor si la característica informativa es categórica

## Sesión 202 - Jueves 5, febrero

> Resumen

En esta clase práctica se trabajó con la librería de Pandas y Seaborn para mostrar las diferentes formas de analizar características numéricas y categóricas.

> Carga del conjunto de datos

```py
import pandas

titanic = pandas.read_csv("titanic.csv") # DataFrame -> Objeto de tabla compleja (lista de diccionarios)

titanic.sample(10)
```

> Construir una variable categórica

```py
c1 = titanic["Survived"] # Columna / Vector / Serie catagórica (2 clases -> binaria)
```

> Obtener los conteos o soportes por clase

```py
c1.value_counts()
```

> Obtener los porcentajes o proporciones por clase

```py
c1.value_counts(normalize=True)
```

> Graficar los conteos por clase (mostrar el desbalanceo de entre las clases y la clase base)

```py
c1.value_counts().plot.bar() # Gráfica de barras de los conteos
```

> Graficar las proporciones por clase (mostrar la clase dominante y la uniformidad entre clases)

```py
c1.value_counts().plot.pie(autopct="%.1f%%", explode=[0, 0.1])
```

> Construir una variable numérica

```py
c7 = titanic["Fare"] # Columna / Vector / Serie numérica (positiva)
```

> Obtener los estadísticos principales

```py
c7.describe()
```

> Graficar la caja estadística (muestra la ubicación de los cuartiles y los puntos atípicos)

```py
c7.plot.box(vert=False)
```

> Graficar la caja estadística sin los puntos atípicos (muestra la ubicación de los cuartiles y el rango)

```py
c7.plot.density()
```

> Graficar la densidad (muestra la distribusión o masa de acumulación de los datos)

```py
c7.plot.density()
```

> Graficar la densidad espejo (muestra una hoja o violín para ubicar los centros de acumulación)

```py
seaborn.violinplot(x=c7)
```

Con esta clase práctica se podrá trabajar sobre la práctica [ML-CIC-IPN-P201](ML-CIC-IPN-P201.pdf).


## Sesión 301 - Martes 10, febrero

> Resumen

En esta clase teórica se mostró la teoría sobre el problema de clasificación y los modelos principales para hacer predicción o inferencia de una respuesta categórica con las características informativas.

El problema de de la clasificación es parte del aprendizaje supervisado, y consiste en determinar o predecir el comportamiento para una característica de respuesta de tipo categórica, es decir de naturaleza cualitativa. Por ejemplo, predecir si alguien tiene diabetes (2 clases o respuesta binaria), si alguien comprará una casa, un carro o un viaje (3 clases o respuesta multibinaria).

Para poder hacer la predicción los modelos usan la información de las características restantes formando un modelo de caja, donde la idea es lograr dividir la caja o espacio multidimensional de las características, usando la respuesta como el espacio de verdad en cada categoría o clase.

Los modelos principales para entender dos enfoques de la clasificación son:

* **Árboles de decisión** - Se basan en encontrar el mejor umbral que separe la respuesta mediante un índice de error que mide la probabilidad de pertenecer a una clase o la otra, más comunmente usado el índice de GINI, aunque se pueden utilizar otras formas de medir el error como la ENTROPÍA CRUZADA.
* **Curva logística** - Se basa en construir una curva que use la información ponderada de las características informativas o covariables y aplicarle a dicha ponderación o predictor lineal la función logística que se estructura de tal manera que para valores infinitos la respuesta será cercana a 1, mientras que para valores infinitos negativos la respuesta será cercana a cero. Esto se traduce como un problema de optimización donde debemos encontrar los pesos o ponderadores (parámetros de ajuste) que hagan que la curva explique mejor cuándo la respuesta será 0 o 1.

También se revisó la matriz de confusión que permite contrastar las predicciones verdaderas o falsas sobre las respuestas positivas o negativas, de tal manera que se construyen cuatro posibles espacios de verdaderos positivos, verdaderos negativos, falsos positivos y falsos negativos, generando porcentajes sobre la precisión, sensibilidad y especificidad, así como una métrica que balancea la presición y sensibilidad para dar un rendimiento llamado F1-SCORE.
