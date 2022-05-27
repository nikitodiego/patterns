# segundaentrega
API utilizando ES6 y DAOs con persistencia en MongoDB Atlas, Firebase y File System.

Para correr el proyecto, ejecutar en consola: npm run start

Para cambiar de base de datos, modificar la variable de entorno DB(mongo, firebase o filesystem) y volver a correr el servidor.
Por default está seteada: DB=mongo

Las 3 bases de datos tienen objetos (productos y carritos) distintos intencionalmente, para que cuando se prueben las distintas persistencias 
con Postman se noten los cambios. 

Endpoints Productos:

GET: localhost:8080/api/producto => Lista todos los productos.

GET: localhost:8080/api/producto/:id_producto => Lista el producto correspondiente al id_producto.

POST: localhost:8080/api/producto => Crea un nuevo producto en base al req.body.

PUT: localhost:8080/api/producto/:id_producto => Actualiza el producto correspondiente al id_producto.

DELETE: localhost:8080/api/producto/:id_producto => Elimina el producto correspondiente al id_producto.

Endpoints Carritos:

GET: localhost:8080/api/carrito=> Lista todos los carritos.

GET: localhost:8080/api/carrito/:id_carrito => Lista el carrito correspondiente al id_carrito.

POST: localhost:8080/api/carrito => Crea un nuevo carrito con id, fecha de creación, y un array de productos vacío.

POST: localhost:8080/api/carrito/:id_carrito/producto/:id_producto => Agrega el producto id_producto al array del carrito id_carrito.

DELETE: localhost:8080/api/carrito/:id_carrito/producto/:id_producto => Borra el producto id_producto del array del carrito id_carrito.

GET: localhost:8080/api/carrito/:id_carrito/producto/:id_producto => Muestra la cantidad del producto id_producto que hay en el array del carrito id_carrito.

DELETE: localhost:8080/api/carrito/:id_carrito => Borra el carrito con id_carrito.
