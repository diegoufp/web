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
// el metodo insert no permite conocer los id's de los objetos persistidos
// los meotods insertOne() y insertMany() si permite conocer los id's de los objetos persistidos
```

lo que ocurre con el comando anterior es que primero se valida la base de datos(db), si este objeto no existe se procede a crearlo, de igual forma ocurre con la collection, solamente cuando estas dos dentidades existan se procede a insertar el documento, es por eso que cuando ejecutamos `db.users.insert(user1);` por primera vez, se crearn tanto la base de datos como la collection

Con esto abremos creado nuestra primera collection.

- Para conocer que **documentos existen en una coleccion**:
```
db.users.find()
```

La segunda forma en la cual nosotros podemos insertar documentos es utilizando el metodo `insertOne()` es metodo como su nombre lo indica, nos permite insertar un solo documento.
```js
user2 ={
    "username": "user2",
    "age": 28,
    "email": "hola@gmail.com"
};

db.users.insertOne(user2);
```

La tercera forma y manera de insertar multiples registros es con `insertMany()`, donde vamos a pasar como argumento un listado de documentos, que serian los documentos que queremos persistir.
```js
db.users.insertMany([
    {
        "username": "user3",
        "age": 29,
        "email": "hola@gmail.com"
    },
    {
        "username": "user4",
        "age": 29,
        "email": "hola@gmail.com"
    },{
        "username": "user5",
        "age": 29,
        "email": "hola@gmail.com"
    }
]);
```

La cuarta forma en la cual nosotros podermos insertar un documento es utilizando el metodo `save()`.
```js
// este es un metodo obsoleto
user8 ={
    "username": "user8",
    "age": 18,
    "email": "hola@gmail.com"
};

db.users.save(user8);
```

## consultas 
```js
const dbi = [{
    
    username: 'user10',
    age: 27,
    email: 'hola@gmail.com',
    status: "active"
  },
  {

    username: 'user20',
    age: 28,
    email: 'hola@gmail.com',
    status: "inactive"
  },
  {

    username: 'user30',
    age: 29,
    email: 'hola@gmail.com',
    status: "inactive"
  },
  {

    username: 'user40',
    age: 29,
    email: 'hola@gmail.com',
    status: "inactive"
  },
  {
      
    username: 'user50',
    age: 29,
    email: 'hola@gmail.com',
    status: "active"
  }
];

db.users.insertMany(dbi);
```

- obtener el usuario con username user50:
```js
// el metodo find puede recibir como argumento un documento
// mediante este documento nosotros seremos capaces de indicar todas aquellas condiciones que deben cumplirse para notros poder obtener asi los documentos


// find() retorna un cursor
db.users.find({
    username: "user50"
});
// con esto obtendremos como resultado todo aquellos doucmentos que cumplan con la condicion cullo atributo username sea igual a user50

//findOne() retorna un documento 
db.users.findOne({
    username: "user50"
});
// con findOne solamente obtendremos un documento que cumpla con la condicion 
```

- Obtener todos los usuarios con una edad mayor a 20:
```js
// para que nosotros podamos condicionar usando un operador relacional colocamos $gt (significa mayor que)
db.users.find({
    age: {$gt: 20}
});
```
Los **operadores relacionales** serian: 
- gt: mayor que
- gte: mayor igual
- lt: menor que 
- lte: menor igual
- ne: no igual
- and: and
- or: or

- Obtener la **cantidad** de usuarios con una edad menor a 28:
```js
// los meotod de tipo cursor tiene el metodo countDocuments()
// el metodo countDocuments() nos permite contar
// el metodo count() por si solo esta obsoleto
db.users.find({
    age: {$lt: 28}
}).countDocuments();
```

- Obtener todos los usuarios con edad mayor a 20 y cuyo estatus sea activo:
```js
// para hacer consultas con varias condificonales vamos a usar el operador logico and, que en mongo seria $and
// dentro de la lista de $and vamos a poner todas aquellas condiciones las cuales deben cumplirse para asi obtener los documentos 
// las concionales iran dentro de llaves 
db.users.find({
    $and: [
        {age: {$gt: 20}},
        {status: "active"}
    ]
});

