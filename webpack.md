# WEBPACK
webpack es un empaquetador de archivos para aplicaciones javascript modernas totalmente configurable y a diferencia de los tacksruners como grond y golp donde los procesos de van gestionando de forma separada en webpack se conoce el punto de origen desde el cual se va a compilar todo en un solo unico archivo y en webpack va a crear solamente una grafica de todas las dependencias que la aplicacion en la que estas desarrollando necesita, para ello va a hacer uso de un archivo de configuracion que se llama `webpack.fing.js` donde se van definiendo todos estos procesos de construccion en un objeto javascript.

`webpack.fing.js`:  Este archivo de configuracion js es un archivo javascript pero es un archivo que esta escrito en el hambiente del lado del servidor node.js.

**Webpack** tiene 4 conceptos muy importantes:
- las **Entry**: **Indica cuál es el punto(s) de entrada.**. Es decir cual es el achivo del cual va hacer la grafica antes mencionada y a partir de ahi va hacer las importaciones de las dependencias.

- el **Output**: **Indica cuál es el punto(s) de salida.**. Es decir, cuando ya compule todo a codigo ECMASCript5 donde se van a alojar esos archivos para que cualquier navegador los pueda interpretar.

- los **Loaders**: **Realizan transformaciones en los archivos.**. Por ejemplo: se puede usar un loader para que webpack pueda compilar e interpretar el codigo css, otro loader para que pueda interpretar la sintaxis de react, otro loader si quieres agregar la sintaxis de typescrypt.

- los **Plugins**: **Realizan acciones en los archivos**. Por ejemplo: se pueda utilizar un modulo para inyectar todas las dependencias al archivos principal html de nuestra aplicacion o para extraer el codigo css en un hoja independiente, etc.

