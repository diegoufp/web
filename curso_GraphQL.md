# [GraphQL](https://graphql.org/)

Para empezar a utilizar GraphQL hay herramientas como por ejemplo [Apollo](https://www.apollographql.com/).

**Apollo** es una herramienta que brinda como poder crear un servidor y como integrarlos con framework del fort-end para oider intercambiar y recibir datos.

## Inicializacion 

Crearemos una carpeta para el backend. En la carpeta backend ejecutamos:
```
npm init -y
npm i graphql-yoga mongoose
```
- `graphql-yoga`: sirve para crear auna api de graphql.
- `mongoose`: permite conectarnos a mongodb

```
npm i @babel/cli @babel/core @babel/node  @babel/preset-env nodemon -D
```
- `nodemon`: se encarga de recargar el servidor cada vez que haya un cambio 
- `babel`: el es una herramienta que nos permite usar codigo moderno de javascript y luego convierte ese codigo a uno que sea soportado por todos los navegadores

Despues creamos otra carpeta llamada `backend/src` y dentro de src vamos a crear un archivo que va arrancar todo el servidor `backend/src/index.js`

En la carpeta src vamos a editar los `scripts`:
```
"scripts": {
    "dev": "nodemon src/index.js --exec babel-node"
}
```
- `--exec babel-node`: es una instruccion para que primero convierta el codigo y despues lo ejecute


Ahora que se a creamo el comando se puede ejecutar:
```
npm run dev
```
Este compando ejecutara con nodemosn nuestro proyecto y cada vez que se haga un cambio se vuelve a ejecutar.

**babel**

Ahora crearemos el archivo `.babelrc` al mismo nivel que `package.json`.

Este archivo `.babelrc` va a servir para decirle a babel que codigo va a interpretar. Dentro de `.babelrc`:
```js
{
    "presets": [
        ["@babel/env"]
    ]
}
```

**graphql-yoga**

Vamos a crear otro archivo en la ruta `backend/src/server.js`, en este archivo `server.js` vamos a escribir la configuracion de graphql-yoga.

Vamos a crear otro archivo en la ruta `backend/src/database.js`, en este archivo `database.js` va a ser el encargado de tener la conexion con la base de datos.

Se creara una carpeta en la ruta `backend/src/models/` donde se va a definir que es lo que vamos a estar guardando en la base de datos(los modelos de datos).

Se creara una carpeta en la ruta `backend/src/graphql/` donde se guardara los archivos relacionado con la api.

Dentro del archivo :
- `server.js`:
```js

```

https://www.youtube.com/watch?v=mOXabxAUkzg 

8:12