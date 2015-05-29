## Qué es Node

Node no es un lenguaje de programación ni un interprete, entonces ¿qué es?
Según la página es una plataforma para construir aplicaciones, o sea que podría
ser considerado un framework.

El lenguaje que se utiliza es JavaScript, el interprete es node, que está
basado en V8 el interprete JavaScript de Chromiun.^[ O sea que si, también es un
interprete.]

## Lo interesante

JavaScript es un lenguaje interesante en sí, pero estaba encerrado en el
navegador cosa que lo hace un poco menos útil. Node permite usarlo en el
servidor, permite hacer aplicaciones *en serio* usandoló y abre así muchas
oportunidades interesantes.

## JavaScript

JavaScript está re-bueno por varias razones, tiene una idea de objetos simple y
a la vez clara, los objetos son lo que en otros lenguajes llamaríamos
diccionarios o hash. Un conjunto de valores asociados a claves, pero algunas de
estos valores son funciones (que en otros lenguajes serían métodos).

Por otro lado, las funciones son objetos por lo tanto además de llamarlas
podemos tratarla como un dato más, pasarla como argumento en otra función, etc.

Esta flexibilidad permite hacer cosas muy interesantes de forma bastante
concisa (aunque a veces un poco críptica al principio).

Otra ventaja del lenguaje es que el eje está puesto en los eventos y
procesamiento asíncrono de forma que facilita el desarrollo de aplicaciones
distribuidas que se pueden comunicar mediante eventos evitando bloqueos.

## Módulos

Pero la plataforma tiene algo más que solo JavaScript, tiene una forma
particular de escribirlo mediante el uso de módulos. Los módulos son
simplemente un archivo javascript, que exporta simplemente un objeto, en
la mayoría de los casos una función.

## No hay estado

Otra ventaja del require de Node, es que los módulos están fuertemente
encapsulados, de forma en que se hace posible disminuir el estado. O sea,
tenemos a disposición la principal ventaja de la programación funcional sin
pagar el precio.

Esto significa que cuando uno hace `var http = require('connect');` eso no
afecta el estado de la aplicación más que en el valor de la variable http. Eso
no es menor, en ruby eso es lisa y llanamente imposible, e incluso en
javascript es imposible (WAT!).

Obviamente que podemos hacer las cosas mal y afectar el estado global desde
dentro de un módulo, pero eso es un **gran** error y debe ser evitado!

## Actividad

Escribir un hola mundo usando node. Hay que usar require!