Aprende más sobre Webpack:
- [Sitio Oficial](https://webpack.js.org/)
- [Conceptos básicos](https://webpack.js.org/concepts/)
- [Configuración básica](https://webpack.js.org/configuration/)
- [Loaders](https://webpack.js.org/loaders/)
- [Plugins](https://webpack.js.org/plugins/)
- [Dev Server](https://webpack.js.org/configuration/dev-server/)

## Sin configuracion
Primero que nada vamos a necesitar instalar node.js de preferencia npm.

En este momento webpack va en la version 5 y a partir de la version 4 las configuraciones son mas amigables, digamos que ya nos ofrece varias cosas webpack.

Podemos empezar a utilizar webpack sin necesidad de tener un archivo de configuracion, es decir sin la necesidad de tener el archivo `webpack.fing.js`, para ellos necesitamos instalar via node las dependencias.

En una carpeta nueva ejecutamos:
```
npm init
```
Y lo siguiente seria la configuracion del npm:
```
package name: (youtube-webpack) 
version: (1.0.0) 
description: Codigos del curso de webpack
entry point: (index.js) 
test command: 
git repository: 
keywords: webpack
author: Diego Fernandez <diegofernandezp001@gmail.com>
license: (ISC) MIT
```
con esto se va agenerar el archivo `package.json` que va a ser el archivo de configuracion de este proyecto. EL cual seria similar a este:
```json
{
  "name": "youtube-webpack",
  "version": "1.0.0",
  "description": "Codigos del curso de webpack",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "keywords": [
    "webpack"
  ],
  "author": "Diego Fernandez <diegofernandezp001@gmail.com>",
  "license": "MIT",
}

```

**Muy importante**: aqui necesitamos instalar dos dependencias inicialmente webpack y webpack-cli, es decir la interfaz de linia de comando que nos va apermitir ejecutar todos los comandos que vayamos haciendo en node.js.

**webpack y webpack-cli** las vamos a instalar como dependencias de desarrollo por que solo las necesitamos para la face de desarrollo de nuetra aplicacion ya cuando la aplicacion se despliege no es por eso que va a ser una dependencia de desarrollo.

le vamos a dar la siguinete instruccion a node, (la opcion -D es para que lo instale como dependencia de desarrollo):
```
npm install -D webpack webpack-cli
```
Cuando termina de instarse te vas a dar cuenta que en el `package.json` va a generar un arbol de dependencias con la version exacta que a instalado de webpack y de webpack-cli.Esto seria lo que se le agrego el archivo `package.json`:
```json
"devDependencies": {
    "webpack": "^5.58.2",
    "webpack-cli": "^4.9.0"
  }
```

Practicamente ya podriamos utilizar sin la necesidad de configurar webpack, lo unico que tendriamos que hacer es crear un comando que ejecute webpack, para ellos vamos a modificar el `scripts`:
```json
{
  "name": "youtube-webpack",
  "version": "1.0.0",
  "description": "Codigos del curso de webpack",
  "main": "index.js",
  "scripts": {
    "build": "webpack"
  },
  "keywords": [
    "webpack"
  ],
  "author": "Diego Fernandez <diegofernandezp001@gmail.com>",
  "license": "MIT",
  "devDependencies": {
    "webpack": "^5.58.2",
    "webpack-cli": "^4.9.0"
  }
}
```
Entonces con esto ya solamente tendriamos que ejecutar en nuestra terminal el comando:
```
npm run build
```
despues de ejecutar este comando saldra un error por que no encontro la carpeta `src`.

Webpack está buscando un punto de entrada en ./src 😱😱😱¡¡¡ Sin Archivo de configuración !!!

A partir de la versión 4 no es necesario definir el punto de entrada, tomará ./src/index.js como valor predeterminado 🤓.

En versiones anteriores, el punto de entrada debe definirse dentro del archivo de configuración denominado **webpack.config.js**.

Vamos a crear un carpeta `src` y dentro de esa carpeta lo que nos pide webpack es tener un archivo que se llame `index.js` el cual vamos a crear:
```
mkdir src
cd src
touch index.js
```
tambien tenemos que hacer una modificacion al `package.json` en el `main` (donde se encuantra el archivo principal):
```json
{
  "name": "youtube-webpack",
  "version": "1.0.0",
  "description": "Codigos del curso de webpack",
  "main": "src/index.js",
  "scripts": {
    "build": "webpack"
  },
  "keywords": [
    "webpack"
  ],
  "author": "Diego Fernandez <diegofernandezp001@gmail.com>",
  "license": "MIT",
  "devDependencies": {
    "webpack": "^5.58.2",
    "webpack-cli": "^4.9.0"
  }
}
```

Y ahora si en ese archivo `index.js` es donde podriamso empezar a escribir lineas de codigo. 

Si escribirmos codigo en `index.js` y luego ejecutamos en la terminal:
```
npm run build
```
Podemos ver que logro compilarlo y creo una carpeta `dist` y dentro de esa carpeta `dist` me a generado un archivo `main.js`.

Mientras que el archivo `index.js` es nuestro punto de entrada el archivo `main.js` que esta en la carpeta `dist` es nuestro punto de salida.

## Modos
### Producción y Desarrollo
En Webpack un patrón común es tener 2 archivos de configuración uno para las tareas de desarrollo y otro para las de producción.

Mientras que para proyectos grandes aún se pueden necesitar 2 archivos, en proyectos pequeños , es posible especificar el tipo de configuración en una sola línea de configuración.

Desde la versión 4 se introdujo el modo de producción y el modo de desarrollo.

De hecho cuando corrimos el comando build la terminal nos mando un mensaje de advertencia:
```
WARNING in configuration
The 'mode' option has not been set, webpack will fallback to 'production' for this value. Set 'mode' option to 'development' or 'production' to enable defaults for each environment.
You can also set it to 'none' to disable any default behavior. Learn more: https://webpack.js.org/concepts/mode/
```

Estos **modos** hacen referencia al ambiente para el cual va a empaquetar si es un hambiente de **desarrollo** es decir mientras estamos desarrollando nuestra aplicacion o si ya va a preparar el build para **produccion**.

Vamos a modificar de nuevo el archivo `package.json` y le vamos a agregar el modo produccion y de desarollo a `scripts`:
```json
{
  "name": "youtube-webpack",
  "version": "1.0.0",
  "description": "Codigos del curso de webpack",
  "main": "src/index.js",
  "scripts": {
    "dev": "webpack --mode development",
    "build": "webpack --mode production"
  },
  "keywords": [
    "webpack"
  ],
  "author": "Diego Fernandez <diegofernandezp001@gmail.com>",
  "license": "MIT",
  "devDependencies": {
    "webpack": "^5.58.2",
    "webpack-cli": "^4.9.0"
  }
}
```

y si ejecutamos en la terminal el comando:
```
npm run dev
```
Estariamos en el modo de desarrollo, si vemos el archivo `dist/main.js` podemos observar que tiene varios comentarios y algunas evaluaciones de javascript. Justamente esa es la diferencia entre el modo de desarrollo y el modo de produccion.

el **buld** lo que hace es minificar y oufucar nuestro codigo mientras de `**dev** lo ejecuta identado con algunos comentarios y digamos que sin tanta preparacion para que salga a produccion y pese menos.

hasta el momento no hemos creamos un archivo de configuracion y sin embargo ya esmos empezando a trabajar con webpack.

## Diferentes puntos de entrada y salida desde la 
Para hacer esto de tener diferentes puntos de entrada y por ende de salida vamos a crear dos comandos mas en el archivo `package.json`:
```json
{
  "name": "youtube-webpack",
  "version": "1.0.0",
  "description": "Codigos del curso de webpack",
  "main": "src/index.js",
  "scripts": {
    "dev-foo": "webpack --mode development --entry ./foo/src/index.js --output-path ./foo/dist",
    "build-foo": "webpack --mode production --entry ./foo/src/index.js --output-path ./foo/dist",
    "dev": "webpack --mode development",
    "build": "webpack --mode production"
  },
  "keywords": [
    "webpack"
  ],
  "author": "Diego Fernandez <diegofernandezp001@gmail.com>",
  "license": "MIT",
  "devDependencies": {
    "webpack": "^5.58.2",
    "webpack-cli": "^4.9.0"
  }
}
```
despues de esto tenemos que crear las carpetas correspondientes desde la carpeta raiz:
```
mkdir foo
cd foo
mkdir src
cd src
touch index.j
```
Y para entrar a modo desarrolo o modo produccion ahora como indicamos tenemos que usar los comandos:
```
npm run dev-foo
npm run build-foo
```

[comandos Line Interface](https://webpack.js.org/api/cli/) o con `webpack -h` en la terminal de comandos podemos ver las opciones.

## Transpilando JS con Babel

Webpack por sí sólo no sabe como transpilar código ESNext, pero tiene un loader que lo hace.

**Babel** es un un transpilador de codigo javascript, nos permite utilizar. Un ejemplo de su uso es que el codigo y funciones de ECMASCript del 2015 hacia el ahora los transpila hacia el javascript viejo

Instala babel-loader y sus dependencias:
```
npm i -D babel-loader @babel/core @babel/preset-env
```
- `babel-loader`: es el que va a hacer las transformaciones con babel
- `i`: una abreviacion de `install`
- `@babel/core` y `@babel/preset-env`: son los paquetes que justamnete hacen funcionar a babel.

adicionalmente a esta instalacion tenemos que crear un archivo de configuracion que se llama `.babelrc` desde la carpeta raiz. 

Dentro del archivo `.babelrc` en formato json tenemos que indicarle que `presets` vamos a utilizar:
```json
{
  "presets": ["@babel/preset-env"]
}
```

Despues tenemos que crear un archivo `webpack.config.js` en la carpeta raiz.

Toda la programacion que vamos a ejecutar en el archivo `webpack.config.js` es programacion en un entorno del lado del servidor, es decir lo va a ejecutar node.js .

Dentro del archivo `webpack.config.js` escribirmos:
```js
module.exports = {
    module: {
        rules: [
            {
                test: /\.js$/i,
                exclude: /node_modules/,
                use: {
                    loader: "babel-loader"
                }
            }
        ]
    }
}
```
- `module`: va a ir cargando todas las caracteristicas, entre ellas todas las `rules`(reglas) que vamos a estar utilizando.
- `rules` : va a ser un arregloy por cada elemento que tenga puede ser una cadena de texto o un objeto. Las reglas tienene principalmente dos atributos de este objeto:
    - `test`: cual va a ser la prueba, esta prueba realmente es una **expresion regular** que se le pasa, es decir que en el test le vamos a indicar que archivos son en los que voy a trabajar esta regla.
    - `exclude`: podemos indicar que carpetas excluya 
    - `use`: en use podemos indicar el `loader` que vamos a utilizar

Ejecutemos los comandos **dev** y **build** y miremos el archivo ./dist/main.js después de ejecutarlos:_

- **npm run dev**: transpiló el archivo con sintaxis ESNext a ES5 indentado y con comentarios, gracias a la configuración del archivo **webpack.config.js**.
- **npm run build**:  transpiló el archivo con sintaxis ESNext a ES5 minificado y sin comentarios, gracias a la configuración del archivo **webpack.config.js**.

## Inyección de JS en HTML

Para inyectar el código dinámico que genera Webpack en los archivos HTML, necesita 2 dependencias : **html-webpack-plugin** y **html-loader**.

Instala las dependencias:
```
npm i -D html-webpack-plugin html-loader
```
- `html-loader`: gestiona la inyeccion al archivo html
- `html-webpack-plugin`: toma como referencia el archivo index que nosotros le digamos y posteriormente estaria generando los archivos html de salida

ahora crearemos un archivo html de referencia desde la carpeta raiz:
```
cd src
touch index.html
```
ESto seria lo unico que necesitamos escribir en el archivo `index.html`:
```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Aprendiendo webpack</title>
</head>
<body>
    <div id="app"></div>
</body>
</html>
```

Agrega la siguiente regla al archivo `webpack.config.js`:
```js
const HtmlWebpackPlugin = require("html-webpack-plugin");

module.exports = {
    module: {
        rules: [
            {
                test: /\.js$/i,
                exclude: /node_modules/,
                use: {
                    loader: "babel-loader"
                }
            },
            {
                test: /\.html$/i,
                use: [
                    {
                        loader: "html-loader",
                        options: {
                            minimize: true
                        }
                    }
                ]
            }
        ]
    },
    plugins: [
        new HtmlWebpackPlugin({
            template: "./src/index.html",
            filename: "./index.html"
        })
    ]
}
```
En la segunda **rules**(regla) en el atributo **use** usamos `[]` en lugar de `{}` esto quiere decir que podemos usar mas de un loader.

- `options`: pasar algunas opciones
    - `minimize`: significa que cuando el archivo html pasase la compilacion a webpack  me lo va a entregar minificado en la carpeta `dist`.

- `plugins`: para agregar los plugin primero tienen que mandarlos a llamar en legunaje node.js. En este caso seria: 
`const HtmlWebpackPlugin = require("html-webpack-plugin");`

- `HtmlWebpackPlugin`: le pasamos en un objeto las propiedades a este plugin.
  - `template`: cual es el archivo html base de; que se va a vazar para generarme la minimizacion.
  - `filename`: como quiero que se llame el archivo en la carpeta de distribucion.

En la documentacion de[webpak se pueden ver las formas de agregar los [html-loader](https://webpack.js.org/loaders/html-loader/).

Ejecutemos los comandos **dev** o **build** y miremos el archivo `./dist/index.html` después de ejecutarlos.

No es necesario incluir el JavaScript dentro del archivo HTML, Webpack lo ha inyectado automáticamente y ha minificado el código.

## Extracción de CSS
Webpack por sí sólo no sabe como extraer código CSS en un archivo externo, pero tiene un loader y un plugin que lo hace.

Instala las dependencias:
```
npm i -D mini-css-extract-plugin css-loader
```

Agrega la siguiente regla al archivo `webpack.config.js`:
```js
const HtmlWebpackPlugin = require("html-webpack-plugin"),
MinicssExtractPlugin = require("mini-css-extract-plugin");

module.exports = {
    module: {
        rules: [
            {
                test: /\.js$/i,
                exclude: /node_modules/,
                use: {
                    loader: "babel-loader"
                }
            },
            {
                test: /\.html$/i,
                use: [
                    {
                        loader: "html-loader",
                        options: {
                            minimize: true
                        }
                    }
                ]
            },
            {
                test: /\.css$/i,
                use: [MinicssExtractPlugin.loader, "css-loader"]
            }
        ]
    },
    plugins: [
        new HtmlWebpackPlugin({
            template: "./src/index.html",
            filename: "./index.html"
        }),
        new MinicssExtractPlugin()
    ]
}
```

ES importante que en `use` se agregen los louder en el orden correspondiente por que si no no va a funcionar.

Ahora crea el archivo `./src/style.css` con algo de código:
```css
html {
  box-sizing: border-box;
  font-family: sans-serif;
  font-size: 16px;
  color: #8dd6f9;
  background-color: #2b3a42;
}
```

Ahora importamos los estilos desde el punto de entrada, el archivo `./src/index.js`:
```js
import style from "./style.css"; //esto es lo unico que vamos a agregar

const arr = [1,2,3],
condeESNext = () => console.log(...arr);

condeESNext();
```

Ejecutemos los comandos **dev** o **build** y miremos el archivo ``./dist/index.html`` después de ejecutarlos.

No es necesario incluir el CSS dentro del archivo HTML, Webpack lo ha inyectado automáticamente y ha creado el archivo de estilos **main.css**. 

## Servidor Web de Desarrollo
No es muy óptimo estar ejecutando el comando **dev** cada vez que hacemos un cambio en nuestra aplicación lo ideal es configurar un servidor web de prueba que en automático recompile nuestro código y recargue el navegador.

Webpack, cuenta con su propio servido de desarrollo.

Instala la dependencia:
```
npm i -D webpack-dev-server
```

Agregamos el comando **start** a nuestro **package.json**:
```json
"scripts": {
  "start": "webpack serve  --mode development --open --port 3000"
}
```
- `open`: indicacion oara que abra automaticamente nuestro navegador.
- `port`: incia el numero del puerto, si no lo ponemos, por defecto sera el puerto 8080
Al ejecutarlo, Webpack abrirá la aplicación en una ventana del navegador.

```
npm start
```

## Manejo de archivos

## optimizacion de imagenes