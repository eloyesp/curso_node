# Qué es Node

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

JavaScript está re-bueno por varias razones, tiene una idea de objetos simple y
a la vez clara, los objetos son lo que en otros lenguajes llamaríamos
diccionarios o hash. Un conjunto de valores asociados a claves, pero algunas de
estos valores son funciones (que en otros lenguajes serían métodos).

Por otro lado, las funciones son objetos por lo tanto además de llamarlas
podemos tratarla como un dato más, pasarla como argumento en otra función, etc.

Esta flexibilidad permite hacer cosas muy interesantes de forma bastante
concisa (aunque a veces un poco críptica al principio).

Pero la plataforma tiene algo más que solo JavaScript, tiene una forma
particular de escribir javascript mediante el uso de módulos y los módulos son
simplemente un objeto, en la mayoría de los casos una función.

## Lo mejor

Sin embargo lo mejor de node no es node, sino el gestor de paquetes NPM (node
package manager), que aprovecha la modularización de node para hacer
paquetes muy poco acoplados que proveen mucha flexibilidad.
