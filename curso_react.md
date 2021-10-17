# REACT JS

## Introducción
React es una biblioteca JavaScript altamente eficiente y declarativa que se utiliza para crear interfaces de usuario interactivas.

Fue creado por el ingeniero de Facebook Jordan Walke y se lanzó en mayo de 2013.

En los últimos años, ha superado a sus rivales y ha establecido firmemente su dominio.

React te insita a crear **código declarativo** (indicas el qué, no el cómo) y orientado a **componentes**.

Un componente es un pieza de código que puede representar una parte de la interfaz de usuario o una funcionalidad en particular que se puede encapsular y reutilizar en diferentes partes de un desarrollo o incluso en diferentes aplicaciones.

Cada componente **reaccionará** a cambios internos (en su estado) o externos (nuevas propiedades recibidas) y se volvera a redibujar (**renderizado**) en la interfaz. Para ello React utiliza su **Virtual DOM** que es una copia del DOM original del navegador para sólo hacer los cambios necesarios en los nodos que hayan reaccionado y evitar redibujar todo el árbol del DOM.

Para poder interactuar con la interfaz React tiene **eventos sintéticos** que son una abstracción de los eventos nativos de los navegadores, para mejorar la compatibilidad y evitar el uso de librerías para **crossbrowsing**.

### ¿Por qué usarlo?
#### Ventajas:
- **Alto rendimiento**: React es conocido por su alta eficiencia y flexibilidad. Se puede integrar fácilmente con diferentes tecnologías. Se puede usar tanto para el lado del cliente como para el lado del servidor.
- **Recursos abundantes** : como Facebook la mantiene, existe una gran cantidad de documentación y recursos disponibles en la web que hace que la curva de aprendizaje sea muy fluida.
- **Compatibilidad con versiones anteriores** : la transición o migración de versiones anteriores a nuevas es bastante fácil y retrocompatible.
- **Estructura de componentes fácil de mantener**: la arquitectura basada en componentes de React ayuda a aumentar la reutilización del código y facilita bastante el mantenimiento de proyectos a gran escala.
- **Fuerte Comunidad**: React tiene más de 1300 colaboradores en GitHub.
- **Documentación Multi idioma**: Actualmente React tiene su documentación en diferentes idiomas entre ellos el español.
- **Flujo de datos unidireccional**: el enlace de datos unidireccional y hacia abajo (de componentes padres a hijos), ayuda a garantizar que los cambios realizados en la estructura del componente hijo no afecten la estructura del componente padre.

#### Desventajas:
- **Complejo**: muchos desarrolladores pueden encontrar en un inicio demasiado compleja la curva de aprendizaje de React en comparación con otros frameworks como el caso de Vue. Dicha complejidad puede ser innecesaria para proyectos a pequeña escala.
- **JSX**: el uso de JSX agrega otra capa de complejidad. JSX es un preprocesador que agrega extensión de sintaxis XML a JavaScript. Aunque JSX ayuda a codificar el código React de una manera más segura y rápida, puede ser difícil de comprender para los nuevos desarrolladores.
- **Necesidad de un ecosistema de muchas herramientas**: React requiere una amplia gama de herramientas para funcionar correctamente y ser compatible con otras tecnologías.
- **Problemas de SEO**: se sabe que las **SPAs** (Single Page Applications) creadas con React se enfrentan a problemas de indexación por parte de los rastreadores y bots de motores de búsqueda.

#### ¿Quién lo usa?

Grandes empresas como Netflix, Yahoo, Airbnb, Instagram, Facebook, WhatsApp, PayPal, Microsoft, la BBC, Aeroméxico, etc. Incluso grandes sitios de información y noticias que antes usaban WordPress se están migrando a sitios hechos con JAM stack y React como librería principal, tal es el caso de Smashing Magazine.

### Entorno y Herramientas de Desarrollo.

React es una librería y no técnicamente un framework. Por lo que sólo maneja la capa de Vista, tomando como referencia el modelo MVC (Modelo Vista Controlador) para el desarrollo de aplicaciones web. Sin embargo cuenta con una amplia gama de herramientas, librerías y frameworks para complementar su entorno de desarrollo, por ejemplo:

