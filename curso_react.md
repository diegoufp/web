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

## Estado

Todos los componentes pueden tener estado. El estado no es mas que las varibales que intervienen en la modificacion de dicho componente y como se encuentran en cierto momento dado, es decir, que valores tienen.

El **state** son los valores internos que manejan la lógica y los datos de un componente, permite que éste reaccione a cualquier cambio lo que hará que se vuelva a renderizar en la interfaz.

El estado tiene 3 características importantes:
1. Es inmutable.
2. No se puede modificar directamente.
3. Es asíncrono.

Para hacer cambios hay que hacer uso del método **setState()**.

El estado de un componente no es accesible desde otro componente excepto de aquel que lo posee y lo asigna.

La **propagación del estado** fluye de forma **unidireccional** y **descendiente** (hacia abajo), esto significa que un componente padre puede pasar valores de su estado a componentes hijos que lo recibirán como propiedades.

En el momento que los valores del estado del padre sufran cambios esto causará que tanto el padre como los hijos que recibieron esos valores como propiedades se rendericen nuevamente y reaccionen a dicho cambio.

Cada componente que se defina como una clase cuenta con un objeto para almacenar información llamado **state**.

Cada vez que cambia el **state** React vuelve a renderizar (pintar) el componente en la vista.

```js
class Welcome extends Component {
  constructor() {
    super();

    this.state = {
      title: "Hola Mundo",
    };
  }

  render() {
    return <h1>{this.state.title}</h1>;
  }
}
```

En este ejemplo estamos definiendo una componente **Welcome** que inicializa el estado con una llave **title**. En el método **render** estamos obteniendo el valor de esa llave con **this.state.title**.

Para cambiar el estado utiliza el método **setState**:
```js
this.setState({
  title: "Hello World",
});
```

### Ejemplo de cambio de estado
```js
import React, {Component} from "react";

export default class Estado extends Component {
    // EL estado lo podemos definir en el constructor
    constructor(props){
        // tenermos que mandar a llamar el objeto del constrcutor del cual hereda(COmponent) y esto se hace son super
        super(props);
        // aqui estariamos creado en objeto del estado
        this.state = {
            contador: 0
        };
        // el estado se actualiza con setState
        setInterval(()=>{
            this.setState({
                contador: this.state.contador + 1
                //this.state.contador += 1;
                //lo que esta comentado es lo que no podemos hacer 
                // ya que no podemos modificar directamente el estado 
            })
        },1000);
    }
    render(){
        //cada vez que es estado se modifica se vuelve a renderizar(pintar)
        return(
            <div>
                <h2>El State</h2>
                <p>{this.state.contador}</p>
            </div>
        )
    }
}
```
Existen tecnicas mas eficientes.

Cuando se use este codigo va a generar un warning ya que no podemos llamar a setState en un componente que todavia no a sido montado.
El warning ocurre por el ciclo de vida de los componentes.
El ciclo de vida principalmente tiene 3 fases:
- Montado : Cuando la aplicacion react carga en el navegador y ya tenermos el elemento incertado en el dom
- Actualizacion
- Desmontaje

Como estamos ejecutando el serInterval en el constructor, cuando se ejecuta el constructor todavia no se hace el renderizado.

El estado de un **component padre** se le puede pasar como propiedad a las propiedades de un componente hijo.
```js
import React, {Component} from "react";

//los componentes funcionales(creado con function) no pueden tener estado
//en las ultimas actualizaciones si se puede con hooks
function EstadoAHijo(props){
    return(
        <div>
            <h3>{props.contadorHijo}</h3>
        </div>
    );
}

export default class Estado extends Component {
    constructor(props){
        super(props);
        this.state = {
            contador: 0
        };
        setInterval(()=>{
            this.setState({
                contador: this.state.contador + 1
            })
        },1000);
    }
    render(){
        return(
            <div>
                <h2>El State</h2>
                <p>{this.state.contador}</p>
                <EstadoAHijo contadorHijo={this.state.contador}/>
            </div>
        )
    }
}
```

## Renderizado Condicional

En React, puedes crear distintos componentes que encapsulan el comportamiento que necesitas. Entonces, puedes renderizar solamente algunos de ellos, dependiendo del estado de tu aplicación.

El renderizado condicional en React funciona de la misma forma que lo hacen las condiciones en JavaScript. Puedes usar el condicional **if** o el **operador ternario** para crear elementos dinámicamente en base al valor del estado o las propiedades que recibe el componente.

