# Rosa Dorada (Gilded Rose) Kata con JavaScript

### Cómo empezar
```
git clone git@github.com:jgabardini/gilded-rose-js.git
cd gilded-rose-js
docker-compose run --service-ports csd-service bash  # si usas con docker
npm install
npm start
```

### Comandos probar:

Ejecutar pruebas de unidad de forma continua --watch: `npm test`

Ejecutar pruebas de unidad solo una vez: `npm run test-once`



![](https://github.com/yamitcar/gilded-rose-ruby/workflows/Ruby/badge.svg)

withTest:  
![](https://github.com/yamitcar/gilded-rose-ruby/workflows/Ruby/badge.svg?branch=withTest)

para ver el reporte de analisis de codigo: 

https://yamitcar.github.io/gilded-rose-ruby/

## Cómo opera la posada La Rosa Dorada (Gilded Rose) 

Bienvenido al equipo de **Gilded Rose**.
Como quizá sabes, somos una pequeña posada ubicada estratégicamente en una prestigiosa ciudad, atendida por la amable **Allison**.
También compramos y vendemos mercadería de alta calidad.
Por desgracia, nuestra mercadería va bajando de calidad a medida que se aproxima la fecha de venta.

Tenemos un sistema instalado que actualiza automáticamente el `inventario`.
Este sistema fue desarrollado por un muchacho con poco sentido común llamado Leeroy, que ahora se dedica a nuevas aventuras.
Tu tarea es agregar una nueva característica al sistema para que podamos comenzar a vender una nueva categoría de items.

Pero primero, vamos a introducir el sistema:

* Todos los artículos (`Item`) tienen una propiedad `sellIn` que denota el número de días que tenemos para venderlo
* Todos los artículos tienen una propiedad `quality` que denota cúan valioso es el artículo
* Al final de cada día, nuestro sistema decrementa ambos valores para cada artículo mediante el método `updateQuality`

Bastante simple, ¿no? Bueno, ahora es donde se pone interesante:

* Una vez que ha pasado la fecha recomendada de venta, la `calidad` se degrada al doble de velocidad
* La `calidad` de un artículo nunca es negativa
* El "Queso Brie envejecido" (`Aged brie`) incrementa su `calidad` a medida que se pone viejo
  * Su `calidad` aumenta en `1` unidad cada día
  * luego de la `fecha de venta` su `calidad` aumenta `2` unidades por día
* La `calidad` de un artículo nunca es mayor a `50`
* El artículo "Sulfuras" (`Sulfuras`), siendo un artículo legendario, no modifica su `fecha de venta` ni se degrada en `calidad`
* Una "Entrada al Backstage", como el queso brie, incrementa su `calidad` a medida que la `fecha de venta` se aproxima
  * si faltan 10 días o menos para el concierto, la `calidad` se incrementa en `2` unidades
  * si faltan 5 días o menos, la `calidad` se incrementa en `3` unidades
  * luego de la `fecha de venta` la `calidad` cae a `0`

## El nuevo requerimiento

Hace poco contratamos a un proveedor de artículos *conjurados mágicamente*.
Esto requiere una actualización del sistema:

* Los artículos `conjurados` degradan su `calidad` al doble de velocidad que los normales

Siéntete libre de realizar cualquier cambio al mensaje `updateQuality` y agregar el código que sea necesario, mientras que todo siga funcionando correctamente. Sin embargo, **no alteres el objeto `Item` ni sus propiedades** ya que pertenecen al goblin que está en ese rincón, que en un ataque de ira te va a liquidar de un golpe porque no cree en la cultura de código compartido.

## Notas finales

Para aclarar: un artículo nunca puede tener una `calidad` superior a `50`, sin embargo las Sulfuras siendo un artículo legendario posee una calidad inmutable de `80`.


### Referencias
Docker
https://www.docker.com/blog/getting-started-with-docker-using-node-jspart-i/

Adaptado a partir de: https://github.com/bressain/gilded-rose-js && https://github.com/yamitcar/gilded-rose-ruby

