# [REACT Y TYPESCRIPT](https://www.typescriptlang.org/docs/handbook/react.html)

## Introduccion a typescript
Typecript es un lenguaje superconjunto de javascript desarrollado por microsoft.

Lo que hace javascript es convertir todo el codigo de typescript ( archivo con terminacion `.ts`) a un archivo javascript y al final lo que va a terminar ejecutandose es el achivo javascript, esto quiere decir que podemos ejecutar typescript en todos los entornos donde se pueda ejecutar javacript y integrarlos a proyectos de javascript existentes.

Typescript fue dise;ado para aplicaciones grandes.

- **Arquitectura de typescript**:
  - `language`:
El lenguaje de typecript en pocas palabras es la sintaxiste de javascript para algunas otras caracteristicas, las cuales se les llama `type annotations`, las cuales permiten especificar el tipo de dato que se va a utilizar.

Tiene una sintaxis muy cercana a los lenguajes orientados a objetos.

  - `compiler`: 
Convierte de archivos `.ts` a archivo `.js`.

  - `language service`:
Son herramientas de desarrollo que permiten autocompletar el codigo o informacion acerca de tu codigo 

**Lo que ofrece typescritp**:
- **Static type checking**(revision de tipado estatico):
    - (optional) check adn assign types 
    - Compilation Errors(Reduce bugs,assuies), estos errores aparecen cuando escribes el codigo cuando ejecutas el codigo, no remplaza los test, puedes seguir usandolos.
    - mas descripcion del codigo
- **Types**:
    - String, Number, Boolean, Array, Any, Void, Null, Tuple, Enums, Generics
    - podemos usar los tipos de datos de javascript siemplemente ahora los podemos enlazar a otros tipos de datos nuevos
    - Classes:
        - No protoTypes
        - encapsulation
        - inheritance
        - modifiers

## TYPES
```TS
var myString = "hello";
// al simplemente nosotros asignarle esta declaracion de un estring luego no vamos a poder cambiar el tipo de dato que esta pueda almacenar
myString = 22; //esto no lo podemos hacer por que generar una advertencia, si ignoramos esta advertencia no ocurrira nada por que al momento de ejecutar el archivo .ts este lo convertira a codigo js y no ocurrira ningun error
// pero es importante observar estas advertencias por que es un posible error del codigo 
```
```ts
//nosotros tambien podemos indicarle explisitamente que una varibale contendra cierto tipo de dato esto lo hacemos con dospuntos despues de la variable
var myString: string = "hello";
var myNumber: number = 22;
var myBool: boolean = true;

//si queremos que una variable acepte cualqueir tipo de datos podemos asignarle any
var myVar: any = "hello";
myVar = 22;

```
**strings**
```ts
//strings
var myString: string = "22";
var myNumber: number = 22;

document.write(myString);//lo que hara es que en la pagina web aparecera un 22

document.write(myNumber);// saldra un error por que el type number no es asignable como parametro de un tipo string 
document.write(myNumber.toString());// ahor aya no saldra un error por que lo convertimos a un string
```
**arrays**
```ts
var StringArray = ["","",""];
StringArray = [1,2,3];//aqui marcara un error por que al principio se indico que erra un arreglo de strings y despues un arreglo denumeros
//para solucionar este error tenemos que indicar que va a contener cualquier tipo de dato dento del arreglo:
var StringArray:any[] = ["","",""];

//tambien s ele puede indicar un tipo de dato especifico dentro del arreglo
var StringArray: string[] = ["","",""];
var numberArray: number[] = [1,2,3];

//tupls
//los tupls son arreglos con una estructura definida 
var strnumtuple: [string, number];
strnumtuple = ["hello", 22];
strnumtuple = [22, "hello"];// aqui ocurre un error por que el 22 no es un string y el "hello" no es un number
strnumtuple = ["hello", 22, 22, "hello"]; //aqui ocurriria un error po que se estan asignando 4 datos a un array donde permite 2
```

**void , undefined, null**
```ts
//void es un tipo de dato vacio, si lo ponemos en un return de funcion entonces indicamos la funcion no retorna nada
// undefined es un tipo de dato indefinido hasta el momento
// null un tipo de dato nulo
let myVoid: void = undefined;
let mynull: null = null;
let myundefined:undefined  = undefined;
```

