+++
title = "Estrategias de diseño con CSS"
date = 2019-10-22T11:51:00+02:00
tags = ["css", "BEM"]
categories = ["diw", "diw-estilos-multimedia"]
draft = false
+++

En ocasiones resulta difícil pensar en cómo abordar el diseño con CSS. Las recomendaciones actuales van en la línea de priorizar el **uso de clases** para poder utilizarlas dentro de los archivos HTML. Dentro de esta recomendación nos encontramos con dos posibilidades: priorizar el **diseño de componentes** o priorizar el diseño de **clases de utilidades**.

<!--more-->


## Diseño basado en componentes {#diseño-basado-en-componentes}

Esta filosofía de diseño prioriza el desarrollo de clases CSS que hagan referencia a **componentes** creados en HTML. Un componente puede ser una tarjeta, un menú, un formulario o un botón. De esta manera tendríamos CSS como el siguiente:

```css
.card {
    background: white;
    border: 1px solid grey;
    text-align: justify;
}

.card--left {
    text-align: left;
}

.card--right {
    text-align: right;
}

.tooltip {
    background: black;
    color: white;
    text-align: center;
}
```

Como podemos ver, las clases CSS hacen referencia a componentes que serán creados en HTML.

Dentro de este tipo de diseño podemos distinguir dos enfoques: el primero sería la creación de clases CSS **anidadas**:

```html
<div class="autor">
  <img src="" alt="">
  <div class="contenido">
    <h2 class="nombre">Juan Gómez</h2>
  </div>
</div>
```

```css
.autor {
    background-color: white;
    border: 1px solid hsl(0,0%,85%);
    border-radius: 4px;
    box-shadow: 0 2px 4px rgba(0,0,0,0.1);
    overflow: hidden;
}
.autor img {
    display: block;
    width: 100%;
    height: auto;
}
.autor .contenido {
    padding: 1rem;
}
.autor .nombre {
    font-size: 1.25rem;
    color: rgba(0,0,0,0.8);
}
```

El segundo sería la creación de clases CSS **independientes** (uno de los ejemplos más utilizados es la metodología [BEM](http://getbem.com/naming/)):

```html
<div class="autor">
  <img class="autor__img" src="" alt="">
  <div class="autor__contenido">
    <h2 class="autor__nombre">Juan Gómez</h2>
  </div>
</div>
```

```css
.autor {
    background-color: white;
    border: 1px solid hsl(0,0%,85%);
    border-radius: 4px;
    box-shadow: 0 2px 4px rgba(0,0,0,0.1);
    overflow: hidden;
}
.autor__img {
    display: block;
    width: 100%;
    height: auto;
}
.autor__contenido {
    padding: 1rem;
}
.autor__nombre {
    font-size: 1.25rem;
    color: rgba(0,0,0,0.8);
}
```


### Ventajas: {#ventajas}

-   Se prioriza el significado **[semántico](https://developer.mozilla.org/en-US/docs/Glossary/Semantics)** de las clases: los nombres de clase hacen referencia a entidades con significado dentro de la estructura HTML, ya que hacen referencia a componentes con una funcionalidad definida.
-   Produce un código **fácil de leer**.
-   Se crea código **estructurado** en función de los distintos componentes que tenga la página.


### Desventajas: {#desventajas}

-   Las clases van asociadas a una determinada estructura HTML, por lo que resulta **difícil reutilizarlas**.
-   La creación **variaciones de un tipo de componente** es complicada: normalmente supone duplicar código CSS, modificar el HTML o crear clases que deshagan las acciones creadas por la clase original.
-   Se favorece el paradigma de **herencia** sobre el de **composición**: normalmente acaban creándose múltiples niveles de abstracciones que se van heredando para dar servicio a todos los posibles casos.


## Diseño basado en clases de utilidades {#diseño-basado-en-clases-de-utilidades}

Por el contrario, este paradigma de diseño prioriza el desarrollo de clases CSS que implementen **pequeñas funcionalidades** que puedan ser reutilizadas por todos los elementos o componentes de la página. Un ejemplo de código sería el siguiente:

```css
/* Font sizes */
.font-13 { font-size: 13px }
.font-16 { font-size: 16px }
...

/* Font styles */
.font-bold { font-weight: bold }
.font-italic { font-style: italic }
...

/* Font colors */
.font-purple { color: purple }
...
```

Como podemos ver, las clases CSS hacen referencia a características genéricas no asociadas a ningún componente o estructura HTML específica: pueden ser utilizadas por multitud de ellos (enlaces, encabezados, menús, botones,...).


### Ventajas: {#ventajas}

-   El código CSS resulta altamente **reutilizable**, ya que las clases no suelen estar asociadas a estructuras HTML determinadas o con función específica.
-   Favorece el patrón de **[composición sobre herencia](https://en.wikipedia.org/wiki/Composition%5Fover%5Finheritance)**, por lo que la creación de componentes ligeramente distintos de los originalmente planteados resulta más fácil que con el patrón de diseño basado en componentes.


### Desventajas: {#desventajas}

-   Aumenta el número de clases a aplicar en etiquetas HTML, por lo que el código HTML puede resultar más difícil de leer:

<!--listend-->

```html
<h2 class="font-16 font-bold font-purple">Game of Thrones</h2>
```

-   Aumenta el número de clases disponibles, por lo que puede resultar difícil conocerlas todas o saber cuál aplicar.


## Conclusión {#conclusión}

Como hemos podido ver, tenemos dos posibilidades de enfocar el diseño de clases en CSS. ¿Cuál deberíamos elegir? La respuesta depende por supuesto de las metodologías de trabajo, el tipo de proyecto y las elecciones personales. Quizá la mejor opción sería optar por una aproximación del tipo **clases de utilidades Primero** y proceder a una posterior **abstracción** en forma de componentes cuando se vean **patrones repetidos**.


## Referencias {#referencias}

-   <http://getbem.com/>
-   <https://frontstuff.io/in-defense-of-utility-first-css>
-   <https://adamwathan.me/css-utility-classes-and-separation-of-concerns/>
