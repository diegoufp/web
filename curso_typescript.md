# REACT Y TYPESCRIPT

## instalacion
```
npx create-react-app@5.0.0 react-tasks-app --template typescript
```
Con esto se creara todo un entorno configurado de typescript para react.

Se creara en la carpeta un archivo llamado `tsconfing.jon` aqui es donde se configura typescritp.

Otro cambio es que en lugar de archivos `js` o `jsx` van a ser archivos `tsx`, basicamente es lo mismo solo que ahora vamos a tener acceso a declarar tipos de datos y algunas otras caracteristicas mas que nos da typescript.

**Instalacion paquete por paquete**

- crear una package.json:
```
npm init --yes
```
- instalar typescript de manera global:
```
npm i -g typescript
```
Cuando se instale globalmente typescript vamos a tener un nuevo comando disponible llamado `tsc`, este comando `tsc` es el compilador de typescript, es el programa que convierte codigo typescript a javascript.
En este caso lo vamos a usar dentro de nuestro proyecto para generar un archivo de configuracion de typescript.
```
tsc -v
tsc --init
```
Con esto se creara un achivo llamado `tsconfig.json`, es un archivo que define como queremos que trabaje typescript. Vamos a descomentar la opcion de:
```json
{
  "compilerOpcions":{
    // "jsx": "preserve", 
  // "sourceMap": true, 
  // "outDir": "./", 
  //"removeComments": true,    
  // "noEmit": true, 
  // "noImplicitAny": true, //opcional si no queremos quie haya tipos de datos any por defecto
  }
}

```
y la vamos a cambiar por:
```json
{
  "compilerOptions":{
    "jsx": "react",  
    "sourceMap": true,
    "outDir": "./build/",  //esto sirve para que el codigo final este en la carpeta build
    "removeComments": true,  //esto sirve para remover los comentarios  cuando todo el codigo este generado
    "noImplicitAny": true,
     "noEmit": true, 
  },
  //adicional a las opciones del compilador vamos a agregar la opcion include
  // include es simplemente para indicarle los archivos que va a vigilar, en este caso los que esten dentro de la carpeta src
  "include": [
    "./src/**/*"
  ]
}

"jsx": "react",  
"sourceMap": true,
"outDir": "./build/",  //esto sirve para que el codigo final este en la carpeta build
"removeComments": true,  //esto sirve para remover los comentarios  cuando todo el codigo este generado
```

- modulos:
```
npm i react react-dom
```
- dependencias de desarrollo:
  - `ts-loader`: manera de integrar typescript con webpack.
  - `webpack-cli`: necesario para que funcione webpack.
  - `webpack`: herramienta de ayuda
  - `webpack-dev-server`: servidor de desarrollo.
  - `html-webpack-plugin`:  modulo para que webpack entienda html
  - `css-loader`: permite entender el css
  - `mini-css-extract-plugin`: permite minimizar y extraer el css
  - `node-sass`: permite entender sass
  - `sass-loader`: permite cargar el codigo de sass 
  - `@/types/react @/types/react-dom`:  permite a typescript a entender el modulo de react y react dom
```
npm i -D typescript webpack webpack-dev-server webpack-cli ts-loader html-webpack-plugin css-loader node-sass sass-loader @types/react @types/react-dom source-map-loader mini-css-extract-plugin
```

- archivo de configuracion
ESte archivo de configuracion va ayudar a traducir todo el codigo a codigo estandar.

se creara un archivo llamado `webpack.config.js`:
```js
// el modulo path es para trabajar con los directorios
const path = require('path');
const MiniCss = require("mini-css-extract-plugin");
const htmlWebpack = require("html-webpack-plugin")

// entry : cual es el archiv origen
// output : en donde queremos colocar el codigo convertido
// atravez del modulo path se va utilizar el metodo resolve
// con el metodo resolve se indica donde va estar el rpoyecto
// filname: se indica el nombre del archivo js en donde se pondra el codigo convetido
// resolve.extensions:  se pondran todas las extenciones que se planear usar en el proyecto
// module: sirve para indicarle como va a entender todo el codigo
// rules: un arreglo donde se va a especidifcar todo lo que podemos entender
// test: testea todos los archivos que terminen con...
// loader: el modulo que ayuda a entender los archivos con el test indicado
// source-map-loader : para cuando cometamos algun error, nos indica en que linea se a cometido el error exactamente 
module.exports = {
    entry: "./src/index.tsx",
    output: {
        path: path.resolve(__dirname, "dist"),
        filename: "index.js"
    },
    resolve: {
        extensions: [".ts",".tsx", ".js", ".jsx", ".json"]
    },
    module:{
        rules: [
            {
                test: /\.tsx?$/i,
                exclude: /node_modules/,
                use: {
                    loader: 'ts-loader',
                    options: {
                        compilerOptions: {
                            noEmit: false
                        }
                    }
                }
            },
            {
                test: /\.scss$/i,
                use: [MiniCss.loader ,"css-loader", "sass-loader"]
            },
            {
                enforce : "pre",
                test: /\.js$/i,
                loader: "source-map-loader"
            }
        ]
    },
    plugins: [
        new htmlWebpack({template: "./public/index.html"}),
        new MiniCss()
    ],
    devtool: "source-map"
}
```

- configuracion de `package.json`:
```json
"scripts": {
    "dev": "webpack --mode development",
    "build": "webpack --mode production",
    "start": "webpack-dev-server --mode development"
  },
```


## iniciando

```tsx
// en este caso el objeto del enlace "name" tiene un typo "any" 
// es decir que si nosotros no le colocamos ningun tipo de dato como lo pide typescript el asume el dato dependiendo de que valor nosotros le demos
// si nosotros no le damos ningun valor el lo asume que es de tipo "any"
function hello({name}){

  return(
    <div>{name}</div>
  )
}
```

Nosotros podemos agregar cualquier tipo de datos a todos los elementos que queramos.
```tsx

// para definir el tipo de dato en un componente funcional tener que usar dos puntos y un objeto para definirlo
// con esto estariamos declarando que el atrignuto "name", es de tipo string
function hello({name}:{name: string}){

  return(
    <div>{name}</div>
  )
}

```

Otra manera de declarar el tipo de dato en un componente funcional es:
```tsx
function hello(props:{name:string}){

  return(
    <div>{props.name}</div>
  )
}
```

## definicion

Typescript nos permite definir nuestro propio tipo de dato.

```tsx
interface HelloProps {
  name: string;
}


function hello({name}: HelloProps){

  return(
    <div>{name}</div>
  )
}

function App() {
  
  return (
    <>
    {/*En este caso el componente Hello para aparecer subrayado.
    Esto es por que un no se le asigna valor a la propiedad name que se le indico que existe.
    ESta tambien es una ayuda de typescript para observar los errores*/}
    <Hello />
    </>
  );
}

```

Si queremos que la propiedad "name" no siempre sea requerida entonces podemos asignarle un `?` al type.
```tsx
interface HelloProps {
    // si le sginamos el ? significa que es opcional 
  name?: string;
}


function hello({name}: HelloProps){

  return(
    <div>{name}</div>
  )
}

function App() {
  
  return (
    <>
    {/*En este caso ya no apareceria subrayado la palabra Hello por que ya indicamos que la propiedad name es opcional*/}
    <Hello />
    </>
  );
}

```
