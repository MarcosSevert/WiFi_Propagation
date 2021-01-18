---
author:
- Marcos Severt Silva
bibliography:
- references.bib
date: Diciembre 2020
title: "Propagación del WiFi: Reflexión, Dispersión y Difracción"
---

# Introducción

El término propagación se aplica a una señal cuando queremos explicar
como se comportan las ondas de radio cuando estas son trasmitidas o
propagadas de un punto a otro. Entendemos, por tanto, que el mecanismo
de propagación establece como se propaga la señal, teniendo en cuenta
los efectos de reflexión, dispersión y difracción de
esta.[@hidayab2009wifi]\
Hablamos de que se produce reflexión cuando la onda que transmitimos
colisiona con un objeto de dimensión superior a su longitud de onda,
como sería el caso de las paredes o muros de un edificio. Algunas de
estas ondas serán absorbidas y la energía restante se reflejará de nuevo
al medio. La energía de las ondas transmitidas y reflejadas sigue una
función dependiente de la geometría y las propiedades materiales de la
obstrucción y de la amplitud, fase y polarización de la onda incidente.
La dispersión se produce cuando la onda transmitida se encuentra con una
gran cantidad de objetos de pequeña dimensión, como postes de luz,
arbustos y árboles. La energía reflejada en una situación de dispersión
se dispersa en todas las direcciones antes de llegar al receptor. La
difracción se produce cuando la superficie de la obstrucción tiene
bordes afilados que producen ondas secundarias que, en efecto, se doblan
alrededor de la obstrucción. Al igual que la reflexión, la difracción se
ve afectada por las propiedades físicas de la obstrucción y las
características de la onda incidente.[@asmussen2004mc1319x]\
Los escenarios en interiores suelen ser más complejos, donde numerosos
objetos pueden dispersar, difractar, reflejar y absorber radiación. Se
hace más complicado debido al movimiento de personas, que cambia
rápidamente de entorno. El ambiente interior no es estacionario tanto en
el espacio como en el tiempo. La capacidad de predecir el comportamiento
de las señales en los ambientes interiores es crucial. Por lo tanto, es
necesario entender el comportamiento de las señales de estos sistemas
inalámbricos.[@ali2010investigation]\

# Cuatro ecuaciones de Maxwell

El WiFi es una onda electromagnética que contiene una señal: datos de
Internet. Las ondas electromagnéticas son bien conocidas por los físicos
y se rigen por las 4 ecuaciones de Maxwell, que dan la solución para E,
el campo eléctrico, y B, el campo magnético, en el espacio y en el
tiempo.

## Primera ecuación de Maxwell

La primera de las cuatro ecuaciones se basa en la ley de Gauss de la
electrostática, la cual nos asegura que \"cuando una superficie es
cerrada, la integral de la densidad de flujo eléctrico es siempre igual
a la carga encerrada sobre esa superficie\", la cual podemos expresar
como el producto del vector de densidad de flujo eléctrico y de la
integral de la superficie siendo igual a la carga encerrada:\
$$\oiint\overrightarrow{D}.d\bar{s} = Q_{encerrada}$$ Un sistema
cerrado, como el que hemos planteado antes, tiene múltiples superficies
pero un único volumen, por ello podemos convertir la integral de la
superficie anterior (1) en una integral de volumen, tomando la
divergencia del mismo vector:
$$\oiint\bar{D}.d\bar{s} = \iiint\nabla . \overrightarrow{D}d\overrightarrow{v}$$
Ahora si combinamos la ecuación (1) con la ecuación (2) obtenemos la
siguiente:
$$\iiint\nabla . \overrightarrow{D}d\overrightarrow{v} =  Q_{encerrada}$$
El siguiente paso será conocer que es la carga encerrada en una
superficie cerrada. Esta carga se distribuirá en el volumen de la misma,
pudiendo definir el volumen de la densidad de la carga como:
$$pv =  \frac{dQ_{encerrada}}{dv}$$ Si reordenamos e integramos (4)
obtenemos el valor de la carga encerrada:
$$Q_{encerrada} =  \iiint pvdv$$ Si sustituimos (5) en (3) obtenemos la
siguiente igualdad: $$\iiint\nabla . Ddv =  \iiint pvdv$$ Si cancelamos
la integral del volumen en ambos lados de (6) obtenemos la primera
ecuación de Maxwell[@parker1970electrostatics]: $$\nabla . Ddv = pv$$

## Segunda ecuación de Maxwell

La segunda de las cuatro ecuaciones está basada en la ley de Gauss para
el campo magnético o magnetostática, la cual nos asegura que \"en una
superficie cerrada, la integral de la densidad de flujo magnético es
siempre igual al flujo magnético escalar total encerrado dentro de esa
superficie de cualquier forma o tamaño y en cualquier medio\". la
podemos expresar de la siguiente forma:
$$\oiint\overrightarrow{B}.ds = \phi_{encerrado}$$ Donde:
$$\phi = \text{Flujo magnético escalar}$$ De donde sacamos que el flujo
magnético no puede ser encerrado por ninguna superficie de ningun tamaño
o forma: $$\oiint\overrightarrow{B}.ds = 0$$ Si ahora aplicamos el
teorema de la divergencia de Gauss a la ecuación (10) podemos convertir
la integral de la superficie en una integral del volumen tomando la
divergencia del mismo vector:
$$\oiint\overrightarrow{B}.ds = \iiint\nabla .\overrightarrow{B}dv$$ Si
sustitutimos la ecuación (11) en (10) obtenemos lo siguiente:
$$\iiint\nabla .\overrightarrow{B}dv = 0$$ Para satisfacer la ecuación
anterior (12) se tiene que cumplir: $$\iiint dv = 0$$ O bien:
$$\nabla .\overrightarrow{B} = 0$$ Y como el volumen de un cuerpo no
puede ser nunca 0, llegamos a la segunda ecuación de
Maxwell[@field2006derivation]: $$\nabla .\overrightarrow{B} = 0$$