Considera estos dos componentes:
```js
function SaludoUsuario(props) {
  return <h1>¡Bienvenid@ nuevamente!</h1>;
}
```
```js
function SaludoInvitado(props) {
  return <h1>Por favor, regístrate.</h1>;
}
```
Vamos a crear un componente **Saludar** que muestra cualquiera de estos componentes dependiendo si el usuario ha iniciado sesión o no:
```js
function Saludar(props) {
  const isLoggedIn = props.isLoggedIn;

  if (isLoggedIn) {
    return <SaludoUsuario />;
  }
  return <SaludoInvitado />;
}

ReactDOM.render(
  // Intentar cambiando isLoggedIn={true}:
  <Saludar isLoggedIn={false} />,
  document.getElementById("root")
);
```
Con el **operador ternario** el código quedaría de la siguiente manera:
```js
function Saludar(props) {
  const isLoggedIn = props.isLoggedIn;

  return isLoggedIn ? <SaludoUsuario /> : <SaludoInvitado />;
}

ReactDOM.render(
  // Intentar cambiando isLoggedIn={true}:
  <Saludar isLoggedIn={false} />,
  document.getElementById("root")
);
```

### Ejemplo de renderizado condicional
```js
import React,{Component} from "react";

function Login(){
    return(
        <div>
            <h3>Login</h3>
        </div>
    )
}

function Logout(){
    return(
        <div>
            <h3>Logout</h3>
        </div>
    )
}

export default class RenderizadoCondicional extends Component {
    constructor(props){
        super(props);
        this.state = {
            session: true
        }
    };
    render() {
        return(
            <div>
                <h2>Renderizado Condicional</h2>
                {this.state.session ? <Login/> : <Logout/>}
            </div>
        )
    }
};
```

## Renderizado de elementos
Puedes hacer colecciones de elementos e incluirlos en JSX usando llaves **{}**.

Recorriendo los elementos de un **array** y usando la función **map()** de Javascript.

Por ejemplo:
```js
const numeros = [1, 2, 3, 4, 5];
const listaElementos = numeros.map((numero) => <li>{numero}</li>);
```
Incluimos el **array listaElementos** dentro de un elemento `<ul>`, y lo renderizamos en el DOM:
```js
ReactDOM.render(<ul>{listaElementos}</ul>, document.getElementById("root"));
```
Refactorizamos el ejemplo anterior en un componente que acepte un **array** de numeros e imprima una lista de elementos.
```js
function ListaNumeros(props) {
  const numeros = props.numeros;
  const listaElementos = numeros.map((numero) => <li>{numero}</li>);
  return <ul>{listaElementos}</ul>;
}

const numeros = [1, 2, 3, 4, 5];
ReactDOM.render(
  <ListaNumeros numeros={numeros} />,
  document.getElementById("root")
);
```

Al ejecutar este código, serás advertido que una **key** debería ser proporcionada para elementos de lista.

Una “**key**” es un atributo especial de tipo **string** que debes incluir al crear listas de elementos.

Las **keys** ayudan a React a identificar que elementos han cambiado, son agregados, o son eliminados. Las **keys** deben ser dadas a los elementos dentro del array para darle una identidad estable.

La mejor forma de elegir una **key** es usando un string que identifique únicamente a un elemento de la lista entre sus hermanos. Habitualmente vas a usar los IDs de tus datos como **key**.

Cuando no tengas IDs estables para renderizar, puedes usar como **key** el índice de los elementos del **array** de datos como último recurso.

Las **keys** usadas dentro de **arrays** deberían ser únicas entre sus hermanos. Sin embargo, no necesitan ser únicas globalmente. Podemos usar las mismas **keys** cuando creamos dos o más **arrays** diferentes.

Entonces refactorizando nuestro código anterior quedaría así:
```js
function ListaNumeros(props) {
  const numeros = props.numeros;
  const listaElementos = numeros.map((numero, indice) => (
    <li key={indice}>{numero}</li>
  ));
  return <ul>{listaElementos}</ul>;
}

const numeros = [1, 2, 3, 4, 5];
ReactDOM.render(
  <ListaNumeros numeros={numeros} />,
  document.getElementById("root")
);
```

