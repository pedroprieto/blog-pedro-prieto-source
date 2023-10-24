+++
title = "Lenguajes de programación"
date = 2023-10-24T13:16:00+02:00
tags = ["lenguaje", "programacion"]
categories = ["puestaprodseg", "puestaprodseg-lenguajes"]
draft = false
author = "Pedro Prieto"
+++

## Código fuente {#código-fuente}

Conjunto de ficheros que almacenan **texto** escrito en un lenguaje legible por el ser humano. Dicho lenguaje, denominado **lenguaje de programación**, tiene una sintaxis específica. El texto escrito en dicho lenguaje especifica las **acciones** que llevará a cabo el programa cuando se ejecute.

El código fuente debe traducirse a **código máquina** para que pueda ser ejecutado en un computador mediante un proceso denominado **compilación**.

[Código fuente en la Wikipedia](https://en.wikipedia.org/wiki/Source_code).


## Código máquina, arquitectura y sistemas operativos {#código-máquina-arquitectura-y-sistemas-operativos}

El código máquina, también denominado código ejecutable, contiene las **instrucciones** que deberá ejecutar un computador en su CPU para que pueda funcionar el programa correspondiente.

El código máquina depende de la **arquitectura** del computador para la que se haya generado: el **conjunto de instrucciones** soportado por el procesador. Por ello, el código máquina de un programa suele ser **incompatible** con **otras arquitecturas** para las que no ha sido producido.

Ejemplos de arquitecturas:

-   x86
-   Arm
-   Arm64
-   PowerPC

El código máquina también depende del **sistema operativo** para el que se haya generado: normalmente, el código fuente utiliza una serie de **librerías** para utilizar funciones específicas de un sistema operativo (acceso al sistema de ficheros, redes, elementos hardware,...). Cuando se ejecuta, el programa hace uso de esas librerías, que están en el Sistema Operativo en cuestión.

[Código máquina en la Wikipedia](https://en.wikipedia.org/wiki/Machine_code).


## Compilación {#compilación}

La **compilación** es el proceso de generación de ejecutables a partir del código fuente. Existen varias métodos:

-   **Compilación y enlace** - Los ficheros de código fuente se transforman a ficheros de código máquina. Posteriormente, el **enlazador** genera un ejecutable a partir de los ficheros de código máquina, conectándolo con las librerías adicionales necesarias para su funcionamiento.
-   **Interpretación** - Los ficheros de código fuente no se transforman a código máquina: en lugar de ello, un programa, denominado **intérprete**, lee línea a línea el código fuente y va realizando la compilación de cada línea de manera independiente.
-   **Compilación JIT** o _Just In Time_ - Los ficheros de código fuente no se transforman a código máquina: en su lugar, un programa se encarga de realizar la compilación **en el momento de la ejecución**. Se trata de un híbrido entre la compilación y la interpretación.

{{< figure src="/ox-hugo/compilacion.png" >}}

{{< figure src="/ox-hugo/interpretacion.png" >}}

{{< figure src="/ox-hugo/jit.png" >}}


## Enlace {#enlace}


## Intérpretes {#intérpretes}


## Compilación JIT {#compilación-jit}


## ByteCode {#bytecode}

-   .NET
-   Java
-   Python, JavaScript (JIT)


## Sintaxis {#sintaxis}


### Variables {#variables}


### Tipos de datos {#tipos-de-datos}


### Condicionales {#condicionales}


### Bucles {#bucles}


### Asignación {#asignación}


### Funciones {#funciones}


## Módulos, clases, ficheros {#módulos-clases-ficheros}