## Tercera ecuación de Maxwell

La tercera ecuación de Maxwell se deriva de la ley de inducción
electromagnética de Faraday, la cual establece que \"siempre que hay n
vueltas de bobina conductora en un campo magnético que varía con el
tiempo una fuerza electromotriz alterna se induce en todas y cada una de
las bobinas\". Esto es descrito por la ley de Lenz, que matematicamente
podemos expresarla como: $$emf_{alt} = -N\frac{d\phi}{dt}$$ Donde:
$$N = \text{Número de vueltas en una bobina}$$
$$\phi = \text{Flujo magnético escalar}$$ El signo negativo nos indica
que el campo magnético inducido siempre se opone al flujo magnético.
Siendo N=1: $$emf_{alt} = -\frac{d\phi}{dt}$$ Sabiendo que l el flujo
magnético escalar puede ser sustituido de la siguiente forma:
$$\phi = \iint\overrightarrow{B}.d\overrightarrow{s}$$ Si sustituimos la
ecuación (21) en la (20) obtenemos:
$$emf_{alt} =-\frac{d}{dt}\iint\overrightarrow{B}.d\overrightarrow{s}$$
Que podemos observar que se trata de una ecuación diferencial dada por:
$$emf_{alt} =\iint-\frac{\delta\overrightarrow{B}}{\delta t}.d\overrightarrow{s}$$
Por otra parte, la fuerza electromotriz alternante inducida en una
bobina se trata de un camino cerrado:
$$emf_{alt} = \oint\overrightarrow{E}.d\overrightarrow{l}$$ Si
combinamos (23) con (22) obtenemos:
$$\oint\overrightarrow{E}.d\overrightarrow{l} = \iint-\frac{\delta\overrightarrow{B}}{\delta t}.d\overrightarrow{s}$$
Haciendo uso del teoriema de Stoke, podemos convertir la integral de
línea en una integral de superficie:
$$\oint\overrightarrow{E}.d\overrightarrow{l} = \iint(\nabla \times \overrightarrow{E}).d\overrightarrow{s}$$
Combinando (25) con (24) y eliminando ambos términos obtenemos la
tercera ecuación de Maxwell:
$$\nabla \times \overrightarrow{E} = -\frac{\delta\overrightarrow{B}}{\delta t}$$

## Cuarta ecuación de Maxwell

La cuarta y última ecucación de Maxwell se basa en la ley de Ampere la
cual postula que \"la linea integral cerrada del vector del campo
magnético es siempre igual a la cantidad total del campo eléctrico
escalar encerrado en el camino de cualquier forma\", esto puede
expresarse matemáticamente de la siguiente forma:
$$\oint\overrightarrow{H}.d\overrightarrow{l} = I_{encerrado}$$ Haciendo
uso del teorema de Stokes:
$$\oint\overrightarrow{H}.d\overrightarrow{l} = \iint (\nabla \times \overrightarrow{H}).d\overrightarrow{s}$$
Si juntamos la ecuación (27) y la (28) obtenemos:
$$\iint (\nabla \times \overrightarrow{H}).d\overrightarrow{l} = I_{encerrado}$$
Donde la primera parte de la igualdad es un vector y la segunda parte se
trata de un escalar. El siguiente paso será transformar la segunda parte
en un vector multiplicando por el vector densidad definido como el flujo
escalar actual por unidad de superficie:
$$\overrightarrow{J} = \frac{I}{s}aN$$ Por lo que:
$$\overrightarrow{J} = \frac{dI}{ds}dI = \overrightarrow{J}.d\overrightarrow{s} \longrightarrow I = \iint\overrightarrow{J}.d\overrightarrow{s}$$
Si sustitutimos la ecuación (31) eb la (29) obtenemos:
$$\iint (\nabla \times \overrightarrow{H}).d\overrightarrow{l} = \iint\overrightarrow{J}.d\overrightarrow{s}$$
Eliminando la integral de superfice en ambas partes de la igualdad
obtenemos la cuarta ecuación de Maxwell:
$$\overrightarrow{J} = \nabla \times \overrightarrow{H}$$

# Ecuación de Helmholtz

En el caso de las ondas de WiFi, no tenemos por que tener en cuenta el
tiempo puesto que, al ser el período de la señal tan corto, la calidad
de la señal no cambiará con el tiempo. Al tratarse entonces de
soluciones estacionarias, podemos simplificar las ecuaciones de Maxwell
en una sola ecuación conocida como Ecuación de Helmholtz:
$$\nabla^2E+\frac{k^2}{n^2}E = f(x)$$ Donde k es la frecuencia espacial
de la señal WiFi y n es el índice de refracción del material donde se
encuentra la onda. Este índice en las paredes es un número complejo con
la siguiente interpretación:

-   La parte real determina la reflexión en las paredes.

-   La parte imaginaria determina la absorción de la pared.

La segunda parte de la igualdad, f(x) es alguna función fuente. Dada una
fuente de radiación y una geometría por la que propagarse, la ecuación
de Helmholtz puede ser resuelta para todo el campo de radiación
E(x,y,z)[@canino1998numerical]. En la práctica encontrar esta solución
no es tribial, por ello he optado por un modelo 2D en este caso
práctico. De hecho, el punto principal de este estudio es el impacto de
las paredes en la potencia de la señal, donde la n es diferente del
aire, siendo en la pared de valor 1.

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
