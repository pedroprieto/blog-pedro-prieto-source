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

-   **Compilación y enlace** - Los ficheros de código fuente se transforman a ficheros de código máquina o **ficheros objeto**. Posteriormente, el **enlazador** genera un ejecutable a partir de los ficheros de código máquina, conectándolos con las librerías adicionales necesarias para su funcionamiento.
-   **Interpretación** - Los ficheros de código fuente no se transforman a código máquina: en lugar de ello, un programa, denominado **intérprete**, lee línea a línea el código fuente y va realizando la compilación de cada línea de manera independiente.
-   **Compilación JIT** o _Just In Time_ - Los ficheros de código fuente no se transforman a código máquina: en su lugar, un programa se encarga de realizar la compilación **en el momento de la ejecución**. Se trata de un híbrido entre la compilación y la interpretación.

{{< figure src="/ox-hugo/compilacion.png" caption="<span class=\"figure-number\">Figure 1: </span>Ejemplo de compilación" >}}

{{< figure src="/ox-hugo/interpretacion.png" caption="<span class=\"figure-number\">Figure 2: </span>Ejemplo de interpretación" >}}

{{< figure src="/ox-hugo/jit.png" caption="<span class=\"figure-number\">Figure 3: </span>Ejemplo de compilación JIT" >}}


## Enlazador (_linker_) {#enlazador--linker}

El enlazador es el programa que se encarga de **combinar** los **ficheros objeto** en un **único objeto o fichero ejecutable**. El enlazador puede funcionar de dos maneras: **estática** y **dinámica**:

-   Al enlazar de manera **estática**, las **librerías** de las que depende el programa principal quedan **integradas** en el fichero ejecutable final.
-   Al enlazar de manera **dinámica**, las **librerías** de las que depende el programa principal **no se incorporan al ejecutable final**. En su lugar, el programa final, cuando se **ejecuta**, busca las librerías en **ficheros externos**. Estas librerías externas pueden estar instaladas en el sistema operativo donde se ejecuta el programa o pueden distribuirse junto a él mediante un **paquete** o instalador, o a través de algún sistema de **virtualización**, como máquinas virtuales o contenedores.


## Intérpretes {#intérpretes}

Un intérprete es un programa que se encarga de **ejecutar instrucciones** escritas en un determinado lenguaje de programación. El intérprete ejecuta las instrucciones de **una en una**, **sin** tener que realizar ningún paso de **compilación** previo.

En ocasiones se habla de **lenguajes interpretados** o **lenguajes compilados**. En realidad, la mayoría de lenguajes podrían soportar ambos modelos. Así, cuando se dice que un programa es interpretado o compilado, lo que se quiere decir es que la implementación "canónica" o más habitual de dicho programa funciona de esa manera determinada.


## Compilación JIT {#compilación-jit}

La compilación JIT, o _Just in Time_, es un mecanismo de compilación que se realiza **durante la ejecución** del programa. Por tanto, elimina la necesidad de realizar un paso previo de compilación.

La compilación JIT en ocasiones realiza la traducción de código fuente a código ejecutable, aunque en muchos casos lo que se realiza es una traducción de un tipo de lenguaje especial, el **bytecode**, a código ejecutable.


## ByteCode {#bytecode}

Bytecode es un tipo de formato de código **intermedio**, normalmente de tipo **binario**. Se utiliza habitualmente para **reducir la dependencia del hardware** donde se ejecuta el programa. Una vez compilado el código fuente a bytecode, éste se ejecuta sobre algún tipo de **máquina virtual**. De esta manera, el programa compilado podrá ejecutarse en cualquier sistema que tenga instalada dicha máquina virtual.

El ejemplo más famoso de lenguaje que utiliza bytecode es **Java**. El código fuente de Java se compila a bytecode, por ejemplo, un fichero `jar`. Dicho fichero bytecode puede ejecutarse en la **Máquina Virtual Java** (**JVM**, o _Java Virtual Machine_). Así, en cualquier equipo donde esté instalada la JVM podrá ejecutarse dicho programa.

{{< figure src="/ox-hugo/bytecode.png" caption="<span class=\"figure-number\">Figure 4: </span>Ejemplo de compilación Bytecode" >}}


## Virtualización {#virtualización}

La **virtualización** permite la ejecución de un programa en un **entorno aislado**. De esta manera se garantiza que las aplicaciones **no interfieran** unas con otras, o que tengan acceso exclusivo a sus recursos, **sin afectar al resto de aplicaciones**.

En ocasiones, diferentes aplicaciones necesitan acceder a diferentes librerías, o incluso a versiones diferentes de las mismas librerías. Si esas librerías necesitan ser cargadas de manera **dinámica**, en tiempo de ejecución, deben estar disponibles en el entorno donde se ejecuta dicha aplicación. Pongamos por ejemplo una aplicación que necesita la versión 1 de la librería `lib1`, y que una segunda aplicación necesita la versión 2 de la misma librería. Es posible que solo una de ellas pueda estar disponible a la vez, por lo que una de las aplicaciones podría no funcionar correctamente al no encontrar la versión que necesita:

{{< figure src="/ox-hugo/libreria_compartida.png" caption="<span class=\"figure-number\">Figure 5: </span>Conflicto de dependencias" >}}

Mediante la virtualización, sería posible ejecutar cada aplicación en un entorno aislado independiente, por lo que cada entorno podría tener instalada su propia versión de la librería necesaria:

{{< figure src="/ox-hugo/virtualizacion.png" caption="<span class=\"figure-number\">Figure 6: </span>Ejemplo de virtualización" >}}

Existen diferentes posibilidades para implementar esa virtualización. Algunas de las opciones son las siguientes:

-   **Dependencias de proyecto** - No es estrictamente un tipo de virtualización, pero está relacionado con el tema que nos ocupa. En el desarrollo de aplicaciones, cada aplicación puede instalar las dependencias necesarias para su funcionamiento en una **carpeta de proyecto**. De esta manera, las **versiones** necesarias de las librerías **no se instalan a nivel de sistema**, sino que se instalan a nivel de proyecto.
-   **Máquina virtual de aplicación o proceso** - Son programas software que se encargan de **ejecutar aplicaciones** de manera **independiente del hardware**. Normalmente, estas máquinas **ejecutan bytecode**. La **Máquina Virtual de Java**, JVM, es su ejemplo más paradigmático.
-   **Máquina virtual de sistema** - Son las máquinas virtuales completas, que usualmente integran un **sistema operativo invitado**. Aplicaciones como **VirtualBox** o **VMWare** permiten crear este tipo de máquinas. Las aplicaciones que se ejecutan dentro de este tipo de máquinas virtuales tienen **acceso exclusivo a un sistema operativo**. De esta manera, todas las librerías que se instalen dentro de una máquina virtual no interferirán con las del resto de máquinas virtuales.
-   **Contenedores** - También llamados sistemas de **virtualización ligera**. Permiten **encapsular aplicaciones, junto con sus librerías y configuración**, en un formato específico que puede ser desplegado mediante un **motor de contenedores**. El más popular es **Docker**. Los contenedores se diferencian de las máquinas virtuales de sistema en que **no incorporan sistema operativo invitado**.

{{< figure src="https://upload.wikimedia.org/wikipedia/commons/f/f9/Dockervsvm.jpg" caption="<span class=\"figure-number\">Figure 7: </span>Docker vs MV Drinkler, CC BY-SA 4.0 <https://creativecommons.org/licenses/by-sa/4.0>, via Wikimedia Commons" >}}