```

- Obtener todos los usuarios cuya edad no sea 29

`ne` : operador relacional de (no igual).
```js
db.users.find({
    age: {$ne: 29},
     
});
```

- Obtener todos los usuarios que tengan por edad: 20 o 28 o 10:
```js
// a diferencia de and que es necesario que se cumplan todas las condiciones para mostrar el documento
// en or solamente con que el documento cumpla una de las condiciones se mostrara
db.users.find({
    $or: [
        {age: 20},
        {age: 28},
        {age: 10}

    ]
});

// en caso de que se tenga que buscar entre mas parametros el operador or no es tan eficiente.
// es mejor opcion buscar sobre un listado
// $in : nos permite buscar sobre un listado
db.users.find({
    age: {$in:[20,28,10]}
});
```

- Obtener todos los usuarios con atributo status:
```js
// con eso indicamos que quermos obtener los documentos cuyo status exista  
db.users.find({
    status: {$exists: true}
});
```

- Obtener todos los usuarios con status activo
```js

db.users.find({
    status: "active"
});

//o


db.users.find({
    $and: [
        {status: {$exists : true}},
        {status: "active"}
    ]
});
```

- Obtener todos los usuarios con status activos y correo electronico
```js
db.users.find({
    $and: [
        {status: {$exists : true}},
        {status: "active"},
        {email: {$exists : true}}
    ]
});
```

- Obtener el usuario con mayor edad 
```js
// vamos a usar el metodo find puesto que nos interesa ordenar
// el metodo find nos retorna un cursor
// el objeto cursor posee el metodo sort()
//sort() nos permite ordenar
db.users.find().sort(
    {
        age: -1
    }
);
// ordenamos a los usuarios con respecto a su edad de forma descendente
//despues lo limitamos la cantidad de documentos
db.users.find().sort(
    {
        age: -1
    }
).limit(1);
// limit() nos permite limitar la cantidad de documentos que queremos obtener
```

- Obtener los 3 usuarios mas jovenes
```js
db.users.find().sort(
    {
        age: 1
    }
).limit(3);
```

- Condicionar con expresion regular
```js
//le indicaremos que nos muestre los usuarios cuyo correo electronico termine con .com
db.users.find({email: /.com$/})

//le indicaremos que nos muestre los usuarios cuyo correo electronico empeize con user
db.users.find({email: /^user/})
```

## cursores

Un cursor es un objeto el cual nos permite copnocer todos aquellos documentos obtenidos apartir de una cosulta.

Por defoult el curso trabaja bajo paginacion y cada pagina posee un maximo de 20 documentos. nosotros vamos obteniendo los documentos conforme los necesitemos (Como un iterador).

- `find().countDocuments()`: saber la cantidad de documento obtenidos.

- `find().limit()`: limitar la cantidad de documentos obtenidos.

- `find().skip()` : permite saltar el numero indicado de documentos.

- `find().sort()`: permite ordenar mediante parametros.

- `find().pretty()`: nos permite tener la infomacion con una vista mas amigable

Podemos almanecar los cursores en variables(pero solo se puede usar una vez, esto es por que cuando se usa se consume).
```js
cons cursor = db.users.find();
// solo se va apoder usar una vez
```

Para usar un cursor una multitud de veces podemos hacer con un forEach:
```js
db.users.find().forEach( user => print(user.username));
```

## Proyecciones  

las proyecciones no son mas que la forma en la cual nosotros podemos obtener atributos de los documentos de forma muy precisa

```js
db.users.find({
    {}, //defonimos las condiciones
    {
        //_id: false,   // esto en caso de que no queramos que se imprima el id
        username: true,
        email: true
    } , //se puede recibir un segundo argumento 
    // sera en este segundo argumento donde nosotros podemos definir los atributos que queremos obtener
    // por defoult el id siempre se refornara
})
```

## actualizar documentos

- `updateOne()`:
```js
// update recibe dos argumentos(obligatoriamente), ambos argumentos seran documentos
// el primer documento hace referencia a las codiciones que nostros vamos a establecer para poder actualzar un documento o mutiples documentos 
//actualizemos el documento cuyo id sea el:  _id: ObjectId("61d35ef4daa255004e06961f")
// el segundo documento nos permite definir todos aquellos cambios que va a tener el documento, para ello vamos a utlizar $set
db.users.updateOne(
    {
        _id: ObjectId("61d35ef4daa255004e06961f")
    },
    {
        $unset: {
            username: "cody"
        }
    }
)


