# Mongo

## Que es mongodb?

Mongodb es uno de los gestores de bases de datos No relacionales(NOSQL), no estaremos trabajando con tablas ni con registros sino que haremos uso de **colecciones** y **documentos**.

Podemos ver a las las **colecciones** como las tablas de mysql, una coleccionas nos permitira almacenar diferentes entidades bajo un contexto.

Los **documentos** serian las filas en las tablas, la entidad que nosotros queremos almacenar, solamente que en mongodb estos documentos se representan mediante un fomato json.

## instalacion

E este caso usaremos una base de datos de [mongodb](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-ubuntu/) e iniciamos el servidor con el comando.
- iniciar servidor de mongo
```
sudo systemctl start mongod
```
si sale un error `Failed to start mongod.service: Unit mongod.service not found.` por el codigo anterior, ejecutar:
```
sudo systemctl daemon-reload
```

- status de mongo
```
sudo systemctl status mongod
```

- Opcionalmente, puede asegurarse de que MongoDB comenzará después de un reinicio del sistema emitiendo el siguiente comando:
```
sudo systemctl enable mongod
```

- Detener MONGODB:
```
sudo systemctl stop mongod
```

- Reiniciar MONGODB:
```
sudo systemctl restart mongod
```

- Inicie una mongoshsesión en la misma máquina host que mongod. Puede ejecutar mongosh sin ninguna opción de línea de comandos para conectarse a un mongodservidor que se está ejecutando en su host local con el puerto predeterminado 27017.

activar el servidor, con esto el servidor ahora esta a la escucha de cualquier posible conexion por parte de algun cliente
```
mongod
```

activa el shiel de mongo:
```
mongosh
```
par salir del shield de mongo:
```
exit;
```

ESte shield interactivo funciona internamnete con js asi que dentro de el podemos ejecutar codigo js asi que podemos terminar nuestras sentencias con o sin `;`. Un que lo recomendable es que siempre finalizemos con `;`.
## inicializacion
```
sudo systemctl start mongod
mongod
mongosh
```

- **conocer las bases de datos** que se encuentan en nuestro sistema:
```
show databases
```

- para saber en que **base de datos nos encontramos**:
```
db
```
En este caso estamos en una base de datos llamada `test` la cual no aparece en el sistema, nosotros podemos utilizar bases de datos las cuales no se encuentren persisitidas en el sistema, podemos decir que essas bases de datos solamente existen en memoria ram, en ningun momento se encuentran en el disco duro.

- para **crear una base de datos**:
```
use nombre_de_la_db
```

- para **ver una coleccion**(como la tablas en una base de datos relacional), la coleccion nos permetira almacenar diferentes documentos(entidades):
```
show collections
```

Para crear una coleccion, la foma mas sencilla de hacerlo es simplemente insertando un documento en ella, vamos a crear los objetos y las sentencias en un objeto json y posteriormento los ejecutaremos en el cliente:

- Crear un documento:
Escribirmos en la shield de mongo:
```
user1 ={
    "username": "user1",
    "age": 27,
    "email": "hola@gmail.com"
}
```
Ahora este e snuestro peimer documento, `user1` no es mas que un objeto json que posee tres atributos.

Apartir de ese objeto insertar en la collection.
```js
//primero colocamos el objeto de nuestra base de datos (db)
// despues colocaremos el nombre de la coleccion(users)
//recordemos que una coleccion no es mas que donde vamos a almacenrar los diferentes documentos
//posteriormente podemos ejecutar el metodo insert()
// insert() recibe como argumento el objeto el cual queremos persistir

//ahora insertamos en la shield de mongo:
db.users.insert(user1);
```

lo que ocurre con el comando anterior es que primero se valida la base de datos(db), si este objeto no existe se procede a crearlo, de igual forma ocurre con la collection, solamente cuando estas dos dentidades existan se procede a insertar el documento, es por eso que cuando ejecutamos `db.users.insert(user1);` por primera vez, se crearn tanto la base de datos como la collection

Con esto abremos creado nuestra primera collection.

- Para conocer que **documentos existen en una coleccion**:
```
db.users.find()
```

24:30