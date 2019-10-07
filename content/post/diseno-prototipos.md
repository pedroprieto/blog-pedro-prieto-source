+++
title = "Diseño de prototipos"
date = 2019-10-07T11:01:00+02:00
tags = ["prototipos", "diseño", "moqups", "wireframe", "mockup"]
categories = ["diw", "diw-planificacion-interfacesweb"]
draft = false
+++

En todo proyecto de desarrollo web es recomendable realizar un prototipo o boceto del interfaz. De esta manera se puede tener una idea aproximada del aspecto visual que tendrá, qué secciones lo compondrán, cómo se verá en pantalla, etc.

<!--more-->

El principal objetivo es generar un boceto de manera rápida, sin necesidad de utilizar código. Estos bocetos permiten acordar las características del interfaz web con el cliente o con el resto de miembros del equipo de desarrollo.

Como paso previo a la creación de un prototipo es necesario [haber planificado adecuadamente la interfaz](/post/planificacion-fundamentos) y haber acordado las [normas de diseño y el aspecto visual](/post/planificacion-guia-estilo) del sitio.

Existen varias posibilidades para crear prototipos:

-   **Papel** - Es la opción más rápida y sencilla.
-   **Digital** - Hace uso de algún programa de edición sencillo. Puede ofrecer algo de funcionalidad (interacción con enlaces, por ejemplo).
-   **Nativo** - Está implementado haciendo uso de las tecnologías reales de la aplicación. Normalmente se utiliza como último paso antes del lanzamiento del producto.


## Prototipos en papel {#prototipos-en-papel}

{{< figure src="https://upload.wikimedia.org/wikipedia/commons/thumb/6/67/Paper%5Fprototype%5Fof%5Fwebsite%5Fuser%5Finterface%2C%5F2015-04-16.jpg/640px-Paper%5Fprototype%5Fof%5Fwebsite%5Fuser%5Finterface%2C%5F2015-04-16.jpg" caption="Figura 1: Prototipo de papel. Fuente: Wikimedia" >}}

Los prototipos en papel ofrecen una primera aproximación al diseño de la interfaz. Pueden realizarse tan sencillos como se desee (en blanco y negro, en la típica servilleta de bar que se pone como ejemplo de germen de todas las grandes ideas,...) o con un nivel de complejidad más elevado (utilizando distintos tipos de papeles, colores, materiales,...).

La principal ventaja de este tipo de prototipos es que no necesitan de ningún tipo de conocimiento técnico. Por lo tanto, se suelen utilizar como una primera aproximación para el diseño de la interfaz.

Una vez creados en papel los bocetos de las distintas páginas que componen el sitio se pueden tomar **fotografías** para simular determinadas interacciones y estados de la aplicación. Esas imágenes pueden utilizarse a su vez para crear **animaciones** y distribuir el prototipo de manera más eficiente sin la necesidad de tener que cargar con el papel de un lado a otro.