### Ejemplo de Renderizado de Elementos
```js
import React,{Component} from "react";

export default class Register extends Component {
    constructor(props){
        super(props);
        this.state = {
            seasons: ["Primavera", "Verano", "Oto;o","Invierno"]
        }
    }
    render(){
        return (
            <div>
                <h2>Renderizado de Elementos</h2>
                <h3>Estaciones del A;o</h3>
                <ol>
                    {this.state.seasons.map((el,index)=> <li key={index}>{el}</li>)}
                </ol>
            </div>
        )
    }
};


```
La key es como un id pero este no aparece en el html, es algo que internamente react neceita para detectar cada uno de los elementos que va renderizando 

## Eventos & Binding
ES6

Manejar eventos en React es muy similar a manejar eventos en el DOM. Sin embargo existen algunas diferencias de sintaxis:

- Los eventos de React se nombran usando camelCase, en vez de minúsculas.
- Con JSX pasas una función como el manejador del evento, en vez de un string.
Ejemplo, en HTML:

Ejemplo, en HTML:
```html
<button onclick="cambiarIdioma()">Cambiar idioma</button>
```
Ejemplo, en React:
```js
<button onClick={cambiarIdioma}>Cambiar idioma</button>
```

Otra diferencia es que en React no puedes retornar **false** para prevenir el comportamiento por defecto. Debes, explícitamente, llamar **preventDefault**.

Por ejemplo, en nuestro ejemplo del componente **Welcome** visto en el tema del **Estado** podemos cambiarlo para que cuando hagan click sobre el **h1** cambie el texto. Para eso vamos a definir un método **updateText** que vamos a invocar cuando hagan **click** sobre el **h1**:
```js
class Welcome extends Component {
  constructor() {
    super();

    this.state = {
      title: "Hola Mundo",
    };

    // tenemos que enlazar el método al contexto actual
    this.updateText = this.updateText.bind(this);
  }

  updateText() {
    this.setState({
      title: "Hello World",
    });
  }

  render() {
    return <h1 onClick={this.updateText}>{this.state.title}</h1>;
  }
}
```

### Ejemplo de Eventos
```js
import React,{Component} from "react";

export default class Eventos extends Component {
    constructor(props){
        super(props);
        this.state = {
            contador: 0
        };

        //un detalle muy importante en los componentes basados en estructuras de clase 
        //tengo que bindear(usar bind) el this de la clase
        //se puede hacer directamente en la definicion del metodo(en onClick)
        // pero la buena practica y lo que nos recomienda la gente de react es que lo hagamos justamente en el constructor
        //asi todo las intancias que despues en el metodo render invoquemos de esa funcion ya van a tener enlazado el this de la clase
        this.sumar = this.sumar.bind(this);
        this.restar = this.restar.bind(this);
    };

    sumar(e){
        this.setState({
            contador: this.state.contador + 1
        })
    };
    restar(e){
        this.setState({
            contador: this.state.contador - 1
        })
    }


    render(){
        return(
        <div>
            <h2>Eventos en Componentes de Clase</h2>
            <h3>{this.state.contador}</h3>
            <nav>
                <button onClick={this.sumar}>+</button>
                <button onClick={this.restar}>-</button>
            </nav>
        </div>
        );
    }
}
```

## Eventos & [Property Initializers](https://reactjs.org/blog/2015/01/27/react-v0.13.0-beta-1.html#es7-property-initializers)

- `Property Initializers`: ES7

```js
import React,{Component} from "react";

//eventos en componentes de clase ES6
export class EventosES6 extends Component {
    constructor(props){
        super(props);
        this.state = {
            contador: 0
        };

        this.sumar = this.sumar.bind(this);
        this.restar = this.restar.bind(this);
    };

    sumar(e){
        this.setState({
            contador: this.state.contador + 1
        })
    };
    restar(e){
        this.setState({
            contador: this.state.contador - 1
        })
    }


    render(){
        return(
        <div>
            <h2>Eventos en Componentes de Clase ES6</h2>
            <h3>{this.state.contador}</h3>
            <nav>
                <button onClick={this.sumar}>+</button>
                <button onClick={this.restar}>-</button>
            </nav>
        </div>
        );
    }
};

//eventos en componentes de clase ES7
export class EventosES7 extends Component {
    //YA NO PONDREMOS EL CONSTRUCTOR
    state = {
        contador: 0
    }

    //para evitar ponerle el bind en el evento(onCLick)
    //los eventos dentro de la clase los vamos a defrinir con funciones flecha 
    // la caracteristica d elas funciones flecha es que erendan el this del contexto en el que se encuentran
    // asi que con funciones flecha ya no tendriamos que usar el bind
    sumar = (e)=>{
        this.setState({
            contador: this.state.contador + 1
        })
    };
    restar = (e) =>{
        this.setState({
            contador: this.state.contador - 1
        })
    }


    render(){
        return(
        <div>
            <h2>Eventos en Componentes de Clase ES7</h2>
            <h3>{this.state.contador}</h3>
            <nav>
                <button onClick={this.sumar}>+</button>
                <button onClick={this.restar}>-</button>
            </nav>
        </div>
        );
    }
};
```