- [**Node.js y NPM**](https://nodejs.org/en/): Para ejecutar el entorno de desarrollo e instalar dependencias.
- [**Yarn**](https://yarnpkg.com/): Un gestor de paquetes JavaScript.
- [**Webpack**](https://webpack.js.org/): Es un empaquetador de archivos para aplicaciones JavaScript.
- [**React Router**](https://reactrouter.com/): Librería para manejar rutas declarativas.
- [**Redux**](https://es.redux.js.org/): Es una librería para gestionar el estado de las aplicaciones JavaScript.
- [**Flux**](https://facebook.github.io/flux/): Es la arquitectura de aplicaciones que Facebook usa para crear aplicaciones web del lado del cliente.
- [**Create React App**](https://create-react-app.dev/): Un conjunto de configuraciones preestablecidadas para comenzar a trabajar con React ejecutando un sólo comando.
- [**Gatsby**](https://www.gatsbyjs.com/): Es un framework basado en React para desarrollar rápidamente sitios y aplicaciones web, usando diferentes fuentes de datos como CMS, Markdowns, APIs, etc.
- [**Next.js**](https://nextjs.org/): Es un framework basado en React para desarrollar sitios estáticos y aplicaciones del lado del servidor (SSR - Server Side Rendering).
- [**GraphQL**](https://graphql.org/): Es un lenguaje de consulta de datos para APIs.
- [**React Bootstrap**](https://react-bootstrap.github.io/): Es la versión del popular framework frontend **Bootstrap** pero creado con componentes hechos en React.
- [**Material UI**](https://mui.com/): Es un framework frontend inspirado en **Material Design** creado con componentes hechos en React.
- [**React Native**](https://reactnative.dev/): Es un framework basado en React para la creación de aplicaciones móviles y nativas.
- [**React Dev Tools Chrome**](https://chrome.google.com/webstore/detail/react-developer-tools/fmkadmapgofadopljbjfkapdkoienihi?hl=es): Es una extensión para Chrome que agrega de herramientas de depuración para React.
- [**React Dev Tools Firefox**](https://addons.mozilla.org/es/firefox/addon/react-devtools/): Es una extensión para Firefox que agrega de herramientas de depuración para React.
- [**Simple React Snippets for VSCode**](https://marketplace.visualstudio.com/items?itemName=burkeholland.simple-react-snippets): Es una extensión para Visual Studio Code que nos permite usar atajos para agilizar la escritura de código React.

## [Create React App](https://create-react-app.dev/)
Aunque existen varias formas de empezar con React, una manera sencilla y eficiente es con **create-react-app**, una aplicación de consola que nos va a permitir crear aplicaciones React con cero configuración, lo que nos permitirá centrarnos en los más importante: **Programar en React**.

El unico requisito es tener instalado node.js .
Ubicamos una carpeta donde quieras ejecutar el **create-react-app**.

Para crear una aplicación utilizamos el comando **npx create-react-app** seguido del nombre que le quieras dar a tu aplicación. Por ejemplo:
```
npx create-react-app react-basicos
```
- `react-basicos`: es el nombre que le vamos a dar a a la carpeta.

Cuando ejecutas ese comando create-react-app va a crear una carpeta llama react-basicos con una serie de archivos y subcarpetas para que puedas empezar a trabajar en tu proyecto.

### ¿Qué incluye create-react-app?

Un proyecto creado con create-react-app, además de React, incluye librerías como:

- **Webpack**: que se encarga de procesar y empaquetar nuestro código JavaScript (con sus dependencias), archivos CSS y otros archivos estáticos como imágenes, vectores, fuentes, etc.
- **Babel**: que nos permite usar nuevas características de ECMAScript.
- **PostCSS** que es una librería para el procesamiento de CSS.
**Jest** que es una librería para testing.
etc.
Uno podría configurar un proyecto de React manualmente e incluir cada una de estas librerías, pero es bastante engorroso, create-react-app nos hace la vida más fácil.

### Estructura de carpeta

create-react-app crea la siguiente estructura de archivos y carpetas:
```
react-basicos/
  README.md
  node_modules/
  package.json
  public/
    index.html
    favicon.ico
  src/
    App.css
    App.js
    App.test.js
    index.css
    index.js
    logo.svg
```
Los dos archivos más importantes son:

- **public/index.html** - la plantilla HTML de la aplicación.
- **src/index.js** - el punto de entrada JavaScript de la aplicación.

Puedes eliminar o renombrar otros archivos según tus necesidades.

Dentro de **src** se incluyen todos los archivos JavaScript y CSS de tu aplicación.

También es recomendable incluir otros archivos estáticos como imágenes y fuentes en esta carpeta. Puedes crear subcarpetas para organizar mejor los archivos.

En **public** van todos los archivos estáticos que necesites incluir en la plantilla **public/index.html**.

Puedes crear otras carpetas además de **src** y **public**. Estas carpetas no van a ser incluídas en el paquete de distribución.

### Scripts

En la carpeta del proyecto puedes ejecutar los siguientes comandos:

- **npm start** - inicia el servidor de desarrollo y abre un navegador con la aplicación.
- **npm test o npm run test** - ejecuta las pruebas.
- **npm run build** - empaqueta la aplicación para producción en la carpeta **build**.
- **npm run eject** - permite cambiar manualmente las librerías y configuración que utiliza create-react-app por defecto. Ten cuidado con este comando, una vez que se expulsa la configuración inicial **no hay vuelta atrás**.

### Hot reloading
Una de las funcionalidades más importantes de los proyectos creados con create-react-app es la capacidad de hacer cambios en vivo sin necesidad de reiniciar el servidor. Si haces un cambio en algún archivo en src o public el navegador se refresca automáticamente.

## JSX
Es una extensión de la sintaxis de JavaScript que produce elementos de React.

Se puede usar:

- Dentro de estructuras de control como if y for.
- Asignarlo a variables.
- Aceptarlo como argumento o retorno en funciones.
- Expresiones JavaScript.

Veamos un ejemplo tomado del código que genera create-react-app:

```jsx
<div className="App">
  <header className="App-header">
    <img src="{logo}" className="App-logo" alt="logo" />
    <h1 className="App-title">Welcome to React</h1>
  </header>
  <p className="App-intro">
    To get started, edit <code>src/App.js</code> and save to reload.
  </p>
</div>
```

**JSX** es similar a HTML pero con algunas diferencias importantes:

Algunas reglas importantes:
- Toda etiqueta debe cerrarse por ejemplo `<br>` debera cerrarse a `<br />`.
- Los componentes deben devolver un sólo elemento padre.
- Algunos atributos HTML cambian como:
  - **class** por **className**.
  - **for** por **htmlFor**.
- Los atributos de un elemento JSX pueden aceptar valores de tipo String entrecomillados o expresiones JavaScript entre llaves, por ejemplo:
  - `<img alt="Avatar" src={user.avatarURL} />`

### JSX se transforma en JavaScript

Por debajo **JSX** se transforma en código JavaScript. Por ejemplo, el siguiente código **JSX**.

```HTML
<div class="active">Hola Mundo</div>
```
se transforma en el siguiente código JavaScript:

```js
React.createElement("div", { className: "active" }, "Hola mundo");
```
Puedes utilizar el [REPL de Babel](https://babeljs.io/repl) para ver en qué se convierte el código JSX que escribes.

La ventaja de **JSX** es que, como es JavaScript, podemos:

1. Ver algunos errores en tiempo de compilación.

2. Asignar **JSX** a variables. Por ejemplo:
```js
const el = <p>Hola</p>;
```
3. Retornar **JSX** desde métodos. Por ejemplo:
```js
 renderText() {
   if (someCondition) {
     return <p>Hola</p>;
   } else {
     return <p>Mundo</p>;
   }
 }
```

Una restricción de **JSX** es que siempre debes tener un elemento raíz:
```js
const el = (
  <div>
    <p>Hola</p>
    <p>Mundo</p>
  </div>
);
```
Pero imaginate que por cuestiones de maquetacion necesitas que dos elementos sean adjacentes para que los puedas maquetar, quizas no necesitas una etiqueta padre.

En las nuevas versiones de react hay un concepto que se llama **fragmento** y lo que hace es crear un graper vacio para cumplir con esta regla de jsx que se debe empaquetar toda la sintaxis jsx en un solo contenedor y a la hora de ser renderizado en etiquetas html solo van a estar los nodos hijos:
```js
//jsx
<>
  <div className="container">
    hola mundo
  </div>
  <article></article>
</>
```
Esta sintaxis que parece una etiqueta sin nombre en codigo js seria:
```js
React.createElement(
  React.Fragment,
  null,
  React.createElement(
    {
      className: "container"
    },
    "hola mundo"
    ),
    React.createElement("article",null) 
);
```
Para agregar una variable y/o expresiones al codigo jsx:
```js
let nombre = "Jon";
<>
  <div className="container" id={nombre}>
    hola mundo
  </div>
  <article>{nombre}</article>
</>
```
Con solamente hacer uno de las llaves ya podemos hacer uso de las variables y/o expresiones.

Este es un patrón muy común en las aplicaciones de React.

### Mezclando JSX con JavaScript
Para mezclar código JavaScript en **JSX** utiliza corchetes (**{}**):

```js
const style = "active";
const title = "Hola Mundo";

<div className={style}>{title}</div>;
```
Una restricción de **JSX** es que no puedes utilizar **if**, **else**, **while** o **for**.

Para agregar condicionales utiliza el **operador ternario**:
```js
<div>
  {
    condition
      ? <h1>Hola Mundo</h1>
      : null
  }
</div>
```
Para mostrar elementos de un arreglo o un objeto utiliza **map**:
```js
const names = ["Jon", "Irma", "kEnAi"];

const jsx = (
  <ul>
    {names.map((name, index) => (
      <li key={index}>{name}</li>
    ))}
  </ul>
);
```

### Estilos CSS inline en JSX

Es posible definir y utilizar estilos inline en **JSX**:
```js
let styles = {
  borderColor: "#999",
};

const jsx = <div style={styles}>Hola mundo</div>;
```

### Eventos del DOM en JSX
En **JSX** se utilizan los eventos estándar del DOM como **onclick**, **onchange**, **onkeydown**, ... pero utilizando camelCase: **onClick**, **onChange**, **onKeyDown**, ...
```js
<button onClick={alert("Hola")}></button>
```
Fíjate que utilizamos corchetes (**{}**) para escribir nuestro código JavaScript.

También podríamos pasar una función que es invocada cuando se genere el evento:
```js
const saludar = () => alert("Hola!");

<button onClick={saludar}></button>;
```
Fíjate que no estamos invocando la función saludar, sólo la estamos pasando para que React la invoque cuando ocurra el evento.

## Componentes
Un componente es una interfaz UI que tiene codigo de contenido(html), codigo de presentacion(css), interactividad(js).

En React se introduce el concepto de **componentes** para crear la interfaz gráfica de nuestra aplicación.

Permiten separar el código y los elementos de la interfaz en pequeñas piezas independientes y reutilizables que estarán aisladas una de otras.

El objetivo es que cada componente sea independiente y encapsule su marcado, estilos y estado(las variable que pueda tener). De esa forma los componentes pueden ser reutilizables y la interfaz gráfica más fácil de mantener y evolucionar.

Se le pueden pasar datos a un componente a través de algo llamado **props** y devuelven a React elementos que describen lo que debe verse en pantalla.

En React los datos fluyen de forma unidireccional, de componentes padres a componentes hijos.

React te permite definir componentes como **clases** o como **funciones**.

### Tipos de Componentes

Como una clase que extiende de **Component** con un método **render**:

```js
import React, { Component } from "react";

class Title extends Component {
  render() {
    return <h1>Hola mundo</h1>;
  }
}
```
O como una función que retorna lo que se va a renderizar:
```js
const Title = () => {
  return <h1>Hola Mundo</h1>;
};
```
### Utilizando un componente
Para utilizar un componente debes importarlo y después incluirlo en tu JSX como se muestra en el siguiente ejemplo:
```js
import React from "react";
import Title from "./Title";

function App {
    return <Title />;
```
Desde la version 17 ya no es necesario importar la libreria de react almenos con **create-react-app**.
Pero por cuestiones de buenas practicas se recomienda importarlo siempre:
```js
import React from "react";
```

### Componentes de ejemplo
crearemos un componente en la carpeta `src` que se creo cuando usamos **create-react-app** y la llamaremos `components`.
Despues crearemos el archivo del componente con el nombre `Componente.js`(puede ser .js o .jsx)

- **Componente basado en clases**:
```js
import React, { Component} from "react";

// el nombre del componente sera el nombre del archivo
class Componente extends Component {
    //un componente de clase por defaul tiene que tener su metodo render
    // render es el que le va a permitir renderizar el codigo jsx
    render() {
        return <h2>Hola soy un Componente</h2>
    }
}

export default Componente;
```
- **Componente basado en funciones**:
```js
import React, { Component} from "react";

function Componente(){
    return <h2>Soy un componente</h2>
}

export default Componente;
```
```js
import React, { Component} from "react";

const Componente = () => <h2>Soy un componente</h2>;

export default Componente;
```

## Propiedades
Son valores que recibe un componente hijo de uno padre. Se agrupan en un objeto llamado **props**, el cual puede recibir diferentes tipos de datos, como:

**Strings**
**Numbers**
**Booleans**
**Arrays**
**Objects**
**Functions**
**React Elements**
**React Components**

Las **props** son **inmutables**, es decir, son valores de **sólo lectura**, no se pueden modificar.

El componente las recibe como atributos que se pasan a través de **JSX**.

Por ejemplo, podemos pasar un atributo **name** al componente **Welcome**:
```js
<Welcome name="Jon" />

<Welcome name="Irma" />
```
Si defines el componente en una clase, las **props** se reciben en el constructor de la clase:
```js
class Welcome extends Component {
  constructor(props) {
    super(props);
  }

  render() {
    return <h1>{this.props.name}</h1>;
  }
}
```
Si defines el componente como una función, las **props** se reciben como un parámetro de la función:
```js
const Welcome = (props) => {
  return <h1>{props.name}</h1>;
};
```
### Propiedades de ejemplo
```js
import React from "react";

export default function Propiedades (){
    return(
        <div>
            <h2>{props.porDefecto}</h2>
            <ul>
                <li>{props.cadena}</li>
                <li>{props.numero}</li>
                <li>{props.booleano}</li>
                <li>{props.arreglo.join(", ")}</li>
                <li>{props.objeto.nombre + "-" + props.objeto.correo}</li>
                <li>{props.arreglo.map(props.funcion).join(", ")}</li>
                <li>{props.elementoReact}</li>
                <li>{props.componenteReact}</li>

            </ul>
        </div>
    )
};

// tenemos una propiedades especial que se llama defaultProps
// este defaultProps va a ser un objeto
// si necistamos definir algunas propiedades por defecto las puedo especificar
Propiedades.defaultProps = {
    porDefecto: "Las Props"
};
```
En otro archivo con react lo vamos a usar como:
```js
import Propiedades from "./components/Propiedades"

function App(){
  return(
    <div>
    <Propiedades 
    cadena="Esto es una cadena de texto" 
    numero={19} 
    booleano={true} 
    arreglo={[1,2,3]} 
    objeto={{nombre:"jon", correo:"correo@gmail.com"}}
    funcion={(num) => num * num}
    elementoReact = {<i>Esto es un elemento React</i>}
    componenteReact={<Componente/>}
    />
    <div>
  )
}
```

### [prop-types](https://www.npmjs.com/package/prop-types)
Nosotros podemos definir que sientos valores o ciertas **props** se inicializen con un tipo de dato especial o por ejemplo que sean requeridos.

Para ellos hay que importar un modulo que se llama **prop-types** desde la terminal de comandos:
```
npm i -S prop-types
```

Estas **prop-types**  me permiten definirle a mi componente las diferentes caracteristicas que necesitamos que soporten las propiedades.
```js
import React from "react";
import PropTypes from "prop-types"

export default function Propiedades (){
    return(
        <div>
            <h2>{props.porDefecto}</h2>
            <ul>
                <li>{props.cadena}</li>
                <li>{props.numero}</li>
                <li>{props.booleano}</li>
                <li>{props.arreglo.join(", ")}</li>
                <li>{props.objeto.nombre + "-" + props.objeto.correo}</li>
                <li>{props.arreglo.map(props.funcion).join(", ")}</li>
                <li>{props.elementoReact}</li>
                <li>{props.componenteReact}</li>

            </ul>
        </div>
    )
};

Propiedades.defaultProps = {
    porDefecto: "Las Props"
};

//propTypes
Propiedades.propTypes = {
    numero: PropTypes.number.isRequired //con esto le estamos diciendo que esta propiedad solamente va a recibir numeros
    // isRequired es por si la propiedad es requerida forsozamente
}
```