// si queremos eliminar informacion en lugar de $set, vamos a usar $unset
db.users.updateOne(
    {
        _id: ObjectId("61d35ef4daa255004e06961f")
    },
    {
        $unset: {
            username: true
        }
    }
)
```

- `updateMany()`:
```js
db.users.updateMany(
    {
        status: "inactive"
    },
    {
        $set: {
            status: "active"
        }
    }
)

// incrementar la edad en uno para todos los documentos
// $inc se refiere a increment
db.users.updateMany(
    {
    },
    {
        $inc:{
            age: 1
        }
    }
)
```

## eliminar documentos

- `remove()`:
```js

db.users.deleteOne({
    status: "active"
})


db.users.deleteMany({
    status: 'active'
});

```

## eliminar colecciones y base de datos

- `db.dropDatabase();` :  este metodo permite eliminar la base de datos

- `db.la_collection.drop()` : con esto eliminaremos una collecion de objetos.

## acceder a subconjuntos

```js
user13 = {
    "address":{
        "country": "MX"
    }
}
```

Para saber si es usuario radica el mexico, la consulta seria:
```js
db.users.findOne({
    "address.country": "MX"
})
```

Para agregar un atributo:

```js
db.users.updateMany(
    {
        "address": {$exists: false}
    }
    {
        $set:{
            "address": {
                country: "MX"
            }
        }
    }
)
```


## filtrar sobre listas

```js
user15 = {
    "comments": [
        {
            body: "Best curse",
            like: false
        }
    ]
}
```

Como ahora no vamos a filtar sobre un documento objetos si no sobre documentos que se encuentran dentro de una lista(array), vamos a utilizar `$elemMatch`, atravez de esta funcion seremos capaces de filtrar sobre atributos de documentos que se encuentren dentro de listados.

```js
db.users.findOne(
    {
        comments: {
            $elemMatch : {
                like: false
            }
        }
    }
)

```

Al utilizar `$elemMatch` ya estariamos trabajando los documentos dentro del listado.

## agregar un nuevo elemento a un listado
```js
user13 = {
    courses: [
        "python",
        "mongodb"
    ],
    "comments": [
        {
            "body": "Best curse",
            "like": true
        }
    ]
}

```


```js
db.users.updateOne(
    {
        username: "user13"
    },
    {
        $push: {
            comments: {
                like: false
            }
        }
    }
)
```
```js
db.users.updateOne(
    {
        username: "user13"
    },
    {
        $push: {
            curses: "rust"
        }
    }
)
```
Mediante `$push` seremos capaces de agregar elementos al final de la lista.

## agregar elementos sobre un listado que se encuantra en un documento dentro dentro de otro listado

```js
user13 = {
    courses: [
        "python",
        "mongodb",
        "rust"
    ],
    "comments": [
        {
            "body": "Best curse",
            "like": true
        },
        {
                like: false,
                "tags": [
                    "bad"
                ]
        }
    ]
}

```

```js
db.users.updateOne(
    {username: "user13"},
    {
        $push: {
            "comment.1.tags": "tutor"
        }
    }
)
```

Pero hay que ser muy cuidadosos, siempre que especifiquemoz la posicion del documento que vamos a actualizar, no olvidemos el atributo definir el atributo que vamos a actualizar o en dado caso estariamos actualizando el documento(objeto) completo.

## actualizar sin conocer la posicion

```js
db.users.updateOne({
    {
        username: "user13",
        "comments.like": false  //nos permitira conocer el infice de los documentos dentro de la lista que queremos actualizar . Ya que de antemano nosotros no conocemos el indice

    
        // con esto le indicamos que queremos actualizar todos aquellos documentos
        //cuyo username sea user13
        // y dentro de los comentarios aquellos cumentos cuyo like sea igual a falso
    },{

        $set:{
            // el signo de dolar $(sera un comodin) sera remplazado automaticamnete por el indice de todos aquellos comentarios que cumplan con la condicion ("comments.like": false)
            "comments.$.body" : "Buen curso",
            "comments.$.like" : true
        },
        $unset: {
            "comments.$.tags": true
        }
    }
});
```