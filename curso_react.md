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

Los Hooks son una nueva incorporación a partir de **React 16.8.0**, que nos permiten **"enganchar"** el estado y el ciclo de vida en componentes basados en funciones.

### ¿Por qué se crearon los Hooks?

**Las clases confunden a las personas y a las máquinas.**

Entender la estructura y reglas que implican crear una clase puede ser una curva de aprendizaje lenta y requerir de ciertos conceptos, como el manejo de this en JavaScript, por el contrario las funciones son muy fáciles de entender y manipular incluso para personas que van comenzando.

A las máquinas tampoco les gusta las clases ya que no minifican tan bien como las funciones, esto significa que nuestro código ocupará más texto y por ende más espacio de almacenamiento.

### Preguntas frecuentes

- ¿Los hooks hacen que mi aplicación sea más rápida? **NO**.
- ¿Los hooks hacen algo que un Componente de Clase no pueda hacer? **NO**.
- ¿Los Componentes de Clase van a desaparecer? **NO**.
- ¿Mi conocimiento del estado, las propiedades y los eventos serán obsoleto ahora con hooks? **NO**.
- ¿Debo reescribir todas mis aplicaciones React, ahora con hooks? **Probablemente NO**.
- ¿Debo implementar hooks en mi próximo proyecto? **Probablemente SÍ**.

### Tipos de Hooks

- Básicos (en el 100% de tus proyectos):
    - useState.
    - useEffect.
- Avanzados (tal vez no en todos tus proyectos):
    - useContext.
    - useRef.
    - useReducer.
    - useCallback.
    - useMemo.

