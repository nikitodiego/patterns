# Mejorando la arquitectura de la REST API. 

REST API utilizando patrones de diseño Singleton, Factory y Builder, con persistencia en MongoDB Atlas, Firebase y File System.

Para correr el proyecto, ejecutar en consola: npm run start

Sobre la API de la segunda entrega se realizan las siguientes modificaciones:

1) Se implementa el patrón Singleton en los 3 contenedores de persistencia. 

2) Se crea la clase Factory a partir de la cual se generan las DAOs dependiendo de la persistencia. 

3) En los routers se genera la instancia mediante el patrón builder (métodos aplicados consecutivamente).

Dejo comentadas las líneas de la implementación anterior, para que se vea cómo se aplicaban las DAOs antes de la refactorización de esta entrega.

Para cambiar de base de datos, modificar la variable de entorno DB(mongo, firebase o filesystem) y volver a correr el servidor.
Por default está seteada: DB=mongo

Endpoints Productos:

GET: /api/productos => Lista todos los productos.

GET: /api/productos/:id_producto => Lista el producto correspondiente al id_producto.

POST: /api/productos => Crea un nuevo producto en base al req.body.

PUT: /api/productos/:id_producto => Actualiza el producto correspondiente al id_producto.

DELETE: /api/productos/:id_producto => Elimina el producto correspondiente al id_producto.

Endpoints Carritos:

GET: /api/carritos => Lista todos los carritos.

GET: /api/carritos/:id_carrito => Lista el carrito correspondiente al id_carrito.

POST: /api/carritos => Crea un nuevo carrito con id, fecha de creación, y un array de productos vacío.

POST: /api/carritos/:id_carrito/producto/:id_producto => Agrega el producto id_producto al array del carrito id_carrito.

DELETE: /api/carritos/:id_carrito/producto/:id_producto => Borra el producto id_producto del array del carrito id_carrito.

GET: /api/carritos/:id_carrito/producto/:id_producto => Muestra la cantidad del producto id_producto que hay en el array del carrito id_carrito.

DELETE: /api/carritos/:id_carrito => Borra el carrito con id_carrito.
