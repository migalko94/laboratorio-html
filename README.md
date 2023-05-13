# Laboratorio HTML

> El proyecto consiste en implementar una página web de una tienda de ropa

> Aquí describiremos la estructura básica del proyecto

## Introducción

El proyecto tiene su _html_ con el nombre por defecto _index_, su hoja de estilos externa en CSS con el también genérico _style_ y los recursos empleados como las imágenes de las tarjetas, las fuentes y los iconos en una carpeta llamada _assets_.

## Tipografía

Se han llamado la fuente de _Google fonts_ a través de `@font-face`, puesto que así mejoraríamos la velocidad de carga del sitio al evitar solicitudes externas.

## `title`

- El `title` de la página web es "Nuevas colecciones".

## Aplicación estilos

La forma de aplicación de estilos es a través de una hoja CSS **externa**.

## `border-box`

Se ha cambiado del valor por defecto `content-box` a `border-box` intentando seguir buenas prácticas y evitar problemas que pudiesen surgir en el cálculo de medidas. Esto se ha hecho con el "selector" universal ("\*").

## Barra de navegación

La barra de navegación está compuesta por los iconos _svg_ y el texto. A los iconos les hemos dado un _alt_ descriptivo. Como está en construcción, se vincula a un _href_ aleatorio "#".

La barra de navegación se mantiene fija al hacer _scroll_. Creamos un conjunto ("menú") que queríamos mantener fijo que era no sólo la barra de navegación sino también la línea horizontal `<hr/>` inferior.

Previamente a la solución ofrecida, se intentó posicionamiento _sticky_ con _z index_ distintos para el global ("\*") y el `.stickymenu` (nombre último de este conjunto), pero no lo resolvíamos porque, de una forma u otra, se veían superpuestos los elementos: o veíamos de fondo el conjunto y las imágenes de las tarjetas ocupaban sólo su espacio, o, viceversa, el conjunto aparecía por delante cubriendo las imágenes.

El posicionamiento _fixed_ nos apilaba los ítems de la barra de navegación de formas no deseadas.

Se ha solventado finalmente gracias al posicionamiento _sticky_ y la superposición de elementos la hemos resuelto aplicando un _background color_ en CSS que la oculta.

Se ha animado el texto y los iconos de la barra de navegación con _keyframes_ como se explica más adelante.

La barra de navegación se ha construido gracias a _Flexbox_. Gracias al `space-between`, hemos distribuido uniformemente los _items_, que se reparten equitativamente. Con el `flex-flow`, en concreto con _wrap_, conseguimos que sea _responsive_.

## `<hr/>`

Con esta etiqueta, hemos creado la línea horizontal que separa la barra de navegación del `h1` que hemos asignado a "Nuevas colecciones".

## `h1` "Nuevas colecciones"

Hemos nombrado "Nuevas colecciones" como el `h1` de nuestra página web.

## Tarjetas

A continuación, vienen las tarjetas en una disposición tipo tabla 3x2 con su pie de página que establece el producto con su precio.
Las imágenes tienen su _title_ descriptivo.

En este punto, nos hemos ayudado de _Grid Layout_ para que sea _responsive_. Hemos ido probando sobre el `min` de `minmax` en base también a entender como referencia los 1280px de ancho de pantalla en diseño.

El pie de página se ha realizado con _FlexBox_ anidado en el _Grid Layout_.

## Footer

Es muy similar a cómo se construyó la barra de navegación.

Lo diferencial del _Footer_ se destaca, sin embargo, principalmente, por el _svg_ recortado a modo de círculo. Se investigaron múltiples formas de cómo podíamos obtener el resultado visual.

Recortarlo como si fuese una imagen al uso no dió resultado porque no estaba ajustada la figura del icono (por ejemplo, se cortaban los laterales).

La mejor solución fue crear un círculo y después introducir dentro el icono. Para ello, tuvimos que examinar las dimensiones del _svg_ con el inspector web de las herramientas de desarrollo web (0 0 34 34) y orientativamente hacer las dimensiones del círculo además de centrarlo.

## Animaciones

Por último, hemos animado con `hoover` las tarjetas y los _items_ de la barra de navegación. Lo hemos hecho llamando la función `@keyframes` con nuestra categoría creada bajo el nombre de `webanimation`. Se ha optado por mantener un efecto "chicle".

> Fin del laboratorio.
