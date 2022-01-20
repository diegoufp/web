# [GraphQL](https://graphql.org/)

GraphQL es un lenguaje de consultas para APIs.

Las caracteristicas mas importantes de Graphql:
- Describir tus datos: Tienes que describir los datos que quieres capturar, manipular.
- Puedes preguntar lo que quieres recuperar de estos datos
- obtener resultados predecibles: cuando pides unos datos sabes la estructura del objeto que va a devolver los datos.

Las ventajas de usar GraphQL es que en lugar de hacer un monton de peticiones para recuperar los datos, lo que vamos a poder hacer es, hacer solamente una request y que sea al servidor de graphql el que se encarge de recoger los datos de las diferentes fuentes donde estan estos datos


Para empezar a utilizar GraphQL hay herramientas como por ejemplo [Apollo](https://www.apollographql.com/).

**Apollo** es una herramienta que brinda como poder crear un servidor y como integrarlos con framework del fort-end para oider intercambiar y recibir datos.

Apollo server es un framework que nos permite crear un servidor y ademas un cliente.

Podemos

## Inicializacion 

intalaremos apollo server y graphql:
```
npm i apollo-server graphql
```

Ahora creamos un archivo `index.js`:
```js
const persons = [
    {
        name: "Midu",
        city: "Barcelona"
    },
    {
        name: "Youseff",
        city: "Mataro"
    },
    {
        name: "Itzi",
        city: "Ibiza"
    }
]
```
EStos serian los datos que queremos hacer cosultas con graphql.

### Definiciones de los datos

1. Describir tus datos:
```js
typpe Person {
        name: String!
        city: String!
    }
```

```js
//primero tenemos que importar graftql
import {gql} from "apollo-server";

//para describir los datos creamos una constante

//gql lo que esta haciendo es utilizar una plantilla de texto, es un metodo que ejecuta un string/template string 

// los datos que tienen la exclamacion al final (!) significa que son campos requeridos 
// podemos usar todos tipos de datos ademas de String y hasta podemos crear nuestros propios tipos de datos
const typeDefs = gql`
    type Person {
        name: String!
        city: String!
    }
`
```

2. Describir tus datos:
```js

```

```js
import {gql} from "apollo-server";

// cuando queramos hacer peticiones a graphql server
// tenemos que describir tambien las peticiones que se pueden hacer 
//esto pos hacemos con `type Query{}`

//en este caso le estamos pidiendo un numero entero de forma obligatorio(siempre lo va tener que devolver)
// en alPersons queremos que devuelva un array de Person
const typeDefs = gql`
    type Person {
        name: String!
        city: String!
    }

    type Query {
        personCount: Int!
        allPersons: [Person]!
    }
`

```

### RESOLVERS

Para hacer una consulta necesitamos las definiciones de los datos y tambien como los **resolvers** los cuales son donde y como se resulve la informacion.

```js
import {gql} from "apollo-server";

const typeDefs = gql`
    type Person {
        name: String!
        city: String!
    }

    type Query {
        personCount: Int!
        allPersons: [Person]!
    }
`
// para que gql pueda saber de donde va a sacar el numero de la query: personCount: Int!

// en personCount lo que queremos es el numero de personas que queremos recuperar
// () => persons.length este metodo es la funcion programatica para el numero de personas que queremos recuperar
const resolvers = {
    Query: {
        personCount: () => persons.length,
        allPersons: () => persons
    }
}
```

### crear servidor

Ahora que tenemos tanto las definiciones de datos como los resolvers podemos crear el servidor:

```js
import {gql} from "apollo-server";

const typeDefinitios = gql`
    type Person {
        name: String!
        city: String!
    }

    type Query {
        personCount: Int!
        allPersons: [Person]!
    }
`

const resolvers = {
    Query: {
        personCount: () => persons.length,
        allPersons: () => persons
    }
}

const server = new ApolloServer({
    typeDefs: typeDefinitios,
    resolvers: resolvers
})

//para iniciar el serviro:
// el listen devulve una promesa
server.listen().then(({url}) => {console.log(url)})
```

### Graphql PlayGround

En la consola vamos a ejecutar el archivo con node para iniciar el servidor:
```
node index.js
```

Cuando estemos en el servidor nos apareceran la funcionalidad **Graphql PlayGround** en la cual podemos probar deferentes funcionalidades de Graphql.

Si pulsamos `CTRL + SPACE` vamos a tener un auto complite que nos dice las cosas que podmeos hacer.

Vamos a hacer una consulta en el Graphql PlayGround:
```js
query {
    personCout
} 
```

Despues ejecutamos la query y nos dara la respuesta:
```js
{"data" :{
    "personCout": 3
    } 
}
```

Ahora si traejecutamos la segunda query que creamos:
```js
query {
   allPersons
} 
```

La respuesta da un error, esto es por que los campos de `allPersons` son de un tipo `[Person!]` y tenemos que tener una seleccion de subcampos, por que no le estamos indicando que es lo queremos extraer del `allPersons`, al final es un array de objetos y graphql en este caso no nos devuelve directamente los datos en conjunto si no que tenemos que ser mas especificos de los que quermeos extraer del `Persons`

El `personCout` solamente nos devolvio un numero asi que no hace falta una propiedad de un objeto, por ello no nos da error con `personCout`.

Esta vez seamos mas especificos con `allPersons`:
```js
query  {
   allPersons {
       name
   }
} 
```

Ahora tenemos una respuesta valida:

```js
{"data": {
   "allPersons":[
       {
           "name": "Midu"
       },
       {
           "name": "Youseff"
       },
       {
           "name": "Itzi"
       }
   ]
    } 
}
```

En caso de que un campo no este disponible para uno de los objetos que hemos recuperado va a dar un `null`

## Resolvers complejos

```js
const persons = [
    {
        name: "Midu",
        city: "Barcelona"
    },
    {
        name: "Youseff",
        city: "Mataro"
    },
    {
        name: "Itzi",
        city: "Ibiza"
    }
]
```
```js
import {gql} from "apollo-server";

// indicar un parametro es parecido a un metodo
// le indicamos que tiene un parametro name que es de tipo string y ademas es obligatorio y que devuelva una persona: 
//findPerson(name: String!) : Person
const typeDefinitios = gql`
    type Person {
        name: String!
        city: String!
    }

    type Query {
        personCount: Int!
        allPersons: [Person]!
        findPerson(name: String!) : Person
    }
`

// en los resolver de findPerson vamos a usar los parametros
//args serian los parametros que tiene nuestra query (name: String!)
const resolvers = {
    Query: {
        personCount: () => persons.length,
        allPersons: () => persons
        findPerson: (root, args) => {
            const {name} = args
            return persons.find(person => person.name === name)
        }
    }
}

const server = new ApolloServer({
    typeDefs: typeDefinitios,
    resolvers: resolvers
})


server.listen().then(({url}) => {console.log(url)})
```

En el servidor la peticion seria:
```js
query {
    findPerson(name: "Midu"){
        city
    }
}
```
la respuesta seria: 
```js
{"data" :{
    "findPerson":{
        "city": "Barcelona"
        }
    }
}
```

en caso de que no se encuentre la persona la respuesta seria:
```js
{"data" :{
    "findPerson": null
    }
}
```
Estaria devolviendo directamente un null, no estaria devolviendo un objeto.

En caso de que si encuentre a la persona pero el campo de la persona no exista devolvera un objeto y un null.
```js
{"data" :{
    "findPerson": {
        "city": null
        }
    }
}
```

### Root
Apollo server tiene un resolver por defecto donde esta buscando la las propiedades de las query en los datos y los maxea, sin embargo, podemos cambiar ese comportamiento en los resolvers.

```js
const resolvers = {
    Query: {
        personCount: () => persons.length,
        allPersons: () => persons
        findPerson: (root, args) => {
            const {name} = args
            return persons.find(person => person.name === name)
        }
    },
    Person: {
        name: (root) => root.name
    }
}
```

`root` es basicamente lo que se a resulto antes, en este caso se llama `root` por que es la raiz pero en realidad seria `prev`,una vez que te pones a anidar querys que se resulven sucesivamente al final no estas hablando de la raiz, si no de lo que se a resuelto antes.

En este caso el `root` seria el propio objeto que a encontrado cuando se hizo la peticion. Para extraer la informacion del root en este caso: `name: (root) => root.name`. Esto tambien se podria hacer con la propiedad `city` pero esto ya ocurre por defecto sin que lo tengamos quye hacer.

Pero en algunos casos puede ser util para crear campos que son calculos, y estos se estan haciando en el servidor en lugar del cliente:

```js
const persons = [
    {
        name: "Midu",
        city: "Barcelona"
    },
    {
        name: "Youseff",
        city: "Mataro"
    },
    {
        name: "Itzi",
        city: "Ibiza"
    }
]
```
```js
import {gql} from "apollo-server";

//para que podamos crear los campos que no existan en los datos es importante definirlos en el typeDefinitios
const typeDefinitios = gql`
    type Person {
        name: String!
        city: String!
        address: String!
        check: String!
    }

    type Query {
        personCount: Int!
        allPersons: [Person]!
        findPerson(name: String!) : Person
    }
`

//en Person estamos creando campos que no existen en los datos
const resolvers = {
    Query: {
        personCount: () => persons.length,
        allPersons: () => persons
        findPerson: (root, args) => {
            const {name} = args
            return persons.find(person => person.name === name)
        }
    },
    Person: {
        address: (root) => `${root.name}, ${root.city}`,
        check: () => "midu"
    }
}

const server = new ApolloServer({
    typeDefs: typeDefinitios,
    resolvers: resolvers
})


server.listen().then(({url}) => {console.log(url)})
```

### de respuesta tener un objeto dentro de otro objeto


```js
const persons = [
    {
        name: "Midu",
        city: "Barcelona",
        street: "calle1"
    },
    {
        name: "Youseff",
        city: "Mataro",
        street: "calle2"
    },
    {
        name: "Itzi",
        city: "Ibiza",
        street: "calle3"
    }
]
```
```js
import {gql} from "apollo-server";
//en lugar de tener el address como un string(en el Person) lo vamos a ponerlo en otro type

// un type lo podemos usar en otro type
const typeDefinitios = gql`
    type Address {
        street: String!
        city: String!
    }

    type Person {
        name: String!
        address: Address!
    }


    type Query {
        personCount: Int!
        allPersons: [Person]!
        findPerson(name: String!) : Person
    }
`

const resolvers = {
    Query: {
        personCount: () => persons.length,
        allPersons: () => persons
        findPerson: (root, args) => {
            const {name} = args
            return persons.find(person => person.name === name)
        }
    }
}

const server = new ApolloServer({
    typeDefs: typeDefinitios,
    resolvers: resolvers
})


server.listen().then(({url}) => {console.log(url)})
```

si tratamos de hacer una peticion:
```js
query{
    findPerson(name:"Itzi"){
        address
    }
}
```
En esta ocacion va a marcar un error por que el campo `address` es del tipo `Address!` y se tiene que hacer la seleccion de los campos.

Lo corregimos:

```js
query {
    findPerson(name:"Itzi"){
        address{
            street
            city
        }
    }
}
```
Ahora si corremos la solicitud igual nos marca un error, esto esta ocurriendo por que no es capaz de resolver el campo `Address!` ya que en los datos no se encuentra el campo address, tener que ayudarle a resolver esto.

Es importante diferenciar en como tienes la informacion en la base de datos y como nosotros vamos a recuperar esta en el cliente. Los resolvers van a ayudarnos a ser capaces de transformar la informacion de la base de datos a los datos que hemos descrito en graphql.

En como tengas la informacion en la base de datos no tiene que ser una prolongacion en como llega al cliente, lo que se hace en graphql es adaptar esta informacion a las diferentes solicitudes para que se puedan consumir mas facilmente.

```js
import {gql} from "apollo-server";

const typeDefinitios = gql`
    type Address {
        street: String!
        city: String!
    }

    type Person {
        name: String!
        address: Address!
    }


    type Query {
        personCount: Int!
        allPersons: [Person]!
        findPerson(name: String!) : Person
    }
`
// agregando person y mas infomacion del atributo address
//vamos a lograr que person tenga este nuevo atributo sin que este realmente en la base de datos 
const resolvers = {
    Query: {
        personCount: () => persons.length,
        allPersons: () => persons
        findPerson: (root, args) => {
            const {name} = args
            return persons.find(person => person.name === name)
        }
    },
    Person:{
        address: (root) => {
            return {
                street: root.street,
                city: root.city
            }
        }
    }
}

const server = new ApolloServer({
    typeDefs: typeDefinitios,
    resolvers: resolvers
})


server.listen().then(({url}) => {console.log(url)})
```

Ahora si ejecutamos denuevo el request:
```js
query {
    findPerson(name:"Itzi"){
        address{
            street
            city
        }
    }
}
```

El resultado sera correcto:
```js
{
    "data":{
        "findPerson"{
            "address":{
                "street":"calle3",
                "city": "Ibiza"
            }
        }
    }
}

```
Nos da una respuesta satisfactoria de address cuando en realidad esta no se encuentra en el objeto original