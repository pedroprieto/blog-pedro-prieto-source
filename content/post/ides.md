+++
title = "Entornos de desarrollo"
date = 2023-10-24T15:28:00+02:00
categories = ["puestaprodseg", "puestaprodseg-lenguajes"]
draft = false
author = "Pedro Prieto"
+++

Para trabajar con lenguajes de programación, no basta con utilizar un editor de texto: es recomendable contar con una serie de **herramientas adicionales** que nos ayuden en el proceso de desarrollo o pruebas.

<!--more-->

Al conjunto de herramientas que, junto con el editor, se utilizan para el desarrollo de código, se le denomina **entorno de desarrollo**, o `IDE` (_Integrated Development Environment_);

A continuación podemos ver algunas de las herramientas más útiles.


## Editor {#editor}

Herramienta fundamental. Se utiliza para editar el código fuente.


## Resaltado de sintaxis {#resaltado-de-sintaxis}

El _syntax highlighting_ es una característica que permite resaltar las palabras reservadas del lenguaje, así como sus estructuras (funciones, bucles, condicionales,...) para favorecer el proceso de desarrollo.


## Auto-completado de código {#auto-completado-de-código}

Esta característica ofrece opciones para completar el código que se está escribiendo, en tiempo real.


## Comprobación sintáctica {#comprobación-sintáctica}

Es muy útil contar con herramientas que nos indiquen en tiempo real si el código que hemos escrito está correctamente escrito y no tiene errores sintácticos. A este proceso se le denomina `linting`. Algunas de las comprobaciones que realizan son:

-   Las palabras reservadas están correctamente escritas
-   Las variables contienen tipos de datos válidos
-   Las variables referenciadas están definidas
-   Los nombres de función están correctamente escritos


## Refactorización y renombrado {#refactorización-y-renombrado}

En ocasiones es necesario cambiar el nombre de una variable o una función. Para ello, hay que cambiar su nombre en diferentes lugares: en la definición y en los sitios donde se utilice. Este proceso puede ser laborioso si se realiza de manera manual. Por ello, la mayoría de los IDEs ofrecen la opción de **renombrar** estos elementos.

En otro plano similar, es posible que en ocasiones sea necesario cambiar el código para optimizarlo, de manera que produzca los mismos resultados de manera más eficiente o más limpia. A este proceso se le denomina **refactorización**.


## Documentación {#documentación}

También es útil contar con la documentación del lenguaje de programación utilizado, así como las descripciones de las funciones y elementos de las librerías con las que se está trabajando. La mayoría de los IDEs muestran de manera contextual esta información.


## Control de versiones {#control-de-versiones}

La herramienta fundamental es `git`. Es recomendable que el IDE sea compatible con esta herramienta y nos proporcione un interfaz para:

-   Ver los archivos nuevos o modificados
-   Ver los archivos en el área de preparación
-   Mostrar los cambios realizados en el directorio de trabajo.
-   Añadir cambios al área de preparación y hacer commits.
-   Obtener y enviar cambios de los repositorios remotos.


## Interfaz de comandos {#interfaz-de-comandos}

La mayoría de los IDEs ofrecen la posibilidad de abrir un terminal de comandos para realizar acciones en la carpeta del código.


## Herramientas de construcción {#herramientas-de-construcción}

Es recomendable también que los IDEs dispongan de herramientas para construir (_build_) el proyecto. El proceso de construir consiste en transformar el código fuente en código máquina o código ejecutable.


## Herramientas de ejecución y depuración {#herramientas-de-ejecución-y-depuración}

Los IDEs suelen incluir también herramientas para ejecutar el código y hacer pruebas. Algunas características deseables son:

-   Ejecutar el programa
-   Ejecutar el programa en diferentes configuraciones
-   Ejecutar el programa llamándolo con diferentes parámetros
-   Ejecutar tests integrados
-   Establecer puntos de ruptura (_break points_). Los puntos de ruptura permiten interrumpir la ejecución del programa en una determinada línea de código. De esta manera se puede inspeccionar el estado de la ejecución(variables,...) y comprobar si se ejecuta el código tal como esperamos.


## IDEs tradicionales {#ides-tradicionales}

La mayoría de los lenguajes de programación tradicionales ofrecen un IDE de referencia para trabajar con ellos. Por ejemplo:

-   **Eclipse** - Utilizado para el desarrollo en Java principalmente, aunque soporta multitud de lenguajes (C#, C++,...).
-   **Netbeans** - Utilizado para Java, principalmente.
-   **IntelliJ IDEA** - Utilizado para Java, principalmente.
-   **Microsoft Visual Studio** - Utilizado por C#, C++ y otros muchos lenguajes. Se utiliza para desarrollar aplicaciones Windows, web o multiplataforma.
-   **PyCharm** - Utilizado por Python.
-   **Visual Studio Code** - Se considera también un editor, aunque ofrece muchas características de IDE. Se utiliza sobre todo en desarrollo web, para CSS, HTML, JavaScript y TypeScript. También se utiliza para desarrollo multiplataforma con flutter.


## Kits de desarrollo: SDK {#kits-de-desarrollo-sdk}

Los SDK (_Software Development Kit_) son paquetes de software que es necesario instalar en el equipo de desarrollo para poder crear programas con una determinada tecnología o lenguaje de programación.

Así, por ejemplo, para desarrollar programas en Java, es necesario instalar el JDK, _Java Development Kit_; para desarrollar programas en JavaScript, es necesario instalar un navegador o la plataforma **NodeJS**; o, para desarrollar programas en Python, es necesario instalar el intérprete del lenguaje y las librerías (utilidades) que vayamos a utilizar.

Si utilizamos un IDE específico, es posible que la **instalación del SDK** se realice de manera **automática** al instalar dicho IDE. Por ejemplo, Microsoft Visual Studio incorpora la posibilidad de instalar los SDK para el desarrollo de aplicaciones web o aplicaciones de escritorio; algunos IDEs de Java, como NetBeans, incorporan en sus instaladores el JDK.

Es importante tener en cuenta que la instalación de dichos **SDK** es **imprescindible** para el desarrollo en un lenguaje concreto. Sobre todo, si se va a utilizar algún IDE genérico o multilenguaje, dado que dichos IDEs no suelen incorporar ningún SDK.


## IDEs Cloud {#ides-cloud}

Como alternativa a la instalación de un IDE junto con el SDK correspondiente en el equipo local, se puede utilizar un **IDE Cloud**.

Los IDEs Cloud ofrecen la posibilidad de instalar un entorno de desarrollo **virtualizado** accesible a través de Internet.

En función del proveedor, el IDE se suele ofrecer en una **máquina virtual** o en un **contenedor**. Ambos entornos permiten la ejecución en servidores en la nube, de tal manera que son accesibles a través de una conexión web desde cualquier lugar.

Como **ventajas**, tenemos las siguientes:

-   Acceso sencillo a través del navegador
-   Acceso desde cualquier equipo
-   No es necesario instalar nada en el equipo local: todo está instalado en el entorno virtualizado
-   Posibilidad de colaboración entre diferentes personas
-   Copias de seguridad
-   Replicación sencilla en otros equipos o cuentas.

Como **inconveniente principal**, tenemos dos:

-   Coste. Suelen ser de pago, aunque hay descuentos para estudiantes.
-   Dependencia de Internet. Es necesario disponer de acceso a Internet para acceder al IDE.

Algunos de los IDEs Cloud más utilizados son:

-   [GitHub CodeSpaces](https://github.com/features/codespaces) - Entornos basados en contenedores.
-   [AWS Cloud9](https://aws.amazon.com/es/cloud9/) - Entornos basados en máquinas virtuales.