## Eventos Nativos, Sintéticos & Personalizados
- [SyntheticBaseEvent](https://es.reactjs.org/docs/events.html) : react envuelve el evento nativo del navegador, le da soporte a los diferentes navegadores donde react se soporta, pero adicionalmente tiene la caracteristica de que tienes un mejor control desde react del evento. No todos los eventos estan soportados, sin embargo, la mayoria si estan soportados.

- `nativeEvent` : Si tienes la necesidad de acceder al evento nativo(al evento de js), eso se puede hacer con `e.nativeEvent`.

```js

export class MasSobreEventos extends Component {

    //si queremos agrear otro paramentros (ademas del evento entonces tenemos que crear una funcion fecha en el onCLick)
    handleClick = (e, mensaje) => {
    //e.nativeEvent   //asi accedemos al evento nativo
    //e.nativeEvent.target   // asi accedemos al targen del evento nativo 
    //e  //en este caso este seria el evento sintetico de react
    // e.target  //en este caso seria el target del evento sintetico de react
    }

    render(){
        return(
            <div>
                <h2>Mas sobre eventos</h2>
                <button onClick={(e) => this.handleClick(e,"parametro extra agregado")}>Saludar</button>
            </div>
        )
    }
}
```

### Evento personalizado en react

Si en lugar de tener un boton(por ejemplo) ya tuvieramos un componente propio que ya fuera un boton y tratamos de asignarle un evento:
```js
function Boton(){
    return(
        <button>Boton hecho componente</button>
    )
}
```
```js

export class MasSobreEventos extends Component {
    handleClick = (e, mensaje) => {

    }

    render(){
        return(
            <div>
                <h2>Mas sobre eventos</h2>
                <button onClick={(e) => this.handleClick(e,"parametro extra agregado")}>Saludar</button>
                <Boton onClick={(e) => this.handleClick(e,"parametro extra agregado")}/>
            </div>
        )
    }
}
```
Si ejecutamos este codigo no saldran errores pero al momento de hacer click y tratar de activar el evento no ocurrira nada.
Esto ocurre por que el evento `onClick` es un atributo de las etiquetas **jsx** y el componente `Boton` no es una etiqueta **jsx**, es un componente de react personalizado que nosotros hemos creado.

Entonces si queremos que funcione el evento `onClick` en este componente persoanlizado tenemos que hacer uso de un **Evento personalizado**.

El **Evento Persoanlizado** en pocas palabras es crear una `prop` que se la pasamos al componente y esa prop se la asignamos al evento con el que estemos trabajando de la etiqueta jsx que internamente este dentro del componente.
```js
/*
function Boton(props){
    return(
        <button onClick={props.myOnClick}>Boton hecho componente</button>
    )
}*/
//si usamos la destructuracion podemos simprificar las props y el codigo
const Boton = ({myOnClick})=>{
        <button onClick={myOnClick}>Boton hecho componente</button>
}
```
```js
export class MasSobreEventos extends Component {
    handleClick = (e, mensaje) => {

    }

    render(){
        return(
            <div>
                <h2>Mas sobre eventos</h2>
                <button onClick={(e) => this.handleClick(e,"parametro extra agregado")}>Saludar</button>
                {/*<Boton onClick={(e) => this.handleClick(e,"parametro extra agregado")}/>*/}
                <Boton myOnClick={(e) => this.handleClick(e,"parametro extra agregado")}/>
            </div>
        )
    }
}
``` 

## Comunicación entre Componentes
La comunicacion entre los componentes en react se da en un solo flujo, de elementos padres a elementos hijos.

Tenemos 3 casos de comunicación entre los componentes de React:

- Comunicación entre un componente padre a uno hijo.
- Comunicación entre un componente hijo y su padre.
- Comunicación entre componentes no relacionados.

### Comunicación entre un componente padre a uno hijo
Éste es el caso más natural en el mundo de React y se hace a través del paso de **props** de un componente padre a uno hijo.

```js
import React, { Component } from "react";

class Padre extends Component {
  render() {
    return (
      <div>
        <Hijo mensaje="Mensaje para el hijo 1" />
        <Hijo mensaje="Mensaje para el hijo 2" />
      </div>
    );
  }
}

function Hijo(props) {
  return <h2>{props.mensaje}</h2>;
}

export default Padre;
```
### Comunicación entre un componente hijo y su padre

Cuando tenemos la necesidad de que un componente hijo mande datos a su padre los podemos hacer a traves de los **eventos**, simplemente pasamos una función como **prop** del componente padre al componente hijo, y éste ejecutará la función .

En este ejemplo, cambiaremos el estado del componente padre pasando una función al componente hijo e invocando esa función dentro del componente hijo.
```js
import React, {Component} from "react";

export default class Padre extends Component {
    state={
        contador:0
    }

    //este metodo lo va a ejecutar el hijo
    incrementarContador = (e) =>{
        this.setState({
            contador: this.state.contador + 1
        })
    }
    render(){
        return(
            <>
            <h2>Comunicacion entre Componentes</h2>
            <p>Contador <b>{this.contador}</b></p>
            {/*Cuando un componente padre necesite ejecutar un metodo del padre simplemente se le pasa como propiedad*/}
            <Hijo incrementarContador={this.incrementarContador} mensaje="mensaje para hijo 1"/>
            <Hijo incrementarContador={this.incrementarContador} mensaje="mensaje para hijo 2"/>
            </>
        );
    };
};


function Hijo(props){
    return (
        <>
            <h3>{props.mensaje}</h3>
            <button onClick={props.incrementarContador}>+</button>
        </>
    )
}
```
En este caso cuando se le da click el boton hijo se renderizan los 3 componentes(el padre y los dos hijos).

### Comunicación entre componentes no relacionados

Si los componentes no tienen una relación padre-hijo o están relacionados, pero están demasiado lejos, como por ejemplo, un bisnieto o tataranieto, tenemos que crear un mecanismo de observación y/o suscripción para la comunicación entre dichos componentes.

Al menos existen 3 patrones para hacer esto.

1. Patrón **Emisor de eventos / Destino / Despachador** : los oyentes deben hacer referencia a la fuente para suscribirse.
2. Patrón **Publicación / Suscripción**: no necesita una referencia específica a la fuente que desencadena el evento, hay un objeto global accesible en todas partes que maneja todos los eventos.
3. Patrón **Señales**: similar al Emisor de Eventos, pero aquí no usa cadenas aleatorias. Cada objeto que podría emitir eventos debe tener una propiedad específica con ese nombre. De esta manera, se sabe exactamente qué eventos puede emitir un objeto.
4. [Portales](https://es.reactjs.org/docs/portals.html): proporcionan una opción de primera clase para renderizar hijos en un nodo DOM que existe por fuera de la jerarquía del DOM del componente padre.
Puedes encontrar más información al respecto en este enlace.

Otra manera de compartir datos entre componentes sin que tengan una relación padre-hijo es compartiendo un **estado global** accesible para todos los componentes de nuestra aplicación, para ello podríamos usar 2 opciones:

1. **Redux**: librería externa a React para el manejo del estado.
2. **Context**: un API interna de React que provee una forma de pasar datos a través del árbol de componentes sin tener que pasar props manualmente en cada nivel. Esta API la retomaremos cuando veamos el tema de Hooks.

## Ciclo de Vida

Son métodos que se ejecutan automáticamente en un **Componente de Clase**, ocurren en 3 fases:

1. Montaje.
2. Actualización.
3. Desmontaje

### Montaje

Estos métodos se ejecutan cuando se crea un componente y se inserta en el arbol del DOM.

- **constructor()**: Se ejecuta al crear la instancia del componente, en el constructor puedes inicializar el estado y enlazar manejadores de eventos.
- **render()**: Es el único método requerido, cuando se ejecuta, examina el estado y las propiedades y dibuja el componente en el árbol del DOM.
- **componentDidMount()**: Se invoca inmediatamente después de que un componente se ha insertado al árbol del DOM. Es útil para ejecutar suscripciones o peticiones asíncronas a API's, bases de datos, servicios, etc.

### Actualización

Estos métodos son ejecutados por cambios en el estado o las propiedades de los componentes.

- **render()**: redibuja el componente cuando detecta cambios en el estado o las propiedades del componente.
- **componentDidUpdate()**: Se ejecuta inmediatamente después de que la actualización del estado o las propiedades sucede, al igual que componenDidUpdate es un método ideal para hacer peticiones externas.

### Desmontaje

Estos métodos son ejecutados una vez que el componente ha sido eliminado del árbol del DOM.

- **componentWillUnmount()**: Se ejecuta antes de destruir el componente del árbol del DOM, es un método útil para hacer tareas de limpieza.

### ejemplo de ciclo de vida
```js
import React, { Component } from 'react';


class Reloj extends Component {
    constructor(props){
        super(props);
    }

    //componentWillUnmount este metodo se ejecuta cuando el componente ya no exista
    //puede ser usado para desuscribirte a servicios
    componentWillUnmount(){
        console.log(3,"EL componente ha sido eliminado del DOM");
    };

    render(){
        return <h3>{this.props.hora}</h3>
    }
}

export default class CicloVida extends Component {
    constructor(props){
        super(props);
        console.log(0, "El componente se inicializa, aun NO esta en el DOM");

        this.state = {
            hora: new Date().toLocaleString(),
            //visible servira como condicional para la activacion de componentWillUnmount
            visible: false
        };

        this.temportizador = null;
    };

    //react nos pide que cualquier suscripcion a una base de datos o solicitar datos de una API lo hagamos en el componentDidMount
    //por que si nosotros lo hacemos en el cosntructor cuando hagamos la peticion y la API nos responda 
    // y ya queramos interactuar con la data hacia elementos que se van a pintar en el dom 
    // no es correcto hacerlo en el constructor por que que compononente aun no esta en el dom
    // cuando componentDidMount se ejecuta significa que ya esos elementos estan cargados en el dom y entonces ya se pueden hacer peticiones a APIs y cualquier cosa que requiera que previamente mis elementos esten insertados en el dom
    componentDidMount(){
        console.log(1,"El componente ya se encuentra en el DOM");
    };

    // componentDidUpdate adicionalmente me permite pasar las propiedades previas y el estado previo por si neceitamos trabajar con esos valores antes de actualizar el nuevo estado
    componentDidUpdate(prevProps,prevState){
        console.log(2,"El estado o las props del componente han cambiado");
        console.log(prevProps);
        console.log(prevState);
    };

    

    tictac = () => {
        this.temportizador = setInterval(()=>{
            this.setState({
                hora: new Date().toLocaleString()})
        },1000)
    };

    iniciar = () =>{
        this.tictac();
        this.setState({
              visible: true
        })
    };

    detener = () =>{
        clearInterval(this.temportizador);
        this.setState({
            visible: false
      })
    };
    
    render(){
        console.log(4, "El componente se dibuja (o redibuja por algun cambio) en el DOM") 
        return(
            <>
                <h2>Ciclo de Vida de los Componentes</h2>
                {this.state.visible && <Reloj hora={this.state.hora}/>}
                <button onClick={this.iniciar}>Iniciar</button>
                <button onClick={this.detener}>Detener</button>
            </>
        )
    }
}
```

## Peticiones Asíncronas (AJAX y API's)
```js
import React, { Component } from 'react';

function Pokemon (props){
    return(
        <figure>
            <img src={props.avatar} alt={props.name}/>
            <figcaption>{props.name}</figcaption>
        </figure>
    )
}

export default class AjacApis extends Component {
    state = {
        pokemons:[]
    };

    componentDidMount(){
        let url = "https://pokeapi.co/api/v2/pokemon/"
        fetch(url)
        .then(res => res.json())
        .then(json => {
            json.resuls.forEach(el =>{
                fetch(el.url)
                .then(res => res.json())
                .then(json =>{
                    let pokemon = {
                        id: json.id,
                        name: json.name,
                        avatar: json.sprite.front_default
                    };

                    let pokemons = [...this.state.pokemons, pokemon];

                    this.setState({pokemons});
                })
            })
        })
    }

    render(){
        return(
            <>
            <h2>Peticiones Asincrones en Componentes de clase</h2>
            {this.state.pokemons.map(el => <Pokemon key={el.id} name={el.name} avatar={el.avatar} />)}
            </>
        )
    }
};

```

## Hooks