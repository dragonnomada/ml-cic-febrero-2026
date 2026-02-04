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

## Sesión 101 - Jueves 29, enero

> Resumen

En esta clase práctica se trabajó sobre la práctica [ML-CIC-IPN-P101](ML-CIC-IPN-P101.pdf).

## Sesión 101 - Martes 3, febrero

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