Puedes ver toda la lista de hooks disponibles en la [documentación](https://reactjs.org/docs/hooks-reference.html) de React.

En este artículo explicaremos los hooks:

- useState.
- useEffect.

## Hook useState

Permite manipular el estado de un componente funcional, se comporta como el objeto state y a la función this.setState de los componentes de clase.

Para usarlo, debemos importarlo desde la librería de React.
```js
import React, { useState } from "react";
```

Ahora, en nuestro componente funcional, vamos a inicializar el hook, para ello asignaremos mediante la **destructuración de arreglos** 2 elementos:

El valor del estado y,
Un método para actualizarlo
Adicionalmente le pasaremos como parámetro el valor inicial del estado al método useState.
```js
import React, { useState } from "react";

export default function Componente() {
  const [valor, setValor] = useState(0);

  return <span>El valor del componente es {valor}</span>;
}
```

Para actualizar el estado tenemos que utilizar el método resultante de la destructuración de useState y pasarle el nuevo valor.

```js
import React, { useState } from "react";

export default function Componente() {
  const [valor, setValor] = useState(0);
  return (
    <div>
      <span>El valor del componente es {valor}</span>
      <button onClick={() => setValor(valor + 1)}>Aumentar valor</button>
    </div>
  );
}
```

Un detalle del estado en los Hooks, es que no debe ser tratado como un objeto como en los componentes de clases, si necesitas más de un valor cada uno debe ser almacenado en una variable diferente y usar la destructurción de useState.

```js
import React, { useState } from "react";

export default function Componente() {
  const [valor, setValor] = useState(0);
  const [valor2, setValor2] = useState("Hola Mundo");
  const [valor3, setValor3] = useState(true);

  return (
    <div>
      <span>El valor del componente es {valor}</span>
      <button onClick={() => setValor(valor + 1)}>Aumentar valor</button>
    </div>
  );
}
```

### Ejemplo de Hook useState
```js
import React, { useState } from 'react';

export default function ContadorHooks(){
    // useState puede recibir cualquier tipo de dato:
    // string,boolean,arreglo,objeto
    const {contador, setContador} = useState(0); 

    const sumar = () => setContador(contador + 1);
    const restar = () => setContador(contador - 1);

    return (
        <>
        <h2>Hooks -useState</h2>
        <nav>
            <button onClick={sumar}>+</button>
            <button onClick={restar}>-</button>
        </nav>
        <p>Contador de {props.titulo}</p>
        <h3>{contador}</h3>
        </>
    )
};

// Para agregar una prop por defecto:
ContadorHooks.defaultProps = {
    titulo:"Clicks"
}
```

## Hook useEffect

Permite hacer uso del ciclo de vida en un componente funcional. Usar useEffect equivale a la combinación de los métodos:

- componentDidMount() (montaje).
- componentDidUpdate() (actualización).
- componentWillUnmount() (desmontaje).

useEffect recibe como parámetro una función que se ejecutará cada vez que nuestro componente se renderice, ya sea por cambios del estado o las propiedades.

Para usarlo, debemos importarlo desde la librería de React.
```js
import React, { useEffect } from "react";
```

Para añadir un efecto que se ejecutará cada vez que nuestro componente se renderice, se debe pasar como parámetro una función al hook useEffect misma que se ejecutará al renderizarse el componente.

```js
import React, { useEffect } from "react";

export default function Efecto() {
  useEffect(function () {
    console.log("Me he renderizado!!!");
  });

  return <span>Este es un ejemplo del hook useEffect.</span>;
}
```
Con useEffect también podemos suscribirnos y desuscribirnos a eventos, temporizadores, servicios, API's, etc.

Para ello hay que escribir el código de la suscripción en el cuerpo de la función de useEffect y para evitar problemas de rendimiento o aumento indiscriminado de la memoria y recursos de nuestra aplicación retornar en una función el código que desuscriba o cancele lo que se ejecuto en el cuerpo de la función.

```js
import React, { useEffect, useState } from "react";

export default function ScrollYNavegador() {
  const [scrollY, setScrollY] = useState(0);

  useEffect(() => {
    //Creamos una función para actualizar el estado
    const actualizarScrollY = () => {
      let scrollY = window.pageYOffset;
      console.log(`scrollY: ${scrollY}`);
      setScrollY(scrollY);
    };
    //Actualizamos el scroll al montar el componente
    actualizarScrollY();
    //Nos suscribimos al evento scroll de window
    window.addEventListener("scroll", actualizarScrollY);

    //Devolvemos una función para desuscribir el evento
    return () => {
      window.removeEventListener("scroll", actualizarScrollY);
    };
  });

  return (
    <div>
      <span>ScrollY del Navegador: {scrollY}px</span>
    </div>
  );
}
```

Por defecto los efectos se ejecutan cada vez que se realiza un renderizado, si queremos evitar actualizaciones innecesarias o indiscriminadas podemos pasarle un segundo parámetro al hook.

El parámetro debe ser un array con todos los valores de los que dependerá el efecto, de forma que sólo se ejecutará cuando ese valor cambie.

```js
import React, { useEffect, useState } from "react";

export default function ScrollYNavegador() {
  const [scrollY, setScrollY] = useState(0);

  useEffect(() => {
    //Creamos una función para actualizar el estado
    const actualizarScrollY = () => {
      let scrollY = window.pageYOffset;
      console.log(`scrollY: ${scrollY}`);
      setScrollY(scrollY);
    };
    //Actualizamos el scroll al montar el componente
    actualizarScrollY();
    //Nos suscribimos al evento scroll de window
    window.addEventListener("scroll", actualizarScrollY);

    //Devolvemos una función para desuscribir el evento
    return () => {
      window.removeEventListener("scroll", actualizarScrollY);
    };
  }, [scrollY]);

  return (
    <div>
      <span>ScrollY del Navegador: {scrollY}px</span>
    </div>
  );
}
```

Si le pasamos un array vacío, eso hará que el efecto no dependa de ningún valor, por lo que sólo se ejecutará al montarse y desmontarse el componente.
```js
import React, { useEffect, useState } from "react";

export default function ScrollYNavegador() {
  const [scrollY, setScrollY] = useState(0);

  useEffect(() => {
    //Creamos una función para actualizar el estado
    const actualizarScrollY = () => {
      let scrollY = window.pageYOffset;
      console.log(`scrollY: ${scrollY}`);
      setScrollY(scrollY);
    };
    //Actualizamos el scroll al montar el componente
    actualizarScrollY();
    //Nos suscribimos al evento scroll de window
    window.addEventListener("scroll", actualizarScrollY);

    //Devolvemos una función para desuscribir el evento
    return () => {
      window.removeEventListener("scroll", actualizarScrollY);
    };
  }, []);

  return (
    <div>
      <span>ScrollY del Navegador: {scrollY}px</span>
    </div>
  );
}
```

### Ejemplos de  Hook useEffect

```js
import React, {useEffect,useState} from 'react';

export default function ScrollHook(){
    const {scrollY, setScrollY} = useState(0);
    // const {name,setName} = useState("Jon");

    //puedes tener tantos useEffects como necesites 
    useEffect(()=>{
        // Cada vez que se necesite renderizar este componente
        //useEffect va a ejecutar todo lo que este en esta funcion  
        console.log("Fase de Actualizacion")
        const detectarScroll = () => setScrollY(window.pageYOffset);
        
        window.addEventListener('scroll', detectarScroll);

        //cuando este componente ya no exista en el ui   
        return ()=> {
            window.removeEventListener('scroll', detectarScroll);
            console.log("Fase de Desmontaje");
        }
    }, [scrollY]);

    useEffect(() => {
        console.log("Fase de Montaje");
        // el segundo parametro que le podmeos pasar a useEffect son las dependencias que se van a estar revisando
        // estas dependencyList es un arreglo
        // cuando tu le pasas alguna variable de estado que quieras estar controlando eso significa que este useEffect solamente se va a ejecutar cuando la variable cambie
        // RECOMENDACION:
        //si tu necesitas que que una peticion como es el caso de solicitar servicios o apis externas solamente se ejecute una vez entonces...
        // lo que te recomienda react es dejar el arreglo vacio
    }, []);
     

    useEffect(() => {
        console.log("Fase de Actualizacion");
    });

    useEffect(() => {
        console.log("Fase de Desmontaje");
        // cuando a un useEffect le agregas la sintaxis de que retorne una funcion 
        return ()=>{
            //aqui es una buena oportunidad para desuscribirte de servicios
            // desconectarte de apis
            //limpiar intervalos de tiempos
            //limpiar menejadores de eventos de componentes que dejaron de existir
        }
    });

    return(
        <>
            <h2>Hooks - useEffect y el Ciclo de vida</h2>
            <p>Scroll Y del navegador {scrollY}</p>
        </>
    );
}

```

**Ejemplo 2**

```js
import React, { useEffect, useState } from 'react';

function Reloj({hora}){
    return <h3>{hora}</h3>
}

export default function RelojHooks(){
    const {hora, setHora} = useState(new Date().toLocaleTimeString());
    const {visible, setVisible} = useState(false);
  
    useEffect(()=>{
        let temporizador;

        if(visible){
            temporizador = setInterval(()=>{
                setHora(new Date().toLocaleTimeString());
            },1000);
        }else{
            clearInterval(temporizador);

        }
        return () =>{
        console.log("Fase de Desmontaje");
        clearInterval(temporizador);
        }; 
        //esta function solamente esta ejecutandose cuando hay un cambio en la variable visible
    },[visible])

    return(
        <>
            <h2>Reloj con Hooks</h2>
            {visible && <Reloj hora={hora}/>}
            <button onClick={()=> setVisible(true)}>Iniciar</button>
            <button onClick={()=> setVisible(false)}>Detener</button>
        </>
    )
};
```

## Peticiones Asíncronas con Hooks (AJAX y API's)

```js
import React, { useState, useEffect } from 'react';


function Pokemon ({avatar,name}){
    return(
        <figure>
            <img src={avatar} alt={name}/>
            <figcaption>{name}</figcaption>
        </figure>
    )
}

export default function AjaxHooks(){
    const {pokemons,setPokemons} = useState([])

    /*useEffect(()=>{
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

                    //para no tener una variable intermediaria podemos lanzar en formato de funcion de felcha la actualizacion del estado(setState = setPokemons)
                    setPokemons((pokemons)=>[...pokemons,pokemon])
                })
            })
        })
    },[]);*/

    //funciones asincronas con fetch
    // es una mala practica volver asincrono a useEfect(se deja comentado el async para mostrar lo que no se debe hacer).
    
    useEffect(/*async */()=>{
        const getPokemons = async (url) =>{
            // si necesitas hacer peticiones asincronas dentro de un useEffect es mejor crear una function expresada dentro de la funcion flecha del useEffect
            let res = await fetch(url);
            let json = await res.json();

            json.resuls.forEach(async el =>{
                let res = await fetch(el.url);
                let json = await res.json();

                let pokemon = {
                    id:json.id,
                    name: json.name,
                    avatar: json.sprite.front_default
                };
                setPokemons((pokemons)=>[...pokemons,pokemon]);
                });
            
        };
        getPokemons("https://pokeapi.co/api/v2/pokemon/");

        
    },[]);

    return(
        <>
            <h2>Peticiones Asincrones en Hooks</h2>
            {pokemons.length === 0 ? (<h3>Cargando...</h3>): (
                pokemons.map(el => <Pokemon key={el.id} name={el.name} avatar={el.avatar} />)
            )}
        </>
    )
}
```

## [Custom Hooks](https://es.reactjs.org/docs/hooks-custom.html)

Para que react sepa que es un hook personalizado el hook tiene que empezar con la palabra **use**.

En este caso el nombre del archivo de la funcion sera `use.Fetch.js`:
```js
import { useState, useEffect } from 'react';

// no importamos react por que lo que vamos a hacer no va a ser un componente funcional
//sino que va a ser solamente una funcion
export const useFetch =(url)=>{
    const {data,setData} = useState(null);
    const {isPending, setIsPending} = useState(true);
    const {error,setError} = useState(null);//esta va a ser la manipulacion del error

    useEffect(() => {
        const getData = async (url)=> {
            try {
                let res = await fetch(url);
                if(!res.ok){
                    throw {
                        err : true, 
                        status : res.status, statusText: res.statusText || "Ocurrio un error"
                    };
                };
                let data = await res.json();
                setIsPending(false);
                setData(data);
                setError({err:false})
            } catch (err) {
                setIsPending(true);
                //no se esta actualizando en setData por si llega a ocurrir un error con las peticiones aun asi conserva los valores anteriores
                setError({err:true})
            }
        };

        getData(url);
    },[url])

    //un hooks personalizado tiene que retornar ciertos valores
    return {data,isPending,error}
}

```

Con este hooks personalizado ahora podemos hacer peticiones a apis de manera mas rapida
```js
import React from 'react';
import { useFetch } from '../hooks/useFetch';

export default function HooksPersonalizados (){
    let url = "https://pokeapi.co/api/v2/pokemon/";

    let {data,isPending, error} = useFetch(url);

    return(
        <>
            <h2>Hooks HooksPersonalizados</h2>
            <h3>{JSON.stringify(isPending)}</h3>
            <h3><mark>{JSON.stringify(error)}</mark></h3>
            <h3>
                {/*whiteSpace:"pre-wrap" permite que rompa cuando haya un espacio en blanco */}
                <pre style={{whiteSpace:"pre-wrap" }}
                <code>{JSON.stringify(data)}</code>
            </h3>
        </>
    )
}
```

## [Referencias](https://es.reactjs.org/docs/refs-and-the-dom.html)

Las referencias es la manera en que nos permite react poder controlar un elemento que ya ha sido cargado en el dom.

**Cuando usar referencias**
Existen unos cuantos buenos casos de uso para referencias:

- Controlar enfoques, selección de texto, o reproducción de medios.
- Activar animaciones imperativas.
- Integración con bibliotecas DOM de terceros.
Evita usar referencias en cualquier cosa que pueda ser hecha declarativamente.

Por ejemplo, en lugar de exponer los métodos open() y close() en un componente Dialog, pasa una propiedad isOpen a este en su lugar.

Esto es lo que no tienes que hacer:
```js
import React from 'react';

export default function Referencias(){
    const handleToggleMenu = (e) =>{
        const $menu = document.getElementById("menu");
        if(e.target.textContent === "Menu"){
            e.target.textContent = "Cerrar";
            $menu.style.display="block";
        }else{
            e.target.textContent = "Menu";
            $menu.style.display="none";
        };
    };

    return(
        <>
            <h2>Referencias</h2>
            <button id="menu-btn" onClick={handleToggleMenu}>Menu</button>
            <nav id="menu" style={{display:none}}>
                <a href="#">Seccion1</a>
                <br/>
                <a href="#">Seccion2</a>
                <br/>
                <a href="#">Seccion3</a>
                <br/>
                <a href="#">Seccion4</a>
                <br/>
                <a href="#">Seccion5</a>
            </nav>
        </>
    )
};
```

La manera correcta de hacerlo es:
```js
import React,{createRef, useRef} from 'react';
// no se puede usar createRef en un componente funcional
//si tienes un componente de clase usa createRef
//si tienes un hook(componente funcional) usa useRef 

export default function Referencias(){
    //cuando trabajamos con referencias a las variables las inicializamos con ref
    let refMenu = useRef();
    let refMenuBtn = useRef();

    const handleToggleMenu = (e) =>{
        /*
        const $menu = document.getElementById("menu");
        if(e.target.textContent === "Menu"){
            e.target.textContent = "Cerrar";
            $menu.style.display="block";
        }else{
            e.target.textContent = "Menu";
            $menu.style.display="none";
        };*/
        if(refMenuBtn.current.textContent === "Menu"){
            refMenuBtn.current.textContent = "Cerrar";
            refMenu.current.style.display="block";
        }else{
            refMenuBtn.current.textContent = "Menu";
            refMenu.current.style.display="none";
        };
        //cuando tengamos que manupular sobretodo la visivilidad de elementos que ya estan cargados en el dom y que no tenemos que redibujar.
    };

    return(
        <>
            <h2>Referencias</h2>
            <button id="menu-btn" ref={refMenuBtn} onClick={handleToggleMenu}>Menu</button>
            <nav id="menu" ref={refMenu} style={{display:none}}>
                <a href="#">Seccion1</a>
                <br/>
                <a href="#">Seccion2</a>
                <br/>
                <a href="#">Seccion3</a>
                <br/>
                <a href="#">Seccion4</a>
                <br/>
                <a href="#">Seccion5</a>
            </nav>
        </>
    )
};
```

## Formularios
Existen los formularios **no controlados** que serian hacerlos de la manera del tema anterior(referencias), sin embargo no es la manera mas recomendada.

La otra manera de hacer un formulario es hacer que los elementos del formulario esten gestionados por el estado del componente, a esto se le llama **formularios controlados**.

```js
import React, { useState } from 'react';

export default function Formularios(){
    //lo que nos recomienda react para trabajar el manejo del estado es crear una variable de estado y asignarsela al input
    const {nombre,setNombre}= useState("");
    


    return(
        <>
            <h2>Formularios</h2>
            <form>
                <label htmlFor="nombre">Nombre</label>
                {/*Es buena practica que los input tengan el atributo name asi podemos acceder a ellos mediante el punto */}
                {/* si utilizamos la etiqueta value tenemos que asignar el evento onChange para el cambio de estado */}
                <input type="text" id="nombre" name="nombre" value={nombre} onChange={(e) => setNombre(e.target.value)}/>
            </form>
        </>
    )
}
```
```js
import React, { useState } from 'react';

export default function Formularios(){
    const {nombre,setNombre}= useState("");
    const {sabor, setSabor} = useState("");
    const {lenguaje,setLenguaje} = useState("");
    const {terminos,setTerminos} = useState(false);

    const handleSubmit = e=>{
        e.preventDefault();

    }

    return(
        <>
            <h2>Formularios</h2>
            <form onSubmit={handleSubmit}>
                <label htmlFor="nombre">Nombre</label>
                <input type="text" id="nombre" name="nombre" value={nombre} onChange={(e) => setNombre(e.target.value)}/>
            
            <p>Elige tu Sabor JS Favorito:</p>
            <input type="radio" id="vanilla" name="sabor" value="vanilla" onChange={e => setSabor(e.target.value)} defaultChecked/>
            {/*defaultChecked: sirve para que en el primer renderizado uno de los imputs este chekeado, en html es checked pero es react es defaultChecked */}
            <label htmlFor="vanilla">Vanilla</label>
            <input type="radio" id="react" name="sabor" value="react" onChange={e => setSabor(e.target.value)}/>
            <label htmlFor="react">React</label>

            <p>Elige tu lenguaje de programacion favorito</p>
            <select name="lenguaje" onChange={e => setLenguaje(e.target.value)} defaultValue="">
                {/*si quieres un valor por defecto para el select lo podemos hacer con la propiedad defaultValue */}
                <option value="">---</option>
                <option value="js">JavaScript</option>
                <option value="py">Python</option>
                <option value="go">GO</option>
            </select>
            <br/>

            <label htmlFor="teminos">Acepto terminos y condiciones</label>
            <input type="checkbox" id="terminos" name="terminos" onChange={e => setTerminos(e.target.checked)} />

            <br/>
            <input type="submit"/>

            </form>
        </>
    )
}
```

En lugar de tener una variable de estado por cada input se puede hacer con una sola variable de estado.
```js
export default function Formularios(){
    const {form,setForm}= useState({});

    const handleChange = e =>{
        //este handleChange va a ser la funcion que se le va a asignar al evento onChange de todos los elementos del formulario que decida vincular a alguna de las propiedades de la variable form
        //es muy importante que los elementos del fomulario tenga el atributo name 
        setForm({
            ...form,
            [e.target.name]: e.target.value
            // y asi de simple podemos tener un formulario con 1000 elementos de formulario con el mismo change y estar actualizando el estado en una sola variable 
        });
    };

    const handleChecked = (e) =>{
        setForm({
            ...form,
            [e.target.name]: e.target.checked
            //esto serviria para almanar los valores que sean booleanos
        })
    }

    const handleSubmit = e=>{
        e.preventDefault();

    }

    return(
        <>
            <h2>Formularios</h2>
            <form onSubmit={handleSubmit}>
                <label htmlFor="nombre">Nombre</label>
                <input type="text" id="nombre" name="nombre" value={form.nombre} onChange={handleChange}/>
            
            <p>Elige tu Sabor JS Favorito:</p>
            <input type="radio" id="vanilla" name="sabor" value="vanilla" onChange={handleChange} defaultChecked/>
            <label htmlFor="vanilla">Vanilla</label>
            <input type="radio" id="react" name="sabor" value="react" onChange={handleChange}/>
            <label htmlFor="react">React</label>

            <p>Elige tu lenguaje de programacion favorito</p>
            <select name="lenguaje" onChange={handleChange} defaultValue="">
                <option value="">---</option>
                <option value="js">JavaScript</option>
                <option value="py">Python</option>
                <option value="go">GO</option>
            </select>
            <br/>

            <label htmlFor="teminos">Acepto terminos y condiciones</label>
            <input type="checkbox" id="terminos" name="terminos" onChange={handleChecked} />

            <br/>
            <input type="submit"/>

            </form>
        </>
    )
};
```

## Estilos CSS
Para agregar estilos css la primera opcion siempre es crear un archivo .css e importarlo en js como si fuera un modulo.
```css
/*css*/
.estilos h3{
    padding: 2rem;
    text-align: center;
}

.bg-react {
    background-color: #61dafb;
}
```
```js
/* js */
import React from 'react';
import "../css/Estilos.css"

export default function Estilos(){
    return(
        <section className="estilos">
            <h2>EStilos CSS en React</h2>
            <h3 className="bg-react ">EStilos en hoja CSS externa</h3>
        </section>
    );
}
``` 

Otra forma es mandar a llamar los estilos en linea
```js
import React from 'react';
import "../css/Estilos.css"

export default function Estilos(){
    let myStyles={
        borderRadius: ".5rem",
        margin: "2rem auto",
        maxWidth: "50%"
    }


    return(
        <section className="estilos">
            <h2>EStilos CSS en React</h2>
            <h3 className="bg-react ">EStilos en hoja CSS externa</h3>
            <h3 className="bg-react" style={{borderRadius:".25rem", margin: "1rem"}}>Estilos en linea (atributo style)</h3>
            <h3 className="bg-react" style={myStyles}>Estilos en linea</h3>
        </section>
    );
};
```

**Normalize**
Podemos agregar la hoja de estilos normalize con `@import-normalize` en el archivo de css(en el archivo principal de css):
```css
@import-normalize;

.estilos h3{
    padding: 2rem;
    text-align: center;
}

.bg-react {
    background-color: #61dafb;
}
```


**Estilos como modulos**
Si queremos tratar las hojas de estilos css como si fueran modulos entonces tiene que tener la siguiente sintaxis de nombre:

```
nombre_que_quieras.module.css
```
```css
/*csc*/
.error{
    background-color: #dc3545;
}

.success{
    background-color: #198754;
}
```
```js
//js
/* eslint-disable jsx-a11y/heading-has-content */
import React from 'react';
import "../css/Estilos.css";
//tenemos que mandar a importar la hoja de estilos module
// en moduleStyles se van a almacenar todos los selectores que tenga la hoja de estilos 
import moduleStyles from "../css/Estilos.module.css"

export default function Estilos(){
    let myStyles={
        borderRadius: ".5rem",
        margin: "2rem auto",
        maxWidth: "50%"
    }


    return(
        <section className="estilos">
            <h2>EStilos CSS en React</h2>
            <h3 className="bg-react ">EStilos en hoja CSS externa</h3>
            <h3 className="bg-react" style={{borderRadius:".25rem", margin: "1rem"}}>Estilos en linea (atributo style)</h3>
            <h3 className="bg-react" style={myStyles}>Estilos en linea</h3>
            <h3 className={moduleStyles.error}>EStilos con Modulos</h3>
            <h3 className={moduleStyles.success}>EStilos con Modulos</h3>

        </section>
    );
};
```
Una de las cosas que tiene esta tecnica de los modulos es que si miramos el inspector de elementos y revisamos el nombre de estas clases podemos observar que le da un nombre aleatorio. ESto ayuda a que sea mas especifico el nombre del selector y estar evitando errores de cascada.

## [Styled Components](https://styled-components.com/)

Esta libreria nos va a permitir tener presentacion/contenido/logica de programacion de un mismo componente en un solo archivo para ello vamos a hacer uso de la libreria [Styled Components](https://styled-components.com/).

Para instalarlo ejecutamos:
```
npm install --save styled-components
```

Tambien es recomedable instalar en el vsc la libreria `styled-components-snippets` de Jon Wheeler. Lo que va hacer es interpretar el color de la libreria y no veamos como cadena de texto los estilos.

creamos un archivo nuevo .js
Esta seria la **sintaxis** inicial de como usar styled:
```js
import React from 'react';
import styled from 'styled-components';

export default function ComponentesEStilizados(){
    const MyH3 = styled.h3`
        padding: 2rem;
        text-align: center;    
    `;

    return(
        <>
            <h2>Styled-Components</h2>
            <MyH3> estilizado con styled-components</MyH3>
        </>
    )
}
```

Pero tambien se pueden usar **variable y funciones**:
```js
import React from 'react';
import styled from 'styled-components';

export default function ComponentesEStilizados(){
    let mainColor = "#db7093",
    mainAlphaColor80 = "#db709380";
    const setTransitionTime = (tiempo) => `all ${tiempo} ease-in-out`;

    const MyH3 = styled.h3`
        padding: 2rem;
        text-align: center;  
        background-color: ${mainColor};
        transition: ${setTransitionTime(".5s")};

        &:hover{
            /*el mismo h3 pero en hover */
            background-color: ${mainAlphaColor80}
        }  
    `;

    return(
        <>
            <h2>Styled-Components</h2>
            <MyH3> estilizado con styled-components</MyH3>
        </>
    )
}
```

Tambien se le pueden **pasar propiedades**:
```js
import React from 'react';
import styled from 'styled-components';

export default function ComponentesEStilizados(){
    let mainColor = "#db7093",
    mainAlphaColor80 = "#db709380";
    const setTransitionTime = (tiempo) => `all ${tiempo} ease-in-out`;

    const MyH3 = styled.h3`
        padding: 2rem;
        text-align: center;  
        color: ${({color}) => color || "#000"};/*Aqui se le esta pasando la propiedad */
        background-color: ${mainColor};
        transition: ${setTransitionTime(".5s")};

        &:hover{
            /*el mismo h3 pero en hover */
            background-color: ${mainAlphaColor80}
        }  
    `;

    return(
        <>
            <h2>Styled-Components</h2>
            <MyH3> estilizado con styled-components</MyH3>
            <MyH3 color="#61dafb">estilizado con styled-components</MyH3>
        </>
    )
}
```

**styled-components dentro de styled-components**:
```js
import React from 'react';
import styled,{css} from 'styled-components'; //vamos a llamar tambien a css de la misma libreria
// css funciona para utilizar styled-components dentro de styled-components

export default function ComponentesEStilizados(){
    let mainColor = "#db7093",
    mainAlphaColor80 = "#db709380";
    const setTransitionTime = (tiempo) => `all ${tiempo} ease-in-out`;

    const MyH3 = styled.h3`
        padding: 2rem;
        text-align: center;  
        color: ${({color}) => color || "#000"};
        background-color: ${mainColor};
        transition: ${setTransitionTime(".5s")};

        /*aqui le estamos diciendo que si existe la propiedad isButton entonces aplique los siguientes estilos */
        ${({isButton}) => isButton && css`
            margin: auto;
            max-width: 50%;
            border-radius: 0.25rem;
            cursor: pointer;
        `};

        &:hover{
            background-color: ${mainAlphaColor80}
        }  
    `;

    return(
        <>
            <h2>Styled-Components</h2>
            <MyH3> estilizado con styled-components</MyH3>
            <MyH3 color="#61dafb">estilizado con styled-components</MyH3>
            <MyH3 isButton>h3 estilizado como boton</MyH3>
        </>
    )
}
```
**animaciones y keyframes**
```js
import React from 'react';
import styled,{css, keyframes} from 'styled-components'; 

export default function ComponentesEStilizados(){
    let mainColor = "#db7093",
    mainAlphaColor80 = "#db709380";
    const setTransitionTime = (tiempo) => `all ${tiempo} ease-in-out`;

    const fadeIn = keyframes`
        0%{
            opacity: 0;
        }
        100%{
            opacity: 1;
        }
    `;

    const MyH3 = styled.h3`
        padding: 2rem;
        text-align: center;  
        color: ${({color}) => color || "#000"};
        background-color: ${mainColor};
        transition: ${setTransitionTime(".5s")};
        animation: ${fadeIn} 5s ease-out;

        ${({isButton}) => isButton && css`
            margin: auto;
            max-width: 50%;
            border-radius: 0.25rem;
            cursor: pointer;
        `};

        &:hover{
            background-color: ${mainAlphaColor80}
        }  
    `;

    return(
        <>
            <h2>Styled-Components</h2>
            <MyH3> estilizado con styled-components</MyH3>
            <MyH3 color="#61dafb">estilizado con styled-components</MyH3>
            <MyH3 isButton>h3 estilizado como boton</MyH3>
        </>
    )
}
```

- `ThemeProvider`: contexto para temas
- `createGlobalStyle`: nos permite crear estilos globales que vana  aplicar para toda la aplicacion(reseteo global de estilos)
- `styled()`: nos permite heredar los estilos de otro componente.

## CRUD App: Creación de componentes y renderizado de datos

### 1/4
- `Apps.js`:
```js
import React from "react";
import CrudApp from "./components/CrudApp";

function App() {
  return (
    <>
      <h1>Ejercicios con React</h1>
      <CrudApp/>
    </>
  );
}

export default App;
```

- `CrudApps.js`:
```js
import React, { useState } from 'react';
import CrudForm from './CrudForm';
import CrudTable from './CrudTable';

const initialDb = [
    {
        id: 1,
        name: "Seiya",
        constellation: "Pegaso"
    },
    {
        id: 2,
        name: "Shiryu",
        constellation: "Dragon"
    },
    {
        id: 3,
        name: "Hyoga",
        constellation: "Cisne"
    },
    {
        id: 4,
        name: "Shun",
        constellation: "Andromeda"
    },
    {
        id: 5,
        name: "Ikki",
        constellation: "Fenix"
    },
    
];  

const CrudApp = () => {
    const [db, setdb] = useState(initialDb)
    return (
        <div>
            <h2>CRUD App</h2>
            <CrudForm/>
            <CrudTable data={db}/>
        </div>
    );
};

export default CrudApp;
```
- `CrudForm.js`:
```js
import React, { useState, useEffect } from 'react';
 
    const initialForm = {
        name:"",
        constellation: "",
        id: null
    };

const CrudForm = () => {
        const [form, setform] = useState(initialForm);

    const handleChange = (e) =>{
        /* function para los input text*/
    };

    const handleSubmit = (e) =>{
        /* function para el submit del formulario*/
    };

    const handleReset = (e) =>{
        /* function para el boton de limpieza*/
    }

    return (
        <div>
            <h3>Agregar</h3>
            <form onSubmit={handleSubmit}>
                <input type="text" name="name" placeholder="Nombre" onChange={handleChange} value={form.name}/>
                <input type="text" name="constellation" placeholder="Constelacion" onChange={handleChange} value={form.constellation}/>
                <input type="submit" value="Enviar"/>
                <input type="reset" value="Limpiar" onClick={handleReset}/>
            </form>
        </div>
    )
};

export default CrudForm;
```

- `CrudTable.js`:
```js
import React from 'react'
import CrudTableRow from './CrudTableRow';

const CrudTable = ({data}) => {
    return (
        <div>
            <h3>Tabla de Datos</h3>
            <table>
                <thead>
                    <tr>
                        <th>Nombre</th>
                        <th>Cosntelacion</th>
                        <th>Acciones</th>
                    </tr>
                </thead>
                <tbody>
                    {data.length === 0 
                    ? <tr><td colSpan="3">Sin datos</td></tr> 
                    : data.map((el) => <CrudTableRow key={el.id} el={el}/>
                    )}
                </tbody>
            </table>
        </div>
    )
}

export default CrudTable;
```

- `CrudTableRow.js`:
```js
import React from 'react'

const CrudTableRow = ({el}) => {
    return (
        <tr>
            <td>{el.name}</td>
            <td>{el.constellation}</td>
            <td>
                <button>Editar</button>
                <button>Eliminar</button> 
            </td>
        </tr>
    )
}

export default CrudTableRow
```
### 2/4
ya que tenemos la estructura incial hora debemos comprender como debemos crear la estrategia para ir actualizando cada una de las operaciones del crud.
- `CrudApp.js`:
```js
import React, { useState } from 'react';
import CrudForm from './CrudForm';
import CrudTable from './CrudTable';

const initialDb = [
    {
        id: 1,
        name: "Seiya",
        constellation: "Pegaso"
    },
    {
        id: 2,
        name: "Shiryu",
        constellation: "Dragon"
    },
    {
        id: 3,
        name: "Hyoga",
        constellation: "Cisne"
    },
    {
        id: 4,
        name: "Shun",
        constellation: "Andromeda"
    },
    {
        id: 5,
        name: "Ikki",
        constellation: "Fenix"
    },
    
];  

const CrudApp = () => {
    const [db, setDb] = useState(initialDb);
    //neceitamos una variable de estado que me permita saber si va a ser una funcion de insercion o de actualizacion :
    const [dataToEdit, setDataToEdit] = useState(null);//cuando este null significa que vamos a hacer una insercion y cuando sea true vamos a hacer una actualizacion
    const createData =(data)=>{
        //en lugar de descargar una dependencia que genere id unicos,como por ejemplo uniteId, podemos usar Date.now() para crear un id provicional unico
        data.id= Date.now();
        setDb([...db, data]);
    };
    const updateData = (data)=>{};
    const deleteData = (id)=>{}
    ;
    return (
        <div>
            <h2>CRUD App</h2>
            <CrudForm createData={createData} updateData={updateData} dataToEdit={dataToEdit} setDataToEdit={setDataToEdit}/>
            <CrudTable data={db} setDataToEdit={setDataToEdit} deleteData={deleteData}/>
        </div>
    );
};

export default CrudApp;
```

- `CrudForm.js`:
```js
import React, { useState, useEffect } from 'react';
 
    const initialForm = {
        name:"",
        constellation: "",
        id: null
    };

const CrudForm = ({createData, updateData, dataToEdit, setDataToEdit}) => {
        const [form, setForm] = useState(initialForm);

    const handleChange = (e) =>{
        /* function para los input text*/
        setForm({
            ...form,
            [e.target.name]: e.target.value
        })
    };

    const handleSubmit = (e) =>{
        /* function para el submit del formulario*/
        e.preventDefault();
        if(!form.name || !form.constellation){
            alert("Datos incompletos");
            return;
        };

        if(form.id === null){
             createData(form);
        }else{
            updateData(form);
        };

        handleReset();
    };

    const handleReset = (e) =>{
        /* function para el boton de limpieza*/
        setForm(initialForm);
        setDataToEdit(null);
    }

    return (
        <div>
            <h3>Agregar</h3>
            <form onSubmit={handleSubmit}>
                <input type="text" name="name" placeholder="Nombre" onChange={handleChange} value={form.name}/>
                <input type="text" name="constellation" placeholder="Constelacion" onChange={handleChange} value={form.constellation}/>
                <input type="submit" value="Enviar"/>
                <input type="reset" value="Limpiar" onClick={handleReset}/>
            </form>
        </div>
    )
};

export default CrudForm;
```

### 3/4
- `CrudApps.js`:
```js
import React, { useState } from 'react';
import CrudForm from './CrudForm';
import CrudTable from './CrudTable';

const initialDb = [
    {
        id: 1,
        name: "Seiya",
        constellation: "Pegaso"
    },
    {
        id: 2,
        name: "Shiryu",
        constellation: "Dragon"
    },
    {
        id: 3,
        name: "Hyoga",
        constellation: "Cisne"
    },
    {
        id: 4,
        name: "Shun",
        constellation: "Andromeda"
    },
    {
        id: 5,
        name: "Ikki",
        constellation: "Fenix"
    },
    
];  

const CrudApp = () => {
    const [db, setDb] = useState(initialDb);
    const [dataToEdit, setDataToEdit] = useState(null);
    const createData =(data)=>{
        data.id= Date.now();
        setDb([...db, data]);
    };
    const updateData = (data)=>{
        let newData = db.map(el => el.id === data.id ? data : el);
        setDb(newData); 
    };
    const deleteData = (id)=>{}
    ;
    return (
        <div>
            <h2>CRUD App</h2>
            <CrudForm createData={createData} updateData={updateData} dataToEdit={dataToEdit} setDataToEdit={setDataToEdit}/>
            <CrudTable data={db} setDataToEdit={setDataToEdit} deleteData={deleteData}/>
        </div>
    );
};

export default CrudApp;
```
- `CrudForm.js`:
```js
import React, { useState, useEffect } from 'react';
 
    const initialForm = {
        name:"",
        constellation: "",
        id: null
    };

const CrudForm = ({createData, updateData, dataToEdit, setDataToEdit}) => {
    const [form, setForm] = useState(initialForm);

    useEffect(() => {
        if(dataToEdit){
            setForm(dataToEdit);
        }else{
            setForm(initialForm);
        }
    },[dataToEdit]);

    const handleChange = (e) =>{
        /* function para los input text*/
        setForm({
            ...form,
            [e.target.name]: e.target.value
        })
    };

    const handleSubmit = (e) =>{
        /* function para el submit del formulario*/
        e.preventDefault();
        if(!form.name || !form.constellation){
            alert("Datos incompletos");
            return;
        };

        if(form.id === null){
             createData(form);
        }else{
            updateData(form);
        };

        handleReset();
    };

    const handleReset = (e) =>{
        /* function para el boton de limpieza*/
        setForm(initialForm);
        setDataToEdit(null);
    }

    return (
        <div>
            <h3>{dataToEdit ? "Editar" : "Agregar"}</h3>
            <form onSubmit={handleSubmit}>
                <input type="text" name="name" placeholder="Nombre" onChange={handleChange} value={form.name}/>
                <input type="text" name="constellation" placeholder="Constelacion" onChange={handleChange} value={form.constellation}/>
                <input type="submit" value="Enviar"/>
                <input type="reset" value="Limpiar" onClick={handleReset}/>
            </form>
        </div>
    )
};

export default CrudForm;
```
- `CrudTable.js`:
```js
import React from 'react'
import CrudTableRow from './CrudTableRow';

const CrudTable = ({data,setDataToEdit, deleteData}) => {
    return (
        <div>
            <h3>Tabla de Datos</h3>
            <table>
                <thead>
                    <tr>
                        <th>Nombre</th>
                        <th>Cosntelacion</th>
                        <th>Acciones</th>
                    </tr>
                </thead>
                <tbody>
                    {data.length === 0 
                    ? <tr><td colSpan="3">Sin datos</td></tr> 
                    : data.map((el) => <CrudTableRow key={el.id} el={el} setDataToEdit={setDataToEdit} deleteData={deleteData}/>
                    )}
                </tbody>
            </table>
        </div>
    )
}

export default CrudTable;
```
- `CrudTableRow.js`:
```js
import React from 'react'

const CrudTableRow = ({el, setDataToEdit, deleteData}) => {
    let {name,constellation,id} = el;
    return (
        <tr>
            <td>{name}</td>
            <td>{constellation}</td>
            <td>
                <button onClick={() => setDataToEdit(el)}>Editar</button>
                <button onClick={() => deleteData(id)}>Eliminar</button> 
            </td>
        </tr>
    )
}

export default CrudTableRow

```
### 4/4
- `CrudApps`:
```js
import React, { useState } from 'react';
import CrudForm from './CrudForm';
import CrudTable from './CrudTable';

const initialDb = [
    {
        id: 1,
        name: "Seiya",
        constellation: "Pegaso"
    },
    {
        id: 2,
        name: "Shiryu",
        constellation: "Dragon"
    },
    {
        id: 3,
        name: "Hyoga",
        constellation: "Cisne"
    },
    {
        id: 4,
        name: "Shun",
        constellation: "Andromeda"
    },
    {
        id: 5,
        name: "Ikki",
        constellation: "Fenix"
    },
    
];  

const CrudApp = () => {
    const [db, setDb] = useState(initialDb);
    const [dataToEdit, setDataToEdit] = useState(null);
    const createData =(data)=>{
        data.id= Date.now();
        setDb([...db, data]);
    };
    const updateData = (data)=>{
        let newData = db.map(el => el.id === data.id ? data : el);
        setDb(newData); 
    };
    const deleteData = (id)=>{
        let isDelete = window.confirm(`Estas segundo de eliminar el registro con el id "${id}"?`);
        if(isDelete){
            let newData = db.filter(el => el.id !== id);
            setDb(newData);
        }else{
            return;
        }
    }
    ;
    return (
        <div>
            <h2>CRUD App</h2>
            <CrudForm createData={createData} updateData={updateData} dataToEdit={dataToEdit} setDataToEdit={setDataToEdit}/>
            <CrudTable data={db} setDataToEdit={setDataToEdit} deleteData={deleteData}/>
        </div>
    );
};

export default CrudApp;
```

- `CrudForm.js`:
```js
import React, { useState, useEffect } from 'react';
 
    const initialForm = {
        name:"",
        constellation: "",
        id: null
    };

const CrudForm = ({createData, updateData, dataToEdit, setDataToEdit}) => {
    const [form, setForm] = useState(initialForm);

    useEffect(() => {
        if(dataToEdit){
            setForm(dataToEdit);
        }else{
            setForm(initialForm);
        }
    },[dataToEdit]);

    const handleChange = (e) =>{
        /* function para los input text*/
        setForm({
            ...form,
            [e.target.name]: e.target.value
        })
    };

    const handleSubmit = (e) =>{
        /* function para el submit del formulario*/
        e.preventDefault();
        if(!form.name || !form.constellation){
            alert("Datos incompletos");
            return;
        };

        if(form.id === null){
             createData(form);
        }else{
            updateData(form);
        };

        handleReset();
    };

    const handleReset = (e) =>{
        /* function para el boton de limpieza*/
        setForm(initialForm);
        setDataToEdit(null);
    }

    return (
        <div>
            <h3>{dataToEdit ? "Editar" : "Agregar"}</h3>
            <form onSubmit={handleSubmit}>
                <input type="text" name="name" placeholder="Nombre" onChange={handleChange} value={form.name}/>
                <input type="text" name="constellation" placeholder="Constelacion" onChange={handleChange} value={form.constellation}/>
                <input type="submit" value="Enviar"/>
                <input type="reset" value="Limpiar" onClick={handleReset}/>
            </form>
        </div>
    )
};

export default CrudForm;
```
- `CrudTable.js`:
```js
import React from 'react'
import CrudTableRow from './CrudTableRow';

const CrudTable = ({data,setDataToEdit, deleteData}) => {
    return (
        <div>
            <h3>Tabla de Datos</h3>
            <table>
                <thead>
                    <tr>
                        <th>Nombre</th>
                        <th>Cosntelacion</th>
                        <th>Acciones</th>
                    </tr>
                </thead>
                <tbody>
                    {data.length === 0 
                    ? <tr><td colSpan="3">Sin datos</td></tr> 
                    : data.map((el) => <CrudTableRow key={el.id} el={el} setDataToEdit={setDataToEdit} deleteData={deleteData}/>
                    )}
                </tbody>
            </table>
        </div>
    )
}

export default CrudTable;
```
- `CrudTableRow.js`:
```js
import React from 'react'

const CrudTableRow = ({el, setDataToEdit, deleteData}) => {
    let {name,constellation,id} = el;
    return (
        <tr>
            <td>{name}</td>
            <td>{constellation}</td>
            <td>
                <button onClick={() => setDataToEdit(el)}>Editar</button>
                <button onClick={() => deleteData(id)}>Eliminar</button> 
            </td>
        </tr>
    )
}

export default CrudTableRow
```

## CRUD API: Creando una API con JSON Server
Vamos a hacer:
- Un componente de mensajes(nos va a permitir enviar mensajes de exito y mensajes de error cada vez que hagamos una transaccion)
- Vamos a crear un componente de loader que nos permita interactuar hasta que se cargen por completo los datos de la api.
## 1/5
- `db.json`:
```json
{
    "santos": [
        {
            "id": 1,
            "name": "Seiya",
            "constellation": "Pegaso"
        },
        {
            "id": 2,
            "name": "Shiryu",
            "constellation": "Dragon"
        },
        {
            "id": 3,
            "name": "Hyoga",
            "constellation": "Cisne"
        },
        {
            "id": 4,
            "name": "Shun",
            "constellation": "Andromeda"
        },
        {
            "id": 5,
            "name": "Ikki",
            "constellation": "Fenix"
        }
    ]
}
```

- podemos crear un comando para ejecutar el inicio de json-server:
En el archivo de `package.json` del webpack en `scripts` ingresamos:
```
"fake-api":"json-server --watch src/api/db.json --port 3000"
```
`--watch`: me indica la ruta donde esta el archivo que simula la base de datos

- `CrudApi.js`:
```js
import React, { useState } from 'react';
import CrudForm from './CrudForm';
import CrudTable from './CrudTable';



const CrudApi = () => {
    const [db, setDb] = useState([]);
    const [dataToEdit, setDataToEdit] = useState(null);
    const createData =(data)=>{
        data.id= Date.now();
        setDb([...db, data]);
    };
    const updateData = (data)=>{
        let newData = db.map(el => el.id === data.id ? data : el);
        setDb(newData); 
    };
    const deleteData = (id)=>{
        let isDelete = window.confirm(`Estas segundo de eliminar el registro con el id "${id}"?`);
        if(isDelete){
            let newData = db.filter(el => el.id !== id);
            setDb(newData);
        }else{
            return;
        }
    }
    ;
    return (
        <div>
            <h2>CRUD App</h2>
            <CrudForm createData={createData} updateData={updateData} dataToEdit={dataToEdit} setDataToEdit={setDataToEdit}/>
            <CrudTable data={db} setDataToEdit={setDataToEdit} deleteData={deleteData}/>
        </div>
    );
};

export default CrudApi;
```

### 2/5
Un helper podria ser una funcion que te ayuda a resolver una tarea mas enfocada a logica abstracta que de ui.

[AbortController](https://developer.mozilla.org/en-US/docs/Web/API/AbortController)

Haremos un helper para hacer peticiones a apis con fetch:
- `helpHttp.js`:
```js
export const helpHttp = () => {
    //peticion fetch
    const customFetch = (endpoint,options) => {
        const defaultHeader = {
            //cabeceras
            accept:"application/json"
        };

        /*AbortController: sirve  para cuando la peticion fetch detecta que no hay
        una respuesta del servidor aborta la peticion*/ 
        const controller = new AbortController();
        options.signal = controller.signal;

        options.method = options.method || "GET";
        options.headers = options.headers ? {...defaultHeader, ...options.headers} : defaultHeader;

        //convertir el objeto a cadena
        options.body = JSON.stringify(options.body) || false;
        if(!options.body) delete options.body;/*en las peticiones no puedes mandar la opcion del body falsa asi que creamos este if para que borre la propiedad con delete */

        setTimeout(() => controller.abort(), 3000);

        return fetch(endpoint,options).then(res => res.ok ? res.json() : Promise.reject({
            err:true,
            status: res.status || "00",
            statusText: res.statusText || "Ocurrio un error"
        })).catch(err => err);
    };

    const get = (url, options = {}) => customFetch(url,options);

    const post = (url,options={}) =>{
        options.method = "POST";
        return customFetch(url, options);
    };

    const put = (url,options={}) =>{
        options.method = "PUT";
        return customFetch(url, options);
    };

    const del = (url,options={}) =>{
        options.method = "DELETE";
        return customFetch(url, options);
    };

    return {
        get,post,put,del
    }
}
```

### 3/5

Recordar iniciar el servidor de json-server y de app:
- `CrudApi.js`:
```js
import React, { useState, useEffect } from 'react';
import { helpHttp } from '../helpers/helpHttp';
import CrudForm from './CrudForm';
import CrudTable from './CrudTable';



const CrudApi = () => {
    const [db, setDb] = useState([]);
    const [dataToEdit, setDataToEdit] = useState(null);
    
    let api = helpHttp();
    let url = "http://localhost:3000/santos";
    
    useEffect(() => {
        api.get(url).then(res =>{
            if(!res.err){
                setDb(res);
            }else{
                setDb(null)
            }
        })
    },[])


    const createData =(data)=>{
        data.id= Date.now();
        setDb([...db, data]);
    };
    const updateData = (data)=>{
        let newData = db.map(el => el.id === data.id ? data : el);
        setDb(newData); 
    };
    const deleteData = (id)=>{
        let isDelete = window.confirm(`Estas segundo de eliminar el registro con el id "${id}"?`);
        if(isDelete){
            let newData = db.filter(el => el.id !== id);
            setDb(newData);
        }else{
            return;
        }
    }
    ;
    return (
        <div>
            <h2>CRUD App</h2>
            <CrudForm createData={createData} updateData={updateData} dataToEdit={dataToEdit} setDataToEdit={setDataToEdit}/>
            <CrudTable data={db} setDataToEdit={setDataToEdit} deleteData={deleteData}/>
        </div>
    );
};

export default CrudApi;
```

### 4/5 : Implementando Loaders y Mensajes de errores
[loading.io](https://loading.io/) : Es una pagina que tiene varios louders animados con diferentes tecnologias. Existe una seccion de loaders con puro codigo css [Pure CSS Loaders](https://loading.io/css/).

- `App.js`:
```js
import React from "react";
import CrudApi from "./components/CrudApi";
import CrudApp from "./components/CrudApp";

function App() {
  return (
    <>
      <h1>Ejercicios con React</h1>
      <hr/>
      <CrudApi/>
      <hr/>
      <CrudApp/>
    </>
  );
}

export default App;
```
- `CrudApi.js`:
```js
import React, { useState, useEffect } from 'react';
import { helpHttp } from '../helpers/helpHttp';
import CrudForm from './CrudForm';
import CrudTable from './CrudTable';
import Loader from './Loader';
import Message from './Message';



const CrudApi = () => {
    const [db, setDb] = useState(null);
    const [dataToEdit, setDataToEdit] = useState(null);
    const [error, setError] = useState(null);
    const [loading, setLoading] = useState(false);
    
    //let api = helpHttp();
    let url = "http://localhost:3000/santos";
    
    useEffect(() => {
        /*antes de hacer la peticion se actualizara loading */
        setLoading(true);
        helpHttp().get(url).then(res =>{
            if(!res.err){
                setDb(res);
                setError(null);
            }else{
                setDb(null);
                /*Si hay un error */
                setError(res);
            }
        });

        /*Cuando obtengamos los datos de la peticion entonces se quitaria el loading */
        setLoading(false);
    },[url /*si hubieramos tratado de agregar la variable api aqui entonces saldria un error infinito en el nacegador */]);


    const createData =(data)=>{
        data.id= Date.now();
        setDb([...db, data]);
    };
    const updateData = (data)=>{
        let newData = db.map(el => el.id === data.id ? data : el);
        setDb(newData); 
    };
    const deleteData = (id)=>{
        let isDelete = window.confirm(`Estas segundo de eliminar el registro con el id "${id}"?`);
        if(isDelete){
            let newData = db.filter(el => el.id !== id);
            setDb(newData);
        }else{
            return;
        }
    }
    ;
    return (
        <div>
            <h2>CRUD App</h2>
            {/*La tabla siempre va a estar disponible(crudForm) */}
            <CrudForm createData={createData} updateData={updateData} dataToEdit={dataToEdit} setDataToEdit={setDataToEdit}/>
            {loading && <Loader/>}
            {error && <Message msg={`Error ${error.status}: ${error.statusText}`} bgColor="dc3545"/>}
            {/*si db es nulo entonces no se carga el componente CrudTable */}
            {db && <CrudTable data={db} setDataToEdit={setDataToEdit} deleteData={deleteData}/>}
        </div>
    );
};

export default CrudApi;
```
- `Loader.js`:
```js
import React from 'react';
import "./Loader.css";

const Loader = () => {
    return (
        <div>
            <h2>Loader</h2>
            <div className="lds-circle"><div></div></div>
        </div>
    )
}

export default Loader;
```

- `Loader.css`:
```css
.lds-circle {
    display: inline-block;
    transform: translateZ(1px);
  }
  .lds-circle > div {
    display: inline-block;
    width: 64px;
    height: 64px;
    margin: 8px;
    border-radius: 50%;
    background: #000;
    animation: lds-circle 2.4s cubic-bezier(0, 0.2, 0.8, 1) infinite;
  }
  @keyframes lds-circle {
    0%, 100% {
      animation-timing-function: cubic-bezier(0.5, 0, 1, 0.5);
    }
    0% {
      transform: rotateY(0deg);
    }
    50% {
      transform: rotateY(1800deg);
      animation-timing-function: cubic-bezier(0, 0.5, 0.5, 1);
    }
    100% {
      transform: rotateY(3600deg);
    }
  }
```
- `Message.js`:
```js
import React from 'react'

const Message = ({msg,bgColor}) => {
    let styles ={
        padding:"1rem",
        marginBottom:"1rem",
        textAlign:"center",
        color: "#fff",
        fontWeight: "bold",
        backgroundColor: `${bgColor}`
    }
    return (
        <div style={styles}>
            <p>{msg}</p>
        </div>
    )
}

export default Message;

```
### 5/5
- `CrudApi.js`:
```js
import React, { useState, useEffect } from 'react';
import { helpHttp } from '../helpers/helpHttp';
import CrudForm from './CrudForm';
import CrudTable from './CrudTable';
import Loader from './Loader';
import Message from './Message';



const CrudApi = () => {
    const [db, setDb] = useState(null);
    const [dataToEdit, setDataToEdit] = useState(null);
    const [error, setError] = useState(null);
    const [loading, setLoading] = useState(false);
    
    let api = helpHttp();
    let url = "http://localhost:3000/santos";
    
    useEffect(() => {
        /*antes de hacer la peticion se actualizara loading */
        setLoading(true);
        helpHttp().get(url).then(res =>{
            if(!res.err){
                setDb(res);
                setError(null);
            }else{
                setDb(null);
                /*Si hay un error */
                setError(res);
            }
        });

        /*Cuando obtengamos los datos de la peticion entonces se quitaria el loading */
        setLoading(false);
    },[url /*si hubieramos tratado de agregar la variable api aqui entonces saldria un error infinito en el nacegador */]);


    const createData =(data)=>{
        data.id= Date.now();
        let options = {body:data,headers:{"content-type": "application/json"}};
        api.post(url,options).then((res) =>{
            if(!res.err){
                setDb([...db, res]);
            }else{
                setError(res);
            }
        })
    };

    const updateData = (data)=>{
        let endpoint = `${url}/${data.id}`;
        let options = {body:data,headers:{"content-type": "application/json"}};
        api.put(endpoint, options).then((res) =>{
            if(!res.err){
                let newData = db.map((el)=> el.id ===data.id ?data :el);
                setDb(newData);
            }else{
                setError(res);
            }
        })
        
    };

    const deleteData = (id)=>{
        let isDelete = window.confirm(`Estas segundo de eliminar el registro con el id "${id}"?`);
        if(isDelete){
            let options = {"content-type": "application/json"};
            let endpoint = `${url}/${id}`;
            api.del(endpoint,options).then(res=>{
                if(!res.err){
                    let newData = db.filter(el => el.id !== id);
                    setDb(newData);
                }else{
                    setError(res);
                }
            })
        }else{
            return;
        }
    }
    ;
    return (
        <div>
            <h2>CRUD App</h2>
            {/*La tabla siempre va a estar disponible(crudForm) */}
            <CrudForm createData={createData} updateData={updateData} dataToEdit={dataToEdit} setDataToEdit={setDataToEdit}/>
            {loading && <Loader/>}
            {error && <Message msg={`Error ${error.status}: ${error.statusText}`} bgColor="dc3545"/>}
            {/*si db es nulo entonces no se carga el componente CrudTable */}
            {db && <CrudTable data={db} setDataToEdit={setDataToEdit} deleteData={deleteData}/>}
        </div>
    );
};

export default CrudApi;
```
- `Cr udTable.js`:
```js
import React from 'react'
import CrudTableRow from './CrudTableRow';

const CrudTable = ({data,setDataToEdit, deleteData}) => {
    return (
        <div>
            <h3>Tabla de Datos</h3>
            <table>
                <thead>
                    <tr>
                        <th>Nombre</th>
                        <th>Cosntelacion</th>
                        <th>Acciones</th>
                    </tr>
                </thead>
                <tbody>
                    {data.length > 0 
                    ? data.map((el) => <CrudTableRow key={el.id} el={el} setDataToEdit={setDataToEdit} deleteData={deleteData}/>)
                    :  <tr><td colSpan="3">Sin datos</td></tr>
                    }
                </tbody>
            </table>
        </div>
    )
}

export default CrudTable;
```

## Selects Anidados

###  Definición de componentes y lógica ( 1 / 3 )

- `SelectsAnidados.js`:
```js
import React, { useState } from 'react';
import SelectList from './SelectList';

const SelectsAnidados = () => {
    const [state, setState] = useState("");
    const [town, setTown] = useState("");
    const [suburb, setSuburb] = useState("");

    return (
        <div>
            <h2>Selects Anidados</h2>
            <h3>Mexico</h3>
            {/*El handleChange va a estar revisando el evento de cambio del select html */}
            <SelectList title="estados" url="" handleChange={(e) =>{setState(e.target.value)}} />
            {state && (
                <SelectList title="municipios" url="" handleChange={(e) =>{setTown(e.target.value)}} /> 
            )}
            {town && (
                <SelectList title="colonias" url="" handleChange={(e) =>{setSuburb(e.target.value)}} /> 
            )}
            <pre>
                <code>
                    {state} - {town} - {suburb} 
                </code>
            </pre>
        </div>
    )
}

export default SelectsAnidados;
```
- `SelectList.js`:
```js
import React from 'react'

const SelectList  = () => {
    return (
        <div>
            <select name="" id="">
                <option value="">---</option>
            </select>
        </div>
    )
}

export default SelectList ;

```

### Hook personalizado para peticiones Fetch ( 2 / 3 )

La ap que vamos a usar esta en se llama [COPOMEX](https://api.copomex.com/documentacion/inicio), te tienes que registar para que te den un token para que puedas usar la api o usar el token `d81a7ac7-976d-4e1e-b7d3-b1979d791b6c`.

Tambien vamos a crear un hook personalizado que haga peticiones fetch y que guarde la informacion en variables de estado.

Para nombrar un hook tenemos que usar el formato camelcase, es decir, la primer palabrar tiene que ser en minusculas y tiene que tener el verbo `use`.

- `useFetch.js`:
```js
/*No es necesario mandar a llamar a react por que realmente como es un hook perosnalizado solamente va a devolvernos logica  */
import {useState,useEffect} from "react";

export const usePeticion =(url) =>{
    const [data, setData] = useState(null);
    const [error, setError] = useState(null);
    const [loading, setLoading] = useState(false);

    //este useEffect va hacer la peticion, cual la url cambie se va a ejecutar el efecto
    useEffect(() => {
        const abortController = new AbortController();
        const signal = abortController.signal; //se;al de abortar la peticion

        //lo que recomienda la gente de react es que si vamos a necesitar una peticion asyncrona la funcion que recibe el useEffect no sea asincrono por que eso es un antipatron, por eso vamos a crear una funcion asincrona dentro del useEffect
        const fetchData = async () => {
            // mientras que loading tengsa true se va a ver el louder (singno de cargando)
            setLoading(true);
            try {
                const res = await fetch(url);

                if(!res.ok){
                    let err = new Error("Error en la peticion Fetch");
                    err.status = res.status || "00";
                    err.statusText = res.statusText || "Ocurrio un error";
                    throw err; //el throw arroja el error a la parte del catch 
                };

                const json = await res.json();

                if(!signal.aborted){
                    setData(json);
                    setError(null);
                }
            } catch (error) {
                // que la peticion arroje un error no significa que ese error genere que se aborte la peticion
                // si la se;al no es aborted significa que el erro es de otro tipo pero no de que se haya aborado la peticion fetch
                if(!signal.aborted){
                    setData(null);
                    setError(error);
                }
            } finally {
                if(!signal.aborted){
                    setLoading(false);
                }
            }
        }

        fetchData();

        return() =>{
            //fase de desmontaje
            AbortController.abort();
        }
    },[url]);

    return {data,error,loading}
};
```
### Selects Anidados: Renderizado de datos ( 3 / 3 )

- `SelectsAnidados.js`:
```js
import React, { useState } from 'react';
import SelectList from './SelectList';

const SelectsAnidados = () => {
    const [state, setState] = useState("");
    const [town, setTown] = useState("");
    const [suburb, setSuburb] = useState("");

    const TOKEN = "d81a7ac7-976d-4e1e-b7d3-b1979d791b6c";

    return (
        <div>
            <h2>Selects Anidados</h2>
            <h3>Mexico</h3>
            <SelectList title="estado" url={`https://api.copomex.com/query/get_estados?token=${TOKEN}` } handleChange={(e) =>{setState(e.target.value)}} />
            {state && (
                <SelectList title="municipios" url={`https://api.copomex.com/query/get_municipio_por_estado/${state}?token=${TOKEN}`} handleChange={(e) =>{setTown(e.target.value)}} /> 
            )}
            {town && (
                <SelectList title="colonia" url={`https://api.copomex.com/query/get_colonia_por_municipio/${town}?token=${TOKEN}`} handleChange={(e) =>{setSuburb(e.target.value)}} /> 
            )}
            <pre>
                <code>
                    {state} - {town} - {suburb} 
                </code>
            </pre>
        </div>
    )
}

export default SelectsAnidados;
```

- `SelectList.js`:
```js
import React from 'react'
import { usePeticion } from '../hooks/usePeticion';

const SelectList  = ({title,url,handleChange}) => {
    const {data,error,loading} = usePeticion(url);

    if(!data)return null; //con esto evitamos renderizados de como si el select se estuviera cargando o no, para evitar repintados innecesarios
    if(error){
        console.log(error)
    }
    let id = `select-${title}`;
    let label = title.charAt(0).toUpperCase() + title.slice(1);
    let options = data.response[title];//te aprovecha de la propiedad title para extraer dinamicamente los datos


    return (
        <>
        <label htmlFor={id}>{label}</label>
            <select name={id} id={id} onChange={handleChange}>
                <option value="">Elige un {title}</option>
                {data && options.map((el)=>{
                    <option value={el}>{el}</option>
                })}
            </select>
        </>
    )
}

export default SelectList ;
```

## Validación Formularios
[FormSubmit](https://formsubmit.co/) nos permite enviar informacion de un formulario a un correo electronico.
### Definición de componentes y lógica ( 1 / 4 )
- `ContactForm.js`:
```js
import React from 'react'
import { useForm } from '../hooks/useForm';

const initialForm = {};

const balidationsForm = (form) =>{};

const ContactForm = () => {
    const {form,errors,loading,response,handleChange,handleBlur,handleSubmit} = useForm(initialForm,balidationsForm);
    return (
        <div>
            <h2>Formulario de Contacto</h2>
            <form onSubmit={handleSubmit}>
                <input type="text" name="name" placeholder="Escribe tu nombre" onBlur={handleBlur} onChange={handleChange} value={form.name} required/>
                <input type="email" name="email" placeholder="Escribe tu email" onBlur={handleBlur} onChange={handleChange} value={form.email} required/>
                <input type="text" name="subject" placeholder="Asunto a tratar" onBlur={handleBlur} onChange={handleChange} value={form.subject} required/>
                <textarea name="comments" cols="50" rows="5" placeholder="EScribe tus comentarios" onBlur={handleBlur} onChange={handleChange} value={form.comments} required></textarea>
                <input type="submit" value="Enviar"/>
            </form>
        </div>
    )
}

export default ContactForm;
```
- `useForm.js`:
```js
import { useState } from 'react';


export const useForm = (initialForm,validateForm) => {
    const [form, setForm] = useState(initialForm);
    const [errors, setErrors] = useState({}); //si este objeto vacio no tiene ningun atributo significa que todo esta correcto y podemos enviar el formulario   
    const [loading, setLoading] = useState(false);
    const [response, setResponse] = useState(null); 

    const handleChange = (e)=>{};
    const handleBlur = (e)=>{};
    const handleSubmit = (e)=>{};

    return{form,errors,loading,response,handleChange,handleBlur,handleSubmit}
};
```

### Programación de eventos ( 2 / 4 ) 

- `COntactForm.js`:
```js
import React from 'react'
import { useForm } from '../hooks/useForm';

const initialForm = {
    name: "",
    email: "",
    subject:"",
    comments:"" 
};

const validationsForm = (form) =>{
    let errors = {};

    if(!form.name.trim()){
        errors.name = "El campo 'Nombre' es requerido"; 
    }

    return errors;
};

const ContactForm = () => {
    const {form,errors,loading,response,handleChange,handleBlur,handleSubmit} = useForm(initialForm,validationsForm);
    return (
        <div>
            <h2>Formulario de Contacto</h2>
            <form onSubmit={handleSubmit}>
                <input type="text" name="name" placeholder="Escribe tu nombre" onBlur={handleBlur} onChange={handleChange} value={form.name} required/>
                {errors.name && <p>{errors.name}</p>}

                <input type="email" name="email" placeholder="Escribe tu email" onBlur={handleBlur} onChange={handleChange} value={form.email} required/>
                {errors.email && <p>{errors.email}</p>}

                <input type="text" name="subject" placeholder="Asunto a tratar" onBlur={handleBlur} onChange={handleChange} value={form.subject} required/>
                {errors.subject && <p>{errors.subject}</p>}

                <textarea name="comments" cols="50" rows="5" placeholder="EScribe tus comentarios" onBlur={handleBlur} onChange={handleChange} value={form.comments} required></textarea>
                {errors.comments && <p>{errors.comments}</p>}

                <input type="submit" value="Enviar"/>
            </form>
        </div>
    )
}

export default ContactForm;

```

- `useForm.js`:
```js
import { useState } from 'react';


export const useForm = (initialForm,validateForm) => {
    const [form, setForm] = useState(initialForm);
    const [errors, setErrors] = useState({}); //si este objeto vacio no tiene ningun atributo significa que todo esta correcto y podemos enviar el formulario   
    const [loading, setLoading] = useState(false);
    const [response, setResponse] = useState(null); 

    const handleChange = (e)=>{
        //esto lo que nos permite es tener formularios controlados  con el estado
        // a cada que se escribe en el input la variable se va llenando
        const {name,value} = e.target
        setForm({
            ...form,[name]: value 
        });
    };
    const handleBlur = (e)=>{
        handleChange(e);
        setErrors(validateForm(form));
    };
    const handleSubmit = (e)=>{};

    return{form,errors,loading,response,handleChange,handleBlur,handleSubmit}
};

```

### Programación de validaciones ( 3 / 4 )
- `ContactForm.js`:
```js
import React from 'react'
import { useForm } from '../hooks/useForm';

const initialForm = {
    name: "",
    email: "",
    subject:"",
    comments:"" 
};

const validationsForm = (form) =>{
    let errors = {};
    let regexName = /^[A-Za-zÑñÁáÉéÍíÓóÚúÜü\s]+$/;
    let regexEmail = /^(\w+[/./-]?){1,}@[a-z]+[/.]\w{2,}$/;
    let regexComments = /^.{1,255}$/;


    if(!form.name.trim()){
        errors.name = "El campo 'Nombre' es requerido"; 
    }else if(!regexName.test(form.name.trim())){
        errors.name = "EL campo 'Nombre' solo acepta letras y espacios en blanco";
    };

    if(!form.email.trim()){
        errors.email = "El campo 'Email' es requerido";
    }else if(!regexEmail.test(form.email.trim())){
        errors.email = "EL campo 'Email' es incorrecto";
    };

    if(!form.subject.trim()){
        errors.subject = "El campo 'Asunto a tratar' es requerido";
    };
    if(!form.comments.trim()){
        errors.comments = "El campo 'Comentarios' es requerido";
    }else if(!regexComments.test(form.comments.trim())){
        errors.comments = "EL campo 'Nombre' no debe exceder los 255 caracteres";
    }

    return errors;
};

const ContactForm = () => {
    const {form,errors,loading,response,handleChange,handleBlur,handleSubmit} = useForm(initialForm,validationsForm);
    return (
        <div>
            <h2>Formulario de Contacto</h2>
            <form onSubmit={handleSubmit}>
                <input type="text" name="name" placeholder="Escribe tu nombre" onBlur={handleBlur} onChange={handleChange} value={form.name} required/>
                {errors.name && <p>{errors.name}</p>}

                <input type="email" name="email" placeholder="Escribe tu email" onBlur={handleBlur} onChange={handleChange} value={form.email} required/>
                {errors.email && <p>{errors.email}</p>}

                <input type="text" name="subject" placeholder="Asunto a tratar" onBlur={handleBlur} onChange={handleChange} value={form.subject} required/>
                {errors.subject && <p>{errors.subject}</p>}

                <textarea name="comments" cols="50" rows="5" placeholder="EScribe tus comentarios" onBlur={handleBlur} onChange={handleChange} value={form.comments} required></textarea>
                {errors.comments && <p>{errors.comments}</p>}

                <input type="submit" value="Enviar"/>
            </form>
        </div>
    )
}

export default ContactForm;

```
### Envío de datos AJAX y API FormSubmit ( 4 / 4 )
[FormSubmit](https://formsubmit.co/) nos permite enviar informacion de un formulario a un correo electronico.

- `helpHttp.js`:
```js
export const helpHttp = () => {
  const customFetch = (endpoint, options) => {
    const defaultHeader = {
      accept: "application/json",
    };

    const controller = new AbortController();
    options.signal = controller.signal;

    options.method = options.method || "GET";
    options.headers = options.headers
      ? { ...defaultHeader, ...options.headers }
      : defaultHeader;

    options.body = JSON.stringify(options.body) || false;
    if (!options.body) delete options.body;

    //console.log(options);
    setTimeout(() => controller.abort(), 3000);

    return fetch(endpoint, options)
      .then((res) =>
        res.ok
          ? res.json()
          : Promise.reject({
              err: true,
              status: res.status || "00",
              statusText: res.statusText || "Ocurrió un error",
            })
      )
      .catch((err) => err);
  };

  const get = (url, options = {}) => customFetch(url, options);

  const post = (url, options = {}) => {
    options.method = "POST";
    return customFetch(url, options);
  };

  const put = (url, options = {}) => {
    options.method = "PUT";
    return customFetch(url, options);
  };

  const del = (url, options = {}) => {
    options.method = "DELETE";
    return customFetch(url, options);
  };

  return {
    get,
    post,
    put,
    del,
  };
};
```
- `useForm.js`:
```js
import { useState } from 'react';
import { helpHttp } from '../helpers/helpHttp';


export const useForm = (initialForm,validateForm) => {
    const [form, setForm] = useState(initialForm);
    const [errors, setErrors] = useState({});   
    const [loading, setLoading] = useState(false);
    const [response, setResponse] = useState(null); 

    const handleChange = (e)=>{
        
        const {name,value} = e.target
        setForm({
            ...form,[name]: value 
        });
    };
    const handleBlur = (e)=>{
        handleChange(e);
        setErrors(validateForm(form));
    };
    const handleSubmit = (e)=>{
        e.preventDefault();
        setErrors(validateForm(form));
        if(Object.keys(errors).length === 0){
            alert("Enviando formulario");
            setLoading(true);
            helpHttp().post("https://formsubmit.co/diegofernandez_001@hotmail.com",{
                body: form,
                headers:{
                    "Content-Type":"application/json",
                    "Accept":"application/json"
                }
            }).then(res=>{
                setLoading(false);
                setResponse(true);
                setForm(initialForm);
                setTimeout(()=> setResponse(false),5000)
            })
        }else{
            return;
        }
    };

    return{form,errors,loading,response,handleChange,handleBlur,handleSubmit}
};

```

## Ventana Modal
### La prop children de los componentes ( 1 / 3 )
- `Modals.js`:
```js
import React from 'react'
import Modal from './Modal';

const Modals = () => {
    return (
        <div>
            <h2>Modales</h2>
            <button>Modal 1</button>
            <Modal>
                <h3>Modal 1</h3>
            </Modal>
        </div>
    )
}

export default Modals;
```

- `Modal.js`:
```js
const Modal = ({children}) => {
    //la propiedad children hace referencia al contendio dentro de la etiqueta, no es necesario pasarlo como una propiedad definida
    return (
        <article className="modal is-open">
            <div className="modal-container">
                <button class="modal-close">X</button>
                {children}
            </div>
        </article>
    )
}

export default Modal;
```

### Estilos y lógica del componente ( 2 / 3 )
- `Modals.js`:
```js
import React from 'react'
import { useModal } from '../hooks/useModal';
import Modal from './Modal';


const Modals = () => {
    const [isOpenModal1, openModal1,closeModal1] = useModal(false);
    const [isOpenModal2, openModal2,closeModal2] = useModal(false);


    return (
        <div>
            <h2>Modales</h2>
            <button>Modal 1</button>
            <Modal>
                <h3>Modal 1</h3>
            </Modal>
        </div>
    )
}

export default Modals;

```

- `Modal.css`:
```css
.modal {
    position: fixed;
    z-index: 999;
    top: 0;
    left: 0;
    width: 100%;
    min-height: 100vh;
    background-color: rgba(0,0,0,0.75);
    display:none;
    justify-content: center;
    align-items: center;
}

.modal.is-open {
    display: flex;
}

.modal-container {
    position: relative;
    padding:1rem;
    min-width: 320px;
    max-width: 480px;
    min-height: 200px;
    max-height: 600px;
    overflow-y: auto;
    background-color: #fff;
}

.modal-close{
    position: absolute;
    top: 1rem;
    right: 1rem;
}
```
- `useModal.js`:
```js
import { useState } from 'react';

export const useModal = (initialValue = false) => {
    const [isOpen, setIsOpen] = useState(initialValue);

    const openModal = () => setIsOpen(true);
    const closeModal = () => setIsOpen(false);

    // como vamos a tener varios modales la funcionalidad la crearemos en un hook para que podamos reutilizarla para los diferentes modales
    //de igual forma el return regresa un array para que podamos cambiar el nombre y adecuarlos al modal que queramos
    return [isOpen,openModal,closeModal]
}
```

### Funcionalidad y reutilización del componente ( 3 / 3 )

- `Modals.js`:
```js
import React from 'react'
import { useModal } from '../hooks/useModal';
import Modal from './Modal';


const Modals = () => {
    const [isOpenModal1, openModal1,closeModal1] = useModal(false);
    const [isOpenModal2, openModal2,closeModal2] = useModal(false);


    return (
        <div>
            <h2>Modales</h2>
            <button onClick={openModal1}>Modal 1</button>
            <Modal isOpen={isOpenModal1} closeModal={closeModal1}>
                <h3>Modal 1</h3>
            </Modal>
            <button onClick={openModal2}>Modal 2</button>
            <Modal isOpen={isOpenModal2} closeModal={closeModal2}>
                <h3>Modal 2</h3>
            </Modal>
        </div>
    )
}

export default Modals;

```

- `Modal.js`:
```js
import "./Modal.css";

const Modal = ({children, isOpen,closeModal}) => {
    // crearemos una funcion para que el efecto de closeModal no se propage al hijo por que si le damos click al hijo tambien se va a cerrar el modal aun que el efecto closeModal solamente lo tenga el padre
    const handleModalContainerClick =  e => e.stopPropagation();
    return (
        <article className={`modal ${isOpen && "is-open"}`} onClick={closeModal}>
            <div className="modal-container" onClick={handleModalContainerClick}>
                <button class="modal-close" onClick={closeModal}>X</button>
                {children}
            </div>
        </article>
    )
}

export default Modal;

```

## [Portales](https://es.reactjs.org/docs/portals.html)
- `Modals.js`:
```js
import React from 'react'
import { useModal } from '../hooks/useModal';
import Modal from './Modal';
import ModalPortal from './ModalPortal';


const Modals = () => {
    const [isOpenModal1, openModal1,closeModal1] = useModal(false);
    const [isOpenModal2, openModal2,closeModal2] = useModal(false);
    const [isOpenPortal, openModalPortal,closeModalPortal] = useModal(false);



    return (
        <div>
            <h2>Modales</h2>
            <button onClick={openModal1}>Modal 1</button>
            <Modal isOpen={isOpenModal1} closeModal={closeModal1}>
                <h3>Modal 1</h3>
            </Modal>
            <button onClick={openModal2}>Modal 2</button>
            <Modal isOpen={isOpenModal2} closeModal={closeModal2}>
                <h3>Modal 2</h3>
            </Modal>
            {/*Este boton va a funcionar para el ejemplo de los portales: */}
            <button onClick={openModalPortal}>Modal 2</button>
            <ModalPortal isOpen={isOpenPortal} closeModal={closeModalPortal}>
                <h3>Modal en Portal</h3>
                <p>Este es el contenido de un modal que carga en otro nodo del DOM diferente  a donde carga nuestra app de React, gracias a un React Portal</p>
            </ModalPortal>
        </div>
    )
}

export default Modals;

```

El portal:
- `ModalPortal.js`:
```js
import ReactDOM from "react-dom";
import "./Modal.css";

const ModalPortal = ({children, isOpen,closeModal}) => {
    // crearemos una funcion para que el efecto de closeModal no se propage al hijo por que si le damos click al hijo tambien se va a cerrar el modal aun que el efecto closeModal solamente lo tenga el padre
    const handleModalContainerClick =  e => e.stopPropagation();
    //ReactDOM.createPortal recirbe las etiquetas y el selector donde se quiere cargar
    // lo que hace un portal en react es inyectar el contenido de ese componente en otro nodo que exista en el arbol del dom
    return ReactDOM.createPortal(
        <article className={`modal ${isOpen && "is-open"}`} onClick={closeModal}>
            <div className="modal-container" onClick={handleModalContainerClick}>
                <button className="modal-close" onClick={closeModal}>X</button>
                {children}
            </div>
        </article>,
        document.getElementById("modal")
    )
}

export default ModalPortal;
```

## [React Router](https://v5.reactrouter.com/web/guides/quick-start)
functiona para react para aplicaciones web y para react nativ
```
npm install react-router-dom
```

### Introducción y definición de rutas
```js
import { BrowserRouter as Router, Route} from "react-router-dom"

const ConceptosBasicos = () => {
    return (
        <div>
            <h2>Conceptos Basicos</h2>
            {/*El component padre para react-router se llama BrowserRouter y se estararizo el darle el alias de Router*/}
            <Router>
                {/*Para poder definir una ruta tenemos que usar el componente Route */}
                <Route path="/">
                {/*Las rutas son componentes que reciben ciertas propiedades */}
                {/*La propiedad mas importante que recibe Rote es path la cual es la ruta relativa de la url que se va a cargar */}
                {/*path lo que hace es encontrar la ruta que coinsida con la barra de direcion de la url */}
                <h3>Home</h3>
                </Route>
                <Route path="/acerca">
                <h3>Acerca </h3>
                </Route>
            </Router>
        </div>
    )
}

export default ConceptosBasicos
```
```js
import { BrowserRouter as Router, Route, Switch} from "react-router-dom"

const ConceptosBasicos = () => {
    return (
        <div>
            <h2>Conceptos Basicos</h2>
          
            <Router>
                {/*Si queremos que solante carge una ruta(la que tiene en coincidencia) entonces vamos a usar un switch */}
                <Switch>
                    <Route path="/acerca">
                    <h3>Acerca </h3>
                    </Route>
                    {/*En este caso ponemos el ROute de home hasta el ultimo por que si en el navegador entramos a : localhost:3000/acerca como en su path tiene la diagonal entonces lo reconoce como correcto y ese es el que muestra y no el segundo Route con el path /acerca */}
                    {/*ES por esta razon que el la documentacion recomiendan que primero vayan las rutas con el path mas especifico y hasta abajo las rutas con el path mas generico */}
                    <Route path="/">
                    <h3>Home</h3>
                    </Route>
                </Switch>
            </Router>
        </div>
    )
}

export default ConceptosBasicos
```
```js
import { BrowserRouter as Router, Route, Switch} from "react-router-dom"

const ConceptosBasicos = () => {
    return (
        <div>
            <h2>Conceptos Basicos</h2>
          
            <Router>
                <Switch>
                {/*SI nosotros no queremos ordenar desde lo mas especifico a lo mas generico podemos usar un atributo booleano  que podemos agregar a las rutas que se llama escat */}
                {/*Cuando se agrega este atributo entonces solamente moestrara las ruta con el path de manera exacta que aparesca en el navegador */}
                    <Route exact path="/">
                    <h3>Home</h3>
                    </Route>
                    <Route exact path="/acerca">
                    <h3>Acerca </h3>
                    </Route>
                </Switch>
            </Router>
        </div>
    )
}

export default ConceptosBasicos
```
### Sintaxis para declarar rutas
Algunos desarroladores lo que hacen es crear una carpeta unicamente para las rutas la cual se puede nombrar como `pages`.
```js
import { BrowserRouter as Router, Route, Switch} from "react-router-dom"
import Acerca from "../pages/Acerca"
import Contacto from "../pages/Contacto"

const ConceptosBasicos = () => {
    return (
        <div>
            <h2>Conceptos Basicos</h2>
          
            <Router>
                <Switch>
                    <Route exact path="/">
                        <h3>Home</h3>
                    </Route>
                    <Route exact path="/acerca">
                        <Acerca/>
                    </Route>
                    {/*Si a una ruta solamente se le va a pasar un componente donde ya venga todo el codigo podemos usar rutas de una linea usando el atributo component y asignarle el nombre del componente que tiene el contenido */}
                    {/*tambien podemos usar la propiedad children pero en lugar de solo asignarle "Contacto" vamos a asignarle el componente completo:
                    <Contacto/> */}
                    <Route exact path="/contacto" component={Contacto}/>         
                </Switch>
            </Router>
        </div>
    )
}

export default ConceptosBasicos
```

Esto se puede usar para solamente declarar los header y footer una sola vez y que el contenido sea el que cambie.

### Ruta de Error 404
- `Error404.js`:
```js
const Error404 = () => {
    return (
        <div>
            <h3>Error 404</h3>
            <p>Not Found</p>
        </div>
    )
}

export default Error404

```
- `ConceptosBasicos.js`:
```js
import { BrowserRouter as Router, Route, Switch} from "react-router-dom"
import Acerca from "../pages/Acerca"
import Contacto from "../pages/Contacto"
import Error404 from "../pages/Error404"
import Home from "../pages/Home"

const ConceptosBasicos = () => {
    return (
        <div>
            <h2>Conceptos Basicos</h2>
            <Router>
                <Switch>
                    <Route exact path="/" component={Home}/>
                    <Route exact path="/acerca" component={Acerca}/>
                    <Route exact path="/contacto" component={Contacto}/>
                    {/*Para la ruta del error 404 no necesitamos el exact en su lugar vamos a poner un asterisco * , el cual es un comodin para indicar "lo que sea", otro requisito es que la ruta del error404 este posicionada hasta el ultimo para que no haya problemas de jerarquias*/}
                    <Route path="*" component={Error404}/>     
                </Switch>
            </Router>
        </div>
    )
}

export default ConceptosBasicos;

```

###  Componentes Link y NavLink
**Link**
- `MenuConceptos.js`:
```js
import { Link } from "react-router-dom";

const MenuConceptos = () => {
    return (
        <nav>
            <ol>
                <li>
                    <span>Menu con enlaces html(no recomentado)</span>
                    {/*No se recomienda hacer un menu de esta manera por que nos generan un renderizado de toda la aplicacion */}
                    <a href="/">Home</a>
                    <a href="/acerca">Acerca</a>
                    <a href="/contacto">Contacto</a>
                </li>
                <li>
                    <span>Componente Link:</span>
                    {/*En el component Link en lugar de poner href el atributo se llama "to" */}
                    {/*Como vamos a trabajar con componentes de react-router-dom entonces el componente tiene que estar dentro de componente Router y muy importante, tiene que estar fuera del Switch */}
                    <Link to="/">Home</Link>
                    <Link to="/acerca">Acerca</Link>
                    <Link to="/contacto">Contacto</Link>
                </li>
            </ol>
        </nav>
    )
}

export default MenuConceptos;
```

- `ConceptosBasicos.js`:
```js
import { BrowserRouter as Router, Route, Switch} from "react-router-dom"
import Acerca from "../pages/Acerca"
import Contacto from "../pages/Contacto"
import Error404 from "../pages/Error404"
import Home from "../pages/Home"
import MenuConceptos from "./MenuConceptos"

const ConceptosBasicos = () => {
    return (
        <div>
            <h2>Conceptos Basicos</h2>
            <Router>
            <MenuConceptos/>
                <Switch>
                    <Route exact path="/" component={Home}/>
                    <Route exact path="/acerca" component={Acerca}/>
                    <Route exact path="/contacto" component={Contacto}/>
                    <Route path="*" component={Error404}/>     
                </Switch>
            </Router>
        </div>
    )
}

export default ConceptosBasicos;

```

**NavLink**:
- `MenuConceptos.js`:
```js
import { Link, NavLink } from "react-router-dom";

const MenuConceptos = () => {
    return (
        <nav>
            <ol>
                <li>
                    <span>Menu con enlaces html(no recomentado)</span>
                    
                    <a href="/">Home</a>
                    <a href="/acerca">Acerca</a>
                    <a href="/contacto">Contacto</a>
                </li>
                <li>
                    <span>Componente Link:</span>
                    <Link to="/">Home</Link>
                    <Link to="/acerca">Acerca</Link>
                    <Link to="/contacto">Contacto</Link>
                </li>
                <li>
                    <span>Componente NavLink:</span>
                    {/*NavLink se comporta exactamente igual que Link, pero NavLink puede usar una propiedad que se llama activeClassName */}{/*a activeClassName le podemos asignar una propiedad de css para que se lo ponga al enlace y agregandole el atributo exact hara que cuando este en la ruta del NavLink se asigne el estilo*/}
                    <NavLink exact to="/" activeClassName="active">Home</NavLink>
                    <NavLink exact to="/acerca" activeClassName="active">Acerca</NavLink>
                    <NavLink exact to="/contacto" activeClassName="active">Contacto</NavLink>
                </li>
            </ol>
        </nav>
    )
}

export default MenuConceptos;

```

###  Paso de Parámetros (hook useParams)
- `Usuario.js`:
```js
import { useParams } from "react-router";

const Usuario = () => {
    let {username} = useParams();
    return (
        <div>
            <h3>Perfil del usuario</h3>
            <p>Nombre de usuario <b>{username}</b></p>
        </div>
    )
}

export default Usuario;
```
- `ConceptosBasicos.js`:
```js
import { BrowserRouter as Router, Route, Switch} from "react-router-dom"
import Acerca from "../pages/Acerca"
import Contacto from "../pages/Contacto"
import Error404 from "../pages/Error404"
import Home from "../pages/Home"
import Usuario from "../pages/Usuario"
import MenuConceptos from "./MenuConceptos"

const ConceptosBasicos = () => {
    return (
        <div>
            <h2>Conceptos Basicos</h2>
            <Router>
            <MenuConceptos/>
                <Switch>
                    <Route exact path="/" component={Home}/>
                    <Route exact path="/acerca" component={Acerca}/>
                    <Route exact path="/contacto" component={Contacto}/>
                    {/*Para utilizar dinamicamente en el atributo path un parametros, nosotros hay que anteponerle dos puntos ":" */}
                    <Route exact path="/usuario/:username" component={Usuario}/>
                    <Route path="*" component={Error404}/>     
                </Switch>
            </Router>
        </div>
    )
}

export default ConceptosBasicos;
```
- `MenuConceptos.js`:
```js
import { Link, NavLink } from "react-router-dom";

const MenuConceptos = () => {
    return (
        <nav>
            <ol>
                <li>
                    <span>Menu con enlaces html(no recomentado)</span>
                    
                    <a href="/">Home</a>
                    <a href="/acerca">Acerca</a>
                    <a href="/contacto">Contacto</a>
                </li>
                <li>
                    <span>Componente Link:</span>
                    <Link to="/">Home</Link>
                    <Link to="/acerca">Acerca</Link>
                    <Link to="/contacto">Contacto</Link>
                </li>
                <li>
                    <span>Componente NavLink:</span>
                    <NavLink exact to="/" activeClassName="active">Home</NavLink>
                    <NavLink exact to="/acerca" activeClassName="active">Acerca</NavLink>
                    <NavLink exact to="/contacto" activeClassName="active">Contacto</NavLink>
                </li>
                <li>
                    <span>Parametros:</span>
                    <Link to="/usuario/jon" >jon</Link>
                    <Link to="/usuario/diego" >diego</Link>
                </li>
            </ol>
        </nav>
    )
}

export default MenuConceptos;
```

### Parámetros de consulta (hooks useLocation y useHistory) 

- `Productos.js`:
```js
import { useLocation ,useHistory} from "react-router";

//en la url del navegador le tenemos que agregar :
// ?inicio=1&fin=20
const Productos = () => {
    const LIMIT = 20; //el limite de la pagina
    //vamos a usar useLocation para obtener lo parametros de consulta
    //let location = useLocation();
    //el objeto tiene la propiedad llamada "search" que es de donde podemos obtener el paso de variables
    let {search} = useLocation();
    let query = new URLSearchParams(search);//lo que hace es serialisar los parametros

    let start = parseInt(query.get("inicio")) || 1;  // 1
    let end = parseInt(query.get("fin")) || LIMIT; // 20

    let history = useHistory();

    const handlePrev = (e) => {
        history.push({search:`?inicio=${start - LIMIT}&fin=${end - LIMIT}`})
    };
    const handleNext = (e) => {
        //con el metodo push podemos modificar los searchParams
        history.push({search:`?inicio=${start + LIMIT}&fin=${end + LIMIT}`})
    };

    return (
        <div>
            <h3>Productos</h3>
            <p>Mostrando productos del <b>{start}</b>al<b>{end}</b></p>
            {start > LIMIT && <botton onClick={handlePrev}>atras</botton>}
            <botton onClick={handleNext}>adelante</botton>
        </div>
    )
}

export default Productos;
```
- `MenuConceptos.js`:
```js
import { Link, NavLink } from "react-router-dom";

const MenuConceptos = () => {
    return (
        <nav>
            <ol>
                <li>
                    <span>Menu con enlaces html(no recomentado)</span>
                    
                    <a href="/">Home</a>
                    <a href="/acerca">Acerca</a>
                    <a href="/contacto">Contacto</a>
                </li>
                <li>
                    <span>Componente Link:</span>
                    <Link to="/">Home</Link>
                    <Link to="/acerca">Acerca</Link>
                    <Link to="/contacto">Contacto</Link>
                </li>
                <li>
                    <span>Componente NavLink:</span>
                    <NavLink exact to="/" activeClassName="active">Home</NavLink>
                    <NavLink exact to="/acerca" activeClassName="active">Acerca</NavLink>
                    <NavLink exact to="/contacto" activeClassName="active">Contacto</NavLink>
                </li>
                <li>
                    <span>Parametros:</span>
                    <Link to="/usuario/jon" >jon</Link>
                    <Link to="/usuario/diego" >diego</Link>
                </li>
                <li>
                    <span>Parametros de consulta:</span>
                    <Link to="/productos"></Link>
                </li>
            </ol>
        </nav>
    )
}

export default MenuConceptos;
```
- `ConceptosBasicos.js`:
```js
import { BrowserRouter as Router, Route, Switch} from "react-router-dom"
import Acerca from "../pages/Acerca"
import Contacto from "../pages/Contacto"
import Error404 from "../pages/Error404"
import Home from "../pages/Home"
import Productos from "../pages/Productos"
import Usuario from "../pages/Usuario"
import MenuConceptos from "./MenuConceptos"

const ConceptosBasicos = () => {
    return (
        <div>
            <h2>Conceptos Basicos</h2>
            <Router>
            <MenuConceptos/>
                <Switch>
                    <Route exact path="/" component={Home}/>
                    <Route exact path="/acerca" component={Acerca}/>
                    <Route exact path="/contacto" component={Contacto}/>
                    <Route exact path="/usuario/:username" component={Usuario}/>
                    <Route exact path="/productos" component={Productos}/>
                    <Route path="*" component={Error404}/>     
                </Switch>
            </Router>
        </div>
    )
}

export default ConceptosBasicos;

```

### Redirecciones
Las redirecciones son importantes por ejemplo a la hora de que sea necesario que el usuario tenga que autenticarse para poder acceder a cierto contenido especifico o privado.

- `MenuCOnceptos.js`:
```js
import { Link, NavLink } from "react-router-dom";

const MenuConceptos = () => {
    return (
        <nav>
            <ol>
                <li>
                    <span>Menu con enlaces html(no recomentado)</span>
                    
                    <a href="/">Home</a>
                    <a href="/acerca">Acerca</a>
                    <a href="/contacto">Contacto</a>
                </li>
                <li>
                    <span>Componente Link:</span>
                    <Link to="/">Home</Link>
                    <Link to="/acerca">Acerca</Link>
                    <Link to="/contacto">Contacto</Link>
                </li>
                <li>
                    <span>Componente NavLink:</span>
                    <NavLink exact to="/" activeClassName="active">Home</NavLink>
                    <NavLink exact to="/acerca" activeClassName="active">Acerca</NavLink>
                    <NavLink exact to="/contacto" activeClassName="active">Contacto</NavLink>
                </li>
                <li>
                    <span>Parametros:</span>
                    <Link to="/usuario/jon" >jon</Link>
                    <Link to="/usuario/diego" >diego</Link>
                </li>
                <li>
                    <span>Parametros de consulta:</span>
                    <Link to="/productos"></Link>
                </li>
                <li>
                    <span>Redirecciones:</span>
                    <Link to="/about">About</Link>
                    <Link to="/contact">Contact</Link>
                </li>
            </ol>
        </nav>
    )
}

export default MenuConceptos;
```

- `ConceptosBasicos.js`:
```js
import { BrowserRouter as Router, Route, Switch,Redirect} from "react-router-dom"
import Acerca from "../pages/Acerca"
import Contacto from "../pages/Contacto"
import Error404 from "../pages/Error404"
import Home from "../pages/Home"
import Productos from "../pages/Productos"
import Usuario from "../pages/Usuario"
import MenuConceptos from "./MenuConceptos"

const ConceptosBasicos = () => {
    return (
        <div>
            <h2>Conceptos Basicos</h2>
            <Router>
            <MenuConceptos/>
                <Switch>
                    <Route exact path="/" component={Home}/>
                    <Route exact path="/acerca" component={Acerca}/>
                    <Route exact path="/contacto" component={Contacto}/>
                    <Route exact path="/usuario/:username" component={Usuario}/>
                    <Route exact path="/productos" component={Productos}/>
                    <Route exact path="/about">
                        {/*Para hacer una redireccion usamos el componente Redirect */}
                        <Redirect to="/acerca"/>
                    </Route>
                    <Route exact path="/contact">
                        <Redirect to="/contacto"/>
                    </Route>
                    <Route path="*" component={Error404}/>     
                </Switch>
            </Router>
        </div>
    )
}

export default ConceptosBasicos;

```

### Rutas anidadas (hook useRouteMatch)
- `ReactTopics.js`:
```js
import { Link ,Switch,Route,useRouteMatch,useParams} from "react-router-dom";

const Topic = () => {
    let {topic} = useParams();
    return(
        <div>
            <h4>{topic}</h4>
        </div>
    )
};

const ReactTopics = () => {
    //let match = useRouteMatch();
    // "path" nos permite construir rutas relativas <Route>
    // miestras que "url" nos permite construir enlaces relativos <Link> o <NavLink>

    let {path,url} = useRouteMatch();
    return (
        <div>
            <h3>Temas de React</h3>
            <ul>
                <li><Link to={`${url}/jsx`}>JSX</Link></li>
                <li><Link to={`${url}/props`}>Props</Link></li>
                <li><Link to={`${url}/estado`}>Estado</Link></li>
                <li><Link to={`${url}/componentes`}>Componente</Link></li>
            </ul>
            <Switch>
                <Route exact path={path}/>
                {/*Como vamos a crear rutas dinamicas no vamos a usar el atributo exact */}
                <Route path={`${path}/:topic`} component={Topic}/>

            </Switch>
        </div>
    )
}

export default ReactTopics;
```
- `ConceptosBasicos.js`:
```js
import { BrowserRouter as Router, Route, Switch,Redirect} from "react-router-dom"
import Acerca from "../pages/Acerca"
import Contacto from "../pages/Contacto"
import Error404 from "../pages/Error404"
import Home from "../pages/Home"
import Productos from "../pages/Productos"
import ReactTopics from "../pages/ReactTopics"
import Usuario from "../pages/Usuario"
import MenuConceptos from "./MenuConceptos"

const ConceptosBasicos = () => {
    return (
        <div>
            <h2>Conceptos Basicos</h2>
            <Router>
            <MenuConceptos/>
                <Switch>
                    <Route exact path="/" component={Home}/>
                    <Route exact path="/acerca" component={Acerca}/>
                    <Route exact path="/contacto" component={Contacto}/>
                    <Route exact path="/usuario/:username" component={Usuario}/>
                    <Route exact path="/productos" component={Productos}/>
                    <Route exact path="/about">
                        {/*Para hacer una redireccion usamos el componente Redirect */}
                        <Redirect to="/acerca"/>
                    </Route>
                    <Route exact path="/contact">
                        <Redirect to="/contacto"/>
                    </Route>
                    {/*Para evitar errores en esta ocacion vamos a usar subrutas y no es recomendable usar el exact: */}
                    <Route path="react" component={ReactTopics}/>
                    <Route path="*" component={Error404}/>     
                </Switch>
            </Router>
        </div>
    )
}

export default ConceptosBasicos;
```
- `MenuConceptos.js`:
```js
import { Link, NavLink } from "react-router-dom";

const MenuConceptos = () => {
    return (
        <nav>
            <ol>
                <li>
                    <span>Menu con enlaces html(no recomentado)</span>
                    
                    <a href="/">Home</a>
                    <a href="/acerca">Acerca</a>
                    <a href="/contacto">Contacto</a>
                </li>
                <li>
                    <span>Componente Link:</span>
                    <Link to="/">Home</Link>
                    <Link to="/acerca">Acerca</Link>
                    <Link to="/contacto">Contacto</Link>
                </li>
                <li>
                    <span>Componente NavLink:</span>
                    <NavLink exact to="/" activeClassName="active">Home</NavLink>
                    <NavLink exact to="/acerca" activeClassName="active">Acerca</NavLink>
                    <NavLink exact to="/contacto" activeClassName="active">Contacto</NavLink>
                </li>
                <li>
                    <span>Parametros:</span>
                    <Link to="/usuario/jon" >jon</Link>
                    <Link to="/usuario/diego" >diego</Link>
                </li>
                <li>
                    <span>Parametros de consulta:</span>
                    <Link to="/productos"></Link>
                </li>
                <li>
                    <span>Redirecciones:</span>
                    <Link to="/about">About</Link>
                    <Link to="/contact">Contact</Link>
                </li>
                <li>
                    <span>Runtas Anidadas</span>
                    <Link to="/react">React</Link>
                </li>
            </ol>
        </nav>
    )
}

export default MenuConceptos;

```

### Rutas privadas

Hasta el momento no hay un **componente** privado de react-router que nos haga el trabajo de hacer esto, pero lo podemos contruir por nosotros mismos.

- `PrivateRoute.js`:
```js
import { Route,Redirect } from "react-router";

/*const PrivateRoute = (props) => {
    return (
            <Route exact={props.exact} path={props.path} component={props.component}/>
    )
}*/
/* En lugar de pasar sus propiedades una por una lo podemos hacer de manera conjunta:*/

/*const PrivateRoute = (props) => {
    return (
            <Route {...props}/>
    )
}*/

//simular la Autenticacion
let auth;
auth=true;

/*EN este caso queremos hacer una simulacion de autenticacion asi que vamos a destructurar las propiedades en dos:
- componentes
- el resto de propiedades*/
//tambien le crearemos un alias a la propiedad "component" para que cumpla con la regla de que los componentes tienen que iniciar con una letra en mayuscula, si no hacemos esto puede generar errores de no renderizado
const PrivateRoute = ({component: Component,...rest}) => {
    return (
            <Route {...rest}>{auth? <Component/> : <Redirect to="/login"/>}</Route>
    )
};
//de esta forma aun que sepamos la ruta de dashboard si no estamos auteticados nos redireccionara a login

export default PrivateRoute;
```

- `MenuConceptos.js`:
```js
import { Link, NavLink } from "react-router-dom";

const MenuConceptos = () => {
    return (
        <nav>
            <ol>
                <li>
                    <span>Menu con enlaces html(no recomentado)</span>
                    
                    <a href="/">Home</a>
                    <a href="/acerca">Acerca</a>
                    <a href="/contacto">Contacto</a>
                </li>
                <li>
                    <span>Componente Link:</span>
                    <Link to="/">Home</Link>
                    <Link to="/acerca">Acerca</Link>
                    <Link to="/contacto">Contacto</Link>
                </li>
                <li>
                    <span>Componente NavLink:</span>
                    <NavLink exact to="/" activeClassName="active">Home</NavLink>
                    <NavLink exact to="/acerca" activeClassName="active">Acerca</NavLink>
                    <NavLink exact to="/contacto" activeClassName="active">Contacto</NavLink>
                </li>
                <li>
                    <span>Parametros:</span>
                    <Link to="/usuario/jon" >jon</Link>
                    <Link to="/usuario/diego" >diego</Link>
                </li>
                <li>
                    <span>Parametros de consulta:</span>
                    <Link to="/productos"></Link>
                </li>
                <li>
                    <span>Redirecciones:</span>
                    <Link to="/about">About</Link>
                    <Link to="/contact">Contact</Link>
                </li>
                <li>
                    <span>Runtas Anidadas</span>
                    <Link to="/react">React</Link>
                </li>
                <li>
                    <span>Runtas Privadas</span>
                    <Link to="Login">Login</Link>
                    <Link to="/dashboard">Dashboard</Link>
                </li>
            </ol>
        </nav>
    )
}

export default MenuConceptos;

```

- `Conceptos.js`
```js
import { BrowserRouter as Router, Route, Switch,Redirect} from "react-router-dom"
import Acerca from "../pages/Acerca"
import Contacto from "../pages/Contacto"
import Dashboard from "../pages/Dashboard"
import Error404 from "../pages/Error404"
import Home from "../pages/Home"
import Login from "../pages/Login"
import Productos from "../pages/Productos"
import ReactTopics from "../pages/ReactTopics"
import Usuario from "../pages/Usuario"
import MenuConceptos from "./MenuConceptos"
import PrivateRoute from "./PrivateRoute"

const ConceptosBasicos = () => {
    return (
        <div>
            <h2>Conceptos Basicos</h2>
            <Router>
            <MenuConceptos/>
                <Switch>
                    <Route exact path="/" component={Home}/>
                    <Route exact path="/acerca" component={Acerca}/>
                    <Route exact path="/contacto" component={Contacto}/>
                    <Route exact path="/usuario/:username" component={Usuario}/>
                    <Route exact path="/productos" component={Productos}/>
                    <Route exact path="/about">
                        <Redirect to="/acerca"/>
                    </Route>
                    <Route exact path="/contact">
                        <Redirect to="/contacto"/>
                    </Route>
                    <Route path="react" component={ReactTopics}/>
                    <Route exact path="/login" component={Login}/>
                    {/*Creamos un componente que funcione para rutas privadas */}
                    <PrivateRoute exact path="/dashboard" component={Dashboard}/>
                    <Route path="*" component={Error404}/>     
                </Switch>
            </Router>
        </div>
    )
}

export default ConceptosBasicos;
```

- `Login.js`:

```js
const Login = () => {
    return (
        <div>
            <h3>Login</h3>
        </div>
    )
}

export default Login;

```

- `DashBoard.js`:

```js
const Dashboard = () => {
    return (
        <div>
            <h3>Dashboard</h3>
        </div>
    )
}

export default Dashboard;

```
###  El problema de las rutas en producción 

La libreria react-router lo que hace es hacer un condicionar render , ya de dependiendo en la ruta que estemos muestra un contendio u otro.

El problema es que si no se tiene una estrategia del lado del servidor que permite desplegar informacion cuando el usuario acceda a una ruta en particular en la aplicacion, react-router lo unico que va a hacer a nivel de fronent es hacer el condicionar render.

Pero en el momento que escribimos manualmente la ruta en el navegador podemos tener errores como: `Cannot Get /react/`.

**por que pasa esto?**
Recordemos que lo unico que hace react router es ser una libreria que nos permite manupular (fingir que estamos cambiando las rutas)  y hacer un condicional render del contendio que queramos mostrar dependiendo de una ruta u otra, si no se tiene una estrategia del lado del servidor que cuando se solucite esta ruta de manera manual aparezca un html, pues va ocurrie el error antes moestrado.

Si solamente dejas las estrategias del manejo de rutas del manejo de rutas a react-router, cuando desplieges la aplicacion, **si el usuario no consume tu aplicacion desde el home**, y empieza a tratar de ingresar directamente por medio de la ruta van a ocurri errores 404.

### HashRouter 

Cuando estamos usando `#` internamente en el archivo html es como si estuviera buscando un id, pero al momento en que le ponemos un `#` a la url significa que lo que sigue de la url puede ser que estemos buscando un id o le estemos pasando otra cosa.

`http://localhost:3000/usuario/jonmircha`
- `usuario`: en la parte de usuario debe haber un recurso que acceda a una carpeta o a un recurso que este soportando al usuario.

Lo que hace la tecnica del hash `#` con el manejo de las rutas en react-router es que va a hacer esto:
`http://localhost:3000/#/usuario/jonmircha`
-`#`: cuando la ruta detecta un hash en la url el sabe que aqui no cambiamso de archivo o de recurso, seguimos en el html del home y que lo que sigue del hash puede ser un id dentro del html o cualquier otra cosa que estemos utilizando  

- `ConceptosBasicos.js`:
```js
import { BrowserRouter as Router, Route, Switch,Redirect, HashRouter, Link} from "react-router-dom"
import Acerca from "../pages/Acerca"
import Contacto from "../pages/Contacto"
import Dashboard from "../pages/Dashboard"
import Error404 from "../pages/Error404"
import Home from "../pages/Home"
import Login from "../pages/Login"
import Productos from "../pages/Productos"
import ReactTopics from "../pages/ReactTopics"
import Usuario from "../pages/Usuario"
import MenuConceptos from "./MenuConceptos"
import PrivateRoute from "./PrivateRoute"

const ConceptosBasicos = () => {
    return (
        <div>
            <h2>Hash Router</h2>
            {/*En lugar de utilizar BrowserRouter vamos a utilizar HashRouter */}
            <HashRouter>
            <nav>
            {/*Como ya esta dento de un HashRouter automaticamente pondra el `#` en la url */}
                <Link to="/home">Home</Link>
                <Link to="/acerca">Acerca</Link>
                <Link to="/contacto">Contacto</Link>
            </nav>
            </HashRouter>
            <Switch>
                <Route exact path="/" component={Home}/>
                <Route exact path="/acerca" component={Acerca}/>
                <Route exact path="/contacto" component={Contacto}/>
            </Switch>
            <hr/>
            <h2>Conceptos Basicos</h2>
            <Router>
            <MenuConceptos/>
                <Switch>
                    <Route exact path="/" component={Home}/>
                    <Route exact path="/acerca" component={Acerca}/>
                    <Route exact path="/contacto" component={Contacto}/>
                    <Route exact path="/usuario/:username" component={Usuario}/>
                    <Route exact path="/productos" component={Productos}/>
                    <Route exact path="/about">
                        <Redirect to="/acerca"/>
                    </Route>
                    <Route exact path="/contact">
                        <Redirect to="/contacto"/>
                    </Route>
                    <Route path="react" component={ReactTopics}/>
                    <Route exact path="/login" component={Login}/>
                    <PrivateRoute exact path="/dashboard" component={Dashboard}/>
                    <Route path="*" component={Error404}/>     
                </Switch>
            </Router>
        </div>
    )
}

export default ConceptosBasicos;

```

ESta tecnica de de utilizar los HashRouter van a servir mucho cuando no se tenga una estrategia del lado de backend.

## Memorización ( [memo](https://es.reactjs.org/docs/react-api.html#reactmemo) ) 
Hay que tomar con cautela el proceso de la memorizacion, el proceso de memorizacion consiste en cachear componentes y funciones para cuando se este renderizando un componente por el paso de propiedades o por el cambio de su estado, pero que internamente tenga otros componentes que no se modificaron, que esos componentes como tal permanezcan en cache y no se vuelva a renderizar.

Para memorizar un componente o una funcion en react, internamente la libreria utiliza un proceso de comparacion que muchas veces puede ser mas costoso que el renderizado del componente que tratamos de evitar renderizar, por esta razon hay que utilizarlo con mucha cautela.

- `App.js`:
```js
import './App.css';
import Contador from './components/Contador';

function App() {
  return (
    <div>
    <h1>Memorizacion en React</h1>
    <hr/>
    <Contador/>
    </div>
  );
}

export default App;
```
- `Contador.js`:
```js
import { useState } from "react";
import ContadorHijo from "./ContadorHijo";

const Contador = () => {
    const [contador, setContador] = useState(0);

    const sumar = () =>setContador(contador + 1);
    const restar = () =>setContador(contador - 1);


    return (
        <div style={{textAlign: "center"}}>
            <h2>COntador</h2>
            <nav>
                <button onclick={sumar}>+</button>
                <button onclick={restar}>-</button>
            </nav>
            <h3>{contador}</h3>
            {/*Cada vez que actualizamos la variable del contador padre el hijo tambien se renderiza completo*/}
            <ContadorHijo/>
        </div>
    )
}

export default Contador;
```
- `ContadorHijo.js`:
```js
const ContadorHijo = () => {
    console.log("Contador hijo se renderiza")
    return (
        <div style={{border:"thin solid #000", margin:"1rem", padding:"1rem"}}>
            <h2>Hijo del Contador</h2>
        </div>
    )
}

export default ContadorHijo;
```
Otro ejemplo seria un boton que cambia de tema claro a tema oscuro del la interfaz y en el momento se que le de click a ese boton se tenga que renderizar un componente hijo que este haciando una llamda hacia una api que se este trayendo muchos registros y que los piente en una UI, estos proceso de renderizado podrian ser muy costosos.

En estos casos lo que nos podria convenir es memorizar con la funcion react-memo el componente hijo, detal manera que si el el componente hijo no sufre ningun cambio, aun que la variable del estado del componente padre se este renderizando ya no tendrimos esta clase de problemas de renderizado costosos y entonces el componente va a permanecer memorizado y hasta que el componente internamente cambien es cuando se va a volver a renderizar, en ese sentido estariamos optimizando el rendimiento de nuestra aplicacion.

- `COntadorHijo.js`:
```js
import {memo} from 'react';  

const ContadorHijo = () => {
    console.log("Contador hijo se renderiza")
    return (
        <div style={{border:"thin solid #000", margin:"1rem", padding:"1rem"}}>
            <h2>Hijo del Contador</h2>
        </div>
    )
};
// lo unico que tendriamos que hacer seria envolver en la funcion memo de react pasarle como parametro el componente que queremos memorizar 
// ahora a un que cambiemos la variable de estado del componente padre, el componente no se volvera a renderizar 
export default memo(ContadorHijo);

```

**memo**
- Se escarga de memorizar un componente 
- Lo vuelve memorizar al momento de que sus **props** cambien.
- Evitar re-renderizados.
- Hay que evitarlo en la medida de lo posible, pues podria ser mas constosa la tarea de memorizacion que el re-renderizado del componente.
- Usalo cuando:
    - Tengamos muchso elementos renderizados en una lista.
    - Llamamos datos de Apis.
    - Un componente se vielve muy pesado.
    - Salen alertar de rendimiento en la consola.

## Memorización ( [useCallback](https://es.reactjs.org/docs/hooks-reference.html#usecallback) )
Que va a pasar si nosotros tenemos que pasarle funciones como propiedades a un contenedor hijo, que va a pasar con el renderizado?, se memoriza o no?

La funcionalidad de `useCallback` es memorizar funciones puras.
- `Contador.js`:
```js
import { useState } from "react";
import ContadorHijo from "./ContadorHijo";

const Contador = () => {
    const [contador, setContador] = useState(0);
    const [input, setInput] = useState("")

    const sumar = () =>setContador(contador + 1);
    const restar = () =>setContador(contador - 1);

    const handleInput = (e) => setInput(e.target.value); 


    return (
        <div style={{textAlign: "center"}}>
            <h2>COntador</h2>
            <nav>
                <button onclick={sumar}>+</button>
                <button onclick={restar}>-</button>
            </nav>
            <h3>{contador}</h3>
            <input type="text" onChange={handleInput} value={input}/>
            {/*En este caso el componente dijo se renderiza solamente cuando la variable de estado contador cambia ya que se le esta pasando como parametro, pero que pasaria si en vez de una variable de estado se pasamos como parametro una funcion? */}
            {/*cuando le asignamos una funcion del componente padre al componente hijo entonces ahora ya se ve afectado por la re-renderizacion del input */}
            <ContadorHijo contador={contador} sumar={sumar} restar={restar}/>
        </div>
    )
}

export default Contador;
```
- `ContadorHijo.js`:
```js
import {memo} from 'react';  

const ContadorHijo = ({contador,sumar,restar}) => {
    console.log("Contador hijo se renderiza")
    return (
        <div style={{border:"thin solid #000", margin:"1rem", padding:"1rem"}}>
            <h2>Hijo del Contador</h2>
            <h3>{contador}</h3>
            <nav>
                <button onclick={sumar}>+</button>
                <button onclick={restar}>-</button>
            </nav>
        </div>
    )
};

export default memo(ContadorHijo);
```

React-memo lo que hace es memorizar el componente, pero cuando el componente recibe propiedades que son funciones esas funciones tambien hay que memorizarlas y para eso vamos a hacer uno de un hook llamado `useCallback`, que lo que hace es memorizar una funcion pura.

- `Contador.js`:
```js
import { useState,useCallback } from "react";
import ContadorHijo from "./ContadorHijo";

const Contador = () => {
    const [contador, setContador] = useState(0);
    const [input, setInput] = useState("");

    //const sumar = () =>setContador(contador + 1);
    const sumar = useCallback(
        () => {
            setContador(contador + 1)
        },
        [contador],
    );
    //const restar = () =>setContador(contador - 1);
    const restar = useCallback(
        () => {
            setContador(contador - 1)
        },
        [contador],
    );

    const handleInput = (e) => setInput(e.target.value); 


    return (
        <div style={{textAlign: "center"}}>
            <h2>COntador</h2>
            <nav>
                <button onclick={sumar}>+</button>
                <button onclick={restar}>-</button>
            </nav>
            <h3>{contador}</h3>
            <input type="text" onChange={handleInput} value={input}/>
            
            <ContadorHijo contador={contador} sumar={sumar} restar={restar}/>
        </div>
    )
}

export default Contador;
```

**useCallback**
- Memoriza una funcion, para no volver a definir en cada render.
- Usalo siempre que se pase una funcion como **prop** a un componente memorizado.
- Usalo suiempre que se pase una funcion como parametros de un efecto.

## Memorización ( [useMemo](https://es.reactjs.org/docs/hooks-reference.html#usememo) ) 
`useMemo` nos permite memorizar las **propiedades computadas**, valores que necesitemos calcular en tiempo de ejecucion de nuestra aplicacion, es decir, valor que se calculen y luego se impriman en pantalla por ejemplo.

Tambien cuando tengas que hacer proceso muy pesados como por ejemplo estar esperando recirbir datos de una api, tambien para eso nos va a servir `useMemo`.

- `COntadorHijo.js`:
```js
import {memo} from 'react';  

const ContadorHijo = ({contador,sumar,restar}) => {
    let superNumero = 0;

    for(let i=0; i<100000; i++){
        /*este calculo de superNumero va afectar en el renderizado */
        /*Esto ocurre tambien cuando variable de estado y funciones son usadas ya que estas necesatan ser renderizadas denuevo junto con el componente */
        /*EStos es conocido como valor calculado o computer property */
        /*En estos caso se recomienda memorizar el valor calculado */
        superNumero++;
    }


    return (
        <div style={{border:"thin solid #000", margin:"1rem", padding:"1rem"}}>
            <h2>Hijo del Contador</h2>
            <h3>{contador}</h3>
            <nav>
                <button onclick={sumar}>+</button>
                <button onclick={restar}>-</button>
            </nav>
            <h3>{superNumero}</h3>
        </div>
    )
};

export default memo(ContadorHijo);
```
Despues de `useMemo`:
- `ContadorHijo`:
```js
import {memo, useMemo} from 'react';  

const ContadorHijo = ({contador,sumar,restar}) => {
    /*let superNumero = 0;

    for(let i=0; i<100000; i++){
        superNumero++;
    }*/
    /*use memo necesita una funcion y una variable de estado, pero en esta ocacion no vamos a darle uan variable de estado y aun asi va a funcionar correctamente, para esto tenemos que asignarle una array vacio */
    /*useMemo nos va a marcar un error si no retornamos el valor que pretendemos memorizar, no estas memorizando una funcion, estamos memorizando un valor dado cierto proceso */
    const superNumero = useMemo(() => {
        let numero = 0;

        for(let i=0; i<100000; i++){
            numero++;
        };
        return numero;
    }, [])


    return (
        <div style={{border:"thin solid #000", margin:"1rem", padding:"1rem"}}>
            <h2>Hijo del Contador</h2>
            <h3>{contador}</h3>
            <nav>
                <button onclick={sumar}>+</button>
                <button onclick={restar}>-</button>
            </nav>
            <h3>{superNumero}</h3>
        </div>
    )
};

export default memo(ContadorHijo);
```

**useMemo**
- Memorizar un valor calculado, es decir, el resultado de una funcion.
- genera propiedades computadas.
- Usalo en proceso pesados. 

## [Context API](https://es.reactjs.org/docs/context.html)
### Introducción 
**Context API** es una amanera que tiene react nativamente para manupular el estado de una forma mas optima.

Para pode rutilizar react context es importante que tus aplicaciones sean superiores a la version 16.3 que es cuando se implemento.

El context nos va a servir sobre todo nos va a servir para en lugar de estar pasando como propiedades algunos valores  de un conponente hijo a un componente padre y luego un componente nieto y asi sucesivamente, el contexto, nos va a permitir tener todas estas variables que probable mente algunos de los nodos del arbol de la aplicacion los vaya a utilizar en algun momento lo pueda tener disponible.

Es pocas palabras el **context** va a ser muy util  en aplicaciones donde tengamos que compartir variables de estado global.

**Utiliza context** cuando tengas la nececidad de que una variable te vaya a modificar varios aspectos de tu interfaz.

Por cuestiones de rendimiento solamente usa el contexto cuando necesites compartir variables de estado, efectos en varios elementos dentro del arbol de componentes de la aplicacion.

### Haciendo una APP con THEME Dark/Light SIN Context

- `App.js`:
```js
import './App.css';
import MyPage from './components/MyPage';

function App() {
  return (
    <div className="App">
     <h1>React Context API</h1>
     <hr/>
     <MyPage/>
    </div>

  );
}

export default App;

```

- `MyPage.js`:
```js
import { useState } from "react";
import Footer from "./Footer";
import Header from "./Header";
import Main from "./Main";

const initialState="light";

const MyPage = () => {
    const [theme, setTheme] = useState(initialState);

    const handleTheme = (e) =>{
        if(e.target.value === "light"){
            setTheme("light");
        }else{
            setTheme("dark");
        }
    };
    return (
        <div className="my-page">
            <Header theme={theme} handleTheme={handleTheme}/>
            <Main theme={theme}/>
            <Footer theme={theme}/>
        </div>
    )
}

export default MyPage;
```

- `Header.js`:
```js
const Header = ({theme, handleTheme}) => {
    return (
        <header className={theme}>
            <h2>Mi aplicacion SIN Context API</h2>
            <h3>Mi Cabecera</h3>
            <select name="language">
                <option value="es">ES</option>
                <option value="en">EN</option>
            </select>
            <input type="radio" name="theme" id="ligth" onClick={handleTheme} value="light"/>
            <label htmlFor="light">Claro</label>
            <input type="radio" name="theme" id="dark" onClick={handleTheme} value="dark"/>
            <label htmlFor="dark">Oscuro</label>
            <button>Iniciar Sesion</button>
        </header>
    )
}

export default Header;
```
- `Main.js`:
```js
const Main = () => {
    return (
        <main>
        <p>Bienvenid@ invitad@</p>
        <p>Hola Usuari@</p>
        <p>Mi contenido principal</p>
        </main>
    )
}

export default Main;

```

- `Footer.js`:
```js
const Footer = () => {
    return (
        <footer>
            <h4>MI pie de pagina</h4>
        </footer>
    )
}

export default Footer;

```
- `index.css`:
```css
body {
  margin: 0;
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Roboto', 'Oxygen',
    'Ubuntu', 'Cantarell', 'Fira Sans', 'Droid Sans', 'Helvetica Neue',
    sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

.my-page{
  margin: 2rem auto;
  padding: 1rem;
  width: 70%;
  background: #CCC;
}

.dark{
  background-color: #fff;
  /*no se recomienda usar el filter para cambiar los colores pero en este caso lo usaremos para hacer un ejemplo rapido*/
  filter: invert(1);
}
```

### Haciendo una APP MultiIDIOMA SIN Context 
- `MyPage.js`:
```js
import { useState } from "react";
import Footer from "./Footer";
import Header from "./Header";
import Main from "./Main";

const initialTheme="light";
const initialLanguage = "es";

const translations = {
    es:{headerTitle:"Mi aplicacion SIN Context API",
        headerSubtitle:"Mi cabecera",
        headerLight:"Claro",
        headerDark:"Oscuro",
        buttonLogin: "Iniciar Sesion",
        buttonLogout: "Cerrar Sesion",
        mainWelcome: "Bienvenid@ invitado",
        mainHello: "Hola Usuari@",
        mainContent: "Mi contendio principal",
        footerTitle: "Mi pie de pagina" },
    en:{headerTitle:"My applicaction without Context API",
    headerSubtitle:"My header",
    headerLight:"Light",
    headerDark:"Dark",
    buttonLogin: "Login",
    buttonLogout: "Logout",
    mainWelcome: "Welcome",
    mainHello: "Hello User",
    mainContent: "My main content",
    footerTitle: "My footer"}
}

const MyPage = () => {
    const [theme, setTheme] = useState(initialTheme);
    const [language, setLanguage] = useState(initialLanguage);
    const [texts,setTexts] = useState(translations[language]);


    const handleTheme = (e) =>{
        if(e.target.value === "light"){
            setTheme("light");
        }else{
            setTheme("dark");
        }
    };

    const handleLanguage = (e) =>{
        if(e.target.value === "es"){
            setLanguage("es");
            setTexts(translations.es)
        }else{
            setLanguage("en");
            setTexts(translations.en)
        }
    };
    return (
        <div className="my-page">
            <Header theme={theme} handleTheme={handleTheme} texts={texts} handleLanguage={handleLanguage}/>
            <Main theme={theme} texts={texts}/>
            <Footer theme={theme} texts={texts}/>
        </div>
    )
}

export default MyPage;
```

- `Header.js`:
```js
const Header = ({theme, handleTheme,handleLanguage,texts}) => {
    return (
        <header className={theme}>
            <h2>{texts.headerTitle}</h2>
            <h3>{texts.headerSubtitle}</h3>
            <select name="language" onChange={handleLanguage}>
                <option value="es">ES</option>
                <option value="en">EN</option>
            </select>
            <input type="radio" name="theme" id="ligth" onClick={handleTheme} value="light"/>
            <label htmlFor="light">{texts.headerLight}</label>
            <input type="radio" name="theme" id="dark" onClick={handleTheme} value="dark"/>
            <label htmlFor="dark">{texts.headerDark}</label>
            <button>{texts.bottonLogin}{texts.buttonLogout}</button>
        </header>
    )
}

export default Header;
```

- `Main.js`:
```js
const Main = ({texts,theme}) => {
    return (
        <main className={theme}>
        <p>{texts.mainWelcome}</p>
        <p>{texts.mainHello}</p>
        <p>{texts.mainContent}</p>
        </main>
    )
}

export default Main;

```
- `Footer.js`:
```js
const Footer = ({theme,texts}) => {
    return (
        <footer className={theme}>
            <h4>{texts.footerTitle}</h4>
        </footer>
    )
}

export default Footer;

```

###  Haciendo una APP con SESIÓN de Usuario SIN Context

- `MyPage.js`:
```js
import { useState } from "react";
import Footer from "./Footer";
import Header from "./Header";
import Main from "./Main";

const initialTheme="light";
const initialLanguage = "es";

const translations = {
    es:{headerTitle:"Mi aplicacion SIN Context API",
        headerSubtitle:"Mi cabecera",
        headerLight:"Claro",
        headerDark:"Oscuro",
        buttonLogin: "Iniciar Sesion",
        buttonLogout: "Cerrar Sesion",
        mainWelcome: "Bienvenid@ invitado",
        mainHello: "Hola Usuari@",
        mainContent: "Mi contendio principal",
        footerTitle: "Mi pie de pagina" 
    },
    en:{headerTitle:"My applicaction without Context API",
        headerSubtitle:"My header",
        headerLight:"Light",
        headerDark:"Dark",
        buttonLogin: "Login",
        buttonLogout: "Logout",
        mainWelcome: "Welcome Guest",
        mainHello: "Hello User",
        mainContent: "My main content",
        footerTitle: "My footer"
    }
};

const initialAuth = null;

const MyPage = () => {
    const [theme, setTheme] = useState(initialTheme);
    const [language, setLanguage] = useState(initialLanguage);
    const [texts,setTexts] = useState(translations[language]);
    const [auth, setAuth] = useState(initialAuth)


    const handleTheme = (e) =>{
        if(e.target.value === "light"){
            setTheme("light");
        }else{
            setTheme("dark");
        }
    };

    const handleLanguage = (e) =>{
        if(e.target.value === "es"){
            setLanguage("es");
            setTexts(translations.es)
        }else{
            setLanguage("en");
            setTexts(translations.en)
        }
    };

    const handleAuth = (e)=>{
        if(auth){
            setAuth(null);
        }else{
            setAuth(true);
        }
    };
    return (
        <div className="my-page">
            <Header theme={theme} handleTheme={handleTheme} texts={texts} handleLanguage={handleLanguage} auth={auth} handleAuth={handleAuth}/>
            <Main theme={theme} texts={texts} auth={auth}/>
            <Footer theme={theme} texts={texts}/>
        </div>
    )
}

export default MyPage;
```

- `Header.js`:
```js
const Header = ({theme, handleTheme,handleLanguage,texts, auth,handleAuth}) => {
    return (
        <header className={theme}>
            <h2>{texts.headerTitle}</h2>
            <h3>{texts.headerSubtitle}</h3>
            <select name="language" onChange={handleLanguage}>
                <option value="es">ES</option>
                <option value="en">EN</option>
            </select>
            <input type="radio" name="theme" id="ligth" onClick={handleTheme} value="light"/>
            <label htmlFor="light">{texts.headerLight}</label>
            <input type="radio" name="theme" id="dark" onClick={handleTheme} value="dark"/>
            <label htmlFor="dark">{texts.headerDark}</label>
            <button onclick={handleAuth}>
            {auth? texts.buttonLogout: texts.bottonLogin}
            </button>
        </header>
    )
}

export default Header;
```

- `Main.js`:
```js
const Main = ({texts,theme, auth}) => {
    return (
        <main className={theme}>
        {auth ? <p>{texts.mainHello}</p> : <p>{texts.mainWelcome}</p>}
        <p>{texts.mainContent}</p>
        </main>
    )
}

export default Main;

```

- `Footer.js`:
```js
const Footer = ({theme,texts}) => {
    return (
        <footer className={theme}>
            <h4>{texts.footerTitle}</h4>
        </footer>
    )
}

export default Footer;
```

### Haciendo una APP con THEME Dark/Light CON Context

En el ejercicio anterio pudimos comprobar como al no usar context los componentes tienen muchas propiedades, para esto es que nos ayuda context, cuando tenemos que pasar un valor o un funcion en varios elementos a lo largo de la estructura del arbol de nodos de nuestra aplicacion nos conviene usar **context**.

Ser recomienda crear una carpeta que reuna los contextos.

- `ThemeContext.js`:
```js
import { createContext, useState } from "react";

// cremos un contexto con la funcion createContext()
const ThemeContext = createContext();
//se suele exportar por defecto este contexto;
//este contexto internamente tiene dos objetos, un provedor, es decir, el graper que va a proveer a los elementos internos que tenga todos los valores que van a ser globales y un consumer, es decir, el otro mecanismo que nos va a permitir consumir esos valores que da el provedor 

//ahora vamos a crear un componente el cual v a a ser el provedor, hay quien incluso crea un archivo solamente para el contexto y adicionalmente se crean otro archivo para crear al provedor (el que va a estar almacenanto todos los valores globales)

// en esta cocacion se crearan ambos en el mismo archivo, tanto el cxontexto com el procedor

//el cosumer nos lo vamos a utilizar, vamos a consumir la data mediante un hook
const initialTheme="light";
//el provedor forzosamente tiene que hacer uso de la etiqueta children, el provider es el que va a proveer todos los valores y se los va a pasar a todos los hijos que tenga internamente 
//provedor:
const ThemeProvider = ({children}) =>{
    const [theme, setTheme] = useState(initialTheme);
    const handleTheme = (e) =>{
        if(e.target.value === "light"){
            setTheme("light");
        }else{
            setTheme("dark");
        }
    };
    //cada valor que queramos compartir de manera global lo podremos definir como propiedades del constructor ThemeContext, pero se te sugiere que previamente tengas un objeto y en este objeto por cada propiedad que tenga el objeto es cada un de esos valores que quieres conservar globalmente para lo componentes que compartan este contexto 
    const data={theme,handleTheme};

    return(
        <ThemeContext.Provider value={data}>{children}</ThemeContext.Provider>
    )
};
export {ThemeProvider}
export default ThemeContext;
```

- `MyPageContext.js`:
```js
import { useState } from "react";
import { ThemeProvider } from "./context/ThemeContext";
import FooterContext from "./FooterContext";
import HeaderContext from "./HeaderContext";
import MainContext from "./MainContext";


const initialLanguage = "es";

const translations = {
    es:{headerTitle:"Mi aplicacion SIN Context API",
        headerSubtitle:"Mi cabecera",
        headerLight:"Claro",
        headerDark:"Oscuro",
        buttonLogin: "Iniciar Sesion",
        buttonLogout: "Cerrar Sesion",
        mainWelcome: "Bienvenid@ invitado",
        mainHello: "Hola Usuari@",
        mainContent: "Mi contendio principal",
        footerTitle: "Mi pie de pagina" 
    },
    en:{headerTitle:"My applicaction without Context API",
        headerSubtitle:"My header",
        headerLight:"Light",
        headerDark:"Dark",
        buttonLogin: "Login",
        buttonLogout: "Logout",
        mainWelcome: "Welcome Guest",
        mainHello: "Hello User",
        mainContent: "My main content",
        footerTitle: "My footer"
    }
};

const initialAuth = null;

const MyPageContext = () => {
    
    const [language, setLanguage] = useState(initialLanguage);
    const [texts,setTexts] = useState(translations[language]);
    const [auth, setAuth] = useState(initialAuth)


    const handleLanguage = (e) =>{
        if(e.target.value === "es"){
            setLanguage("es");
            setTexts(translations.es)
        }else{
            setLanguage("en");
            setTexts(translations.en)
        }
    };

    const handleAuth = (e)=>{
        if(auth){
            setAuth(null);
        }else{
            setAuth(true);
        }
    };
    return (
        <div className="my-page">
        {/*Tenemos que mandar a llamar a ThemeProvider y dentro del mismo vamos a poner las etiquetas que se relacionen con la informacvion que contenga*/}
        <ThemeProvider>
            <HeaderContext texts={texts} handleLanguage={handleLanguage} auth={auth} handleAuth={handleAuth}/>
            <MainContext texts={texts} auth={auth}/>
            <FooterContext texts={texts}/>
        </ThemeProvider>
        </div>
    )
}

export default MyPageContext;

```

- `MainContext.js`:
```js
import { useContext } from "react";
import ThemeContext from "./context/ThemeContext";

const MainContext = ({texts, auth}) => {
    const {theme} = useContext(ThemeContext);
    return (
        <main className={theme}>
        {auth ? <p>{texts.mainHello}</p> : <p>{texts.mainWelcome}</p>}
        <p>{texts.mainContent}</p>
        </main>
    )
}

export default MainContext;
```

- `HeaderContext.js`:
```js
import { useContext } from "react";
import ThemeContext from "./context/ThemeContext";

const HeaderContext = ({handleLanguage,texts, auth,handleAuth}) => {
    //las propiedades de theme ahora las va a obtener desde un contexto 
    //vamos a destrucutrar las variable que estan definidas en ThemeContext
    // useContext recibe como parametro el contexto que se a creado, en este caso es ThemeContext
    const {theme,handleTheme} = useContext(ThemeContext);
    return (
        <header className={theme}>
            <h2>{texts.headerTitle}</h2>
            <h3>{texts.headerSubtitle}</h3>
            <select name="language" onChange={handleLanguage}>
                <option value="es">ES</option>
                <option value="en">EN</option>
            </select>
            <input type="radio" name="theme" id="ligth-context" onClick={handleTheme} value="light"/>
            <label htmlFor="light-context">{texts.headerLight}</label>
            <input type="radio" name="theme" id="dark-context" onClick={handleTheme} value="dark"/>
            <label htmlFor="dark-context">{texts.headerDark}</label>
            <button onclick={handleAuth}>
            {auth? texts.buttonLogout: texts.bottonLogin}
            </button>
        </header>
    )
}

export default HeaderContext;
```

- `FooterContext.js`:
```js
import { useContext } from "react";
import ThemeContext from "./context/ThemeContext";

const FooterContext = ({texts}) => {
    const {theme} = useContext(ThemeContext);
    return (
        <footer className={theme}>
            <h4>{texts.footerTitle}</h4>
        </footer>
    )
}

export default FooterContext;

```

### Haciendo una APP MultiIDIOMA CON Context

- `LanguageContext.js`:
```js
import { createContext,useState } from "react";

const LanguageContext = createContext();
const initialLanguage = "es";
const translations = {
    es:{headerTitle:"Mi aplicacion SIN Context API",
        headerSubtitle:"Mi cabecera",
        headerLight:"Claro",
        headerDark:"Oscuro",
        buttonLogin: "Iniciar Sesion",
        buttonLogout: "Cerrar Sesion",
        mainWelcome: "Bienvenid@ invitado",
        mainHello: "Hola Usuari@",
        mainContent: "Mi contendio principal",
        footerTitle: "Mi pie de pagina" 
    },
    en:{headerTitle:"My applicaction without Context API",
        headerSubtitle:"My header",
        headerLight:"Light",
        headerDark:"Dark",
        buttonLogin: "Login",
        buttonLogout: "Logout",
        mainWelcome: "Welcome Guest",
        mainHello: "Hello User",
        mainContent: "My main content",
        footerTitle: "My footer"
    }
};
const LanguageProvider = ({children})=>{
    const [language, setLanguage] = useState(initialLanguage);
    const [texts,setTexts] = useState(translations[language]);

    const data={texts,handleLanguage};

    const handleLanguage = (e) =>{
        if(e.target.value === "es"){
            setLanguage("es");
            setTexts(translations.es)
        }else{
            setLanguage("en");
            setTexts(translations.en)
        }
    };

    return (
    <LanguageContext.Provider value={data}>
    {children}
    </LanguageContext.Provider>)
};

export {LanguageProvider};
export default LanguageContext;
```

- `MyPageContext.js`:
```js
import { useState } from "react";
import { LanguageProvider } from "./context/LanguageContext";
import { ThemeProvider } from "./context/ThemeContext";
import FooterContext from "./FooterContext";
import HeaderContext from "./HeaderContext";
import MainContext from "./MainContext";

const initialAuth = null;

const MyPageContext = () => {
    
    
    const [auth, setAuth] = useState(initialAuth)


    

    const handleAuth = (e)=>{
        if(auth){
            setAuth(null);
        }else{
            setAuth(true);
        }
    };
    return (
        <div className="my-page">
        <ThemeProvider>
        <LanguageProvider>
            <HeaderContext  auth={auth} handleAuth={handleAuth}/>
            <MainContext auth={auth}/>
            <FooterContext/>
        </LanguageProvider>
        </ThemeProvider>
        </div>
    )
}

export default MyPageContext;

```

- `MainContext.js`:
```js
import { useContext } from "react";
import LanguageContext from "./context/LanguageContext";
import ThemeContext from "./context/ThemeContext";

const MainContext = ({auth}) => {
    const {theme} = useContext(ThemeContext);
    const {texts} = useContext(LanguageContext);
    return (
        <main className={theme}>
        {auth ? <p>{texts.mainHello}</p> : <p>{texts.mainWelcome}</p>}
        <p>{texts.mainContent}</p>
        </main>
    )
}

export default MainContext;
```

- `HeaderContext.js`:
```js
import { useContext } from "react";
import LanguageContext from "./context/LanguageContext";
import ThemeContext from "./context/ThemeContext";

const HeaderContext = ({auth,handleAuth}) => {
    
    const {theme,handleTheme} = useContext(ThemeContext);
    const {texts,handleLanguage} = useContext(LanguageContext);
    return (
        <header className={theme}>
            <h2>{texts.headerTitle}</h2>
            <h3>{texts.headerSubtitle}</h3>
            <select name="language" onChange={handleLanguage}>
                <option value="es">ES</option>
                <option value="en">EN</option>
            </select>
            <input type="radio" name="theme" id="ligth-context" onClick={handleTheme} value="light"/>
            <label htmlFor="light-context">{texts.headerLight}</label>
            <input type="radio" name="theme" id="dark-context" onClick={handleTheme} value="dark"/>
            <label htmlFor="dark-context">{texts.headerDark}</label>
            <button onclick={handleAuth}>
            {auth? texts.buttonLogout: texts.bottonLogin}
            </button>
        </header>
    )
}

export default HeaderContext;

```

- `FooterContext.js`:
```js
import { useContext } from "react";
import LanguageContext from "./context/LanguageContext";
import ThemeContext from "./context/ThemeContext";

const FooterContext = () => {
    const {theme} = useContext(ThemeContext);
    const {texts} = useContext(LanguageContext);
    return (
        <footer className={theme}>
            <h4>{texts.footerTitle}</h4>
        </footer>
    )
}

export default FooterContext;

```

### Haciendo una APP con SESIÓN de Usuario CON Context

- `AuthContext.js`:
```js
import { createContext,useState } from "react";

const AuthContext = createContext();

const initialAuth = null;
const AuthProvider = ({children}) =>{
    const [auth, setAuth] = useState(initialAuth)

    const handleAuth = (e)=>{
        if(auth){
            setAuth(null);
        }else{
            setAuth(true);
        }
    };
    const data={auth,handleAuth};
    return(
        <AuthContext.Provider value={data}>{children}</AuthContext.Provider>
    )
};

export {AuthProvider}; 

export default AuthContext;
```

- `MyPageContext.js`:
```js
import { AuthProvider } from "./context/AuthContext";
import { LanguageProvider } from "./context/LanguageContext";
import { ThemeProvider } from "./context/ThemeContext";
import FooterContext from "./FooterContext";
import HeaderContext from "./HeaderContext";
import MainContext from "./MainContext";



const MyPageContext = () => {
    return (
        <div className="my-page">
        <AuthProvider>
        <ThemeProvider>
        <LanguageProvider>
            <HeaderContext/>
            <MainContext/>
            <FooterContext/>
        </LanguageProvider>
        </ThemeProvider>
        </AuthProvider>

        </div>
    )
}

export default MyPageContext;

```

- `MainContext.js`:
```js
import { useContext } from "react";
import AuthContext from "./context/AuthContext";
import LanguageContext from "./context/LanguageContext";
import ThemeContext from "./context/ThemeContext";

const MainContext = () => {
    const {theme} = useContext(ThemeContext);
    const {texts} = useContext(LanguageContext);
    const {auth} = useContext(AuthContext);

    return (
        <main className={theme}>
        {auth ? <p>{texts.mainHello}</p> : <p>{texts.mainWelcome}</p>}
        <p>{texts.mainContent}</p>
        </main>
    )
}

export default MainContext;

```

- `HeaderContext.js`:
```js
import { useContext } from "react";
import AuthContext from "./context/AuthContext";
import LanguageContext from "./context/LanguageContext";
import ThemeContext from "./context/ThemeContext";

const HeaderContext = () => {
    
    const {theme,handleTheme} = useContext(ThemeContext);
    const {texts,handleLanguage} = useContext(LanguageContext);
    const {auth,handleAuth} = useContext(AuthContext);

    return (
        <header className={theme}>
            <h2>{texts.headerTitle}</h2>
            <h3>{texts.headerSubtitle}</h3>
            <select name="language" onChange={handleLanguage}>
                <option value="es">ES</option>
                <option value="en">EN</option>
            </select>
            <input type="radio" name="theme" id="ligth-context" onClick={handleTheme} value="light"/>
            <label htmlFor="light-context">{texts.headerLight}</label>
            <input type="radio" name="theme" id="dark-context" onClick={handleTheme} value="dark"/>
            <label htmlFor="dark-context">{texts.headerDark}</label>
            <button onclick={handleAuth}>
            {auth? texts.buttonLogout: texts.bottonLogin}
            </button>
        </header>
    )
}

export default HeaderContext;

```

## [Reducers](https://es.reactjs.org/docs/hooks-reference.html#usereducer)

### Introducción

EL hook `useReducer` nos permite manejar de una manera mas eficiente el estado, es una alternativa al hook `useState`, de hecho en la documentecion de react nos sugieren que cuando nuestro estado empiece a volverse un poco mas complejo, quizas nos convenga, en lugar de estarlo manejando atravez de `useState` usar `useReducer`.

Esto va a servir para aplicaciones de mediana complejidad y es una alternativa a librerias que manejan el estado como reflux o redux.   

**Reducer** es una funcion pura, es decir, que solamente devuelve el valor y que toda la logia de la funcion es capaz de resolver un solo procesamiento, su programacion no va fectar cosas que esten fuera de esa funcion, tampoco va a generar efectos secudarios, ni internamnete ni externamente.

Los **Reducer** siempre van a devolver un valor y dicho valor se va a considerar como el estado de la aplicacion. No podemos usar `useEffect` dento de funciones reductoras, tampoco podemos hacer tareas asincronas.

En una aplicacion se puede tener mas de un reducer.
- `App.js`:
```js
import './App.css';
import Contador from './components/Contador';

function App() {
  return (
    <div>
      <h1>useReducer</h1>
      <hr/>
      <Contador/>
    </div>
  );
}

export default App;
```

- `Contador.js`:
```js
import { useReducer } from "react";
import { useState } from "react";
//el initialState se sugiere que sea un objeto 
const initialState = {contador:0};

function reducer(state, action){
    //una funcion reductora va a recibir dos parametros:
    //1- El estado anterior
    //2- Un objeto que se va a llamar "action"
    //la "action" internamente va a ser un objeto que va a tener un tipo de accion(el tipo de accion que se va a ejecutar) y adicionalmente pude o no tener una payload
    //el concepto de payload es como el valor que le estamso mandando para que modifique el estado
    // esta funcion si o si siempre va a retornar el estado  

    //en los reducer podrimaos usar condicionales pero se acostumbra usar la estructura switch-case
    switch (action.type) {
        // el objeto action tiene principalmnete dos propiedades en esta cuestion de los reducer:
        // el tipo de accion "type"
        // payload : es el valor que puede existir o no y que le vamos a pasar a  nuestra funcion reductora 
        case "INCREMENT":
            return{contador: state.contador + 1};
        case "DECREMENT":
            return{contador: state.contador - 1};
        default:
            return state;
    }
    
}

const Contador = () => {
    //const [contador, setContador] = useState(0);
    //la variable contador la vamos a remplazar por una useReducer
    // se va a destrucutar la variable de estado y la funcion que va a despachar la actualizacion
    // la funcion useReducer recibe 3 parametros, la funcion reductora(la tendriamos que tener definida fuera del componente), la variable de inicalState
    //el tercer parametro es una funcion que nos permite (si queremos hacer una transformacion al estado incial), podemos hacer una funcionm hacer una modificacion, y asi para que carge ya con la tranformacion/modificacion. ESte tercer parametro es opcional, en este caso no lo usaremos
    const [state, dispatch] = useReducer(reducer, initialState)

    /*el dispatch va a recibir el objeto de la accion que se va a lanzar */
    const sumar =()=> dispatch({type:"INCREMET"});
    const restar = ()=> dispatch({type: "DECREMENT"});

    return (
        <div style={{textAling:"center"}}>
            <h2>Contador Reducer</h2>
            <nav>
                <button onClick={sumar}>+</button>
                <button onClick={restar}>-</button>
            </nav>
            <h3>{state.contador}</h3>
        </div>
    )
}

export default Contador;

```

### Reducers Hook useReducer
- `contador.js`:
```js
import { useReducer } from "react";
 
const initialState = {contador:0};

//
const TYPES = {
    INCREMENT: "INCREMENT",
    DECREMENT: "DECREMENT",
    INCREMENT_5: "INCREMENT_5",
    DECREMENT_5: "DECREMENT_5",
    RESET:"RESET"
}

function reducer(state, action){ 

    switch (action.type) {
        //las opciones se pusieron en mayuscula por que se consideran constantes que nunca van a cambiar y dehecho la buena practica es que tengamos un objeto donde tengamos los diferentes tipos de acciones que nuestra aplicacion va hacer 
        //esto se hace con la intencion de que no tengamos errores
        case TYPES.INCREMENT_5:
            //aqui en lugar de un +5 es +action por que el tipo de la accion y el payload estan dentro de action
            return{contador: state.contador + action.payload};
        case TYPES.INCREMENT:
            return{contador: state.contador + 1};
        case TYPES.DECREMENT:
            return{contador: state.contador - 1};
        case TYPES.DECREMENT_5:
            return{contador: state.contador - action.payload};
        case TYPES.RESET:
            return initialState;
        default:
            return state;
    }
    
}

const Contador = () => {
    const [state, dispatch] = useReducer(reducer, initialState)

    const sumar =()=> dispatch({type:TYPES.INCREMENT});
    const restar = ()=> dispatch({type: TYPES.DECREMENT});
    //EL PAYLOAD ES EL VALOR QUE LE ESTAMOS PASANDO
    const sumar5 =()=> dispatch({type:TYPES.INCREMENT_5, payload: 5});
    const restar5 = ()=> dispatch({type: TYPES.DECREMENT_5});

    const reset = ()=> dispatch({type: TYPES.RESET});

    return (
        <div style={{textAling:"center"}}>
            <h2>Contador Reducer</h2>
            <nav>
                <button onClick={sumar5}>+5</button>
                <button onClick={sumar}>+</button>
                <button onClick={reset}>0</button>
                <button onClick={restar}>-</button>
                <button onClick={restar5}>-5</button>
            </nav>
            <h3>{state.contador}</h3>
        </div>
    )
}

export default Contador;
```

## REDUX

### Introducción 
Redux es una libreria que nos permite manejar de una manera ordenada, predecible y escalable el estado de nuestra aplicacion.

Personalmente redux se va a utilizar cuando la aplicacion sea mediana o grande en complejidad. EN aplicaciones medianas o grandes donde tenemos una gran complejidad de logica, donde tenemos una gran cantidad de componentes, es el tener una estructura ordenada nos va a permitir tener un mejor control sobre la aplicacion.

Redux nos permite tener un solo origen, independientemente que tengamos diferentes tipos de datos o logica de negocio en una aplicacion.

Aun que forma parte de las tecnologias de react sige siendo compatible con angular, vue.js, incluso puramente javascript.

**Caracteristicas de redux**:
- Predecubke
- Centralizado 
- Debuggable 
- Flexible

**Teoria y Conceptos**:
- **Store**: debe de haber un solo almacenamiento global, dentro puede contener varios estados.
- **Dispatch**: Van a ser los disparadores de eventos que van a ejecutar una accion, y esa accion puede adicionalmente e internamente contener un payload(manda los adatos que previamente se van a actualizar) 
- **Action**: objeto JS con 2 propiedades: type y payload(Datos).
- **Subscribe**: es como un listener de los eventos de javascript, es un manejador de eventos para el state.
- **Reducers**: funciones puras que van a getionar la accion.

###  Estructura de archivos

instalaremos:
```
npm install redux react-redux redux-devtools
```
si aparecen errores al momento de instalar intenta:
```
npm install redux react-redux redux-devtools --legacy-peer-deps
```
- **Actions**
ahora en el organizamiento de las carptetas vamos a crear una carpeta dentro de `src` llamda `actions`.`src/actions/`.

- **types**
La siguiente carpeta que vamos a crear es una carpeta llamada **types**, el objeto actions tiene el tipo y el payload(Data), lo que nos sugiere redux es separar los tipos de acciones que vayamos a ejecutar y en un archivo que se le suele llamar `index.js` y ahi vamos a poner todas las acciones que tenga nuestra aplicacion.`src/types/index.js`.

- **reducers**
AHora necesitamos una carpeta donde vayan los reducers(funciones puras que van a actualizar el listado). `src/reducers/`. Lo ideal es tener un archivo por cada funcion reductora.

Independientemente que tengamos cada **reducer** para cada funcion reductora, aparte tenemos que tener un archivo que los combine todos en su totalidad en este caso sera un archivo llamado index.js.`src/reducers/index.js`. Y este va a centralizar todos los reducers que tenga nuestra aplicacion, como va a acentralizar todos los reducer vamos a llamar un metodo de redux llamado `combineReducers`.
```js
import {combineReducers} from "redux";

//la funcion de combineReducers lo unico que recibe es un objeto
//en cada propiedad del objeto va a recibir cada uno de los reducers que tiene.
const reducer = combineReducers({});

export default reducer;
```

- **store**
ahora crearemos la carpeta de store, esta carpeta haria referencia al store, es decir al contenedor global de todos los estado de nuestra apliacion en un archivo `index.js` `src/store/index.js`.
```js
import {createStore} from 'redux';
//sin acele incapie en el archivo index.js automaticamnete lo hara al se;alarle la carpeta reducers
import reducer from "../reducers"; 

const store = createStore(reducer);

//para que este detectando cualquier cambie que este surgiendo en el estado hay que suscribir

//si quisieramos que llegara a hacer alguna cosa adicional algo que se ejecute cuando hay un cambio lo podmeos hacer en esta funcion
store.subscribe(() => console.log(store));


export default store;
```

### Flujo de Trabajo

Creamos un nuevo archivo `src/components/COntador.js`:
```js
const Contador = () => {
    return (
        <div>
            <h2>Contador Redux</h2>
        </div>
    )
}

export default Contador;
```

y luego lo importamos a la `App.js`:
```js
import './App.css';
import {Provider} from "react-redux";
import store from "./store"
import Contador from './components/Contador';

function App() {
    //declaramos en el componente de la aplicacion el provider
    //este provider ya provee todo ese store
    // todos los componentes que esten dentro de este provider van a poder tener accceso al almacenamiento de redux
  return (
    <Provider store={store}>
      <div style={{textAling: "center"}}>
        <h1>Redux</h1>
        <Contador/>
      </div>
    </Provider>
  );
}

export default App;
```

Ahora primero tener que definir los tipos de acciones que se van a ver involucradas con esta funcionalidad del contador, vamos a abrir el arcvhivo `src/types/index.js`:
```JS
//contador
// En los reducer se puede hacer a manera de objeto 
// pero se sugiere que sea a amnera de constante 
export const INCREMENT = "INCREMENT";
export const DECREMENT = "DECREMENT";
export const INCREMENT_5 = "INCREMENT_5";
export const DECREMENT_5 = "DECREMENT_5";
export const RESET = "RESET";

//shopping card

//crud
```

Ahora vamos a crear el archivo de las acciones exclusivamente para el contador `src/actions/contadorActions.js`, en esta ocacion usamos lowercamercase ya que los actions como los reducers no son componentes.

```JS
// vamos a exportar por defecto las funciones que vana ahcer referencia a los tipos de acciones que sea n definido

import { DECREMENT, DECREMENT_5, INCREMENT, INCREMENT_5, RESET } from "../types";

export const sumar = () => ({type: INCREMENT});

export const restar = () => ({type: DECREMENT});

export const sumar5 = () => ({type: INCREMENT_5, payload: 5});

export const restar5 = () => ({type: DECREMENT_5, payload: 5});

export const reset =() => ({type:RESET});
```

El siguiente paso es crear la funcion reducara, va a ser la funcion que va a tener los switch y dependiendo del type va a sumar o restar.`src/reducers/contadorReducer.js`.
```js
const initialState = 0;
export default function contadorReducer(state = initialState, action){
    switch (action.type) {
        case INCREMENT:
            return state + 1;
        case DECREMENT:
            return state - 1;
        case INCREMENT_5:
            return state + action.payload;
        case DECREMENT_5:
            return state - action.payload;
        case RESET:
            return initialState;
        default:
            //cualquier otra accion que se este mandando retornara el estado anterio para que no sufra ningun cambio corrupto el estado de la apliacion 
            return state;
    }
}
```

Ahora vamos a agregar el contadorReducer al reducer central`src/reducers/index.js`.
```js
import {combineReducers} from "redux";
import contadorReducer from "./contadorReducer";

//la funcion de combineReducers lo unico que recibe es un objeto
//en cada propiedad del objeto va a recibir cada uno de los reducers que tiene.
const reducer = combineReducers({
    contador: contadorReducer
});

export default reducer;
```

EL siguiente paso es agregar esta logica al componente del `/components/Contador.js`. Vicularemos la logica con el uso de los despatch, para eso usaremos las hooks que trae la imprementacion de redux (react-redux) y con las redux-devtools para ver el manejo del estado en al consola del navegador.
```js
import {useSelector,useDispatch} from "react-redux";
import {sumar5,sumar, reset, restar5, restar} from "../actions/contadorActions"

const Contador = () => {
    //con useSelector haremos uso del store
    // este useSelector es como el useState de react, pero este nos permite acceder al estado de redux
    const state = useSelector(state => state);
    // los reducer usan los Dispatch para disparar las acciones, aqui es lo mismo
    //como parametro recibe una funcion, pero en esta ocacion se lo agregaremos en el onCLick
    const dispatch = useDispatch();
    return (
        <div>
            <h2>Contador Redux</h2>
            <nav>
                <button onClick={()=> dispatch(restar5())}>-5</button>
                <button onClick={()=> dispatch(restar())}>-1</button>
                <button onClick={()=> dispatch(reset())}>0</button>
                <button onClick={()=> dispatch(sumar())}>1</button>
                <button onClick={()=> dispatch(sumar5())}>5</button>
            </nav>
            <h3>{state.contador}</h3>
        </div>
    )
}

export default Contador;
```

## Error no detectado: demasiados renderizados

En la aplicación React JS, a veces obtuvimos "Error no detectado: demasiados renderizados. React limita la cantidad de renderizados para evitar un bucle infinito". Pero ¿sabes por qué ha sucedido esto? De hecho, es causado por varios errores. Ahora tratamos de entender qué significa realmente este error para nosotros. Significa que nuestro componente se renderiza en un tiempo infinito. Ahora puede surgir una pregunta, ¿por qué nuestro componente se representa en un tiempo infinito? La razón es que nuestro estado cambia inmediatamente cuando se renderiza nuestro componente. Y sabemos que cuando cambie el estado, nuestro componente se renderizará nuevamente. Entonces hace un bucle infinito.

Anteriormente sabemos que este error ocurre por muchas razones. Entonces, primero debe identificar su error y luego tratar de resolver este error. Ahora estoy tratando de dar un ejemplo para entender mejor sobre esto.

**Ejemplo 1.**
```jsx
<button onClick={setToggle(!toggle)}>{ toggle ? 'Close' : 'Open' }</button>
```
En este escenario, necesitamos vincular la función de devolución de llamada para resolver.

**Ejemplo 2.**
```jsx
const [msg, setMsg] = useState('Please open!!!');
const [toggle, setToggle] = useState(false);

if (msg) {
  setToggle(true)
}
```
Podemos resolver de otra manera:
1. 
```
const [toggle, setToggle] = useState(msg ? true : false);
```
2. 
```
const [toggle, setToggle] = useState(!!msg);
```

3. 
```
useEffect(() => {
 if (msg) {
   setToggle(true)
 }
}, []);
```