**functions**
```ts
// de esta manera "num1: number" especificamos el tipo de dato que va a aceptar la function
function getsum (num1: number, num2: number){
    return num1 + num2;
}

// de esta manrea "(num1, num2):number" indicamos el tipo de dato que va a retornar la funcion

function getsum (num1, num2):number{
    return num1 + num2;
}
// de esta manera inficamos que aceptara tipo de dato number o string: number | string
let mySum = function getsum (num1: number | string, num2:number | string):number{
    if(typeof(num1) === "string"){
        //hacemos esto por que sino saldra un error
        num1 = parseInt(num1);
    }
    if(typeof(num2) === "string"){
        num2 = parseInt(num2);
    }
    return num1 + num2
}


// para inficar que es un parametro opcional ponemos el signo de interrogacion ?
function getnam (firstName: string, lastName?:string):string{
    if(lastName == undefined){
        return firstName;
    }
    return `${firstName} ${lastName}`;
}
//como ya indicamos que el segundo parametro es opcional entonces ya no generara un error en la siguiente linea de codigo:
getnam("oscar")

```
### interfaces
```ts
// podemos definir la estructura del objeto que esperamos como parametro: todo: {title: string; text:string}
// aqui le estamos inficando que el objeto todo tiene las propiedades title y texto las cuales son string

function showTodo(todo: {title: string; text:string}){
    console.log(`${todo.title} - ${todo.text}`)
}

showTodo({
    title: `Eat Dinner`,
    text: "lorem"
})


//existen las interfaces que es una manera de definir anticipadamnete la estructura de los parametros
interface ITodo {
    title: string;
    text: string;
}

function showTodo(todo: ITodo){
    console.log(`${todo.title} - ${todo.text}`)
}
//esta interface tambien la ponemos usar para la asignacion de type en variables de objetos: myTodo : ITodo
const myTodo : ITodo = {
    title: `Eat Dinner`,
    text: "lorem"
}

showTodo(myTodo)
```

### class
```ts
//clases
class User {
    private name: string;
    //con el signo de interrogacion le indicamos que la propiedad es opcional(puede o no existir)
    public email?: string;
    //tambien estamos protegiendo cierta informacion para que no se pueda acceder a ella desde afuera de la clase
    protected age?: number;

    
    constructor (name: string, age?: number, email?: string){
        this.name = name;
        this.age = age;
        this.email = email;
    }

    register(){
        console.log(`${this.name} is registed`)
    }

    showMeAge(){
        return this.age;
    }

    public AgeInYears(){
        return this.age + " years";
    }

    payUnvoce(){
        console.log(`${this.name} paide invoce`)
    }
}

let john = new User("string", 17, "hola@gmail.com")
```

**herencia**
```ts

class Member extends User{
    id: number;
    constructor(id, name,email,age){
        super(name,email,age);
        this.id = id;
    }
    //para heredar un metodo
    payInvoce(){
        super.payInvoce();
    }
}

let gordon = new Member(1,"string", 17, "hola@gmail.com");
gordon.payInvoce();
```

## instalacion
si no usamos werbpack entonces tenemos que crear los archivos de typescript con terminacion `.ts` pero cuando los enlacemos al `.html`, dentro de este mismo tenemos que escribir el nombre del archivo typescript pero con terminacion `.js`. Al momento de ejecutarlo en la consola sera como `tsc ejemplo.ts` al momento de hacer esto se creara un nuevo archivo con terminacion `.js`, este nuevo archivo es la conmipilacion del archivo `.ts`

Para estar evitando compilar cada vez que se haga un cambio en el archivo `.ts` podemos ejecutar en la taerminal: `tsc nombre_archiv.ts -w`.




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

## EJEMPLO

```jsx
import ReactDOM from 'react-dom';
import * as React from 'react';
import App, { Appp } from './componentns/App';

const app = document.getElementById('app');

ReactDOM.render(
    <>
    <App title="ts react function"/>
    <Appp title="ts react class"/>
    </>, app);
```

- 1:
```tsx
import * as React from 'react';

//podemos definir cuales seran los tipos de datos que vamos a poder manerjar dentro del componente 

//componente class
// <any,any>: le estamos indicando que vamos a colocar un tipo de dato any para las propiedades y un tipo de dato any para el

export class Appp extends React.Component<any,any> {
    render(){
        return(
            <>
                <h1>{this.props.title}</h1>
            </>
        )
    }
}


//componente function

const App = ({title}:{title: any}) => {
    return (
        <>
            <h1>{title}</h1>
        </>
    )
}

export default App;

```

