---
author:
- Marcos Severt Silva
date: 
- Diciembre 2020
title: "Propagación del WiFi: Reflexión, Dispersión y Difracción"
---

# Introduction

The term propagation is applied to a signal when we want to explain how radio waves behave when they are transmitted or propagated from one point to another. We understand, therefore, that the propagation mechanism establishes how the signal propagates, taking into account the effects of reflection, scattering and diffraction.
We speak of reflection when the transmitted wave collides with an object larger than its wavelength, as would be the case of the walls of a building. Some of these waves will be absorbed and the remaining energy will be reflected back to the medium.  The energy of the transmitted and reflected waves follows a function dependent on the geometry and material properties of the obstruction and the amplitude, phase and polarization of the incident wave. Scattering occurs when the transmitted wave encounters a large number of small dimensional objects, such as light poles, bushes and trees. The reflected energy in a scattering situation is dispersed in all directions before reaching the receiver. Diffraction occurs when the surface of the obstruction has sharp edges that produce secondary waves that, in effect, bend around the obstruction. Like reflection, diffraction is affected by the physical properties of the obstruction and the characteristics of the incident wave.
Indoor scenarios are often more complex, where numerous objects can scatter, diffract, reflect and absorb radiation. It is made more complicated by the movement of people, who rapidly change environments. The indoor environment is not stationary in both space and time. The ability to predict the behavior of signals in indoor environments is crucial. Therefore, there is a need to understand the signal behavior of these wireless systems.

# Cuatro ecuaciones de Maxwell

WiFi is an electromagnetic wave containing a signal: Internet data. Electromagnetic waves are well known to physicists and are governed by Maxwell's 4 equations, which give the solution for E, the electric field, and B, the magnetic field, in space and time. 

## Primera ecuación de Maxwell

The first of the four equations is based on Gauss's law of electrostatics, which assures us that "when a surface is closed, the integral of the electric flux density is always equal to the charge enclosed on that surface", which we can express as the product of the electric flux density vector and the integral of the surface being equal to the enclosed charge:

## Segunda ecuación de Maxwell

The second of the four equations is based on Gauss's law for the magnetic field or magnetostatics, which assures us that "on a closed surface, the integral of the magnetic flux density is always equal to the total scalar magnetic flux enclosed within that surface of any shape or size and in any medium".

## Tercera ecuación de Maxwell

Maxwell's third equation is derived from Faraday's law of electromagnetic induction, which states that "whenever there are n turns of conducting coil in a time-varying magnetic field an alternating electromotive force is induced in each and every coil."

## Cuarta ecuación de Maxwell

Maxwell's fourth and final equation is based on Ampere's law which postulates that "the closed line integral of the magnetic field vector is always equal to the total amount of the scalar electric field enclosed in the path of any shape".

# Ecuación de Helmholtz

In the case of WiFi waves, we do not have to take time into account since, since the period of the signal is so short, the quality of the signal will not change with time. Since these are then stationary solutions, we can simplify Maxwell's equations into a single equation known as the Helmholtz Equation

# Caso Base, piso sin obstáculos

Para este primer caso de estudio he creado ,mediante el uso de una serie
de coordenadas, un supuesto plano de una vivienda sin obstáculos con una
pared de un grosor medio (Fichero SinObstaculos.edp). La idea es añadir
una fuente de WiFi y ver como las ondas se propagan por la vivienda y
así ver en que puntos hay más señal de WiFi. El plano creado y mallado
es el siguiente:

::: {.center}
![image](SinObstaculosMalla.PNG)
:::

En este caso, los índices de reflexión y de absorción son considerados
como aleatorios dentro de un límite, ya que cada material tiene los
suyos propios. La simulación en este caso ofrece el siguiente resultado:

::: {.center}
![image](SinObstaculosResultado.PNG)
:::

Como puede verse, cuanto más alejados estemos de la fuente del WiFi, en
este caso situada en la habitación izquierda, menos potencia de señal
tendremos. Siendo la habitación derecha la más alejada. Este resultado
era el esperado ya que, con cada contacto en las paredes, debido al
fenómeno de absorción y de la cancelación de las ondas entre ellas, la
señal va debilitándose.\
Si ahora añadimos una segunda fuente en el mismo escenario y lo mallamos
tenemos:

::: {.center}
![image](SinObstaculosDosFuentes.PNG)
:::

Y si resolvemos el problema en esta malla podemos ver como se propagan
las ondas de ambas fuentes:

::: {.center}
![image](SinObstaculosDosFuentesResultado.PNG)
:::

Cabe destacar que, a pesar de que en la habitación de la derecha ahora
hay una mejor cobertura, la habitación del medio se ve perjudicada por
la cancelación de ondas.

# Caso con obstáculos

Para este segundo caso de estudio he creado ,mediante el uso de una
serie decoordenadas, un supuesto plano de una vivienda con obstáculos
con una pared de un grosor medio. En este caso, los obstáculos cuentan
con un n con valor igual a la mitad del de la pared, de forma que
podremos ver como el situar cuerpos sólidos en el espacio puede afectar
a la transmisión de ondas del WiFi, sin que estos las frenen por
completo. Teniendo en cuenta la siguiente malla de dos obstáculos:

::: {.center}
![image](Obstaculos.PNG)
:::

El resultado de la simulación será el siguiente:

::: {.center}
![image](Obstaculos2.PNG)
:::

Si ahora colocamos la segunda fuente:

::: {.center}
![image](Obstaculos2f.PNG)
:::

Y ahora el resultado de la simulación sería el siguiente:

::: {.center}
![image](Obstaculos2f2.PNG)
:::

# Caso de la difracción

La ecuación de Helmholtz también modela el comportamiento de las ondas
respecto al fenómeno de la difracción, es por ello que para este caso he
reproducido el comportamiento de las ondas del WiFi si la fuente está
encerrada y solo existe una pequeña ranura por la que pueden salir las
ondas en la parte superior. El proceso que he realizado consiste en ir
ampliando esta ranura para observar el comportamiento de las ondas
respecto a este fenómeno:

::: {.center}
![image](SmallMalla.PNG)
:::

::: {.center}
![image](small.PNG)
:::

Como se observa, excepto las ondas que escapan por las paredes al no ser
absorvidas del todo por el material apenas se produce difracción en la
parte superior al ser el ancho de la ranura muy parecido a la longitud
de onda del WiFi. Para un segundo caso, se amplía un poco más esta
ranura:

::: {.center}
![image](mediumMall.PNG)
:::

::: {.center}
![image](medium.PNG)
:::

Ahora podemos observar que sí que se comienza a dar el fenómeno de
difracción en la parte superior de la caja que encierra a la fuente de
WiFi. Si seguimos aumentando el ancho de la ranura sucede lo siguiente:

::: {.center}
![image](bigMalla.PNG)
:::

::: {.center}
![image](big.PNG)
:::

Como vemos en el resultado, ahora, a parte de la difracción de ondas,
hay algunas que escapan de la caja sin difractarse dado el ancho de la
ranura que ahora es superior a la longitud de onda. Como última prueba
de este fenómeno, he decidido hacer la ranura considerablemente grande:

::: {.center}
![image](gapMalla.PNG)
:::

::: {.center}
![image](gap.PNG)
:::

Como vemos en este último caso, la difracción apenas es visible dada la
cantidad de ondas que atraviesan la ranura sin difractarse.
