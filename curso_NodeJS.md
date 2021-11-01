## Node.js

## Instalación de Node.js
Si vas a trabajar con Node.js, lo primero que tienes que hacer, es instalarlo en tu máquina. Ya sea con Windows, Linux o Mac, si vas a la web de [Node.js](https://nodejs.org), la web detectará tu sistema operativo, y te ofrecerá un paquete con el que instalarlo.

Simplemente pulsa en el botón verde de la versión que quieras (mi recomendación es siempre usar las versiones LTS) y completar el proceso de instalación. Dependiendo del sistema operativo, te hará más o menos preguntas, pero con las opciones por defecto se instalará bien.

Como consejo, asegúrate de tener una buena conexión a internet cuando lo instales, para que tarde poco tiempo.

Una vez lo hayas instalado, para comprobar que todo funciona correctamente, abre una terminal (en windows, CMD o PowerShell valen perfectamente) y escribe:

node -v

Ese comando te devolverá la versión de Node.js que se ha instalado.

También nos habrá instalado NPM, el gestor de paquetes. Para asegurarte de que está instalado, puedes ejecutar:

npm -v

Y te devolverá la versión de NPM que hay instalada.

Con esto, ya tenemos instalado Node.js y NPM, que es todo lo que necesitamos para empezar con nuestro curso de Fundamentos de Node.js.

## Node: orígenes y filosofía

**NodeJS es un entorno de ejecución de JavaScript fuera del navegador**. Se crea en 2009, orientado a servidores. Es muy importante que esté fuera del navegador debido a que ya no es necesario un navegador web para ejecutar código JavaScript.

Características principales de JavaScript:

- **Concurrencia**: Es monohilo, con entradas y salidas asíncronas.

- **Motor V8**: Creado por Google en 2008 para Chrome. Escrito en C++. Convierte JS en código máquina en lugar de interpretarlo en tiempo real.

- Todo funciona en base a **Módulos**, que son piezas de código muy pequeñas que modularizan nuestros sistemas y ayudan a entender mejor el código.

- **Orientación a Eventos**, existe un bucle de eventos que se ejecuta constantemente. Lo que nos permite programar de forma reactiva, lo que quiere decir que podemos programar con la lógica de “Cuando sucede algo, se ejecuta esta parte de mi código y eso a su vez dispara otra parte”.

## EventLoop: asíncrona por diseño

- **Event Lopp** :  UN proceso con un **bucle** que gestiona, de forma asicrona, todos los eventos de tu apliacion. Se encarga de resolver los eventos ultra rápidos que llegan desde el Event Queue. En caso de no poder resolverse rápido, enviá el evento al Thread Pool.

- **Event Queue** : Contiene todos los eventos que se generan por nuestro código (Funciones, peticiones, etc.), estos eventos quedan en una cola que van pasando uno a uno al Event Loop.

- **Thread Pool:**: Se encarga de gestionar los eventos de forma asíncrona. Una vez terminado lo devuelve al Event Loop. El Event Loop vera si lo pasa a Event Queue o no.

## Monohilo: implicaciones en diseño y seguridad

creamos un nuevo archivo `monohilo.js`, simeplemente para crear archivos en donde creamos un archivo de javascript.

```
console.log("Hola mundo");
```

Y ahora en la terminal de comandos ejectuamos:
```
node monohilo.js
```

Simplemente imprimio `Hola mundo`, el **proceso** que ocurrio es:
1.- Va a abrirse un proceso, ese proceso es un proceso de node
2.- Interpreta todo el archivo
3.- Convertirlo a código maquina
4.- Prepara todo lo que necesita para ejecutarse
5.- Se ejecuta
6.- Se cierra el proceso, y termina

**DESVENTAJAS MONOHILO**:
- Si no se manejan bien los errores y uno truena, ya no continua con los procesos posteriores.
- Debes estar pendiente de todo el código

El hecho de que sea monohilo lo hace delicado en el sentido de que puede ejecutarse algo que corte el código y detenga el programa, como la ausencia de sintaxis o una variable pendiente por definir.

Aquí se pueden ver los problemas de seguridad y los Updates en este tema. Muy interesante leerlo para entender cómo atacan y saltan el código y cómo lo resolvieron.

- [Security Issues](https://nodejs.org/en/blog/vulnerability/february-2020-security-releases/)

```js
console.log('Hola mundo');

// SetInterval me permtie ejecutar una función cada n cantidad de tiempo, por lo que quiere que recibe como argumentos: Función a ejecutarse, intervalo de tiempo.
//A tener  en cuenta esta función no se detiene y continúa su ejecución ad infinitum.
// Detener ejecución con ctrl+ alt + m en Run Code, o con Ctrl +c en la terminal.
setInterval(function(){console.log('Voy a contar hasta infinito, detén mi ejecución o consumo tu memoria'),1000}); // Esta instrucción es asíncrona, por lo que se ejecuta en n momento.


let i = 0;
setInterval(function() {
    console.log(i);
    i++;

// Al ser monohilo el peligro recae en que si el código se ejectua y no tenemos cuidado el no asignar una variable de manera correcta me puede arrojar un error.
//Hay que escuchar los errores, es muy imporante de todo lo que pase en el código. Comprobar funciones y revisar lo que posiblmente puede fallar.
//Es clave estar pendiente de todos los errores que pueda cortar la ejecución, lo que se corta corta todo.
// Todo lo que sea asíncono y lo pueda llevar a ello, pues llevarlo, y todo lo que no, revisar que no corte el programa.

    // if (i === 5) {
    //     console.log('forzamos error');
    //     var a = 3 + z;
    // }
}, 1000);


console.log('Segunda instrucción');
```

## Variables de entorno
Para las varibales de entorno se recomienda que sean en mayusculas y si son dos palabras que esten separadas por `_` guion bajo.

EN un archivo .js:
```
let saludo = process.env.NOMBRE;

console.log(nombre)
```

y en la consola para decirle el valor de la variable ejecutamos:
```
NOMBRE=Calors node entorno.js
```

## Herramientas:  Nodemon y PM2

- [nodemon](https://nodemon.io/): ES basicamente un gestor de node, puedes tener un proceso corriendo y observando cambios. Nodemon lo que va hacer es crearnos una herramiento que cada vez que detecte cambios en el codigo que estamos ejecutando o en cualquiera de las dependencias relacionadas con ese codigo, en todos los archivos que esten relacionados con ellos, va a volver a ejectuar ese codigo de forma automatica.

En la terminal de comandos ejecutamos:
```
npm install -g nodemon 
```

Ahora en lugar de ejectuar un archivo con `node` usamos `nodemon` en la terminal de comandos:
```
nodemon entorno.js
```

Ahora en el momento de que hagas algun cambia al archivo `entorno.js` y guardes, automaticamente nodemon va a detectar  el cambio.Se recomienda usar solamente en **produccion**.

- [PM2](https://pm2.keymetrics.io/) : Es algo parecido a nodemon solo que es mas avanzada y mas compleja , tiene mas funcionalidades. No se recomianda usar en desarrollo, por que en desarrollo lo que queremos es que el codigo cambie rapido y podamos verlo rapido, pero una vez lo llevemos a produccion con `PM2` vamos a poder tener todo el codigo monitorizado, si por lo que sea hay un cambio y rompe, `PM2` se encargara de detectar en que se a roto y volverlo a levantar(volver a ejecutar) de manera automatica. 

Para instalarlo:
```
npm install -g pm2
```

para usarla:
```
pm2 start monohilo.js
```

- `pm2 status`

- `pm2 log`

## [globals](https://nodejs.org/docs/latest-v13.x/api/globals.html)
Los modulos que existen en node.js:
```
console.log(global)
```
- `global`: es el objeto donde estan todos los modulos globales guardados.

- `require()`:  nos va a permitir acceder a caulqueir módulo.
 
Podemos agregar variables globales:
```
global.miVriable = "elValor"

console.log(miVriable);
```

## File system
El file system nos va a permitir acceder a los archivos de nuestro sistema. Leerlos, escribirlos, cambiarlos de nombre.

creamos un archivo ejemplo `archivo.txt`:
```
Hola, to soy archivo Y tengo varias lineas 
```

creamos un nuevo archivo `fs.js` o el nombre que quieras:
```js
const fs = require("fs"); //asi nos traemos un modulo dentro de node.No tenemos que ponerle nadamas el como traerlo viene ya en el code de node.

function leer(ruta,cb){
    fs.readFile(ruta ,(err,data)=>{
        console.log(data.toString());
    }) 
};

leer(__dirname + "/archivo.txt"):
/*Lo que imprimiria seria:

Hola, to soy archivo Y tengo varias lineas 

 */
```
Todos los metodos tienen una alternativa asincrona pero no es recomendable, cuando tienes una alternativa asincrona estas bloqueando el proceso principal y en caso de que tuvieras que ejecutar muchas mas cosas el proceso principal esta bloqueado 

```js
const fs = require("fs"); 

function leer(ruta,cb){
    //readFile permite leer un archivo
    fs.readFile(ruta ,(err,data)=>{
        console.log(data.toString());
    }) 
};

function escribir(ruta,contenido,cb){
    //writeFile permite escribir en un archivo
    fs.writeFile(ruta, contenido, function()=>{
        if(err){}else{
            console.log("Se ha escrito correctamente");
        }
    })
}

escribir(__dirname + "/archivo1.txt", "soy un archivo nuevo")

//funcion para borar un archivo
function borrar(ruta, cb){
    fs.unlink(ruta, cb)
}
```

## Console
Con console podemos imprimir todo tipo de valores por
nuestra terminal.

- `console.log`: recibe cualquier tipo y lo muestra en el consola.
- `console.info`: es equivalente a log pero es usado para informar.
- `console.error`: es equivalente a log pero es usado para errores.
- `console.warn`: es equivalente a log pero es usado para warning.
- `console.table`: muestra una tabla a partir de un objeto.
- `console.count`: inicia un contador autoincremental.
- `console.countReset`: reinicia el contador a 0.
- `console.time`: inicia un cronometro en ms.
- `console.timeEnd`: Finaliza el cronometro.
- `console.group`: permite agrupar errores mediante identación.
- `console.groupEnd`: finaliza la agrupación.
- `console.clear`: Limpia la consola.

## Errores (try / catch)
Con Node podemos manejar los errores de una manera muy optima, pero primero debemos entender como Node maneja los errores por defecto.
Cuando sucede un error en Node, él por defecto terminara todo el proceso de nuestro código para avisar que ha ocurrido un error, esto puede ser fatal para nuestros proyectos, los errores además se notifican por hilos, es decir, que si un error sucede en el hilo principal del event loop, es decir, el evento queue, el error se avisara desde este mismo hilo, pero si un error sucede antes desde otro hilo como el hilo de las funciones asíncronas, el error se avisara desde aquel hilo sin dejar mostrar el error del hilo principal.
Nosotros podemos manejar este flujo de errores para que Node no se detenga al momento de que ocurra uno y lo podamos manejar según nuestros deseos, para esto usamos try y catch. Siendo try el bloque de código que ejecutara la función que puede o no fallar y siendo catch la función que atrapara el error y le especificaremos que hacer con él.

## [Procesos hijo](https://nodejs.org/api/process.html)
El módulo de procesos secundarios de Node.js (**child_process**) tiene dos funciones spawn y exec, mediante las cuales podemos iniciar un proceso secundario para ejecutar otros programas en el sistema.

La diferencia más significativa entre child_process.spawn y child_process.exec está en lo que spawn devuelve un stream y exec devuelve un buffer.

Usa spawn cuando quieras que el proceso hijo devuelva datos binarios enormes a Node.
Usa exec cuando quieras que el proceso hijo devuelva mensajes de estado simples.
Usa spawn cuando quieras recibir datos desde que el proceso arranca.
Usa exec cuando solo quieras recibir datos al final de la ejecución.

En node podemos crear procesos hijos que ejecuten cualquier accion de nuestro sistema operativo, como si nos encontraramos en la linea de comandos.

Podemos llamar a **exec** para ejecuciones sencillas:
```js
const {exec} = require("child_process");
// const exec = requier("child_process").exec;

exec('ls -la', (e, stdout) => {
    (e) 
    ? console.log(e) 
    : console.log(stdout);
})
```

Podemos llamar a spawn para obtener el proceso: La ventaja de este enfoque es que obtienes mayor control del proceso, y del estado en el que se encuenta

```js
const { spawn } = require('child_process');

let processSpawn = spawn('ls', ['-la'])

console.log(processSpawn.pid)
console.log(processSpawn.connected)

processSpawn.stdout.on('data', (datos) => {
        console.log('¿Está muerto?')
        console.log(process.killed)
        console.log(datos.toString())
    }
)
processSpawn.on('exit', () => {
        console.log('El proceso termino')
        console.log(processSpawn.killed)
    }
)
```

## HTTP
Node nos ofrece el modulo HTTP el cual nos permite principalmente crear un servidor en nuestro computador.
En este modulo encontraremos todo lo necesario que necesitamos para crear un sistema de rutas, que responderá cada ruta, los header que podrá mandar, etc.
Uno de los métodos principales de este modulo es createServer, el cual nos permitirá abrir un puerto para crear el servidor.

```js
const http = require("http");

// para crear un servidor:
http.createServer((request,response)=>{
    //request: cuando el cliente hace la peticion
    //response: el servidor manda la respuesta al cliente
    console.log("nueva peticion");
    console.log(request.url); //imprimir la url a la que estan llamando

    response.writeHead(201,{"Content-Type": "text/plain"}); //con esto podemos escribir una cabecera, las cabeceras se pueden ver por el navegador en la pesta;a de `Network`

    //EScribir respuesta al usuario
    response.write("Hola");

    response.end();
}).listen(3000); //con listen podemos asignar un puerto a la peticion se recomienda que sea el 3000
```

## OS
```js
const os = required("os");

console.log(os.arch()); //con esto imprimiremos la arquitectura 

console.log(os.plataform()); //con esto imprimiremos la plataforma en la que estamos

console.log(os.cpus()); //informacion de la cpus que tenemos en nuestro sistema

console.log(os.constants); // Errores y señales del sistema

console.log(os.freemem()); // nos va adecir en bytes la memoria libre que tenemos

console.log(os.totalmem()); // memoria total

console.log(os.homedir());  //directorio raiz del usuario

console.log(os.tmpdir()); // directorio temporal

console.log(os.hostname()); // Hostname of a server

console.log(os.networkInterfaces()); // Actived Network interfaces right now
```

## Process
El objecto process es una instancia de EventEmitter; podemos suscribirnos a el para escuchar eventos de node.

- **UncaughtException**: Permite capturar cualquier error que no fue caputurado previamente. Esto evita que Node cierre todos los hijos al encontrar un error no manejado.


```js
//const process = require("process");

process.on('uncaughtException', (error, origen) => console.log(error, origen));

process.on("uncaughRejection");
```

- **exit**: Se ejecuta cuando node detiene el eventloop y cierra su proceso principal.
```js
process.on('exit', () => console.log('Adios'));
process.on("beforeExit", ()=>{
    console.log("El proceso va a terminar")
})
```

## Gestión de paquetes: NPM y package.json
npm (Node Package Manager) es un administrador de paquetes que permiten ejecutar funciones ya realizadas y validadas y de esta manera acelerar y asegurar la calidad de neustro proceso de desarrollo.

Podemos buscar modulos para casi todo en:
```js
// Para instalar un modulo de npm en nuestro proyecto
$ npm install is-odd

// Para requerir el modulo
const isOdd = require('is-odd');
console.log(isOdd(3)); // true

// Para revisar que los paquetes no estan actualizados a nivel global dentro de nuestro proyecto
npm outdated -g --depth=0
/* 
Va a imprimir algo así:
Package         Current  Wanted  Latest  Location
firebase-tools    8.0.1   8.0.2   8.0.2  global
npm              6.13.7  6.14.4  6.14.4  global
*/

// Para actualizar todos los paquetes a nivel global dentro del proyecto
npm update -g
```

## Construyendo módulos: Require e Import
En Node tenemos una forma de importar módulos la cual es con el método require, el cual es la forma por defecto de importar módulos, ya sean nuestros propios módulos como los de otras personas en nuestros proyectos JS, pero suele haber mucha confusión debido al import.
Import es la forma de importar módulos en Ecmascript, el cual es un estándar de JavaScript para la web, esta forma de importar en teoría Node no la acepta oficialmente, a no ser que usemos su modo de .mjs.
Pero gracias a compiladores como Babel, nosotros podremos utilizar estas normas de Ecmascript en nuestro código para cuando se ejecute se transforme en código que sea aceptable por Node.
Se recomienda en la mayoría de veces la importación con require.

Para importar modulos propios o de terceros, debemos utilizar el require o import (import se considera experimental en versiones antiguas de node)

- Modulo: 
```js
function suma(a, b) { return a + b};
function saludar(nombre) { return `Hola ${nombre}`}
const PI = 3.14159264

module.exports = { suma, saludar, PI }
```

- Importación:
```js
const { suma, saludar, PI } = require(...path_module)
suma(3,2)
saludar('Jesuskinto')
console.log(`Pi es un constante y su valor es: ${PI}`)
```

El import de ES+6 todavía no viene incluido en Node.js, solo viene de forma experimental, en 2021 ya este no es experimental.

```js
import modulo from './modulo.mjs'

modulo()
```
```js
// es importante que el archivo finalice con .mjs
function saludar() {
    console.log(`Hola mundo!`);
}

export default saludar
```

## Módulos útiles

La función de cifrado de **bcrypt** nos permite construir una plataforma de seguridad utilizando contraseñas encriptadas con Salt.

```js
const bcrypt = require("bcrypt");
const password = "NuncaParesDeAprender2020";

bcrypt.hash(password, 5, function(err, hash){
	console.log(hash)
});
// La consola nos entregaria una contraseña distinta en cada oportunidad.

// Para evaluar si una contraseña concuerda con un hash
bcrypt.compare(password, hash, function(error, result){
	console.log(result)
	console.log(error)
})
// Nos va a responder **true** *(en el result)* o **false** *(en el error)* dependiendo si la contraseña puede generar el hash
```

**Moment.js** es una librería que nos permite solventar estos problemas e implementa un sistema de manejo de fechas mucho más cómodo.
```js
const moment = require('moment')
const ahora = moment();

// Para formatear una fecha
ahora.format('MM/DD/YYYY HH:MM A'); // 04/11/2020 20:10 PM

// Para validad una fecha
moment('2020-04-11').isValid(); // Nos dara **true** o **false** dependiendo de si la fecha es valida o no

// Para encontrar cuanto tiempo ha pasado hasta hoy
moment('2018-04-11').fromNow(); // Hace 2 años

// Para agregar o eliminar años, días o meses
moment('2020-04-11').add(1, 'years'); // 2021-04-11
moment('2020-04-11').subtract(1, 'years'); // 2019-04-11
```

**Sharp** puede convertir imágenes grandes en imágenes JPEG, PNG más pequeñas y compatibles con la web de diferentes dimensiones.

```js
const sharp = require('sharp')

// La siguiente reducira una imagen de 120x120 o cualquier tamaño a 80x80 y lo guardara en una imagen mas pequeña sin eliminr la original.
sharp('imagen.png').resize(80, 80).toFile('imagen_80x80.png');
```

## Datos almacenados vs en memoria
- La información en memoria esta pensada para ser escrita rapida pero borrada tambien rapida.
- La información almacenada en disco puede ser almacenada durante mucho mas tiempo pero es mucho mas lento escribir y leer en ellos.

Memoria RAM: Es la memoria de corto plazo del computador. Su función principal es recordar la información que tienes en cada una de las aplicaciones abiertas en el computador, mientras este se encuentre encendido.

Disco Duro: El disco duro guarda y protege los datos a largo plazo, lo que significa que quedarán guardados incluso si se apaga el computador.

## Buffers
Un buffer es un espacio de memoria (en la memoria ram), en el que se almacenan datos de manera temporal.

Es la forma mas cruda en la que se pueden almacenar los datos. (Se guardan en **bytes** y no se especifica el tipo de dato)

En la consola, **los datos se muestran en formato hexadecimal**.

**Creacion de un bufer básico**
Para crear un buffer, con 4 espacios por ejemplo, podemos hacerlo con la siguiente sintaxis.
```js
let buffer = Buffer.alloc(4);
console.log(buffer); 
// Output:
//<Buffer 00 00 00 00>
```

**Otras formas de crear un buffer**
- Datos en un arreglo:
```js
let buffer2 = Buffer.from([1,2,3]);
console.log(buffer2);
```

- Datos de tipo string:
```js
let buffer3 = Buffer.from('Hola');
console.log(buffer3);
console.log(buffer3.toString());
```

- Guardar el abecedario en un buffer:
```js
let abc =  Buffer.alloc(26);
console.log(abc);

for (let i = 0; i< abc.length; i++){
  abc[i] = i + 97;
}

console.log(abc);
console.log(abc.toString())
```

## Streams
Podría decirse que un Stream es el proceso de ir consumiendo datos al tiempo en que se reciben. Por ejemplo, cuando vemos un video en Youtube estamos consumiendo datos por medio de streaming (readable stream, porque solo podemos ver los videos mas no editarlos) ya que lo vemos al mismo tiempo en que este se está descargando. de lo contrario habría que esperar a que se descargue el video por completo para poder verlo.

buffer
Si en el caso anterior, mientras vemos el video, fallara el internet, así sea por un segundo, la reproducción se pararía instantáneamente. Pero sabemos que en realidad no es así, el video continúa reproduciéndose por un tiempo mas. Esto es gracias a la implementación de un buffer el cuál es un espacio en memoria ram en donde la información proveniente del servidor llega por fragmentos (chunks), para luego ser consumido, y como ese almacenamiento de datos en el buffer se hace a bajo nivel, de forma binaria, el proceso es mucho mas rápido de lo que se consume. Es por eso que cuando reproducimos un video en Youtube vemos que este se carga mas rápido. (dependiendo del ancho de banda claro está)

## Benchmarking (console time y timeEnd)
```js
console.time("Temporizador");
for (var i = 0; i < 10000; i++) {
  // Nuestro codigo entre los temporizadores puede ser cualquier cosa.
}
console.timeEnd("Temporizador");
```

**¿Qué es más rápido?**
- `Suma++`

- `Suma = Suma + i`

```js
let suma = 0;
let suma2 = 0;

console.time('Tiempo bucle');
for (let i = 0; i < 1000; i++) {
    suma++;
}
console.timeEnd('Tiempo bucle')

console.time('Tiempo bucle 2');
for (let j = 0; j < 1000; j++) {
    suma2 = suma2 + j;
}
console.timeEnd('Tiempo bucle 2')
```

## Debugger

Node.js viene integrado con un modo de debug para poder conectarnos desde cualquier herramienta de inspección de código a nuestro código de node.js.

Podemos utilizar en la terminal el flag de `--inspect` con nodemon.
```
npx nodemon --inspect http.js
```

Para poder acceder a debugger de chrome vamos a la url `chrome://inspect/#devices` y le dan a inspect en el remote target que quieres inspeccionar.


## Error First Callbacks
Los **Error First Callbacks** se utilizan para pasar primero el error y los datos posteriormente. Entonces, puedes verificar el primer argumento, es decir, el objeto de error para ver si algo salió mal y puedes manejarlo. En caso de que no haya ningún error, puedes utilizar los argumentos posteriores y seguir adelante.

```js
fs.readFile('/text.txt', function(err, data) {
	if (err) {
		console.log(err);
	} else {
		console.log(data);
	} 
});
```
Un patrón que se sigue siempre en cualquier lenguaje y programa de devs es Error First Callbacks, esto quiere decir que siempre que tengamos un callback el primer parámetro debería ser el error. **Esto se usa por la convención de que todo puede fallar.**

Otro patrón típico es tener el callback es tener en el callback como la última función que se pasa. Aunque depende del caso.
```js
function asincrona(callback) {
    setTimeout(() => {
        try {
            let a = 3 + w
            callback(null, a)
        } catch (error) {
            callback(error)
        }
    }, 1000)
}

asincrona((err, dato) => {
    if (err) {
        console.error('Tenemos un error')
        console.error(err)
        return false

        // throw err
    }

    console.log(`Todo ha ido bien, mi dato es ${dato}`)
})
```

## Scraping

```
npm i puppeteer
```
```
const puppeteer = require('puppeteer');

(async () => {
    console.log('lanzamos navegador');
    // const browser = await puppeteer.launch();
    const browser = await puppeteer.launch( { headless: false } );

    const page = await browser.newPage();
    await page.goto('https://es.wikipedia.org/wiki/Node.js');

    var titulo1 = await page.evaluate(()  => {
        const h1 = document.querySelector('h1');
        console.log(h1.innerHTML);
        return h1.innerHTML;
    });

    console.log(titulo1);
    console.log('Cerramos navegador');
    browser.close();
    console.log('Navegardor cerrado');
}) ();
```

## Automatización de procesos
**Que es gulp.js?**

Es una herramienta de construcción en JavaScript construida sobre flujos de nodos . Estos flujos facilitan la conexión de operaciones de archivos a través de canalizaciones . Gulp lee el sistema de archivos y canaliza los datos disponibles de un complemento de un solo propósito a otro a través del .pipe()operador, haciendo una tarea a la vez. Los archivos originales no se ven afectados hasta que se procesan todos los complementos. Se puede configurar para modificar los archivos originales o para crear nuevos. Esto otorga la capacidad de realizar tareas complejas mediante la vinculación de sus numerosos complementos. Los usuarios también pueden escribir sus propios complementos para definir sus propias tareas.

```
npm i -g gulp gulp-server-livereload
```
```js
const gulp = require("gulp");
const server = require("gulp-server-livereload");

gulp.task("build", function (cb) {
  console.log("Construyendo el sitio");
  setTimeout(cb, 1200);
});

gulp.task("serve", function (cb) {
  console.log("Abrí la web");
  gulp.src("www").pipe(
    server({
      livereload: false,
      open: true,
    })
  );
});
```

## Aplicaciones de escritorio
(conocido anteriormente como Atom Shell1​) es un framework de código abierto creado por Cheng Zhao, y ahora desarrollado por GitHub. Permite el desarrollo de aplicaciones gráficas de escritorio usando componentes del lado del cliente y del servidor originalmente desarrolladas para aplicaciones web: Node.js del lado del servidor y Chromium como interfaz. Electron es el framework gráfico detrás de muchos proyectos de código abierto importantes, incluyendo a Atom de GitHub​ y Microsoft Visual Studio Code. Wikipedia
Aplicaciones que usan Electron: 💪 Visual Studio Code, Atom, Slack, WhatsApp, Skype, Twich, Signal, Github desktop.
```
npm i electron
```
```js
const { app, BrowserWindow } = require('electron');

let mainWindow;

app.on('ready', createMainWindow);

function createMainWindow(){
    mainWindow = new BrowserWindow ({
        width: 800,
        height: 600,
    })

    mainWindow.loadFile('index.html')
}
```