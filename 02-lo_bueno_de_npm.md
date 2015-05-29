# Que aprendimos

Una de las mejores cosas que tiene NPM es las lecciones aprendidas, de otros
gestores de paquetes, no es tan lento como rubygems, el indice se descarga para
hacer búsquedas rápidas, las dependencias anidadas están resueltas, los valores
por defecto tienen sentido y la forma de correr los test está documentada.

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

## Dependencias anidadas

Dijimos que se podían utilizar distintas versiones de un mismo módulo, y esto
realmente ocurre en muchas aplicaciones, en el caso en que tenemos dependencias
molestas.

Las dependencias funcionan sobre el mecanísmo de funcionamiento de require en
node. Cuando uno usa require, node busca el archivo indicado siguiendo un path
muy interesante: `./node_modules:../node_modules:../../node_modules:etc` de
esta forma se resuelve el problema que se da al utilizar dos paquetes cuyas
dependencias se superponen pero difieren en la versión.

O sea, que si una aplicación usa A, B y ambas dependen de C, pero utilizan la
versión 2 y 3 respectivamente, el árbol de directorios sería:

```
/node_modules
|-/A
  |-/node_modules
    |-/C # version 2
|-/B
  |-/node_modules
    |-/C # version 3
```

Esto tiene el problema de la duplicación, pero eso se soluciona utilizando `npm
dedupe` cuya función es justamente esa.
