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

[uuid](https://github.com/uuidjs/uuid) : sirve para crear id unicos con el comando:
```
npm i uuid
```
y se importa:
```js
import {v3 as uuid} from "uuid"
```
Para no tener que usar `requiere()` en la importaciones de node podemos usart `"type: module"` en el `package.json` al mismo nivel que `"scripsts"` *no* dentro de este mismo. De esta forma en lugar de usar `requiere()` podemos usar `import`


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
import {ApolloServer,gql} from "apollo-server";

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
import {ApolloServer,gql} from "apollo-server";

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
import {ApolloServer,gql} from "apollo-server";

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
import {ApolloServer,gql} from "apollo-server";

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
import {ApolloServer,gql} from "apollo-server";

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
import {ApolloServer,gql} from "apollo-server";

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
import {ApolloServer,gql} from "apollo-server";
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
import {ApolloServer,gql} from "apollo-server";

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

## Mutation

Mutation se refiere a que vamos a cambiar los datos.

En esta ocacion sera un ejemplo para agrgar datos

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
import {ApolloServer,gql} from "apollo-server";
import {v1 as uuid} from "uuid"

//tenemos que definir las mutaciones con type
// la mutacion normalmente devuelve la persona que se a agregado/modificado addPerson():Person
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

    type Mutation{
        addPerson(
            name:String!
            street: String!
            city: String!
        ):Person
    }
`

//en este caso vamos a agregar el objeto de la nueva persona con el metodo .push(), pero si tuvieramos una base datos lo hariamos de otra forma: persons.push(person)

const resolvers = {
    Query: {
        personCount: () => persons.length,
        allPersons: () => persons
        findPerson: (root, args) => {
            const {name} = args
            return persons.find(person => person.name === name)
        }
    },
    Mutation: {
        addPerson: (root, args) => {
            const person = {...args/*, id: uuid()*/}
            persons.push(person) 
            return person
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

ahora si hacemos uso del Graphql PlayGround:
```js
mutation {
    addPerson(
        name: "aborja"
        street: "calle4"
        city: "Albacete"
    )
}
```
si solamente enviamos esto nos va a dar un error, esto es por que al agregar una persona tenemos que tener una seleccion de sus campos, esto es por que a `addPerson` le hemos indicado que devuelva un `person`,`addPerson():Person`, por lo tanto tenemos que extraer los campos del Person:

```js
mutation {
    addPerson(
        name: "aborja"
        street: "calle4"
        city: "Albacete"
    )
}{
    name
    city
    address {
        city
        street
    }
    /*id*/
}
```

### validacion en las mutaciones

[Tipos de errores de apollo](https://www.apollographql.com/docs/apollo-server/data/errors/)

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
import {UserInputError,ApolloServer,gql} from "apollo-server";
import {v1 as uuid} from "uuid"
// UserInputError es para crear alertas de error mas especificas

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

    type Mutation{
        addPerson(
            name:String!
            street: String!
            city: String!
        ):Person
    }
`
//en esta ocacion vamos a agregar una validacion para verificar que en name no sea de uno que ay exista
//if(persons.find(p => p.name === args.name))
const resolvers = {
    Query: {
        personCount: () => persons.length,
        allPersons: () => persons
        findPerson: (root, args) => {
            const {name} = args
            return persons.find(person => person.name === name)
        }
    },
    Mutation: {
        addPerson: (root, args) => {
            if(persons.find(p => p.name === args.name)){
                //vamos a crear un error especifico para estos casos o poner un error comun
                //throw new Error("Name must be unique")

                // a UserInputError le podemos pasar un segundo parametro para indicarle donde esta el problema
                throw new UserInputError("Name must be unique", {invalidArgs: args.name})
            }
            const person = {...args/*, id: uuid()*/}
            persons.push(person) 
            return person
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

## ENUMS

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
import {UserInputError,ApolloServer,gql} from "apollo-server";
import {v1 as uuid} from "uuid"

//enum nos va a permitir crear parametros opcionales
// allPersons: [Person]!  //lo cambiamos a :
// allPersons(city: YesNo): [Person]!
const typeDefinitios = gql`
    enum YesNo{
        YES
        NO
    }

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
        allPersons(city: YesNo): [Person]!
        findPerson(name: String!) : Person
    }

    type Mutation{
        addPerson(
            name:String!
            street: String!
            city: String!
        ):Person
    }
`
// modificamos el resolver de allPersons
const resolvers = {
    Query: {
        personCount: () => persons.length,
        allPersons: (root: args) => {
            //si no tenemos un args del city(ya que hicimos opcional el parametro), entonces no estamos filtrando y vamos a devolver todas las persons en un array
            if(!args.city) return persons;

            const byCity = person => args.city === "YES" ? person.city : !person.city;

            //despues aplicamos un filtro:
            return persons.filter(byCity)


        }
        findPerson: (root, args) => {
            const {name} = args
            return persons.find(person => person.name === name)
        }
    },
    Mutation: {
        addPerson: (root, args) => {
            if(persons.find(p => p.name === args.name)){
                throw new UserInputError("Name must be unique", {invalidArgs: args.name})
            }
            const person = {...args/*, id: uuid()*/}
            persons.push(person) 
            return person
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

ahora si hacemos uso del Graphql PlayGround:
```
query {
    allPersons(city: YES){
        name
        city
    }
}
```

Con esta query que hacemos nos va a devolver las personas que si tengan el dato de `city` y puedemos estrapolar esto a multiples casos de uso.

## Mutation para editar datos en servidor de GraphQL

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
import {UserInputError,ApolloServer,gql} from "apollo-server";
import {v1 as uuid} from "uuid"

// en mutation vamos a crear otro metodo para editar la ciudad

// EN graphql muchas veces lo que hacemos es que al cambiar un dato lo cambiamos en la base de datos y tambien lo cambiamos en la cache local
// de esta forma reflejamos el cambio cuando antes sin necesidad de verificar como a ido la base de datos, de esta forma se hace mucho mas rapido
const typeDefinitios = gql`
    enum YesNo{
        YES
        NO
    }

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
        allPersons(city: YesNo): [Person]!
        findPerson(name: String!) : Person
    }

    type Mutation{
        addPerson(
            name:String!
            street: String!
            city: String!
        ):Person
        editCity(
            name: String!
            city: String!
        ): Person
    }
`
// dentro de las Mutatios de resolver se va agregar el metodo editCity
const resolvers = {
    Query: {
        personCount: () => persons.length,
        allPersons: (root: args) => {
         
            if(!args.city) return persons;

            const byCity = person => args.city === "YES" ? person.city : !person.city;

            return persons.filter(byCity)
        }
        findPerson: (root, args) => {
            const {name} = args
            return persons.find(person => person.name === name)
        },
        editCity: (root,args) =>{
            const personIndex = persons.findIndex(p => p.name === args.name)
            if(personIndex === -1)return null

            const person = persons[personIndex]
            const updatePerson = {...person, city: args.city}

            persons[personIndex] = updatePerson

            //importante al final tenermo que veolver la person que hemos actualizado
            return updatePerson
        }
    },
    Mutation: {
        addPerson: (root, args) => {
            if(persons.find(p => p.name === args.name)){
                throw new UserInputError("Name must be unique", {invalidArgs: args.name})
            }
            const person = {...args/*, id: uuid()*/}
            persons.push(person) 
            return person
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

ahora si hacemos uso del Graphql PlayGround:
```
mutation {
    editCity(name: "Itzi", city:"new city"){
        name
    }
}
```

## Queries compuestas en graphql
Se pueden hacer consultas anidadas en una sola query.

Con las funciones que hemos creado hasta ahora, ahora si hacemos uso del Graphql PlayGround:

```
query {
    personCount
    allPersons {
        name
    } 
}

```
al hacer esta query estamos anidando la informacion de `personCount` y `allPersons` y el `name`, si lo ejecutamos tendremos toda la informacion.

**Pero que pasaria si queremos hacer una query con el mismo metodo mas de una vez?**


```
query {
    personCount
    allPersons {
        name
    } 
    allPersons(city: YES){
        name
    }
}

```
si hacemos esta query sale un error. Esto ocurre por que el campo `allPersons` hay un conflicto en diferentes argumentos, eso quiere decir que, estamos haciando dos veces la misma query dentro de una consulta.

Para solucionar esto podriamos **agregar campo**:
```
query {
    personCount
    allPersonsData: allPersons {
        name
    } 
    allPersonsWhithCity: allPersons(city: YES){
        name
    }
}

```
Y si ahora ejecutamos esta query saldra un resultado positivo.

Entonces si se puede hacer una misma consulta con diferentes parametros.

## llamadas a REST API con GraphQL y Json Server    
primero instalamos `json-server` y axios:
```
npm install json-server axios
```

Y convertirmos los datos a formato json, esto se puede hacer en la consola del navegado ejecutando:
```
copy(JSON.stringify([
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
]))
```
Y el resultado seria:

```json
{
    "persons" : [{"name":"Midu","city":"Barcelona","street":"calle1"},{"name":"Youseff","city":"Mataro","street":"calle2"},{"name":"Itzi","city":"Ibiza","street":"calle3"}]
}
```
EStos datos se tiene que poner dentro de un archivo `.json`

Ahora detiamos el archivo `package.json` y dentro de `scripts` agregamos otro comando:
```
"scripts": {
    "json-server": "json-server --watch db.json"
}
```
ahora iniciamos json server.

```js
import {UserInputError,ApolloServer,gql} from "apollo-server";
import {v1 as uuid} from "uuid"
import axios from "axios"


const typeDefinitios = gql`
    enum YesNo{
        YES
        NO
    }

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
        allPersons(city: YesNo): [Person]!
        findPerson(name: String!) : Person
    }

    type Mutation{
        addPerson(
            name:String!
            street: String!
            city: String!
        ):Person
        editCity(
            name: String!
            city: String!
        ): Person
    }
`

//para hacer llamadas a APIs lo primero sera hacer asincorna la funcion de allPersons
const resolvers = {
    Query: {
        personCount: () => persons.length,
        allPersons: async (root: args) => {
            const {data :personsFromApi} = await axios.get("https://localhost:3000/persons")

            if(!args.city) return personsFromApi;

            const byCity = person => args.city === "YES" ? person.city : !person.city;

            return personsFromApi.filter(byCity)
        }
        findPerson: (root, args) => {
            const {name} = args
            return persons.find(person => person.name === name)
        },
        editCity: (root,args) =>{
            const personIndex = persons.findIndex(p => p.name === args.name)
            if(personIndex === -1)return null

            const person = persons[personIndex]
            const updatePerson = {...person, city: args.city}

            persons[personIndex] = updatePerson

            return updatePerson
        }
    },
    Mutation: {
        addPerson: (root, args) => {
            if(persons.find(p => p.name === args.name)){
                throw new UserInputError("Name must be unique", {invalidArgs: args.name})
            }
            const person = {...args/*, id: uuid()*/}
            persons.push(person) 
            return person
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

## GRAPHQL + REACT + APOLLO CLIENT

Se vera la mejor forma de utilizar un cliente de graphql.

Se vera como conectar el servido con un cliente de apollo.

si iniciamos el servidor de apollo, vamos a tener el graphql playground.     

Pero tambien es importante saber que cuando tenemos un servidor de graphql lo podemos utilizar de cualquier forma, es decir, que no necesitamos una tecnologia en concreto para poder extraer datos de nuestro servidor de graphql.

Para demostrar lo anterior usaremos una extencion de Visual Studio Code llamda `THUNDER CLIENT`  y haremos un request al graphql server para extraer la informamcion de una forma sensilla, sin ningun cliente.

Realizaremos una solicitud `POST` por que graphql solo acepta `POST` y solo tiene un solo endpoint desde el que se hacen todas y cada una de las querys `localhost:4000/` y en la opcion de `Body` de tipo `Json`:
```json
//Json Content
{
    "query": "query {allPersons{name}}"
}
```

Y enviaamos la request, podemos observar que solo con esto ya podriamos utilizar nuestro servidor de graphql, pero realizar peticiones de esta manera perdemos unas cuantas ventajas.

Necesitaremos crear un proyecto con react con `create react app` e iniciamos el servidor de react.

Lo primero que podriamos hacer para conectar nuestro graphql server es:
```jsx
import react, {useEffect} from "react";

function App(){
    useEffect(()=>{
        //hacemos un fetch al graphql server
        fetch("http://localhost:4000",{
            method: "POST",
            headers:{"Content-Type":"application/json"}, body: JSON.stringify({query:`
                query{
                    allPersons {
                        name
                    }
                }
            `}).then(res => res.json()).then(res => {
                //siempre graphql nos devuelve la informacion en data 
                console.log(res.data)
            })
        })
    })
    return (
        <div>
        </div>
    )
}
```

Esto nos moestraria la informacion en el console del navegador. Con esto se quiere demostrar que cualquier quiente que se vaya a utilizar, de forma ultima, lo que hace es muy similar a un peticion con fetch como anterior mente se hizo. Sin embargo de esta forma se pierden alguna vetajas.

Hasta este punto funciona las peticiones hacia el servidor de graphql, no da la respuesta y esta respuesta la podemos guardar en el state, pero este trabajo seria muy manual, tendriamos que estar constantemente guardando la informacion en el estado y para saber cuando esta cargando tendriamos que poner una funcion para saber cuando esta cargando, sin embargo esto ya nos lo da un cliente de apollo, lo mismo para el control de errores.

**tipo de clientes**
Existen diferentes clientes que tienen muchas ventajas a la hora de trabajar con graphql en especifico:

- [relay.dev](https://relay.dev/): es el cliente de graphql que esta utilizando facebook(De forma oficial) en sus productos y esta bien para productos grandes.
- [apollo client](https://www.apollographql.com/docs/react/): lo que ofrece es:
    - puedes ver cada una d elas peticiones, la cache, lo que tiene.
    - te permite implementarlo en tu aplicacion de forma incremental.
    - no hace falta que el servidor de graphql este hecho con apollo, funciona con cualquier servidor de graphql.

Instalaremos apollo client:
```
npm install @apollo/client graphql
```

importamos el apollo cliente a componente principal de la aplicacion:
```js
import React from "react";
import ReactDom from "react-dom";
import {ApolloClient,ApolloProvider,InMemoryCache,HttpLink,gql} from "@apollo/client";

//iniciamos el cliente
//una de las cosas importantes que tiene el cliente de apollo es la cache
//una cache que cada vez que hace una peticion guarda la informacion para evitar hacer mas de una vez esa peticion y tambien sincronizar los cambios que se esten haciando en esa cache   
// y asi poderlo guardar ahi sin necesidad de volver a pedirlos al servidor 
// podriamos tener diferentes caches 
// cada vez que cerremos el servidor y lo volvamos a levantar se pierde la cache, asi que podria haber cache de base de datos, en disco, etc.
const client = new ApolloClient({
    cache: new InMemoryCache(),
    link: new HttpLink({
        uri: "http://localhost:400"
    })
})
//las opciones de apolo son:
//- link: con que nos queremos conectar
//- cache : las mas tipica que se puede utilizar es en memoria

//para hacer una peticion: 
const query = gql`
    query{
        allPersons{
            name
        }
    }
`
client.query({ query: query}).then(res => {
    console.log(res.data)
})

//el provider permite envolver la aplicacion
// utiliza el context para que el cliente este disponible en todos los componentes que estamos envolviendo
RecarDOM.rendes(
    <ApolloProvider client={client}>
        <App/>
    </ApolloProvider>
,document.getElementById("root"))
```

### consultas

Realizaremos una consulta dentro de los componentes hijos del componente principal(el que contiene el provider).
```tsx
import { gql, useQuery} from '@apollo/client'
//useQuery: nos permite llamar dentro del componente 

const ALL_PERSONS = gql`
  query ViewerQuery {
    allPersons{
      name
    }
  }
`

const Home = () => {
  const result = useQuery(ALL_PERSONS);

  console.log(result);
  //en el navegador se mostrara el objeto dos veces:
  //La primera vez no se esta haciendo la peticion sino que esta devolviendo informacion de que se esta cargando
  //en la segunda es cuando ya tenemos el resultado de la peticion y el loading es falso
  // los mas importante de del objeto result es {data, loading, error}

  return (
    <div>
     hola
    </div>
  )
}


export default Home;

```

Un resultado rapido seria asi:
```tsx
import type { NextPage } from 'next'
import Head from 'next/head'
import Image from 'next/image'
import Link from 'next/link'
import { gql, useQuery} from '@apollo/client'

//usar parametros para las queries
const ALL_PERSONS = gql`
  query ViewerQuery {
    allPersons{
      name
    }
  }
`

const Home: NextPage = () => {
  const {data,error,loading} = useQuery(ALL_PERSONS);

  if(error) return <span className="bg-red">{error}</span> 

  return (
    <>
      {loading ? <p>Loading...</p> : (
        <div>
          <h2>Persons</h2>
          {data.allPersons.map(p => (
          <div>
            {p.name}
          </div>))}
        </div>
      )}
     
    </>
  )
}


export default Home;
```

### usar parametros para las queries
```stx
import type { NextPage } from 'next'
import Head from 'next/head'
import Image from 'next/image'
import Link from 'next/link'
import { gql,useLazyQuery,useQuery} from '@apollo/client'
import { useState, useEffect } from 'react'

//useLazyQuery : hara la peticion cuando ocurra un evento

//findPersonByName : es un nombre inventado para la query, puede ser cualquier otro nombre

//findPerson() es la query y el resolver creado el cual tiene la funcion de busca los datos de una person apartir del nombre
const FIND_PERSON = gql`
  query findPersonByName($nameToSearch: String!) {
    findPerson(name: $nameToSearch){
      name
    }
  }
`

const ALL_PERSONS = gql`
  query ViewerQuery {
    allPersons{
      name
    }
  }
`

const Home: NextPage = () => {
  //useQuery: lo que hace es que en cuanto se renderiza hace la peticion
  //para controlar cuando se hace la peticion podemos usar useLazyQuery
  const {data,error,loading} = useQuery(ALL_PERSONS);
  const [getPerson, result] = useLazyQuery(FIND_PERSON);
  //useLazyQuery: devolve un array de dos posiciones:
  // En la primera posicion es cuando queremos activar la consulta (getPerson)
  // la segunda posicion seria el resultado (result)

  const [person, setPerson] = useState(null);
  
  const showPerson = name => {
    getPerson({variables:{nameToSearch: name}})
  }
  if(error) return <span className="bg-red"></span>;

  useEffect(() => {
    if (result.data){
      setPerson(result.data.findPerson)
    }
  },[result])

  return (
    <>
      {loading ? <p>Loading...</p> : (
        <div>
          <h2>Persons</h2>
          {data.allPersons.map(p => (
          <div onClick={() => showPerson(p.name)}>
            {p.name}
          </div>))}
          {person === null ? null : (<div>
            <h2>{person.name}</h2>
            <div>{person.city}</div>
            <button onClick={()=> setPerson(null)}>Close</button>
            </div>)
          }
        </div>
      )}
     
    </>
  )
}


export default Home;
```