- 2: propiedades
```tsx
import * as React from 'react';


//componente class
// ahora le estamos dadno mas infomacion al componente:
// este componente necesita una propiedad llamda title que sera de tipo string
// si no le asignamos la propiedad title va a adar un error

export class Appp extends React.Component<IProps,any> {
    render(){
        return(
            <>
                <h1>{this.props.title}</h1>
            </>
        )
    }
}
// con simplemente colocarle any podemos darle una interface o podemos crear nuestra propia interface especificando cuales son las propiedades
// para nombrar la interface por lo usual se inicia con la letra "I" de interface y despues el nombre
interface IProps {
    title: string;
}

//componente function

const App = (props : IProps) => {
    return (
        <>
            <h1>{props.title}</h1>
        </>
    )
}

export default App;
```

- 3: estado
```tsx
import * as React from 'react';


//componente class

//ahora vamos a crear una interface para el estado
interface IState{
    task: [];
}

export class Appp extends React.Component<IProps,IState> {
    constructor(props: IProps){
        super(props);
        // es necesario especificar la propiedad task en el state
        this.state= {
            task: []
        };
    }

    render(){
        return(
            <>
                <h1>{this.props.title}</h1>
            </>
        )
    }
};

interface IProps {
    title: string;
}
//componente function

const App = (props : IProps) => {

    const [state, setstate] = React.useState([]);

    return (
        <>
            <h1>{props.title}</h1>
        </>
    )
}

export default App;

```

- 4: especificar tipo de dato
```tsx
import * as React from 'react';


//componente class

//ahora vamos a crear una interface para el estado
interface IState{
    task: [];
}
interface IProps {
    title: string;
}
export class Appp extends React.Component<IProps,IState> {
    constructor(props: IProps){
        super(props);
        this.state= {
            task: []
        };
    }
    //podemos especificar el tipo de dato
    // en este caso "e" es un tipo de dato que hace referencia a un evento html :  React.FormEvent
    // y este evento viene desde un evento fomulario: <HTMLInputElement> 
    
    handleNewTask = (e : React.FormEvent<HTMLInputElement>) =>{
        e.preventDefault();
    }

    render(){
        return(
            <>
                <h1>{this.props.title}</h1>
                <form onSubmit={e => this.handleNewTask}></form>
            </>
        )
    }
};


//componente function

const App = (props : IProps) => {

    const [state, setstate] = React.useState([]);
    const handleNewTask = (e : React.FormEvent<HTMLInputElement>) =>{
        e.preventDefault();
    }

    return (
        <>
            <h1>{props.title}</h1>
            <form onSubmit={e => handleNewTask}></form>
        </>
    )
}

export default App;
```

- 5: exportar interface
  - `Task.ts`:
```ts
export interface ITask{
    id: number;
    title: string;
    description: string;
    completed: boolean;
}
```

  - `App.tsx`:
```tsx
import * as React from 'react';
import {ITask} from "./Task"

//componente class

//vamos a indicarle que las tareas de la aplicacion es un arreglo que contiene multiples tareas:  tasks: ITask[]
interface IState{
    tasks: ITask[];
}
interface IProps {
    title: string;
}

interface ITaskFormProps{

}
export class Appp extends React.Component<IProps,IState> {
    constructor(props: IProps){
        super(props);
        this.state= {
            tasks: []
        };
    }
    
    // crearemos un metodo para agregar una nueva tarea al estado
    AddTask(task: ITask){
        this.setState({
            tasks: [...this.state.tasks, task]
        })
    }


    handleNewTask = (e : React.FormEvent<HTMLInputElement>) =>{
        e.preventDefault();
    }

    render(){
        return(
            <>
                <h1>{this.props.title}</h1>
                <form onSubmit={e => this.handleNewTask}></form>
            </>
        )
    }
};


//componente function

const App = (props : IProps) => {

    const [state, setstate] = React.useState([]);
    const handleNewTask = (e : React.FormEvent<HTMLInputElement>) =>{
        e.preventDefault();
    }

    return (
        <>
            <h1>{props.title}</h1>
            <form onSubmit={e => handleNewTask}></form>
        </>
    )
}

export default App;
`
```

