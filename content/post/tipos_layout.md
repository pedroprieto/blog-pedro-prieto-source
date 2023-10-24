+++
title = "Tipos de layouts"
date = 2019-10-28T13:15:00+01:00
tags = ["css", "layout"]
categories = ["diw", "diw-estilos-multimedia"]
draft = false
author = "Pedro Prieto"
+++

El _layout_ o **estructura** de un interfaz web es la manera de organizar o disponer los elementos visuales en la página. El diseño del layout determina la posición de cada uno de los elementos que componen el interfaz web (cabecera, menús, banners, contenido, etc.).

<!--more-->

Además, el diseño del layout comprende también una serie de decisiones que afectan a las siguientes **características**:

-   Tamaño de los márgenes.
-   Tamaño y posición de imágenes y figuras.
-   Número de columnas (o áreas) en que se divide la página.
-   Áreas dejadas en blanco intencionadamente.


## Santo Grial {#santo-grial}

Uno de los patrones de diseño más utilizados es un diseño formado por varias (normalmente tres) columnas, con el contenido principal ocupando una de ellas (normalmente en el centro) y el resto de elementos (menús, banners,...) en las otras columnas. Las columnas idealmente deben tener la misma altura independientemente de su contenido y opcionalmente pueden tener bordes o colores de fondo diferenciados.

{{< figure src="/ox-hugo/holy_grial.png" alt="Diseño de Santo Grial" caption="<span class=\"figure-number\">Figure 1: </span>Diseño de Santo Grial" link="../../images/02_02_holy_grial.png" >}}

Aunque parece sencillo de conseguir, no hay ninguna solución óptima para este diseño. Todas ellas tienen algún inconveniente:

-   Visualización incorrecta en algún navegador.
-   Utilización de muchas etiquetas HTML.
-   Utilización de etiquetas HTML sin significado semántico (es decir, que se utilicen no para estructurar el contenido, sino para alterar la apariencia visual).
-   Adaptación incorrecta en dispositivos móviles.
-   Necesidad de utilizar lenguaje de script.


## Métodos antiguos {#métodos-antiguos}


### Tablas {#tablas}

-   Problemas semánticos.
-   Mezcla de estructura (HTML) con presentación visual.
-   Difícil de mantener.
-   Problemas con lectores de pantalla.
-   Problemas de tiempo de respuesta de los navegadores.

{{< figure src="/ox-hugo/layout_tables.png" alt="Diseño basado en tablas" caption="<span class=\"figure-number\">Figure 2: </span>Diseño basado en tablas" link="../../images/02_02_tables.png" >}}


### Posicionamiento absoluto {#posicionamiento-absoluto}

-   Rígido e inflexible.
-   Utilizado para versiones que deban ser impresas
-   Unidades de medida absolutas (cm, mm,...).


### Anchura fija {#anchura-fija}

-   Muy popular.
-   Se crea una capa contenedora que alberga todo el contenido de la página.
-   Se asigna una anchura fija al contenedor: típicamente un tamaño de 980px, 960px o 760px.
-   El contenedor se centra automáticamente cuando se muestra en una pantalla grande.
-   Aparece una barra de desplazamiento horizontal cuando se muestra en una pantalla pequeña.
-   Utiliza el píxel como unidad de medida principal.

Ventajas:

-   Ajuste perfecto. Son sitios que hacen uso de gran cantidad de imágenes y estructuras muy complejas. Necesitan controlar exactamente el tamaño de las capas para que las imágenes acoplen perfectamente.
-   Fácil de desarrollar y mantener.

Desventajas:

-   Poco usabilidad en pantallas pequeñas.
-   No se adaptan correctamente a dispositivos móviles.
-   No se adaptan correctamente frente a un aumento de zoom o aumento del tamaño del texto.


## Diseño responsivo {#diseño-responsivo}

Los métodos actuales de diseño de layouts suelen tener las siguientes características:

-   No utilizan anchuras fijas.
-   Se adaptan correctamente a pantallas pequeñas y grandes.
-   Utilizan unidades CSS relativas (ems, rems, porcentajes, valores mínimos y máximos,...).
-   Utilizan media queries CSS3 para proporcionar versiones distintas a cada dispositivo en función de su resolución de pantalla.

Ventajas:

-   Muy buena experiencia de uso independientemente del dispositivo o tamaño de pantalla elegido.

Desventajas:

-   Todos los dispositivos reciben todo el código independientemente de si lo van a utilizar o no.
-   Difícil de desarrollar y testear.
-   No hay un control perfecto a nivel de píxel: por tanto, puede ser difícil adaptar imágenes de tamaño fijo.

Ejemplos:

-   <http://designmodo.com/responsive-design-examples/>
-   <http://seesparkbox.com/>


### Conclusiones {#conclusiones}

Independientemente del modelo de layout elegido, el objetivo que se persigue es:

-   Proporcionar a los usuarios una buena **experiencia de uso**.
-   Servir una página web que funcione y se comporte de manera óptima independientemente del dispositivo o tamaño de pantalla utilizado sin comprometer la experiencia de uso.