En el siguiente enlace se puede consultar un vídeo sobre cómo Google utiliza este tipo de prototipos: [Rapid Prototyping 1 of 3: Sketching & Paper Prototyping](https://www.youtube.com/watch?v=JMjozqJS44M).


## Prototipos digitales {#prototipos-digitales}

{{< figure src="/./prototipo.png" caption="Figura 2: Prototipo digital" >}}

Para la creación de estos prototipos se hace uso de alguna herramienta específica de edición. El objetivo es crear un boceto **más parecido a la realidad** que incluso pueda ofrecer un mínimo nivel de **interactividad**. El diseño puede ser exportado a un **archivo de imagen**, **HTML** o **PDF** para adjuntar a la documentación del proyecto.

En el siguiente enlace se puede consultar un vídeo sobre cómo Google utiliza este tipo de prototipos: [Rapid Prototyping 2 of 3: Digital Prototyping](https://www.youtube.com/watch?v=KWGBGTGryFk&t=246s).


## Prototipos nativos {#prototipos-nativos}

{{< figure src="https://upload.wikimedia.org/wikipedia/commons/e/e2/Responsive%5FWeb%5FDesign.png" caption="Figura 3: Prototipo nativo" >}}

Los prototipos nativos utilizan las **mismas tecnologías** (lenguajes de programación, librerías,...) y **dispositivos** (teléfonos móviles, pantallas,...) que utilizará la **aplicación real**. Se utilizan por tanto como **último paso** antes del desarrollo de la aplicación real. Una vez el prototipo ha sido correctamente testado en los dispositivos en los que se va a utilizar puede integrarse en la aplicación junto con el resto de componentes (lógica de negocio y almacenamiento de datos).

En el siguiente enlace se puede consultar un vídeo sobre cómo Google utiliza este tipo de prototipos: [Rapid Prototyping 3 of 3: Native Prototyping](https://www.youtube.com/watch?v=lusOgox4xMI).


## Diseño web adaptable - Mobile First {#diseño-web-adaptable-mobile-first}

La tendencia actual consiste en diseñar siguiendo la teoría de **Mobile First**, o **Móvil primero**. Esta teoría aboga por realizar el diseño pensando en dispositivos móviles y a continuación añadir o modificar características para adaptar el diseño a otro tipo de dispositivos con pantallas más grandes.

La elección de este patrón de diseño se debe a que **[los buscadores dan más peso a los sitios web optimizados para dispositivos móviles](https://developers.google.com/search/mobile-sites/mobile-first-indexing)** dado que la mayoría de usuarios que se conectan a Internet lo hacen mediante este tipo de dispositivos.

Una vez creado el diseño para móvil se procede a crear las versiones para pantallas más grandes. De esta manera el sitio web **se adapta a distintos tipos de pantallas** siguiendo el [patrón de diseño web adaptativo](https://es.wikipedia.org/wiki/Dise%C3%B1o%5Fweb%5Fadaptable).


## Herramientas de creación de prototipos digitales {#herramientas-de-creación-de-prototipos-digitales}

Existe un gran número de herramientas para creación de prototipos. Muchas de ellas son de pago, aunque hay alternativas gratuitas con una funcionalidad algo más reducida pero que puede ser suficiente para realizar un boceto rápido. Algunas de ellas se enumeran a continuación:

-   [Figma](https://www.figma.com/) - Herramienta online. Comercial. Gratuita para 3 proyectos.
-   [Pencil](http://pencil.evolus.vn/) - Programa de escritorio. Open Source.
-   [wireframe.cc](https://wireframe.cc/) - Herramienta online. Comercial. Ofrece demo gratuita.
-   [Moqups](https://moqups.com/) - Herramienta online. Comercial. Ofrece cuentas gratuitas a estudiantes y proyectos Open Source.
-   [Principle](http://principleformac.com/) - Herramienta para Mac. Comercial.
-   [proto.io](https://proto.io/) - Herramienta online. Comercial.
-   [Marvel](https://marvelapp.com/) - Herramienta online. Comercial. Ofrece un plan gratuito para un proyecto.
-   [InVision](https://www.invisionapp.com/) - Herramienta online. Comercial. Ofrece un plan gratuito para un proyecto.
-   [mockup.io](https://mockup.io/) - Herramienta online. Comercial.
-   [Ninja Mock](https://ninjamock.com/) - Herramienta online. Comercial.
-   [Balsamiq](https://balsamiq.com) - Herramienta de escritorio y online. Comercial.


## Otros recursos {#otros-recursos}

A continuación se enumeran algunos enlaces que pueden ser de utilidad en la creación de prototipos:

-   [Lorem Ipsum](https://es.lipsum.com/) - Generador de textos de relleno.
-   [Smashing Magazine](https://www.smashingmagazine.com/) - Sitio web relacionado con el desarrollo y diseño web.
-   [Web Yurt](http://www.webyurt.com/) - Sitio web relacionado con el desarrollo y diseño web.
-   [Creative Bloq](https://www.creativebloq.com) - Sitio web dedicado al arte y diseño gráfico.
