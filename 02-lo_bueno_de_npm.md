# Que aprendimos

Sin embargo lo mejor de node no es node, sino el gestor de paquetes NPM (node
package manager), que aprovecha la modularización de node para hacer
paquetes muy poco acoplados que proveen mucha flexibilidad.

Una de las mejores cosas que tiene NPM es las lecciones aprendidas, de otros
gestores de paquetes, no es tan lento como rubygems, el indice se descarga para
hacer búsquedas rápidas, las dependencias anidadas están resueltas, los valores
por defecto tienen sentido y la forma de correr los test está documentada.

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

## Paquetes globales

Los paquetes se pueden instalar de forma global o de forma local, la ventaja de
realizar la instalación de esta forma, es que se evita el problema de los
paquetes que *quedaron instalados* de cuando probamos algo y que quedan
ensuciando para siempre, cuando se elimina la carpeta del proyecto, todos sus
paquetes se van con él.

## Binarios locales

Otro problema de las instalación global es que se ensucia el path con cada
instalación (cosa que puede llegar a ser muy molesta). NPM soluciona este
problema de una forma muy interesante: cuando instalamos una dependencia de
forma local, esta no ensucia el path del usuario, si queremos ejecutar un
binario que provee una dependencia, se debe ejecutar
`./node_modules/.bin/gulp`.

Esto es bastante incomodo, así que npm permite configurar scripts en el
`package.json` que se ejecutan utilizando el comando `npm run SCRIPT` y que
corren en un entorno en el cual los binarios están en el path. Además hay dos
scripts con coronita, que son 'start' y 'test' que se pueden ejecutar mediante:
`npm start|test`.

## Package.json

De la misma forma, el archivo de entrada del paquete está muy bien pensado,
suele ser muy corto y fácil de leer, sigue todas las convenciones.
