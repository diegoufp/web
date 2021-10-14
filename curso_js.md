# JavaScript
## VisualStudioCode
### Extenciones
- Prettier - code formatter
- Live Server
- ESLint


## Introduccion
### ISOMORFISMO
Hoy JavaScript, es el unico lenguaje capaz de ejecutarse en las 3 capas de una aplicacion:

1. Frontend (JavaScript)
2. Backend (Node.js)
3. Persistencia de Datos (MongoDB, Couch DB, Firebase, etc.)

### Con JavaScript puedes:
- Diseño y Desarrollo Web.
- Hacer Videojuegos.
- Experiencias 3D, Realidad Aumentada, Realidad Virtual.
- Controlar Hardware (Drones, robots, elecctrodomesticos)
- Aplicaciones Hibridas y Moviles.
- Machine Learning.
- etc.

### Caracteristicas
- Lenguaje de Alto Nivel.
- Interpretado.
- Dinámico.
- Débilmente Tipado.
- Multi paradigma.
- Sensible a MAYÚSCULAS y minúsculas.
- No necesitas los puntos y comas al final de cada línea.

### Escritura de codigo
Los **identificadores** deben comenzar con:
- Una letra o
- Un signo de dolar `$` o
- Un guión bajo `_`
- Nunca con números o caracteres especiales.

### Buenas practicas

Usa **snake_case** en:
- Archivos:
```
mi_archivo_javascript.js
```

Usa **UPPER_CASE** en:
- Constantes:
```js
const UNA_CONSTANTE = "Soy una constante",
  PI = 3.141592653589793;
```

Usa **UpperCamelCase** en:
- Clases:
```js
class SerHumano {
  constructor(nombre, genero) {
    this.nombre = nombre;
    this.genero = genero;
  }
```

Usa **lowerCamelCase** en:
- Objetos:
```js
const unObjeto = {
  nombre: "Jonathan",
  email: "jonmircha@gmail.com",
};
```

- Primitivos:
```js
let unaCadena = "Hola Mundo",
  unNumero = 19,
  unBoolean = true;
```

- Funciones:
```js
function holaMundo(nombre) {
  alert(`Hola mundo ${nombre}`);
}
holaMundo("Jonathan");
```

- Instancias:
```js
const ajax = new XMLHttpRequest(),
  jon = new SerHumano("Jonathan", "Hombre");
```

### Palabras reeservadas
```
A: abstract
B: boolean, break, byte
C: case, catch, char, class, const, continue
D: debugger, default, delete, do, double
E: else, enum, export, extends
F: false, final, finally, float, for, function
G: goto
I: if, implements, import, in, instanceof, int, interface
L: let, long
N: native, new, null
P: package, private, protected, public
R: return
S: short, static, super, switch, synchronized
T: this, throw, throws, transient, true, try, typeof
V: var, volatile, void
W: while, with
```

### Ordenamiento de código
- IMPORTACIÓN DE MÓDULOS.
- DECLARACIÓN DE VARIABLES.
- DECLARACIÓN DE FUNCIONES.
- EJECUCIÓN DE CÓDIGO.

### Tipos de datos en JavaScript

- **Primitivos**: Se accede directamente al valor.
    - string
    - number
    - boolean
    - null
    - undefined
    - NaN

- **Compuestos**: Se accede a la referencia del valor.
    - object = {}
    - array = []
    - function () { }
    - Class {}
    - etc.

## Tipos de datos

### Variables
partes donde puede guardar informacion.

- **var** : se utiliza para declarar una variable, esta hara que la varaible sea de ambito global. No es buena practica usarla, puede traer problemas de reasugnacion.
```js
var hola = "hola"
```

- **let**: se utiliza para declarar una variable, esta variable sera de ambito de bloque. Es buena practica usarlo.

```js
let hello = "hello"
```

- **const**: se utiliza para declarar variables que no vayan  a cambiar durante el flujo del programa, en el momento en el que es creada se le tiene que asignar un valor (solo en tipos de dato), los tipos de datos compuestos pueden ser cambiados en los valores que tienen de referencia.

```js
const PI = 3.1416
```

### Cadenas de texto (String)
Un objeto que representa una serie de caracteres dentro de una cadena.

Las propiedades son caracteristicas que estan describiendo algo del objeto.

Los metodos son acciones que el objeto hace.(estos terminan con parentesis)

El string tiene dos **propiedades** muy importantes:
- `string.propotype`
- `string.length` : La propiedad length de un objeto String representa la longitud de una cadena, en unidades de codigo UTF-16.

```js
// cadena de texto
let nombre = 'jon'; // acepta comillas simples
let apellido = "MirCha"; // acepta comillas dobles

let saludo = new String("Hola Mundo");

// se utiliza la palabra reservada ;new; que es un operador 
// new me va a permitir crear un objeto nuevo de un cierto tipo de dato 
// esta forma de crear un string es muy formal y nadie la utiliza 
```

Algunos **metodos**:
- `string.toUpperCase()` : convierte la palabra usando letras mayusculas

- `string.toLowerCase()` : convierte la palabra usando minusculas

- `string.includes("")` : buscar si en la cadena se encuentra alguna palabra en especifico, regresa un true o false.

- `string.trim()` :  lo que hacer es quitar los espacios en blanco que existen a lo largo del texto(cuando son mas de un espacio al mism tiempo).

- `string.split(",")` : generar un array con las palabras separadas con algun signo o letra.

### Numeros (Numbers)

```js
let a = 2;
let b = new Number(1);
let c = 7.19;
```

Algunos **metodos**:

- `.toFized(1)` :  me dice cuantos numeros decimales va a tener un valor numerico (si tiene pocos los redondea)

- `parseInt(x)` : devuelve solo la parte entera sin lso decimales, tambien puede cambiar del tipo de datos de string a entero.

- `parseFloat(x)`: imprime tanto la parte entera como la parte flotante, tambien puede cambiar del tipo de datos de string a entero y flotante.

- `typeof(x)` :  nos dice de que tipo de naturaleza es una variable 

### Bolleans

```js
let verdadero = true
let falso = false
let v = Boolean(true);
let f = Boolean(false);
```

Los **Truthy** son valores que no son ni verdadero ni falso pero que tienden a valores verdadero o a valores falsos.

```js
// Valores que tienden a verdadero
if (true)
if ({})
if ([])
if (42)
if ("0")
if ("false")
if (new Date())
if (-42)
if (12n)
if (3.14)
if (-3.14)
if (Infinity)
if (-Infinity)
```
```js
//valroes que tienden a falso
if (false)
if (null)
if (undefined)
if (0)
if (-0)
if ('')
if (0n)
if (NaN)
if ("")
```

### undefined, null & NaN

- `null` : represanta un valor ausente. es una valor especial, es un valor initencionalmente asignado por el programador.`let nulo = null;`

- `undefined` : represanta un valor ausente. es un variable que no a sido inicializada.(en pocas palabras es una variable que no tiene valor)

- `NaN` : nos dara NaN cuando hagamos operaciones con algo que no sea un numero. `let noEsUnNumero = "hola" * 3.7`

### Funciones
Es un bloque de codigo auto contenido que contiene instrucciones, se va a definir una sola vez y que se puede ejecutar en cualquier momento.

Una funcion puede o no recibir paramentros, puede devolver o no valores.

Las funciones tambien se consideran objetos.

**Declarar** una funcion:
- Funcionn declarada
```js
// - Funcionn declarada
function estoEsUnaFuncion() {
  console.log("uno")
  return "dos" //con return la funcion devulvera un valor
}
//  Invocacion de funciones
let valor = estoEsUnaFuncion();
```
```js
//funcion anonima
const funcionExpresada = function() {}
// Esto es una funcion expresada, es decir, una funcion que se le ha asignado como valor a una variable, si invocamos esta funcion antes de su definicion JS nos dara error
```
```js
//funciones flecha
const funcionExpresada = () => {}

```

Hacer que una funcion reciba valores:
```js
function saludar(nombre, edad) {
  console.log(`Hola mi nombre es ${nombre} y tengo ${edad} años`)
} 

// para asignarle valores por defecto
function saludar(nombre = "Desconocido", edad = 0) {
  console.log(`Hola mi nombre es ${nombre} y tengo ${edad} años`)
} 
```

Funciones declaradas VS funciones expresadas:

las funciones de javascript puede invocarse en cualquier momento, incluso antes de que la funcion sea declarada.
```js
//  Invocacion de funciones
let valor = estoEsUnaFuncion();

// - Funcionn declarada
function estoEsUnaFuncion() {
  console.log("uno")
  return "dos" //con return la funcion devulvera un valor
}
```
```js
funcionExpresada();


//funcion anonima
const funcionExpresada = function() {}
// Esto es una funcion expresada, es decir, una funcion que se le ha asignado como valor a una variable, si invocamos esta funcion antes de su definicion JS nos dara error
```

### Arreglo (arrays)

El length inicia con el elemento 0.

Manera de **declarar** arreglos:
```js
const a = [];
const c = Array.of("x","y");
const d = Array(100).fill(false) //esto lo que hara sera crear un array de 100 con el valor de false
const e = new Array(1,2,3,true);
```

Algunas **Propiedades** de los arrays:
- `.length`

Metodos de los array:
- `variable.push("")` : agrega un nuevo elemento al array

- `variable.pop()` :  quitar el ultimo elemento de un array.

- `variable.forEach(function(e,index){})` : recibe una funcion que se va ejecutar por cada elemento que tenga.
se le puede poner hasta dos parametros

### Objetos
En javascript todo es un objeto

Un objeto es una coleccion de llaves valores

maneras de **declarar** un objeto:
```js
const a = new String("hola");
const b = {nombre: "diego", apellido: "fernandez", funct: funcion(){}}
```

maneras de **acceder** a un objeto:
```js
b["nombre"]
b.apellido //esta es la mejor manera de aceder a las propiedades o metodos o atributos de un objeto

b.funct() //esta es la manera para aceder al metodo de un objeto
```

**Dentro** de un objeto: 
- A las variables se les van a llamar atributos/propiedades.
- A las funciones se les van a llamar metodos.

Para hacer uso de una propiedad **dentro del objeto**:
```js
const jon = {
  nombre: "jon",
  apellido: "mircha",
  decirMiNombre: function(){
    console.log(`Hola me llamo ${this.nombre} ${this.apellido}`)
  }
}

// en pocas palabras this hacer referencia al objeto mismo en el cual se esta trabajando
```

Algunos **metodos** de los objetos:
- `Object.keys(jon)` : Permite listar todas las llaves del objeto

- `Object.values(jon)` : forma un arreglo de los valores que contienen las llaves.

- `jon.hasOwnProperty("nombre")` : Permite saber si un objeto tiene una propiedad en especifico.

## Tipos de Operadores.

- **Aristmeticos**:
  - `+`
  - `-`
  - `*`
  - `/`
  - `%` : el modulo devuelve el residuo de una division.
  - `()`

- **Relacional**
  - `>`
  - `<`
  - `>=`
  - `<=`
  - `=` : asignacion
  - `==` : comparacion de valores.`"7" == 7`
  - `===` : comparacion de tipo de dato y valor.`7 === 7`.

- **Incremente Decremento**
  - `+=`
  - `-=`
  - `/=`
  - `*=`

- **operador unario**
  - `i++`
  - `i--`

- **Logicos**
  - `!` : Not
  - `||` : Or
  - `&&` : And

## Condicionales

Una estrucutra de control aquel mecansimo que permite controlar el flujo del programa

- `if - else` : es una condicion en la programacion, si la condicion se cumpre se estaria ejecutanro el rpograma dentro del if.
```js
if(){

}else if(){

}else{}
```

**Operador Ternario**: 
```js
let eresMayor = (edad >= 18) ? "Eres mayor de Edad": "Eres menor de Edad"

//es una manera simplificada de un if - else
```

- `switch - case` : nos va a servir cuando tengamos que diferentes valores para una misma variable.
```js
/*
Domingo 0
sabado 6
*/
let dia = 0;
switch (dia){
  case 0:
  console.log("Domingo")
  break;
  case 6:
  console.log("Sabado")
  break;
  default:
  console.log("EL dia no existe");
  break;
}
```

## Ciclos (Loops)
- `while` : mientras una condicion se cumpla se ejecutara el codigo en forma de bucle.
```js
let contador = 0;

while(contador < 10)
  contador++;
```

- `do while` : es parecido al while pero primero se ejecuta el codigo y despues pregunta si se cumple la condicion.
```js
let contador = 0;
do {

} while (contador < 10)
```

- `for` : un while mas completo.
```js
//estructura
for (inicializacion de la variable; condicion; decremento o incremento) {
  sentencia a ejecutar
}
```
```js
//ejemplo
for (let i =0; i< 10; i++){
  console.log("for" + i);
}
```
```js
//otro ejemplo
let numeros  = [10,20,30,40,50,60,70]

for (let i = 0; i < numeros.length; i++){

}
```

- `for - in` : perite iterar las propiedades de cualquier objeto que sea iterable.
```js
const jon = {
  nombre: "Jon",
  apellido: "MirCha",
  edad: 35
  }
for (const propiedad in jon){
  // si queremos acceder a las llaver a los valores
  console.log(`key: ${propiedad}, values: ${jon[propiedad]}`)
}
```

- `for - of` : Va a permitir recorrer todos los elementos de cualquier objeto que sea iterable en javascript.
```js
let numeros  = [10,20,30,40,50,60,70]
for (const elemento of numeros) {
  console.log(elemento)
}
```

### break & continue
Estas instucciones nos van a ayudar un poco a mejorar nuestra estrucutra en nuestro codigo en terminos de flujo.

- `break`: permite salirse de la estructura en la que esta. en caso de estar dentro de una funcion breack haria que termine la funcion.

- `continue`: se salta la iteracion en la que esta el continue y va a seguir con la siguiente iteracion.

## Manejo de errores

Para el manejo o deteccion de errores javascript tiene un mecnismo que de alguna manera parece a aun if - else.

```js
try {
  //aqui vamos a escribir nuestro codigo
  // cuando ocurre un error se termina de ejecutar el codigo que este por debajo del error
}catch(error){
  // cuando ocurre algun error en el try entonces carch lo va a capturar 
  // captura cualquier error surgirdo o lanzado en el try
}finally {
  //el bloque finally se ejecutara siempre al final de un bloque try-catch
  // es decir que haya error o no siempre se va a ejecutar el bloque del finally
  // usualmente no se usa el finally
}
```

```js
// ejemplo de error personalizado
try{
  let numero = "y";
  if (isNaN(numero)){
    //con throw estariamos creando el error personalizado
    // javascript tiene diferentes errores, el error estandar generico es Error
    throw new Error("El caracter introducido no es un numero")
  }

}catch(error){

}
```

## Destructuración
la destructuracion es una nueva forma de asignar valores sobre todo a arreglos y a objetos.

- Arreglos:
```js
const numeros = [1,2,3]
// sin destructuracion
let uno = numero[0],
    dos = numeros[1],
    tres = numeros[2];

// con destructuracion
const [one,two,three] = numeros;
```

- objetos:
```js
const persona = {
  nombre: "jon",
  apellido: "MirCha",
  edad: 35
}
// con destructuracion
let {nombre , apellido, edad} = persona
// para que la destructuracion funcione en los objetos es muy importante que la variable que trato de crear se llame igual que la propiedad de la variable que queremos aislar
```

### Objetos literales

Es una forma nueva de escribir atributos y metodos, incluso de asignarlos

```js
let nombre = "kenai",
edad = 7;

const perro = {
  nombre: nombre,
  edad: edad,
  ladrar: function() {
    console.log("wau!!")
  }
}

// con las nuevas caracteristicas de los literales
// si la variable que vas a asignarle como valor a una propiedad del objeto tiene el mismo nombre de la propiedad que estas queriendo asignar, se puede simplificar:
// los metodos tambien podemos siemplificarlos
const dog = {
  nombre,
  edad,
  ladrar(){
    console.log("guau!!")
  }
}

```

## Parámetros REST & Operador Spread

- **Parámetros REST** :  son una forma de virtualmente ir agregando **paramentros** infinitos, ya sea a una funcion o dentro de una variable.

Para definir los parametros REST simplemente hay que definirlos anteponiendoles 3 puntos suspensivos `...` antes del nombre donde estan guardados esos posibles valores infinitos 

```js
function sumar(a,b, ...c){
  let resultado = a + b
  c.forEach(function(n){
    resultado += n
  });
  return resultado;
}

console.log(sumar(1,2));
console.log(sumar(1,2,3,4,5,6));
```

- **Operador Spread** : Nos permite que cuandpo una expresiento la tengamos que expandir en situaciones en donde tengamos que guardar o almacenar multiples argumentos o elementos, lo podamos hacer.

funciona en cualquier sentencia del codigo.

```js
const arr1 = [1,2,3,4,5],
arr2 = [6,7,8,9,0]

const arr3 = [arr1,arr2] // [array(5)][array(5)]

const arr3 = [...arr1,...arr2] //[1,2,3,4,5,6,7,8,9,0]
```

## Arrow Functions
Es una nueva forma para definir funciones anonimas, funciones anonimas que sean expresadas.

Una funcion expresada es cuando a una variable le asignas el valor de una funcion anonima 
```js
// definir una arow funcion
const saludar = () => {}
// contiene un return implisito
```

```js
//ejemplo
const numeros = [1,2,3,4,5];

numeros.forEach((el,index) => {
  console.log(`${el}:${index}`)
  });

```

Una de las caracteristicas que tienen las arrow function es que capturan el objeto this del contexto en que se encuentren.

```js
const perro = {
  nombre: "kenai",
  ladrar: function(){
    console.log(this)
  }
}
perro.ladrar()//este devuelve el this del objeto perro

const gato = {
  nombre: "kenai",
  maullar(){
    console.log(this)
  }
}
gato.maullar()//este devuelve el this del objeto gato


const dog = {
  nombre: "kenai",
  ladrar: ()=>{
    console.log(this)
  }
}
dog.ladrar() //este devuelve el this del objeto window
```

Se tiene que tener cuidado con las arrow function dentro de los objetos

##  Prototipos

Aun que en JavaScript existen las clases gramaticalmente, realmente javascript sigue funcionando basado en prototipo.

En programacion orientada objetos hay 4 conceptos muy importantes que debemos entender: 
- `Clases` : Modelo a seguir.
- `Objetos` : Un objeto es una intacia de una clase.  Los objetos van a tener dos facultades importantes:
  - `Atributos` : Es una caracteristica o propiedad del objeto.(son variables dentro de un objeto)
  - `Metodos` :  Son las acciones que un objeto puede realizar.(son funciones dentro de un objeto.)


**Funcion Construcutora**
Una funcion que vamos a construir una sola vez y apartir de ella voy a generar nuevas instancias, nuevos objetos que sean de este tipo de funcion.

De hecho una funcion en si genera un prototipo vacio.
```js
// vamos a crear una funcion constructora de la cual vamos a crear un prototipo
function Animal(nombre,genero){
  this.nombre = nombre;
  this.genero = genero;
  //estos vendrian siento los atributos de la funcion constructora 
  // funado estemos trabajando con funciones constructoras en javascript tanto los atributos como los metodos tienen que colgar desde el objeto this
  this.sonar = function(){}
}
// new nos va a permitir crear una nueva intancia del tipo que le especifiquemos
const snoopy = new Animal("Snoopy","Macho"),
  lolaBunny = new Animal("Lola Bunny","Hembra");
```
```js
// la forma ideal seria asignarle los metodos al prototipo, no a la funcion como tal

function Animal(nombre,genero){
  this.nombre = nombre;
  this.genero = genero;
}

Animal.prototype.sonar = function(){}
// asi cada vez que nosotros generemos una nueva variable de tipo Animal pue sla funcion solamente tiene la asignacion de los atributos
// y los metodos se le van a quedar solamente a ese prototipo animal
// es decir que va a evitar que las nuevas variables esten duplicando los metodos y pues eso va a mejorar mucho el rendimiento y espacio en memoria de nuestras aplicaciones 
```
De esta forma lograriamos que la funcion sonar este colgada del prototipo Animal, no de la instancia como tal del objeto que hemos generado.

Logramos una mejora muy importante a nivel de rendimiento y de programacion.

## Herencia Prototípica

La caracteristica de poder heredar caracteristicas de un padre a un hijo
```js
//este es el codigo de la anterio infromacion
function Animal(nombre,genero){
  this.nombre = nombre;
  this.genero = genero;
}
Animal.prototype.sonar = function(){}
//Herencia prototipica
funcion Perro(nombre,genero,tamanio) {
  //cuando tratamos de hacer la herencia tenemos un metodo llamado:
  //super , el cual manda a llamar el constructor de la clase padre, este se usa en las clases pero en este caso crearemos uno de manera manual
  this.super = Animal;
  this.super(nombre,genero);
  this.tamanio = tamanio;
}
//Perro esta heredando de Animal
Perro.prototype = new Animal();
Perro.prototype.constuctor = Perro;
```

Cuando una clase hija, en la programacion orientada a objetos hereda los metodos de una clase padre, hablando de los prorotipos, al ser Perro una clase que hereda todo lo de animal puede utilizar sus respectivos metodos como sonar y saludar.

Podemos tambien sobreescribir de los metodos del padre.
```js
// sobreescritura de metodos del prototipo padre en el hijo
Perro.prototype.sonar = function(){}
// creamos un nuevo metodo
Perro.prototype.ladrar = function(){}
```

## Clases y Herencia
Apartir del 2015 nostros en javascript ya podemos escribir clases.

Javascript es un lenguaje orientado a objetos que estan basado en prototipos, aun que nosotros gramatical y sintacticamente escribamos nuestras clases, javascript eso lo va a compilar a prototipos.

```js
// las clases no reciben paramentos, para poder recibir parametros a la hora de que creamos un objeto de este tipo de clase :
// las clases tienen un metodo especial que se llama constructor, esmetodo es justamente el que va a recibir las propiedades
class Animal{
  constructor(nombre,genero){
    this.nombre = nombre;
    this.genero = genero;
  }
  // los metodos se definen de esta manera
  // los metodos si puden recibir parametros
  sonar(){}
  saludar(){
    console.log(`Hola me llamo ${this.nombre}`)
  }
}

//invocacion de la clase
const mimi = new Animal("Mimi","Hembra");
const.log(mimi);
```

**Herencia**
```js
//para pedirle a la nueva clase que herede el prototipo Animal lo hacemos con extends
class Perro extends Animal{
  constructor(nombre,genero,tamanio){
    //con el metodo super() se manda a llamar el constructor de la clase padre
    super(nombre,genero);
    this.tamanio = tamanio;
  }
  //sobreescritura de sonar
  sonar(){}
  //nuevo metodo ladrar
  ladrar(){}
}
```

## Métodos estáticos, getters y setters
Nosotros no podemos hacer que una clase tenga metodos o atributos privados, por que esto significaria que dichos metodos o atributos solamente los vamos a poder utilizar dentro del cuerpo de la clase.
```js
class Perro extends Animal{
  constructor(nombre,genero,tamanio){
    super(nombre,genero);
    this.tamanio = tamanio;
  }
  //si hacer un metodo privado solo lo podriamos usar dentro de la clase
  private sonar(){}
  
  ladrar(){}
}

const mimi = new Perro("Mimi","Hembra", "Gigante");
// si tratamos de usar sonar desde fuera de la clase va a marcar un error por que ahora es privado
mimi.sonar()
```
Todas las clases que creamos dentros de javascript son publicas.

Sin embargo hay ciertas caracteristicas que si existen en la escritura de clases que nos da javascript.Por ejemplo uno de ellos son los metodos estaticos 

**Metodos estaticos**
Un metodo estatico es aquel que se puede ejecutar sin necesidad de instanciar la clase.
```js
class Perro extends Animal{
  constructor(nombre,genero,tamanio){
    super(nombre,genero);
    this.tamanio = tamanio;
  }
  // para volver un metodo estatico simplemente le tenemos que poner la palabra static
  // este es un metodo que puede ser ejecutado sin la necesidad de haber creado un objeto del tipo al que pertenece la clase
  static sonar(){}
  
  ladrar(){}
}

Perro.sonar();
```

**setters y getters**
Son metodos especiales que nos permiten establecer y obtener los valores de atributos de nuestra clase 

```js
class Perro extends Animal{
  constructor(nombre,genero,tamanio){
    super(nombre,genero);
    this.tamanio = tamanio;
    this.raza = null;
  }
  //generalmete lo que se hace para detectar que son metodos setters y getters es:
  // antemonerle el verbo en el nombre de la funcion
  // para indicarle que es metodo de tipo obtenedor ponemos get al inicio 
  get getRaza(){
    return this.raza;
  }
  // para generar un metodo establecedor que modifique dicha propiedad entonces definimos set 
  set setRaza(raza){
    this.raza = raza;
  }
}
const mimi = new Perro("Mimi","Hembra", "Gigante");
// este tipo de metodos se utilizan como si fueran atributos 
console.log(mimi.getRaza);
// para asignarle un nuevo valor
mimi.setRaza = "Gran Danes";
console.log(mimi.getRaza);
```

### Objeto console
`console.log()` : Se utiliza para imprimir en la consola.

`console.error("Esto es un error")` : Imprimir errores en la consola.

`console.warn()`: imprimir warning en la consola.

`console.info()` : imprime informacion en la consola, es parecido al console.log().

`console.clear()` : Limpiar la consola.

`windonw` : representa la ventana del navegador.

`document` : la representacion del documento html atravez de javascript.

`console.dir()`: cuando se quiera representar un elemento como si fuera un objeto de javascript.

`console.dir(docuemnt)`: muestra todas las propiedades, objetos metodos, atributos del document.

`console.log(document)` : muestra el codigo html

`console.group()` : indicar que vas a agrupar informacion en la consola.

`console.groupEnd()`: Indicar que vas a finalizar la agrupacion en consola.

`console.groupCollapsed()`:indicar que vas a agrupar informacion en la consola.

`console.table()` : dibujar en una tabla en la consola.

`console.time("cronometro")`: inicio de la conometracion, se le pueda poner un nombre de etiqueta pero se tiene que poner el mismo en el timeEnd y en el time

`console.timeEnd("cronometro")`: Indicacion de finalizacion de cronometracion.

`console.count()` : Contar una accion.

`console.assert()` : hacer pruebas.Ejemplo:
```js
let x = 3, y = 2, pruebaxy = "Se espera que X siempre sea menor que Y";

console.assert(x<y, {x,y,pruebaxy});
```

##  Objeto Date

`console.log(Date())` : imprime la fecha, hora y zona horaria

```js
let fecha = new Date();
console.log(fecha);
console.log(fecha.getDate()); //devuelve el dia del mes
// dia de la semana D L M MI J V S -> 0 1 2 3 4 5 6
console.log(fecha.getDay()); //devuelve el dia de la semana 
//mes Ene Feb Mar Abr May Jun Jul Ago Sep Oct Nov Dic -> 0 1 2 3 4 5 6 7 8 9 10 11
console.log(fecha.getMonth()); // devuelve el numero del mes
console.log(fecha.getFullYear()); // devuelve el año
console.log(fecha.getHours()); //devuelve las horas en formato de 0 a 23 horas, no hay am ni pm
console.log(fecha.getMinutes()); // obtienes los minutos
console.log(fecha.getSeconds()); //obtienes los sgundos
console.log(fecha.getMilliseconds()); //obtiene los milisegundos 

console.log(fecha.toString()); // un mejor formato para mostrar los datos de tiempo mes,semana,año y hora, zona horaria
console.log(fecha.toDateString()); //un mejor formato para mostrar los datos de tiempo mes,semana,año

console.log(fecha.toLocaleString()); // un mejor formato de mostrar la fecha y hora

console.log(fecha.toLocaleDateString()); // formato reducido para la fecha

console.log(fecha.toLocaleTimeString()); // formato de hora

console.log(fecha.getUTCDate) // la hora del meridiano 0

console.log(Date.now) // los segundos que an pasado desde el primero de enero de 1970, es lo que se conoce como la dichosa fecha timestamp
```
Una libreria muy potente para el manejo de los tiempos en javascrip es [Moment.js](https://momentjs.com/)

### Objeto Math

`Math` : es un objeto estatico, se invoca sin parentesis, permite sacar potencias, raizes cuadradas.

`Math.PI` : el valor de pi

`Math.abs()` : nos devuelve el valor absoluto de un numero, (el valor absoluto es la cantidad sin signo positivo o negativo)

`Math.ceil()` : Permite redodndear el numero al numero entero posterior inmediato. 
```js
Math.ceil(7.2)//8
Math.ceil(7.6)//8
```

`Math.floor()`: redondea numero inmediato entero menor.
```js
Math.floor(7.8)//7
Math.floor(7.2)//7
```

`Math.round()`: redondea al numero mas cercano inmediato.
```js
Math.round(7.5)//8
Math.round(7.49)//7
```

`Math.sqrt()`: calcula la raiz cuadrada de un numero.

`Math.pow()` : eleva un numero a cierta potencia
```js
Math.pow(2,5) // 2 elevado a la potencia 5 = 32
```

`Math.sign()`: indica si el numero es positivo negativo o 0. retorna -1, 0 o 1

`Math.random()` : numero aleatorio comprendido entre 0 y 1.

## Operador de Cortocircuito
Los operadores de corto sircuito funcionan poniendo dos condiciones, ya sea potiendo el operador logico `or` o el operador logico `and`.

- **Contocircuito OR**: cuando el valor de la izquierda en la expresion siempre pueda validar a true, es el valor que se cargara por defecto.
```js
function saludar(nombre){

  nombre = nombre || "Desconocido"; //este es un operador cortocircuito
}

console.log(false || "Valor de la derecha")
//imprimira: Valor de la derecha
console.log(true || "Valor de la derecha")
//imprimira: true
```

- **Cortocircuito AND**: cuando el valor de la izquierda en la expresion siempre pueda validar a flase, es el valor que se cargara por defecto.
```js
console.log(false && "Valor de la derecha")
//imprimira: false
console.log(true && "Valor de la derecha")
//imprimira: Valor de la derecha
```

El perador de cortosircuito usualmente se utiliza en react.js

## alert, confirm y prompt
Metodos importantes para interactuar con el usuario.

se pueden usar sin el window.

`window.alert()` : alerta para interactuar con el usuario.

`window.confirm()` : alerta de confimacion

`window.prompt()`: permite que el usuario ingrese un valor, es un input dentro de un alert

## Expresiones Regulares
Las expresiones regulares son una secuencia de caracteres que forman un patron de busqueda, principalmente es utilizado en la busqueda de cadenas de texto.por ejemplo para validar que los caracteres que se ingresen en un impunt de correo electronico sean correctas.

```js
//definir una expresion regular
let cadena - "Lorem ipsum dolor"
let expReg = new RegExp("lorem", "g");//pide dos parametros
// con la bandera "g" le estamos diciendo que busque todas las coincidencias las veces que se repitan
// la bandera "i" significa que va a ignorar mayusculas y minusculas

//la segunda manera de definir una expresion regular
let expReg2 = /lorem/g;

console.log(expReg.test(cadena)); //probar que la expresion regular exista dentro de la cadena.devuelve verdadero o falso
console.log(expReg.exec(cadena)); //devuelve un arreglo con informacion de las coincidencias y algunas propiedades.
```

## Funciones Anónimas Autoejecutables
Significa que es una funcion en la cual se engloba todo el codigo que se quiere ejecutar.

Es una manera en la que en el momento de que el archivo cargue en el navegador se ejecuta la programacion que esta en ese archivo y aparte esta protegido de efectos secundarios que pudiera tener la invocacion de librerias de terceros o de otros mismo archivos de programacion que tu mismo haya hecho. Tambien permite pasar parametros de una manera mas facil.

```js
//funcion anonima auto ejecutable
(function(){})(); //este seria basciamente la estructura 


(function(d,w,c){
  console.log(d)//se imprimiria el documento
  console.log(w) //se imprimiria el window
  console.log(c) //se imprime el console 
})(document,window,console);//basicamente en estos parentesis se estaria dando los parametros
```

```js
//formas de escribir las funciones anonimas autoejecutables
//clasica
(function(){})();

//La crockford (JavaScript The God Parts)
((function() {}) ());

//Unitaria
+function(){}();

//Facebook
!function(){}();
```

## Módulos ( import / export )
```js
// modulos.html
//salvo casos especiales donde se indiquen algunas librerias, la mayoria de ocaciones los archivos javascript tienen que estar invocados antes del cierre de la etiqueta body
// esto por que el archivo js es bloqueante, si tus archivos son muy pesado o son muchos archivos los que estas mandando a llamar, eso puede hacer que tarde el navegador en cargar pagina 
<head>
</head>
<body>
<script src="modulos.js" type="module"></script> 
</body>
// para que el archivo javascript tenga la capacidad de mandar a llamar internamente otros archivos javascript en muy importante que a la etiqueta script le pongamos un atributo llamado type="module"
// si no tenemos el type="module" en la invocacion del script simplemente las importaciones van a marcar error 
```
```js
//modulos.js
// al exportar por defecto se tiene que importar fuera de las llaves
import saludar as saludo,{PI,sumar,aritmetica} from "./constantes.js"

console.log(sumar(3,4));//7
console.log(aritmetica.restar(3,4));//-1
saludo()
```
```js
//constantes.js
export const PI = 3.1416;

export function sumar(a,b){
  return a + b;
}

export function restar(a,b){
  return a - b;
}

export const aritmetica = {
  sumar,
  restar
};
// esto permite que solamente se exporte lo que necesites e indiques

// si queremos que una funcion se importe por defecto
// cuando mandas a llamar en formato de modulo ese archivo es la funcion que se va a ejecutar

export default function saludar(){
  console.log("Hola")
};
// solo se puede exportan una funcion o variable o clases de manera por default
```

##  Ejercicios de Lógica de Programación
### 1/10

1. Programa una función que cuente el número de caracteres de una cadena de texto, pe. miFuncion("Hola Mundo") devolverá 10.
```js
try {function miFuncion(cadena){
    cadena = cadena.toString()
    console.log(cadena.length)
    };
} catch(error){
    console.log("Ocurrio un error")
}
let alerta = prompt("ingresa una palabra")
miFuncion(alerta);
```

2. Programa una función que te devuelva el texto recortado según el número de caracteres indicados, pe. miFuncion("Hola Mundo", 4) devolverá "Hola".
```js
try {
    function miFuncion(cadena,numero){
    const expReg = /\D/
    if (expReg.test(numero) == false){console.log(cadena.substring(0,numero));
    }else{
        throw new Error("El caracter introducido no es un numero")
    }
} 
} catch(error){
    console.log(error)
}
let palabra = prompt("ingresa una palabra")
let numero = prompt("ingresa un numero")

miFuncion(palabra, numero)
```

3. Programa una función que dada una String te devuelva un Array de textos separados por cierto caracter, pe. miFuncion('hola que tal', ' ') devolverá ['hola', 'que', 'tal'].
```js
function miFuncion(cadena,caracter){
    console.log(cadena.split(caracter))
}

miFuncion('hola que tal', ' ')
```

4. Programa una función que repita un texto X veces, pe. miFuncion('Hola Mundo', 3) devolverá Hola Mundo Hola Mundo Hola Mundo.
```js
function miFuncion(cadena,cantidad){
    let now = cadena;
    for (let i = 0; i < cantidad - 1;i++){
        now = now + " " + cadena;
    }
    console.log(now)
}

miFuncion('Hola Mundo', 3) 
```
###  2 / 10
5. Programa una función que invierta las palabras de una cadena de texto, pe. miFuncion("Hola Mundo") devolverá "odnuM aloH".
```js
try {
    function miFuncion(cadena){
    let invertido = cadena.split('').reverse().join('')
    console.log(invertido);
} 
} catch(error){
    console.log(error)
};
let palabra = prompt("ingresa una palabra");


miFuncion(palabra);

```
6. Programa una función para contar el número de veces que se repite una palabra en un texto largo, pe. miFuncion("hola mundo adios mundo", "mundo") devolverá 2.
```js
try {
    function miFuncion(cadena,palabra){
    let particion = cadena.split(palabra);
    let veces = particion.length - 1;
    console.log(`La palabra se encuentra ${veces} veces.`)
} 
} catch(error){
    console.log(error)
};
let cadena = prompt("ingresa una frase");
let palabra = prompt("ingresa una palabra");

miFuncion(cadena, palabra);
```
7. Programa una función que valide si una palabra o frase dada, es un palíndromo (que se lee igual en un sentido que en otro), pe. mifuncion("Salas") devolverá true.
```js
try {
    function miFuncion(cadena){
    let sin_espacios = cadena.replaceAll(" ","").toLowerCase();
    let invertido = sin_espacios.split('').reverse().join("");
    if(sin_espacios === invertido){
        console.log(true);
    }else{
        console.log(false);
    };
} 
} catch(error){
    console.log(error)
};
let cadena = prompt("ingresa una frase");

miFuncion(cadena);
```

8. Programa una función que elimine cierto patrón de caracteres de un texto dado, pe. miFuncion("xyz1, xyz2, xyz3, xyz4 y xyz5", "xyz") devolverá  "1, 2, 3, 4 y 5.
```js
try {
    function miFuncion(cadena,patron){
    console.log(cadena.replaceAll(patron, ""));
} 
} catch(error){
    console.log(error)
};
let cadena = prompt("ingresa una frase");
let patron =  prompt("ingresa una patron");

miFuncion(cadena, patron);
```

### 3 / 10 
9. Programa una función que obtenga un numero aleatorio entre 501 y 600.
```js
try {
    function miFuncion(){
    let numero = (Math.random() * 100) + 500;
    console.log(Math.ceil(numero))
} 
} catch(error){
    console.log(error)
};


miFuncion();
```
10. Programa una función que reciba un número y evalúe si es capicúa o no (que se lee igual en un sentido que en otro), pe. miFuncion(2002) devolverá true.
```js
try {
    function miFuncion(numero){
    let expReg = /\D/g;
    let sin_espacios = numero.replaceAll(" ",'');
    if ( expReg.test(sin_espacios) == false){
        let invertido = numero.split('').reverse().join('');
        if (invertido == sin_espacios){
            console.log(true)
        }else{
            console.log(false)
        }
    }else{
        console.log("Ingresaste algo que no es un numero")
    }
} 
} catch(error){
    console.log(error)
};
let numero = prompt("ingresa una palabra");


miFuncion(numero);
```
11. Programa una función que calcule el factorial de un número (El factorial de un entero positivo n, se define como el producto de todos los números enteros positivos desde 1 hasta n), pe. miFuncion(5) devolverá 120.
```js
try {
    function miFuncion(numero){
    expReg = /\D/g
    if (expReg.test(numero) == false){
        numer = parseInt(numero);
        let factorial = 1;
        for(let i = 2;numer >= i;i++){
            factorial = factorial * i;
        }
        console.log(factorial)
    }else{
        console.log("Se ingreso algo que no es un numero, solo acepta numero enteros")
    }
} 
} catch(error){
    console.log(error)
};
let numero = prompt("ingresa una palabra");


miFuncion(numero);
```

### 4 / 10
12. Programa una función que determine si un número es primo (aquel que solo es divisible por sí mismo y 1) o no, pe. miFuncion(7) devolverá true.
```js
try {
    function miFuncion(numero){
    expReg = /\D/g
    if(expReg.test(numero) == false){
      numer = parseInt(numero)
    const primos = [2]
    let verificador;
    if(numero => 2){
        for(let i = 3; i <= numer;i++){
            verificador = primos.every(elemento => i%elemento != 0);
            if (verificador == true){
                primos.push(i)
            }
        }
        if(numer === primos[primos.length - 1]){
            console.log(true)
        }else{
            console.log(false)
        }
    }else{
        console.log(false)
    }
    }
} 
} catch(error){
    console.log(error)
};
let numero = prompt("ingresa una palabra");


miFuncion(numero);
```
13) Programa una función que determine si un número es par o impar, pe. miFuncion(29) devolverá Impar.
```js
try {
    function miFuncion(numero,tipo){
    expReg = /\D/g;
    if (expReg.test(numero) == false){
        numer = parseInt(numero);
        if( numer%2 === 0){
            console.log("Par")
        }else{
            console.log("Impar")
        }
    }
}; 
} catch(error){
    console.log(error);
};
let numero = prompt("ingresa una palabra");


miFuncion(numero);
```
14. Programa una función para convertir grados Celsius a Fahrenheit y viceversa, pe. miFuncion(0,"C") devolverá 32°F.
```js
try {
    function miFuncion(numero,tipo){
    expReg = /\D/g;
    expRegl = /c|f/i;
    tipe = tipo.toString().toLowerCase()
    if ((expReg.test(numero) == false) && (expRegl.test(tipe) === true)){
        numer = parseFloat(numero);
        if(tipe === "c"){
            let celsius = (numer - 32) * 5 / 9;
            console.log(`${numer} grados fahrenheit equivalen a ${celsius} grados celsius. `)
        }else{
            if(tipe === "f"){let fahrenheit = (numer * 9 / 5) + 32;
                console.log(`${numer} grados celsius equivalen a ${fahrenheit} grados fahrenheit. `)}
        }
    }else{
        console.log("No se ingresaron los valores de la manera correcta, vuelva a intentarlo")
    };
}; 
} catch(error){
    console.log(error);
};
let numero = prompt("ingresa un valor");
let tipo = prompt("Ingresa C si si quiere convertir a celcius o F si quiere convertir a Fahrenheit")

miFuncion(numero,tipo);
```

### 5 / 10
15. Programa una función para convertir números de base binaria a decimal y viceversa, pe. miFuncion(100,2) devolverá 4 base 10.
```js
try {
    function miFuncion(numero,tipo){
    let expReg = /\D/;
    let expReg2 = /[^0-1]/;
    let expReg3 = /D|B/i;
    let tipe = tipo.toString().toLowerCase()
    if (expReg.test(numero) == false){
       if(tipe === "d"){
        if (expReg2.test(numero) == false){
            let decimal = 0;
            let cadena = numero.split("").reverse();
            cadena.forEach((element,index) => {
              decimal += (parseInt(element) * Math.pow(2,parseInt(index)));
            });
            console.log(decimal);
        }
       }else{
           if(tipe === "b"){
            let numer = parseInt(numero);
            let cadena = [0,0,0,0,0,0,0,0];
            for(let i = 8; i > 0; i--){
                if(numer >= Math.pow(2,i - 1)){
                    cadena[i - 1] = 1;
                    numer -= Math.pow(2,i - 1);
                }
            }
            let binario = cadena.reverse().join("");
            console.log(binario)
           }else{console.log("ocurrio un error al ingresar la opcion D o B, la opcion D solo acepta lenguaje binario para traducirlo a decimal")}
       }
    }else{
        console.log("No se ingresaron los valores de manera correcta, en la primera opcion solo acepta numeros y en la segunda solo D o B como opcion")
    };
}; 
} catch(error){
    console.log(error);
};
let numero = prompt("ingresa un valor");
let tipo = prompt("Ingresa B si quires traducir a lenguaje vinario o D si quieres traducir a decimal, la opcion D solo acepta lenguaje binario para traducirlo a decimal")

miFuncion(numero,tipo);
```
16. Programa una función que devuelva el monto final después de aplicar un descuento a una cantidad dada, pe. miFuncion(1000, 20) devolverá 800.
```js
function miFuncion(cantidad, porcentaje){
    try {
        expReg = /\D/;
        if((expReg.test(cantidad) == false) && (expReg.test(porcentaje) == false)){
            let resultado = parseFloat(cantidad) * (1 - (parseFloat(porcentaje)/100));
            console.log(resultado);
        }
    } catch (error) {
        console.log(`Se produjo un error \n ${error}`)
    }
}


let cantidad = prompt("Ingresa una cantidad");
let porcentaje = prompt("Ingresa un porcentaje");

miFuncion(1000, 20)
```

17. Programa una función que dada una fecha válida determine cuantos años han pasado hasta el día de hoy, pe. miFuncion(new Date(1984,4,23)) devolverá 35 años (en 2020).
```js
function miFuncion(fecha){
    try {
        expReg = /\D\s/;
        if(expReg.test(fecha) == false){
            resultado = new Date().getFullYear() - new Date(fecha).getFullYear();
            console.log(resultado)
        }else{
            console.log("se produjo un error en el if")
        };
       
    } catch (error) {
        console.log(`Se produjo un error \n ${error}`)
    }
}


let fecha = prompt("Ingresa una fecha con el formato: month day year");

miFuncion(fecha)
```

### 6 / 10
18. Programa una función que dada una cadena de texto cuente el número de vocales y consonantes, pe. miFuncion("Hola Mundo") devuelva Vocales: 4, Consonantes: 5.
```js
function miFuncion(cadena){
    try {
        expReg = /[aeiou]/g;
        expReg2 = /[a-z]/g;
        expReg3 = /\d/;
        if(expReg3.test(cadena) == false){
            const cad = cadena.toLowerCase();
            const vocales = [...cad.matchAll(expReg)];
            const letras = [...cad.matchAll(expReg2)];
            const consonantes = letras.length - vocales.length;
            console.log(`Vocales: ${vocales.length}, Consonantes: ${consonantes}`)

        }else{
            console.log("Se ingresaron caracteres no permitidos")
        }
       
    } catch (error) {
        console.log(`Se produjo un error \n ${error}`)
    }
}


let cadena = prompt("ingresa una cadena de texto sin numeros");

miFuncion(cadena)
```
19) Programa una función que valide que un texto sea un nombre válido, pe. miFuncion("Jonathan MirCha") devolverá verdadero.
20. Programa una función que valide que un texto sea un email válido, pe. miFuncion("jonmircha@gmail.com") devolverá verdadero.
```js

function miFuncion(cadena){
    try {
        const expReg = /^(([^<>()\[\]\\.,;:\s@”]+(\.[^<>()\[\]\\.,;:\s@”]+)*)|(“.+”))@((\[[0–9]{1,3}\.[0–9]{1,3}\.[0–9]{1,3}\.[0–9]{1,3}])|(([a-zA-Z\-0–9]+\.)+[a-zA-Z]{2,}))$/;
        if (expReg.test(cadena) == true){
            console.log(true)
        }else{
           console.log(false) 
        }

       
    } catch (error) {
        console.log(`Se produjo un error \n ${error}`)
    }
}


let cadena = prompt("ingresa un correo electronico");

miFuncion(cadena)


```

### 7 / 10
21. Programa una función que dado un array numérico devuelve otro array con los números elevados al cuadrado, pe. mi_funcion([1, 4, 5]) devolverá [1, 16, 25].
```js
function miFuncion(cadena){
    try {
        if(Array.isArray(cadena) == true){
            const cadena_nueva = cadena;
        const expReg = /\D/;
        cadena.forEach((elemento,index) => {
            if(expReg.test(elemento) == false){cadena_nueva[index] = parseFloat(elemento)* parseFloat(elemento)}else{console.log(`El elemento con el index ${index} no es un numero, es ${elemento}`)}
        });
        console.log(cadena_nueva)
        }else{console.log("el dato ingresado no es un array")}
        
    } catch (error) {
        console.log(`Se produjo un error \n ${error}`)
    }
}


miFuncion([1, 4, 5])

```
22. Programa una función que dado un array devuelva el número mas alto y el más bajo de dicho array, pe. miFuncion([1, 4, 5, 99, -60]) devolverá [99, -60].
```js
function miFuncion(cadena){
    try {
        if(Array.isArray(cadena) == true){
        const mayor_menor = [0,0];
        const expReg = /\D/;
        mayor_menor[1] = Math.min(...cadena);
        mayor_menor[0] = Math.max(...cadena);
        console.log(mayor_menor)
        }else{console.log("el dato ingresado no es un array")}
    } catch (error) {
        console.log(`Se produjo un error \n ${error}`)
    }
}


miFuncion([1, 4, 5, 99, -60])
```
23) Programa una función que dado un array de números devuelva un objeto con 2 arreglos en el primero almacena los números pares y en el segundo los impares, pe. miFuncion([1,2,3,4,5,6,7,8,9,0]) devolverá {pares: [2,4,6,8,0], impares: [1,3,5,7,9]}.
```js
function miFuncion(cadena){
    try {
        if(Array.isArray(cadena) == true){
        filtro = {
        pares : cadena.filter(x => x%2 == 0),
        impares : cadena.filter(x => x%2 != 0)
        }
        console.log(filtro)
        }else{console.log("el dato ingresado no es un array")}
    } catch (error) {
        console.log(`Se produjo un error \n ${error}`)
    }
}


miFuncion([1,2,3,4,5,6,7,8,9,0])
```


### 8 / 10

24. Programa una función que dado un arreglo de números devuelva un objeto con dos arreglos, el primero tendrá los numeros ordenados en forma ascendente y el segundo de forma descendiente, pe. miFuncion([7, 5,7,8,6]) devolverá { asc: [5,6,7,7,8], desc: [8,7,7,6,5] }.
```js

function miFuncion(cadena){
    try {
        if(Array.isArray(cadena) == true){
        const ascendente = cadena.sort((a,b) => a - b);
        const descendente = [...ascendente].reverse();
        const orden = {
            ascendente,
            descendente
        }
        console.log(orden);
        }else{console.log("el dato ingresado no es un array")}
    } catch (error) {
        console.log(`Se produjo un error \n ${error}`)
    }
}


miFuncion([7, 5,7,8,6]);
```

25. Programa una función que dado un arreglo de elementos, elimine los duplicados, pe. miFuncion(["x", 10, "x", 2, "10", 10, true, true]) devolverá ["x", 10, 2, "10", true].
```js
function miFuncion(cadena){
    try {
        if(Array.isArray(cadena) == true){
        const nueva_cadena = []
        cadena.forEach(elemento => {
            if ( nueva_cadena.every(element => element != elemento)){
                nueva_cadena.push(elemento)
            }
        })
        console.log(nueva_cadena)
        }else{console.log("el dato ingresado no es un array")}
    } catch (error) {
        console.log(`Se produjo un error \n ${error}`)
    }
}


miFuncion(["x", 10, "x", 2, "10", 10, true, true]);
```
26. Programa una función que dado un arreglo de números obtenga el promedio, pe. promedio([9,8,7,6,5,4,3,2,1,0]) devolverá 4.5.
```js
function miFuncion(cadena){
    try {
        if(Array.isArray(cadena) == true){
        let total = 0;
        cadena.forEach(elemento => {
            total += parseFloat(elemento);
        });
        console.log((total / cadena.length));
        }else{console.log("el dato ingresado no es un array")}
    } catch (error) {
        console.log(`Se produjo un error \n ${error}`)
    }
}


miFuncion([9,8,7,6,5,4,3,2,1,0]);
```

### 9 / 10
27. Programa una clase llamada Pelicula.

La clase recibirá un objeto al momento de instanciarse con los siguentes datos: id de la película en IMDB, titulo, director, año de estreno, país o países de origen, géneros y calificación en IMBD.
  - Todos los datos del objeto son obligatorios.
  - Valida que el id IMDB tenga 9 caracteres, los primeros 2 sean letras y los 
     7 restantes números.
  - Valida que el título no rebase los 100 caracteres.
  - Valida que el director no rebase los 50 caracteres.
  - Valida que el año de estreno sea un número entero de 4 dígitos.
  - Valida que el país o paises sea introducidos en forma de arreglo.
  - Valida que los géneros sean introducidos en forma de arreglo.
  - Valida que los géneros introducidos esten dentro de los géneros 
     aceptados*.
  - Crea un método estático que devuelva los géneros aceptados*.
  - Valida que la calificación sea un número entre 0 y 10 pudiendo ser 
    decimal de una posición.
  - Crea un método que devuelva toda la ficha técnica de la película.
  - Apartir de un arreglo con la información de 3 películas genera 3 
    instancias de la clase de forma automatizada e imprime la ficha técnica 
    de cada película.

* Géneros Aceptados: Action, Adult, Adventure, Animation, Biography, Comedy, Crime, Documentary ,Drama, Family, Fantasy, Film Noir, Game-Show, History, Horror, Musical, Music, Mystery, News, Reality-TV, Romance, Sci-Fi, Short, Sport, Talk-Show, Thriller, War, Western.

```js
class Pelicula{
    constructor(objeto){
        this.id = objeto.id,
        this.titulo = objeto.titulo,
        this.director = objeto.director,
        this.yearEstreno = objeto.yearEstreno,
        this.paisOrigen = objeto.paisOrigen,
        this.genero = objeto.genero,
        this.calificacion = objeto.calificacion
    };
    get verificador(){
        const propiedades = ["id","titulo","director","yearEstreno","paisOrigen","genero","calificacion"];
        const expRegId = /(\W|^)[a-zA-Z]{2}[0-9]{7}(\W|$)/;
        const expRegTitle = /(\W|^)(.|\s){1,100}(\w|$)/;
        const expRegYear = /(\W|^)[0-9]{4}(\W|$)/;
        const generosAceptados = ["Action", "Adult", "Adventure", "Animation", "Biography", "Comedy", "Crime", "Documentary" ,"Drama", "Family", "Fantasy", "Film Noir", "Game-Show", "History", "Horror", "Musical", "Music", "Mystery", "News", "Reality-TV", "Romance", "Sci-Fi", "Short", "Sport", "Talk-Show", "Thriller", "War", "Western"];
        const expRegCali = /(\W|^)((([1][0]){1}(\.[0]{1,2})?){1}|([0-9]{1}(\.[0-9]{1,2})?){1})(\W|$)/;
        
        // validar que se encuentren todas las propiedades
        propiedades.forEach(elemento => {
            
            if(objeto.hasOwnProperty(elemento) == false){
                console.log(`La propiedad "${elemento}" no se encontro, todos los datos del objeto son obligatorios`)
                return false
            }
        });
        // validar el id
        if(expRegId.test(this.id) == false){
            console.log(`El id debe contener 9 caracteres,de los cuales, los primeros 2 seran letras y los 
            7 restantes números.`);
            return false
        };
        // validar el titulo
        if(expRegTitle.test(this.titulo) == false){
            console.log("El titulo debe contener hasta un maximo de 100 caracteres");
            return false
        }
        // validar año de estreno
        if(expRegYear.test(this.yearEstreno) == false){
            console.log("El yearEstreno debe contener un numero entero de 4 digitos");
            return false
        }
        // validar país o paises
        if(Array.isArray(this.paisOrigen) == false){
            console.log("El paisOrigen debe contener los nombres de los paises dentro de un array");
            return false
        }
        // validar generos
        if(Array.isArray(this.genero) == true){
            this.genero.forEach(elemento => {
                if(generosAceptados.includes(elemento) == false){
                    console.log(`El genero:${elemento} , no esta incluido en la lista de generos aceptados`);
                    return false
                }
            })
        }else{
            if((Array.isArray(this.genero) == false)){
                console.log("El genero debe contener los nombres de los generos dentro de un array")
                return false
            }
        }
        // validar calificacion
        if(expRegCali.test(this.calificacion) == true){
            if((this.calificacion >= 0 && this.calificacion <= 10) == false){
                console.log(`El numero dentro de calificacion debe ser mayor o igual a cero y menor o igual a 10`)
                return false
            }
        }else{
            if(expRegCali.test(this.calificacion) == false){
                console.log("La calificacion debe contener un numero menor al 10, puede ser con punto decimal(maximo dos decimales)")
                return false
            }
        }
        return true
    };
    static get allGenerosAceptados(){
        const generosAceptados = ["Action", "Adult", "Adventure", "Animation", "Biography", "Comedy", "Crime", "Documentary" ,"Drama", "Family", "Fantasy", "Film Noir", "Game-Show", "History", "Horror", "Musical", "Music", "Mystery", "News", "Reality-TV", "Romance", "Sci-Fi", "Short", "Sport", "Talk-Show", "Thriller", "War", "Western"];
        return generosAceptados;
    }
    get fichaTecnica(){
        return {
        id : this.id ,
        titulo : this.titulo ,
        director : this.director ,
        yyearEstreno : this.yearEstreno ,
        paisOrigen : this.paisOrigen ,
        genero : this.genero,
        calificacion : this.calificacion 
        }
    }
}

const las_peliculas = [{
    id : "ss1234567",
    titulo: "La chapulina",
    director: "enrique segobiano",
    yearEstreno: "1999",
    paisOrigen: ["Mexico"],
    genero: ["Comedy"],
    calificacion: "10.00"
},
{
    id : "rr1234567",
    titulo: "El santo",
    director: "sabe",
    yearEstreno: "2000",
    paisOrigen: ["Mexico", "Estados unidos"],
    genero: ["Comedy", "Action"],
    calificacion: "8.00"
},
{
    id : "ee1234567",
    titulo: "Matrix",
    director: "el vitor",
    yearEstreno: "1998",
    paisOrigen: ["Estados unidos"],
    genero: ["Fantasy"],
    calificacion: "9.00"
}];

las_peliculas.forEach(elemento => {
    const pelicula = new Pelicula(elemento);
    console.log(pelicula.fichaTecnica)
})
```

## Programacion Asincrona
###  Temporizadores (setTimeout & setInterval)

JavaScrip tiene funciones que nos van a permitir lanzar otras acciones despues de haber pasado cierto tiempo o en una n cantidad de veces.

- `setTimeout(() =>{},1000)` : recive una funcion que va a ejecutar y recibe un tiempo expresado en milisegundos (1000 milisegundos = 1 segundo). Solo se ejecuta una vez


- `setIntervar(() => {},1000)` : recive una funcion que va a ejecutarse indefinidamente cada cierto intervalo de tiempo.

- `clearTimeout()` : cancela un time out, pero para que funcione el `setTimeout()` debe estar guardada de una variable.

- `clearInterval()` : cancela un setinterval, pero para que funcione el `setIntervar()` debe estar guardada en una variable.

###  Asincronía y el Event Loop
**Asincronía**
La asincronía es uno de los pilares fundamentales de Javascript, ya que es un lenguaje de programación de un sólo subproceso o hilo (single thread), lo que significa que sólo puede ejecutar una cosa a la vez.

Si bien los idiomas de un sólo hilo simplifican la escritura de código porque no tiene que preocuparse por los problemas de concurrencia, esto también significa que no puede realizar operaciones largas como el acceso a la red sin bloquear el hilo principal.

Imagina que solicitas datos de una API. Dependiendo de la situación, el servidor puede tardar un tiempo en procesar la solicitud mientras bloquea el hilo principal y hace que la página web no responda.

Ahí es donde entra en juego la asincronía que permite realizar largas solicitudes de red sin bloquear el hilo principal.

JavaScript fue diseñado para ser ejecutado en navegadores, trabajar con peticiones sobre la red y procesar las interacciones de usuario, al tiempo que mantiene una interfaz fluida.

Javascript usa un modelo asíncrono y no bloqueante, con un loop de eventos implementado en un sólo hilo, (single thread) para operaciones de entrada y salida (input/output).

Gracias a esta solución, Javascript es áltamente concurrente a pesar de emplear un sólo hilo.

Antes de explicar como funciona el modelo de JavaScript es importante entender algunos conceptos:

- Procesamiento Single thread (Hilo único) y Multi thread (Hilos múltples).
- Operaciones de CPU y Operaciones de I/O (Entrada y Salida).
- Operaciones Concurrentes y Paralelas.
- Operaciones Bloqueantes y No Bloqueantes.
- Operaciones Síncronas y Asíncronas.

**Single thread y Multi thread**

Un hilo la unidad básica de ejecución de un proceso, cada que abres un programa como el navegador o tu editor de código, se levanta un proceso en tu computadora e internamente este puede tener uno o varios hilos (threads) ejecutándose para que el proceso funcione.

**Operaciones de CPU y de Entrada y Salida**
- **Operaciones CPU**: Aquellas que pasan el mayor tiempo consumiendo Procesos del CPU, por ejemplo, la escritura de ficheros.
- **Operaciones de Entrada y Salida**: Aquellas que pasan la mayor parte del tiempo esperando la respuesta de una petición o recurso, como la solicitud a una API o BD.

**Concurrencia y Paralelismo**
- **Concurrencia**: cuando dos o más tareas progresan simultáneamente.
- **Paralelismo**: cuando dos o más tareas se ejecutan, al mismo tiempo.

**Bloqueante y No Bloqueante**
Se refiere a como la fase de espera de las operaciones afectan a nuestra aplicación:

- **Bloqueante**: Son operaciones que no devuelven el control a nuestra aplicación hasta que se ha completado. Por tanto el thread queda bloqueado en estado de espera.
- **No Bloqueante**: Son operaciones que devuelven inmediatamente el control a nuestra aplicación, independientemente del resultado de esta. En caso de que se haya completado, devolverá los datos solicitados. En caso contrario (si la operación no ha podido ser satisfecha) podría devolver un código de error.

**Síncrono y Asíncrono**

Se refiere a ¿cuándo tendrá lugar la respuesta?:

- **Síncrono**: La respuesta sucede en el presente, una operación síncrona esperará el resultado.
- **Asíncrono**: La respuesta sucede a futuro, una operación asíncrona no esperará el resultado.
Con lo anterior en JavaScript podemos tener:

- Código síncrono y bloqueante o
- Código asíncrono y no bloquenate

**JavaScript Síncrono**

Cada operación se hace de una vez, bloqueando el flujo de ejecución, el hilo es bloqueado mientras espera la respuesta, cuando esta se procesa pasa a la siguiente operación y así sucesivamente al terminar todas las operaciones.

```js
console.log("Inicio");

function dos() {
  console.log("Dos");
}

function uno() {
  console.log("Uno");
  dos();
  console.log("Tres");
}

uno();
console.log("Fin");
```
El resultado en consola es:

```
Inicio
Uno
Dos
Tres
Fin
```

**JavaScript Asíncrono**

Cada operación se ejecuta y devuelve inmediatamente el control al hilo, evitando el bloqueo, cuando cada operación termine se enviará una notificación de que ha terminado, es entonces cuando la respuesta se encolará para ser procesada.

```js
console.log("Inicio");

function dos() {
  setTimeout(function () {
    console.log("Dos");
  }, 1000);
}

function uno() {
  setTimeout(function () {
    console.log("Uno");
  }, 0);
  dos();
  console.log("Tres");
}

uno();
console.log("Fin");
```
El resultado en consola es:
```
Inicio
Tres
Fin
Uno
Dos
```

### Mecanismos asíncronos en JavaScript
Para controlar la asincronía, JavaScript cuenta con algunos mecanismos:

- **Callbacks.**
- **Promises.**
- **Async / Await.**

**Callbacks**
Una **callback** (llamada de vuelta) es una función que se ejecutará después de que otra lo haga.

Es un mecanismo para asegurar que cierto código no se ejecute hasta que otro haya terminado.

Al ser JavaScript un lenguaje orientado a eventos, las callbacks son una buena técnica para controlar la asíncronía, sin embargo... Callback Hell 😈🤘.
```js
function cuadradoCallback(value, callback) {
  setTimeout(() => {
    callback(value, value * value);
  }, 0 | (Math.random() * 1000));
}

cuadradoCallback(0, (value, result) => {
  console.log("Inicia Callback");
  console.log(`Callback: ${value}, ${result}`);
  cuadradoCallback(1, (value, result) => {
    console.log(`Callback: ${value}, ${result}`);
    cuadradoCallback(2, (value, result) => {
      console.log(`Callback: ${value}, ${result}`);
      cuadradoCallback(3, (value, result) => {
        console.log(`Callback: ${value}, ${result}`);
        cuadradoCallback(4, (value, result) => {
          console.log(`Callback: ${value}, ${result}`);
          cuadradoCallback(5, (value, result) => {
            console.log(`Callback: ${value}, ${result}`);
            console.log("Fin Callback");
            console.log("Callback Hell !!!!!😈🤘");
            console.log("http://callbackhell.com/");
          });
        });
      });
    });
  });
});
```

### Promises
Una **promesa** es un objeto que representa el resultado de una operación asíncrona y tiene 3 estados posibles:

Pendiente.
Resuelta.
Rechazada.
Tienen la particularidad de que se pueden encadenar (then), siendo el resultado de una promesa, los datos de entrada de otra posible función.

Las promesas mantienen un código más legible y mantenible que las callbacks, además tienen un mecanismo para la detección de errores (catch) que es posible usar en cualquier parte del flujo de datos.
```js
function cuadradoPromise(value) {
  if (typeof value !== "number") {
    return Promise.reject(
      `Error, el valor " ${value} " ingresado no es un número`
    );
  }

  return new Promise((resolve, reject) => {
    setTimeout(() => {
      resolve({
        value,
        result: value * value,
      });
    }, 0 | (Math.random() * 1000));
  });
}

cuadradoPromise(0)
  .then((obj) => {
    //console.log(obj);
    console.log("Inicio Promise");
    console.log(`Promise: ${obj.value}, ${obj.result}`);
    return cuadradoPromise(1);
  })
  .then((obj) => {
    console.log(`Promise: ${obj.value}, ${obj.result}`);
    return cuadradoPromise(2);
  })
  .then((obj) => {
    console.log(`Promise: ${obj.value}, ${obj.result}`);
    return cuadradoPromise(3);
  })
  .then((obj) => {
    console.log(`Promise: ${obj.value}, ${obj.result}`);
    return cuadradoPromise("4");
  })
  .then((obj) => {
    console.log(`Promise: ${obj.value}, ${obj.result}`);
    return cuadradoPromise(5);
  })
  .then((obj) => {
    console.log(`Promise: ${obj.value}, ${obj.result}`);
    console.log("Fin Promise");
  })
  .catch((err) => console.error(err));
```
```js
//otro ejemplo
funcion cuadradoPromise(){
  if(typeof value !== "number"){
    // con esto estamos mandando directamente al catch para que constrole el error
    return Promise.reject("error");
    }
  // el Promise tiene dos partes:
  // el resolve: la parte que resulve
  // el reject: la parte que rechaza la promesa
  return new Promise((resolve, reject) => {
    setTimeout(() =>{
      resolve({
        value,
        result: value * value
      })
    }, 0);
  })
}

// la forma de trabajar las promesas 
// existen dos metodos con le cual se puede trabajar la asincronia:
// then() : es el siguiente bloque que se va a ejecutar una vez que se cumpla la funcion inicial, se pueden tener tantos metodos then como queramos
// catch() : el metodo catch va a capturar el error
cuadradoPromise().then().catch()
```

### Async / Await

Las promesas fueron una gran mejora respecto a las callbacks para controlar la asincronía en JavaScript, sin embargo pueden llegar a ser muy verbosas a medida que se requieran más y más métodos .then().

Las funciones asíncronas (async / await) surgen para simplificar el manejo de las promesas.

La palabra async declara una función como asíncrona e indica que una promesa será automáticamente devuelta.

Podemos declarar como async funciones con nombre, anónimas o funciones flecha.

La palabra await debe ser usado siempre dentro de una función declarada como async y esperará de forma asíncrona y no bloqueante a que una promesa se resuelva o rechace.
```js
function cuadradoPromise(value) {
  if (typeof value !== "number") {
    return Promise.reject(
      `Error, el valor " ${value} " ingresado no es un número`
    );
  }

  return new Promise((resolve, reject) => {
    setTimeout(() => {
      resolve({
        value,
        result: value * value,
      });
    }, 0 | (Math.random() * 1000));
  });
}

async function funcionAsincronaDeclarada() {
  try {
    console.log("Inicio Async Function");

    let obj = await cuadradoPromise(0);
    console.log(`Async Function: ${obj.value}, ${obj.result}`);

    obj = await cuadradoPromise(1);
    console.log(`Async Function: ${obj.value}, ${obj.result}`);

    obj = await cuadradoPromise(2);
    console.log(`Async Function: ${obj.value}, ${obj.result}`);

    obj = await cuadradoPromise("3");
    console.log(`Async Function: ${obj.value}, ${obj.result}`);

    obj = await cuadradoPromise(4);
    console.log(`Async Function: ${obj.value}, ${obj.result}`);

    obj = await cuadradoPromise(5);
    console.log(`Async Function: ${obj.value}, ${obj.result}`);

    console.log("Fin Async Function");
  } catch (err) {
    console.error(err);
  }
}

funcionAsincronaDeclarada();

const funcionAsincronaExpresada = async () => {
  try {
    console.log("Inicio Async Function");

    let obj = await cuadradoPromise(6);
    console.log(`Async Function: ${obj.value}, ${obj.result}`);

    obj = await cuadradoPromise(7);
    console.log(`Async Function: ${obj.value}, ${obj.result}`);

    obj = await cuadradoPromise(8);
    console.log(`Async Function: ${obj.value}, ${obj.result}`);

    obj = await cuadradoPromise("9");
    console.log(`Async Function: ${obj.value}, ${obj.result}`);

    obj = await cuadradoPromise(10);
    console.log(`Async Function: ${obj.value}, ${obj.result}`);

    console.log("Fin Async Function");
  } catch (err) {
    console.error(err);
  }
};

funcionAsincronaExpresada();
```

```js
// otro ejemplo
// la manera de decirlea java script que una funcion es asicrona es anteponerle la palabra async

async function funcionAsincronaDeclarada(){
  // para le menejo de errores lo mejor es trabajar con try - catch
  try{
  // await : le dice a javascript dentro de una funcion asincrona que espere el resultado de la ejecusion antes de pasar a ala siguiente linea y ejecutarla 
  const valor = await cuadradoPromise();

  }catch(error){}
}

funcionAsincronaDeclarada();

// async tambien se puede usar en funciones flecha 
const funcionAsincronaExpresada = async () =>{}
```

## Nuevos Tipos y Caracteristicas
### Symbols

- `Symbol()` : es un tipo de dato primitivo, una vez que creamos un symbol, su valor se va a mantener privado y para uso interno, generalmente los symbols suelen agregarse como caracteristicas de objetos(como una propiedad) y estas se van a mantener privadas.
```js
// para crear un symbol no podemos usar new 
let id = Symbol()
```
Una peculiaridad es que los symbols nos permiten crear identificadores unicos, identificadores de referencia.
```js
let id = Symbol()
let id2 = Symbol()
console.log(id === id2) // false
```  
los symbols suelen usarse a menudo para identificar las propiedades de objetos, para evitar coliziones entre propiedades que pudieramos sobreescribir.
```js
// como le agregariamos un symbol a un objeto:
// un symbol como es una referencia que no debe cambiar debe ser escrita en mayusculas como una constante
const NOMBRE = Symbol()

// cuando se quiere asignar un identificator uno dentro de las propiedades de un objeto tiene que ponerlo dentro de los conchetes []
const persona = {[NOMBRE]:"JON"}
console.log(persona);
//{Symbol():"JON"}

persona.NOMBRE = "JONATHAN";
console.log(persona);
//{NOMBRE: "JONATHAN", Symbol():"JON"}
// los symbolos usualmente se usan para crear propiedades privadas de los objetOs 

// si quieremos llamar a una propiedade que tiene un symbol podemos usar los corchetes para llamarla:
console.log(persona[NOMBRE]);
//JON
```

Para hacer una funcion privada.
```js
const SALUDAR = Symbol()

const persona = {}

persona[SALUDAR] = function(){}
console.log(persona)
// {Symbol(): f()}

// para invocar la funcion 
persona[SALUDAR]();
```
Si tratamos de extraer la informacion del objeto persona con un for-in no va a imprimir los symbols.
Para listar los atributos privados del objeto:
```js
Object.getOwnPropertySymbols(persona);
```

### Sets
Este nuevo tipo de datos set es una estructura similar a un array pero de datos unicos(hablando de valores primitivos)

```js
// crea un set 
const set = new Set(1,2,3,3,4,5,true,true,{},{});
console.log(set)
// si se llegan a repetir valores dentro del set los elimina dejando solamente el primero
/*
0 : 1
1 : 2
2 : 3
3 : 4
4 : 5
6 : true
7 : Object
8 : Object
*/

//si queremos saber la longitud de un Set, podemos usar la propiedad size
set.size

// tambien podemos agregar valores al Set con el metodo add()
set.add()

// para recorrer un Set podemos usa el metodo for-of, forEach

// para acceder a la posicion del Set se usa from, es decir que lo tener que convertir en un arreglo para poder acceder a sus posiciones
let arr = Array.from(set);
arr[0]

// el set tiene un metodo especial que nos permite eliminar valores
set.delete(true)

// tenemos un metodo que compueba si un valor existe dentro de la coleccion de datos
set.has()// retorna true o false

// si queremos limpiar una coleccion de set usamos el metodo clear()
set.clear();
```

### Maps
Los map son objetos que nos sirven para almacenar conjuntos de valores asociados a manera de objeto, es como si fuera un objeto primitivo. Se usa como una coleccion de datos que estan relacionados entre si.
```js
const mapa = new Map();
// los maps trabajan muy parecido a los getter y setters
// para agregar valores hay dos formas, con set y 
mapa.set("nombre","Jon");
const mapa2 = new Mapa([["nombre","kenai"],["animal","perro"]])
// map es un objeto iterador
console.log(mapa)
//Map(1) {"nombre" => "Jon"}

// si queremos saber la longitud del map podemos usar el size
mapa.size

// evaluar si existe alguna llave o no
mapa.has("nombre")

// si queremos imprimir el valor de la lleva usamos get()
mapa.get("nombre")

// para sobreescribir la llave y el valor
mapa.set("nombre","Jonathan")

// si queremos borrar valores del mal usamos delete()
mapa.delete("nombre")

// para recorrer un mapa podemos usar un for-of
for(let [key,value]of mapa){}

//una cosa extra;a que podria suceder en los objetos map es:
// en los map podemos generar llaves que no son cadenas de texto.ejemplo:
// Nan, null, undefined.etc
mapa.set({},{})
mapa.set(false,"falso")
mapa.set(19,"diecinueve")

// tambien podemos usar metodos como:
mapa.keys()
mapa.values()
```

### WeakSets & WeakMaps
Se refiere a que solamente se pueden almacenar referencias debiles, es decir, que las llaves tienen que ser de tipo objeto. 

Al ser una referencia debil esto le permite al recolector de basura de js que en el momento que alguna de las referencias debiles que tengan estos weaksets o weakmaps, se hayan nulificado o se hayan limpiado dentro de la logica de nuestra programacion, cuando el recolector de basura de nuetro navegador ejecute su proceso, esto hace una mejora en el rendimiento de nuestra aplicacion.

En la misma herramienta de desarrollador del navegador hay una opcion que se llama `Memory`, y el `Collect garbage` reprecenta el recolector de basura, si en algun momento queremos comprobar que se hayan eliminado las referencias debiles siemplementle le damos click al `Collect garbage`.

Los WeakSets y WeakMaps tiene algunas carencias:
- No podemos iterar sobre las claves y los valores(no son elemento iterables)
- No podemos borrar todos los elemento de una sola vez(`con clear()`)(se tienen que eliminar los elementos de uno en uno)
- No podemos verificar su longitud (`size()`)

```js
//weakSet()
const ws = new WeakSet();
// con los weak tenemos que agregar los valores de uno en uno con el metodo add() de uno en uno
// solo aceptan referencias debiles(objetos)
let valor1 = {"valor": 1}
let valor2 = {"valor": 2}
let valor3 = {"valor": 3}

ws.add(valor1)
ws.add(valor2)
// no podemos usar el metodo size()
// si podemos usar el metodo has()
// si podemos usar el metodo delete()

// en el momento de que los weak tengan un valor nulo se limpian sus propias referencias 

setInterval(() => console.log(ws),1000)
setTimeout(() => {
  valor1 = null;
  valor2 = null;
  valor3 = null;
},5000)

```
```js
//WeakMap
const wm = new WeakMap()
// con los weak tenemos que agregar los valores de uno en uno con el metodo set() de uno en uno
// solo aceptan referencias debiles(objetos)
let llave1 = {};
let llave2 = {};
let llave3 = {};

wm.set(llave1, 1);
wm.set(llave2, 2);

// no podemos usar el metodo size()
// si podemos usar el metodo has()
// si podemos usar el metodo delete()
// si podemos usar el metodo get()

// en el momento de que los weak tengan un valor nulo se limpian sus propias referencias 

etInterval(() => console.log(wm),1000)
setTimeout(() => {
  llave1 = null;
  llave2 = null;
  llave3 = null;
},5000)
```

###  Iterables & Iterators 

- **Iterable**: es el elemento el cual su contenido se puede recorrer.
- **Iterador**: es el mecanismo que esta recorreindo los elementos.

```js
const iterable = [1,2,3,4,5];
// para acceder al iterable de nuestro iterador accedemos al Symbol.iterator
const iterador = iterable[Symbol.iterator]()
// al tener al iterador podemos hacer uso de la propiedad next
iterador.next()
// el metodo next devuelve un objeto con dos propiedades
// - el valor como tal
// - un segundo para metro que indica si ya se acabaron los elementos 
```

Esto es lo que se conoce como el iterador que es un metodo especial al cual podemos acceder por parte de todo tipo de dato que sea iterable.

###  Generators

Es una funcion que nos permite trabajar de una manera mas amigable con la interfase de los iteradores en un elemento iterable.

```js
//para que javascript sepa que va a ser una funcion de tipo generador solamente se le tiene que agregar a function el * sin espacio
// con el * basicamente estas accediento al Symbole.iterator
function* iterable(){
  // yield es como un return pero este guarda la posicion en la que termino el codigo
  yield "hola";
  console.log("Hola consola");
  yield "hola 2"
}

let iterador = iterable()
console.log(itelador.next())// {value: "hola", done:false}
console.log(itelador.next()) // {value: "hola 2", done:false}
console.log(itelador.next()) // {value: undefined, done: true}


// para guardar los resultados del yield en un array podemos usar:
const arr = [...iterable()]
```
Con el `yield` podriamos convertir una funcion a un iterable 

### Proxies
los proxies son un nuevo mecanismo en javascript que te permite crear un objeto, basado en un objeto literal inicial.

EL proxie va a recibir el objeto literal, va a generar una copia y va a permitir que tu realices ciertas operaciones, como por ejemplo, validacion de propiedades de tipo de datos dentro de la copia que se esta creando del objeto original. Es decir, que se va a tener un medio de vinculacion entre el objeto del cual te basas y la nueva instancia que has generado y todo eso se va administrar atravez de un objeto especial que tambien recibe el proxie que se conoce como `handler` o manejador.

```js
const persona = {
  nombre: "",
  apellido: "",
  edad: 0
}

const manejador = {
  // el manejador va a recibir un parametro que se va a llamar set
  // en ese set, nosotros podemos estableser todo tipo de validaciones 
  set(obj,prop,valor){
    // aqui podemos hacer validaciones y de tal manera restringir para que no sufra cambios la copia que estamos haciendo apartir de nuestro objeto(persona)
    if(Object.keys(obj).indexOf(prop) === -1){
      return console.error(`La propiedad "${prop}" no existe ene l objeto persona`)
      // con esto etariamos validando que no se pueden agregar mas propidades el objeto 
    }

    obj[prop] = valor; //si no tiene la validacion entonces el proxi no reconocera los valores 
  }
}

const jon = new Proxy(persona, manejador)
// el proxy automaticamente inicializara los valores que tiene el objeto del cual nos estamos basando(persona)
jon.nombre= "Jon"
jon.apellido = "Mircha"
jon.edad = 35;

console.log(jon)
console.log(persona)
//aparte de que el proxy es una copia de (persona), mantiene una vinculacion entre la copia y el objeto original  
```

EL proxi hace una vinculacion entre  el objeto original, el objeto copia y atravez de su objeto especial manejador podemos hacer validaciones antes de hacer la asignacion.

### Propiedades Dinámicas de los Objetos

podemos crear el nombre de las propiedades de manera dinamica en un objeto.
```js
const objUsuarios = {}

const usuario = {"jon","irma","kana"}
// por cada usuario queremos generar al objeto usuario una propiedad 
usuario.forEach((usuario,index) => {
  objUsuarios[`id_${index}`] = usuario;
})
```
```js
// tambien se pueden crear directamente dentro del objeto las propiedades dinamicas
const objUsuarios = {
  [`id_${Math.round(Math.random() *100+5)}`] : "valorAleatorio"
}
```

## this en JavaScript
### this
`this` es una palabra que hace referencia al objeto en el que estamos trabajando y asi podemos invocar propiedades y/o metodos que tenga dicho objeto.
```js
// en este caso como estamos en el javascript de los navegadores this va hacer referencia al objeto global 
// y el objeto global es este objeto que se llama window
console.log(this)
// a diferencia de que si lo estuvieramos ejecutanto en note.js devolveria en la terminal de comandos `global`
console.log(this === window)

this.nombre = "Contexto Global"
console.log(this.nombre); // Contexto Global
function imprimir(){
  console.log(this.nombre);
}

imprimir(); // Contexto Global

const obj = {
  nombre: "Contexto Objeto",
  imprimir: function(){
    console.log(this.nombre);
  }
}

obj.imprimir();//Contexto Objeto

const obj2 = {
  nombre: "Contexto Objeto 2",
  imprimir
}

obj2.imprimir(); //Contexto Objeto 2

const obj3 = {
  nombre: "Contexto Objeto 3",
  imprimir:() => {
    console.log(this.nombre) 
  }
}

obj3.imprimir(); // Contexto Global
```

### call, apply, bind 
Si necesitamos conservar la referencia de un scope en particular y utilizarlo en alguna invocacion en algun codigo para eso sirve call, apply, bind.
```js

console.log(this === window)

this.nombre = "Contexto Global"
console.log(this.nombre); // Contexto Global
function imprimir(){
  console.log(this.nombre);
}

imprimir(); // Contexto Global

const obj = {
  nombre: "Contexto Objeto",
}

// el metodo call recibe de parametro un objeto el cual es el contexto 
imprimir.call(obj) //  Contexto Objeto

// el metodo apply funciona igual que call, la diferencia es como se insertan los parametros
imprimir.apply(obj) //  Contexto Objeto

//la diferencia entre call y apply es como se insertan los parametros:

function saludar(saludo,aQuien){
  console.log(`${saludo} ${aQuien} desde el ${this.nombre}`);
}

saludar.call(obj,"Hola","Jon");
saludar.apply(obj,["Hola", "Jon"])
// si ponemos null en vez de obj es como si nos regresaramos al contexto global 

```

`bind`: lo que hace es un enlace, muy similar a lo que hacen las funciones fecha, no crea un scope para si misma y utiliza ya el scope en el que ya a sido creada.

```js
const persona = {
  nombre: "Jon",
  saludar: function(){
    console.log(`Hola ${this.nombre}`)
  }
}

persona.saludar(); //Hola Jon

let otraPersona = {
  saludar: persona.saludar
}

otraPersona.saludar() // Hola undefined

otraPersona = {
  saludar: persona.saludar.bind(persona)
}

otraPersona.saludar() //Hola Jon

this.nombre = "Window"

otraPersona = {
  saludar: persona.saludar.bind(this)
}

otraPersona.saludar() //Hola Window
```

## JSON: JavaScript Object Notation

**JavaScript Object Notation** o Notación de Objetos de JavaScript, es un formato ligero de intercambio de datos. Leerlo y escribirlo es simple para humanos, mientras que para las máquinas es fácil de interpretar y generar. Todos los lenguajes de programación lo soportan.

**Sintaxis derivada de los objetos JavaScript:**
- Los datos se encuentran en pares de nombre / valor.
- Los datos están separados por comas.
- Las llaves {} contienen objetos.
- Los corchetes [] contienen arreglos.
- Los datos tienen un nombre y un valor.
- Los datos se escriben como pares de nombre / valor "nombre" : "valor".

**Valores JSON:**
- Un número (entero o de coma flotante).
- Una cadena (entre comillas dobles).
- Un booleano (verdadero o falso).
- Un arreglo (entre corchetes).
- Un objeto (entre llaves).
- Un valor nulo (null).

**Métodos JavaScript para JSON:**

`JSON.parse()`: Analiza una notación JSON y la convierte en un tipo de dato JS.

```js
console.log("*** JSON.parse ***");
console.log(JSON.parse("{}"));
console.log(JSON.parse("[1,2,3]"));
console.log(JSON.parse("true"));
console.log(JSON.parse("false"));
console.log(JSON.parse("19"));
console.log(JSON.parse('"Hola Mundo"'));
console.log(JSON.parse("null"));
//console.log(JSON.parse("undefined"));
console.log(JSON.parse('{ "x": 2, "y": 3 }'));
```

`JSON.stringify()`: Convierte un tipo de dato JS a notación JSON.

```js
console.log("*** JSON.stringify ***");
console.log(JSON.stringify({}));
console.log(JSON.stringify([1, 2, 3]));
console.log(JSON.stringify(true));
console.log(JSON.stringify(false));
console.log(JSON.stringify(19));
console.log(JSON.stringify("Hola Mundo"));
console.log(JSON.stringify(null));
console.log(JSON.stringify(undefined));
console.log(JSON.stringify({ x: 2, y: 3 }));
```

Más información en [JSON.org](https://www.json.org/json-es.html)

## DOM: Document Object Model

### WEB APIs
las interfaces de programacion de aplicacion o APIs, en pocas palabras, una API es una serie de objetos y mecanismos que tiene el lenguaje implementado en ciertas areas para poder interactuar con el navegador, como seria el arbol de la estructura del documento html , lo que vendria siendo todo el contron de la ventana del navegador.

**WEB APIs**

- **DOM: Document Object Model** : El `DOM` es justamente como los navegadores representan el codigo HTML O XML para trabajarlo con js. Es una interfaz estandarizada.


- **BOM: Browser Object Model** : no se le considera una API estandart 

- **CSSOM: CSS Object Model** : `CCSOM` es una parte del DOM pero para manipular el css.

- Eventos
- Forms
- AJAX - Fetch
- History
- Web Storage
- Geolocation
- Drag & Drop
- Indexed DB
- Canvas
- MatchMedia
- etc..

`window.navigator` : es un objeto que nos controla caracteristicas como idioma,plataforma(sistema operativo), caracteristicas del navegador, historial, localizacion(host,puerto,protocolo)

```js
// desde una api que ya tiene intergada los navegadore podemos mandar un audio

let texto = "Hola, mi nombre es jose";
const hablar = (texto) => speechSynthesis.speak(new SpeechSynthesisUtterance(texto));

hablar(texto)
// solo funciona en chrome
```

### Introduccion al DOM 

El Modelo de Objetos del Documento es un API para documentos HTML y XML.

Éste proveé una representación estructural del documento, permitiendo modificar su contenido y presentación visual mediante código JavaScript.

El DOM no es parte de la especificación de JavaScript, es una API para los navegadores.

```js
//Elementos del documento
console.log(window.document);
console.log(document);
console.log(document.head);
console.log(document.body);
console.log(document.documentElement); // representa la etiqueta del html
console.log(document.doctype); //tipo de documetno 
console.log(document.charset);
console.log(document.title);
console.log(document.links);
console.log(document.images);
console.log(document.forms);
console.log(document.styleSheets); //css
console.log(document.scripts); //js
setTimeout(() => {
  console.log(document.getSelection().toString());
}, 2000);//seleccion con el mouse
document.write("<h2>Hola Mundo desde el DOM</h2>");//permite escribir en el documento, no es buena practica
```

### DOM: Nodos, Elementos y Selectores 

No confundir una etiqueta html(elemento) que un nodo.

**Node.nodetype** : Diferentes tipos de nodo.

- `Node.ELEMENT_NODE`
- `Node.TEXT_NODE`
- `Node.CDATA_SELECTION_NODE`
- `Node.PROCESSING_INSTRUCTION_NODE`
- `Node.COMMENT_NODE`
- `Node.DOCUMENT_NODE`
- `Node.DOCUMENT_TYPE_NODE`
- `Node.DOCUMENT_FRAGMENT_NODE`
- `Node.ATTRIBUTE_NODE`
- `Node.ENTITY_REFERENCE_NODE`
- `Node.ENTITY_NODE`
- `Node.NOTATION_NODE`

```js
// metodos que ya no suelen utilizarse
// fueron remplazados por metodos mas optimos
document.getElementsByTagName("li");//traera todos los elementos con la etiquetas li
document.getElementsByClassName("card") // traera los elementos con el mismo nombre de clase
document.getElementsByName("nombre") // traera los elementos con el name(atributo Name) igual
```
```js
// metodos mas optimos
document.getElementById("menu") // devuelve el elemento con el nombre del id, a nivel de rendimiento es mejor que querySelector 
document.querySelector("menu");// sirve como parametro un selector valido de css(id,class, etiqueta html), que no sean pseudoclases o pseudoelementos.
// querySelector(): hay que especificar con punto las clases, con gato los id, etc. solo trae el primer selector.
docuemnt.querySelectorAll("a"); // lo mismo que querySelector pero trae todos los elemento con el mismo selector. Devuelve un NodeList
docuemnt.querySelectorAll("a")[0];// tambien podemos acceder por numero de elemento
```

### DOM: Atributos y Data-Attributes
Como trabajar con atributos de las etiquetas html:

```html
<!--Apartir de html5 tambien el standart nos permite crear nuestros propios atributos, que es lo que se conoce como los data atributs -->
<!--lo unico que pide el standart html para crear los data-atributs es que empiezen con la palabra "data-" -->
<input data-description="Document Object Model">
```

Tenemos dos maneras de interactuar con los atributos y tambien de establecerles valores.
```js
// si queremso acceder al atributo lang de la etiqueta html seria:
document.documentElement.lang;// se recomienda usar este meotodo
// tambien se puede usar con querySelector:
document.querySelector(".link").href;

//o
document.documentElement.getAttribute("lang"); //  esta forma tiende a devolver el valor del atributo


// para cambiar los valores de los atributos
document.documentElement.lang = "en";
//o
document.documentElement.setAttribute("lang", "es-MX")
```

Guardar en valiables elementos del dom
```js
// para identificar una variable que hace referencia a codigo de html se le antepone un signo de dolar $
const $linkDOM = querySelector(".link")
$linkDOM.setAttribute("target", "_blank")

// para remover un atributo
$linkDOM.removeAttribute("target")

//verificar si existe el atributo
$linkDOM.hasAttribute("target") // devolvera true of false


//Link types: noopener
$linkDOM.setAttribute("rel","noopener")
/*
La palabra clave noopener para el atributo rel de los elementos <a>, <area> y <form> indica al navegador que navegue hasta el recurso de destino sin otorgar acceso al nuevo contexto de navegación al documento que lo abrió, sin configurar la ventana. .opener propiedad en la ventana abierta (devuelve nulo). Esto es especialmente útil cuando se abren enlaces que no son de confianza, para asegurarse de que no puedan alterar el documento de origen a través de la propiedad Window.opener (consulte Acerca de rel = noopener para obtener más detalles), mientras se proporciona el encabezado HTTP Referer (a menos que noreferrer se use como bien). Tenga en cuenta que cuando se usa noopener, los nombres de destino no vacíos que no sean _top, _self y _parent se tratan como _blank en términos de decidir si abrir una nueva ventana / pestaña. Nota: La configuración de target = "_ blank" en los elementos <a> ahora proporciona implícitamente el mismo comportamiento rel que la configuración de rel = "noopener", que no establece window.opener. Consulte la compatibilidad del navegador para conocer el estado de la compatibilidad.
*/
```

```js
// para trabjar con Data-Attributes
// para obtener
$linkDOM.getAtribute("data-description");

$linkDOM.dataset; //  de esta manjera retornara una coleccion de objetos map

// para ser mas especyfico con la segunda forma usamos .description ya que es el nombre despues del "data-"
$linkDOM.dataset.description

// establecer unuevos valores
$linkDOM.setAtribute("data-description", "DOM")

$linkDOM.dataset.description = "dom";
```

### DOM: Estilos y Variables CSS
`scroll-behaivor: smooth` : en css se puede usar en el html para hacer la transicion de secciones mas suave.

```js
const $linkDOM = querySelector(".link")

// para agregar estilos en linea a nuestra etiqueta
//.style permite agregar estilos en linea a nuestra etiqueta
// es importante acceder con la notacion del punto y no tanto con el metodo getAttribute
$linkDOM.style;
$linkDOM.style.setProperty("text-decoration","none");
// va a retornar un objeto de tipo CSSStyleDeclaration, es un mapa que va agergando todas las propiedades css validas 
// no retorna el valor por defecto del navegador


// podemos acceder a los valores del objeto
// usaremos camerllcase en lugar de - para separar las palabras
$linkDOM.style.backgroundColor;
$linkDOM.style.backgroundColor = "black";


window.getComputedStyle($linkDOM)// regresa un mapa con todas la propiedades, regresa el valor por defecto que el navegador le pone a la etiqueta


// podemos acceder a los valores del objeto
getComputedStyle($linkDOM).getPropertyValue("color")
```

**Variables CSS - custom Properties**
```js
// propiedades dinamicas de css
:root{
  --yelow-color: #F7DF1E;
  --dark-color: #222;
} //esto es del css o del html con la etiqueta <style>


const $html = document.documentElement;

$html.style.setProperty("--dark-color","pink")
let varDarkColor = getComputedStyle($html).getPropertyValue("--dark-color");
```

### DOM: Clases CSS
```js
const $card = document.querySelector(".card");

$card.className;// este atrevitu retorna la cadena de texto de la clase

$card.classList; //devuelve un DOMTokenList
//con este podemos evaluar si un elemento tiene una clase en particular 
$card.classList.contains("rotate-45")// regesa un true en caso de que tenga la classe y un false en caso de que no

// para agregarle una clase
$card.classList.add("rotate-45") //se pueden agregar mas de una clase, solamente tienes que separarlas por comas

// para borrar una clase
$card.classList.remove("rotate-45")//se pueden agregar mas de una clase, solamente tienes que separarlas por comas


// toggle: un metodo que si tiene una clase se la quita y si no la tiene se la agrega
$card.classList.toggle("rotate-45")//se pueden agregar mas de una clase, solamente tienes que separarlas por comas


//remplazar una coase por otra
$card.classList.replace("rotate-45","rotate-135")
```

###  DOM: Texto y HTML
```js
const $textDom = document.getElementById("que-es");

let text = `<p>Modelo de Objetos del Documento</p>`


// Esta manera no es standart 
//fue creado para internet explorer
$textDom.innerText = text; //sirve para agregar contenido textual a un elemento
// no reconoce las etiquetas html


//si forma parte del standart
$textDom.textContent = text; //no interpreta las etiquetas html ni identactiones

$textDom.innerHTML = text; // si interpreta etiquetas html
//lo que va hacer es replazar el contenido **con** contenido html

$textDom.outerHTML = text; //lo que va hacer es replazar el contenido **por** contenido html
```

### DOM Traversing: Recorriendo el DOM

```js
const $cards = document.querySelector(".cards");

// hacer referencia a los hijos de la etiqueta
$cards.children;// devuelve una HTMLCollection
// se puede acceder a un hijo en especifico
$cards.children[2];

//acceder al padre el elemento
$cards.parentElement; // retorna el elemento padre
$cards.parentNode // retorna el nodo padre, cuidado podria retorna un string vacio.

$cards.firstChild; // retorna el primer nodo, por lo general regesara el salto de linea
$cards.firstElementChild; //retorna el primer elemento hijo 
$cards.lastElementChild; // retrona el ultimo elemento hijo

$cards.preveousSibling; //retorna el nodo hermano anterior,por lo general regesara el salto de linea
$cards.preveousElementSibling;// retorna el elemento hermano anterior
$cards.nextElementSibling; // retorna el elemento hermano posterior

//es un metodo que busca el padre mas cercano el selector que le indiquemos
$cards.closest("div"); 
```

### DOM: Creando Elementos y Fragmentos

Crear etiquetas dinamicas 
```js
const $figure = document.createElement("figure"),
$img = document.createElement("img"),
$figcaption = document.createElement("figcaption"),
$figcaptionText = document.createTextNode("Animals"),//en este crearemos un nodo de texto
$cards = document.querySelector(".cards"),
$figure2 = docuement.createElement("figure");

$figcaption.appendChild($figcaptionText)
$figure.appendChild($img)
$figure.appendChild($figcaption)
$cards.appendChild($figure)

$figure2.innerHTML = `<img src="https://placeimg.com/200/200/pople" alt="People">`;
$figure2.classList.add("card");
$cards.apendChild($figure2);
```
```js
// crear dinamicamente las script de estaciones
// cuando vamos a dibujar mas de un elemento, es mejor que primero escribamos el codigo dinamico en una variable y depues mandarlo a dibujar una sola vez
const estaciones = ["Primavera","Verano", "Oto;o", "Invierno"], $ul = document.createElement("ul"),
$fragment = document.createDocumentFragment();

estaciones.forEach(el => {
  const $li = document.createElement('li');
  $li.textContent = el;
  $fragment.appendChild($li)
});

$ul.appendChild($fragment);
document.body.appendChild($ul)
// esta es la manera optima de hacer una insercion al dom de manera dinamica
```

### DOM: Templates HTML
`appendChild()` siempre agrega el elemento al final del selector objetivo.

```html
<!--En el html-->
<!-- La etiqueta template es una etiqueta que no se visualiza en la pantalla aun que si se puede ver en el codigo en la opcion de desarrollador-->
<template id="template-card">
  <figure class="card">
    <img>
    <figcaption></figcaption>
  </figure>
</template>
```

```js
// en el js
const $cards = document.querySelector(".cards"),
$template = document.getElementById("template-card").content,
$fragment = document.createDocumentFragment(),
cardContent = [
  {
    title: "Tecnologia",
    img: "https://placeimg.com/200/200/tech"
  },
  {
    title: "Animales",
    img: "https://placeimg.com/200/200/animals"
  }
]

cardCantent.forEach(el => {
  $template.querySelector("img").setAttribute("src", el.img);
  $template.querySelector("img").setAttribute("alt", el.title);
  $template.querySelector("figcaption").textContent = el.title;
  // para clonar un nodo del documento usamos:
  // el parametro true significa que queremos que copie la estructura interna, si le pusieramos false le estariamos diciento que solo copie la etiqueta template incial y la de cierre
  let $clone = document.importNode($template, true);
  $fragment.appendChild($clone);
});
// de esta manera hariamos una sola incersion 
$card.appendChild($fragment);
```

### DOM: Modificando Elementos (Old Style)

Tenemos otros metodos a demas de `appendChild()` para agregar elementos de manera dinamica.

`appendChild()` siempre agrega el elemento al final del selector objetivo. Pero tenemos otros metodos que nos permite remplazar o insertarlo al inicio o insertarlo en un posicion en particular.

```js
const $cards = document.querySelector(".cars"),
$newCard = document.createElement("figure");

//la manera mas optima no es con innerHTML
$newCard.innerHTML = `
<img src= "https:..." alt="Any">
<figcaption>Any</figcaption>
`;
$newCard.classList.add("card");

// lo que queremos es remplazar un elemento 
//el metodo para remplazar es: replaceChild()
// recibe dos parametros, el valor que decemos insertar y a quien vamos a replazar 
$cards.replaceChild($newCard ,$cards.childen[2]);

// queremos insertarla antes de un nodo que tomemos como referencia
// el metodo se llama: insertBefore()
// recibe dos elementos: el nuevo nodo y el nodo de referencia
// a diferencia de replace no lo va a remplazar, simplemente va a tomar como referencia ese nodo hijo y va insertar el nuevo antes que ese
$cards.insertBefore($newCard , $cards.firstElementChild);

//queremos eliminar un elemento(en ese caso el ultimo elemento)
$cards.removeChild($cards.lastElementChild);


//clonar un nodo
// a diferencia de importNode(importa el template que esta en el html como modelo) el cloneNode lo genera dinamicamente 
// si de parametros no le ponemos o le ponemos false solo estaria clonando el nodo padre, si queremos que clone el contenido interno le tenemos que dar de parametro true
const $cloneCards = $cards.cloneNode(true);
document.body.appendChild($cloneCards)
```

### DOM: Modificando Elementos (Cool Style)

inserta de manera adjacente:
- `.insertAdjacentElement(position,el)` : insera un elemento, parecido a `appendChild`.
- `.insertAdjacentHTML(position, html)` : agrega contenido html, parecido a `innerHTML`.
- `.insertAdjacentText(position,text)` : parecido a un `insetContent`.

Posiciones:
- `beforebegin(hermano anterior)` : antes de el parrafo que tomas de referencia.
- `afterbegin(primer hijo)` : el primer elemento hijo del que tomes como refetencia.
- `beforeend(ultimo hijo)` : el ultimo hijo del que tomes como refetencia.
- `afterend(hermano siguiente)` :  el hermano siguiente.

```js
const $cards = document.querySelector(".cars"),
$newCard = document.createElement("figure");

//la manera mas optima no es con innerHTML
$newCard.innerHTML = `
<img src= "https:..." alt="Any">
<figcaption>Any</figcaption>
`;
$newCard.classList.add("card");

//se inserta intes del nodo de referente(como hermano anterior)
$cards.inserAdjacentElement("beforebegin", $newCard);
// se inserta como primer hijo
$cards.inserAdjacentElement("afterbegin", $newCard);

```

```js
const $cards = document.querySelector(".cars"),
$newCard = document.createElement("figure");

//la manera mas optima no es con innerHTML
let $contentCard = `
<img src= "https:..." alt="Any">
<figcaption>Any</figcaption>
`;
$newCard.classList.add("card");

$newCard.insertAdjacentHTML("beforebegin", $contentCard);
$newCard.querySelector("figcaption").insertAdjacentText("beforebegin", "Any");
$cards.inserAdjacentElement("afterbegin", $newCard);
```

metodos de jquery tambien los acepta js:
- `prepend()` : hijo primero, `inserAdjacentElement("afterbegin")`
- `before()` : hermano anterior, `inserAdjacentElement("beforebegin")`
- `append()` : ultimo hijo , `inserAdjacentElement("beforeend")`
- `after()` : hermano posterior `inserAdjacentElement("afterend")`

### DOM: Manejadores de Eventos

Los eventos es aquel mecanismo que tenemos en javascript para poder controlar las acciones del usuario y definir ciertos comportamientos del documento que sucedan en cierto momento o cuando se cumplan ciertas condiciones.

Las funciones que se ejecutan en un evento es lo que se conoce en ingles como el item handler o en castellano los manejadores de eventos.

Toda funcion que se convierta a un manejador de eventos no puede recibir parametros, el unico parametro que recibe es el **event** en si.

Podemos ver todos los tipos de eventos en [referencia de eventos](https://developer.mozilla.org/es/docs/Web/Events)
Hay 3 maneras de definir los eventos en javascript:

- **Evento con atributo html**(no es la forma mas recomendada) :  para que un evento funcione a manera de atributo lo unico que se tiene que hacer e sinvocarlo de manera simantica.
```html
<!-- COMO ATRIBUTOS TODOS LOS EVENTOS EMPIEZAN CON LA PALABRA on -->
<button onclick="alert('Hola')">
  Evento con atributo HTML
</button>

<!-- se puede poner un alert o una funcion que ya tengamos definida en nuestro codigo javascript -->
<button onclick="holaMundo()">
  Evento con atributo HTML
</button>
```
```js
//codgo js
function holaMundo(){
  //esta funcion es la que se va a convertir en el manejador de eventos 
  alert("Hola mundo");
  // cuando una funcion se convierte en un manejador de eventos, nosotros podemos acceder a un objeto especial que es:
  //  el evento en si, el cual podemos acceder a el con la palabra reservada "event"
  console.log(event);
  // se desecadena un objeto de tipo MoseEvent 
}

```

- **Evento con manejador semantico** : tienen un inconveniente, una vez que has definido el evento semantico solo puede ejecutar una sola funcion. Es decir que por cada evento solo se le puede asignar una funcion.
```html
<!-- html-->
<button id="evento-semantico">Evento con manejador semantico</button>
```
```js
// javascript

function holaMundo(){
  alert("Hola mundo");
  console.log(event);
}

const $eventoSemantico = document.getElementById("evento-semantico")

// la mavoria de los evento inician con la palabra on
// se asigna la funcion sin parentesis
// si se le agregara el parentesis a holaMundo entonces la funcion se ejecuta despues de cargar la pagina.
$eventoSemantico.onclick = holaMundo;
```

- **Manejadores multiples**
```html
<!-- html-->
<button id="evento-multiple">Evento con manejador multiple</button>
```
```js
// javascript

function holaMundo(){
  alert("Hola mundo");
  console.log(event);
}

const $eventoMultiple = document.getElementById("evento-multiple");

//declarar el manejador
// de segundo parametros ingresamos la funcion sin parentesis
$eventoMultiple.addEventListener("click",holaMundo);
$eventoMultiple.addEventListener("click",(e)=>{
  alert("Hola mundo");
  console.log(e);
  //detectar el tipo de evento:
  console.log(e.type)
  //detectar el elemento que lo origina
  console.log(e.target);
  console.log(evento); // es lo mismo que console.log(e);
});

```

### DOM: Eventos con Parámetros y Remover Eventos

```js
// Eventos con parametros

function saludar(nombre = "Desconocid@"){
  alert(`Hola ${nombre}`);
}// esto no se tiene que hacer por que una funcion manejadora de eventos no tiene que llevar parametro, amenos de que se le poga una funcion fecha en addEventListener

const $eventoMultiple = document.getElementById("evento-multiple");

$eventoMultiple.addEventListener("click",() => saludar("Jon"));

// podemos eliminar eventos de un elemento 
```

**Removiendo eventos con manejadores multiples**
```html
<button id="evento-remover">Removiendo eventos con manejadores multiples</button>
```
```js
const $eventoRemover = document.getElementById("evento-remover");

//manrea herronea de hacerla
$eventoRemover.addEventListener("dbclick",(e) => {
  alert(`Removiendo el evento ${e.type}`);
  //removerEventListener necesita dos parametros:
  // el evento que quieres cancelar y la funcion manejadora
  $eventoRemover.removerEventListener("dbclick")
})

//la caracteristica de una funcion anonima en los eventos es que:
// en el momento de que se esta declarando se esta ejecutando, despues se pierde la referencia 
// para remover un manejador de eventos esta tiene que estar guardada en una funcion(con nombre)


//forma correcta de hacerla
const removerDobleClick = (e) => {
  alert(`Removiendo el evento ${e.type}`);
  $eventoRemover.removerEventListener("dbclick", removerDobleClick)
  //vamos a desabilitar el boton con un atributo html llamado desabled
  $eventoRemover.disabled = true;
}

$eventoRemover.addEventListener("dbclick", removerDobleClick);

// de esta manera logramos que el evento solo funcione una vez, por que despues de la primera activacion se elimina momento despues
```

### DOM: Flujo de Eventos (Burbuja y Captura)

Como es que javascript interpreta y trabaja con los eventos.

```html
<!-- html-->
<section class="eventos-flujo">
  <div class="uno">
    1
    <div class="dos">
      2
      <div class="tres">
        3
      </div>
    </div>
  </div>
</section>
```
```css
/*css*/
.eventos-flujo div{
  padding: 4rem;
  font-size: 2rem;
  text-align: center;
}

.uno {
  background: yellow;
}

.dos {
  background: gold;
}

.tres {
  background: lightyellow;
}

```
Principalmente hay dos maneras en que podemos trabajar en como se va propagando el evento.

Una vez que un evento se origina tiene una propagacion a lo largo del arbol del dom, por defecto esa propagacion se va dando desde el elemento mas interno al elemento mas externo y esa fase se llama fase de **burbuja**. Esto ocurre por defecto en los navegadores.

```js
// ejemplo de propagacion
// fase de burbuja
const $divsEventos = document.querySelectorAll(".eventos-flujo div");

function flujoEventos(e){
  console.log("Hola")
}

console.log($divsEventos);

$divsEventos.forEach(div => {
  div.addEventListener("click", flujoEventos)
})

//ahora si en el navegador le damos click los 3 divs nos van a aparecer 6 hola
//Esto es por el efecto de propagacion del evento 

//de esta forma lo podemos ver mas detalladamente:
function flujoEventos(e){
  console.log(`Hola te saluda ${this.className}, el click lo origino ${e.target.className}`)
}

$divsEventos.forEach(div => {
  div.addEventListener("click", flujoEventos)
})
// de esta forma si le damos click en el div 3 los menajes que apareceran seran:
/*
Hola te saluda tres, el click lo origino tres
Hola te saluda dos, el click lo origino tres
Hola te saluda uno, el click lo origino tres
*/
```

`addEventListener` tiene un tercer parametro opcionar que por defecto es `false`, si lo cambiamos por `true` lo ponemos en **fase de captura** del elemento mas externo al elemento mas interno.
```js
// ejemplo de propagacion
const $divsEventos = document.querySelectorAll(".eventos-flujo div");

function flujoEventos(e){
  console.log(`Hola te saluda ${this.className}, el click lo origino ${e.target.className}`)
}

console.log($divsEventos);

$divsEventos.forEach(div => {
  div.addEventListener("click", flujoEventos, true)
})
// de esta forma si le damos click en el div 3 los menajes que apareceran seran:
/*
Hola te saluda uno, el click lo origino tres
Hola te saluda dos, el click lo origino tres
Hola te saluda tres, el click lo origino tres
*/

// dicen que la fase de captura es mas optima que la fase de burbuja, por que no te consume tanta memoria 
```

Cuando en el tercer parametro le pones `true` o `false`, solo hace referencia a la fase de captura o fase de burbuja.

En las utimas versiones el tercer parametro tambien le podemos especificar algunas cosas adicionales, como por ejemplo poder pasarle un objeto.
```js
$divsEventos.forEach(div => {
  div.addEventListener("click", flujoEventos, {
    capture: false,//fase de burbuja 
    // si queremos que el evento se ejecute usa sola vez podemos usar el parametro once
    once: true; // si lo activamos a true el evento se va a ejecutar una sola vez
    // no importa el div que genero el evento, solo se va ejectuar una sola vez 
  })
})
```

### DOM: stopPropagation & preventDefault

Detener la propagacion de los eventos.

Hay veces en que cierto elementos del dom que tienen comportamientos o eventos ya por default, por ejemplo, el input sutmit que tiene un formulario, sin necesidad que nosotro programemos con js el formulario, a la hora de que presionamos el input de tipo sutmit dentro de un formulario, ese formulario se procesa. Otro ejemplo tambien seria el scroll.

```html
<!-- html-->
<section class="eventos-flujo">
  <div class="uno">
    1
    <div class="dos">
      2
      <div class="tres">
        3
        <a href="https://.." target="_blank" rel="noopener">jon.com
      </div>
    </div>
  </div>
</section>
```
```css
/*css*/
.eventos-flujo div{
  padding: 4rem;
  font-size: 2rem;
  text-align: center;
}

.uno {
  background: yellow;
}

.dos {
  background: gold;
}

.tres {
  background: lightyellow;
}

```
```js
// ejemplo de propagacion
const $divsEventos = document.querySelectorAll(".eventos-flujo div"), $linkEventos = document.querySelector("eventos-flujo a");

function flujoEventos(e){
  console.log(`Hola te saluda ${this.className}, el click lo origino ${e.target.className}`)
  //vamos a eliminar la propagacion con stopPropagation
  e.stopPropagation(); 
}

console.log($divsEventos);

$divsEventos.forEach(div => {
  // al usar el stopPropagation se recomienda deja el estado en estado de burbuja 
  div.addEventListener("click", flujoEventos)
})

$linkEventos.addEventListener("click", e => {
  alert("Hola");
  // cancelar la accion que tenga por default el elemento, en este caso el mento del enlace, la accion por default es abrir una nueva pesta;a:
  e.preventDefault();
  e.stopPropagation(); 
});

```

### DOM: Delegación de Eventos

```html
<!-- html-->
<section class="eventos-flujo">
  <div class="uno">
    1
    <div class="dos">
      2
      <div class="tres">
        3
        <a href="https://.." target="_blank" rel="noopener">jon.com
      </div>
    </div>
  </div>
</section>
```
```css
/*css*/
.eventos-flujo div{
  padding: 4rem;
  font-size: 2rem;
  text-align: center;
}

.uno {
  background: yellow;
}

.dos {
  background: gold;
}

.tres {
  background: lightyellow;
}

```
```js
// ejemplo de propagacion
// una particularidad importante de la delegacion de evento es que tambien vamos a evitar la propagacion

// en la delegacion de eventis el addEventListener se lo vamos a poner al document
document.addEventListener("click", (el) => {
  //el metodo matches busca un selector valido
  if(e.target.matches(".eventos-flujo a")){
    e.preventDefault();
    // el stopProgation no es necesario ya que el listener lo tiene el document y como el document es el nodo raiz de nuestro documento ya no hay un nodo padre de document al cual propagar 
  }
})

// esta es la forma mas optima de trabajar los eventos en js
```

### BOM: Propiedades y Eventos

```html
<!-- Manejo de BOM html-->
```

```js
window.innerHeigth;
window.innerWidth; //hace referencia al tama;o del ancho de nuestra ventana (viwport)
window.outerHeigth;
window.outerWidth; // hace referencia al tama;o del ancho de nuestra ventana

// evento despues de modificar la longitud de la ventana del navegador : resize
window.addEventListener("resize", e=>{})

//despazamiento del scroll:
window.scrollX; // cuando se aleja del margern top
window.scrollY; // cuando se aleja del marjen izquierdo
window.addEventListener("scroll", e=>{})

// en que cordenada de la pantalla empieza a dibujarse la ventana del navegador:
window.addEventListener("load", e=>{})
window.screenX;
window.screenY;
// load es disparado cuando el documento html ha sido cargado y parceado, es decir cuando el navegador ya tiene todas las etiquetas perfectamente parceadas en su arbol de elementos 

// carga de la ventana en jquery:
$(window).load(function);
$(window).on("load", function);
$(document).on("ready", function);
$(document).ready(function);

// carga de la ventana en js
window.addEventListener("DOMContentLoaded", e=>{})
// para hacer que algo se carge en cuando el dom este listo es mucho mas eficiente trabajar con el DOMContentLoaded
//DOMContentLoaded no va a esperar a que cargen las hojas de estilo, las imagenes las subtramas o los scrips para que empeice a funcionar 
```

### BOM: Métodos

EL BOM no es un estandar puede variar de un navegador a otro.

```js
//estos metodos se pueden usar sin poner el window
window.alert("Alert");//alerta
window.confirm("confirmacion")// mensaje con boton de aceptar y cancelar(true or false)
window.prompt("");// mensaje que se puede aceptar y cancelar y te permite agregar un input
```
para utilizar los siguienes metodos vamos a crear unas ventanas en el html
```html
<button id="abrir-ventana">Abrir Ventana</button>
<button id="cerrar-ventana">Cerrar Ventana</button>
<button id="imprimir-ventana">Imprimir Ventana</button>
```
```js
const $btnAbrir = document.getElementById("abrir-ventana");
const $btnCerrar = document.getElementById("cerrar-ventana");
const $btnImprimir = document.getElementById("imprimir-ventana");

let ventana;

$btnAbrir.addEventListener("click",e=>{
  //abrir una ventana emergente
  ventana = window.open("https://...");
})
$btnCerrar.addEventListener("click",e=>{
  //cerrar la ventana en la que nos encontramos
  window.close();
  // si queremos cerrar una ventana emergente que acavamos de abrir entonces primero se tiene que guardar en una variable y despues ponemos el close en la variable:
  ventana.close();
  
})
$btnImprimir.addEventListener("click",e=>{
  // mandar a la opcion de imprimir(a una impresora)
  window.print();
})

```

### BOM: Objetos: URL, Historial y Navegador

```js


// Objeto URL(location)

console.log(location)
// el objeto "location" tiene varias propiedades:
location.assign() //permite remprazar una url con otra
location.reload() // permite recargar la pagina 
location.origin; // la ruta de la cual se origina
location.protocol; //protocolo
location.host; // host (nombre del dominio)
location.hostname; // host (nombre del dominio)
location.port; //puerto, si imprime "" significa que es el puerto 80 el cual es el predeterminado 
location.href;//urlcompleta
location.hash; //detectar el valor de la url que esta despues de un "#"
location.pathname; //es el archivo al cual se esta consultando(el que esta despues de host)
location.search; //detecta parametros por la url es decir lo que esta despues de un "?"
```
```js
// Objeto Historial(history)

history; //historial de paginas
history.back(3); //regresar a paginas anteriores
history.forward(3) // paginas adelante en el hsitorial
history.go(-1)//pagina anterior del historial
history.go(1)//una pagina hacia delante de las de mi hsitroial
```

```js
// Objeto Navegador (navigator)

navigator.userAgent; //sistema operativo y navegador del usuario
navigator.connection; // informacion de la coneccion del usuario
navigator.geolocation; //geolocalizacion
navigator.mediaDevices; //camara y microfonos 
navigator.mimeTypes; // tipos de formatos, que depentiendo del tipo de aplicacion soportan los navegadores web 
navigator.onLine; //evento para detectar cuando el usuario pierde la conceccion a internet 
navigator.serviceWorker; // nos ayudar a hacer PWA, es decir a convertir un sitio web en una aplicacion instalable
navigator.storage; //appi de almacenamiento 
navigator.usb; //capacidad de tectar dispositivos usb 
```

## Ejercicios Prácticos del DOM

### Menu de Hamburgesa
Este ejercicio tambien se puede hacer con la ayuda del dise;o css de la pagina [hamburger](https://jonsuh.com/hamburgers/), tambien con la ayuda del [cdn hamburgers](https://cdnjs.com/libraries/hamburgers), eligiremos la hoja de estilos minificada y la pondremos en un link de html.
en js utilizar el metodo `matches` para interactuar con el html.
```js
(function(){
    const $navBurger = document.querySelector(".nav-burger");
    const $burger = document.querySelector(".burger");
    const idDivs = ["hambur-1","hambur-2","hambur-3"];
    const burgerStyle = {
        "height":"5rem",
        "width":"5rem",
        "border":".3rem solid #ffffff",
        "border-radius" : "50%",
        "display": "flex",
        "flex-direction": "column",
        "justify-content": "center",
        "align-items": "center",
        "cursor": "pointer",
        "z-index": "9999"
    };
    const burChilStyle = {
        "height": ".3rem",
        "width" : "3rem",
        "background" : "#ffffff",
        "margin": ".2rem 0",
    };
    const navStyle = {
        "position": "absolute",
        "background": "#14213d",
        "height": "100vh",
        "width": "80vw",
        "top":"0",
        "right" : "0",
        "display": "flex",
        "justify-content": "center",
        "align-items": "center",
        
        "transform": "translateX(100%)",
        "transition": "transform 0.5s ease-in"
    };
    const ulStyle= {
        "display": "flex",
        "justify-content": "space-around",
        "align-items": "center",
        "flex-direction": "column",
        "height": "80%",
        "width": "80%"
    };

    const aStyle = {
        "color": "#ffffff",
        "text-decoration": "none",
        "letter-spacing": ".3rem",
        "font-weight": "bold",
        "font-size": "3rem",
        "font-family": "sans-serif"
    }


    function burgerActive(){
        $burger.classList.toggle("#");
            document.getElementById("hambur-2").style.setProperty("opacity","1");
            document.getElementById("hambur-1").style.transform = "none";
            document.getElementById("hambur-3").style.transform = "none";
    }
    function navDeactiv(){
        $navBurger.style.setProperty("transform","translateX(100%)");
        $navBurger.querySelectorAll("li").forEach((li,index) => {
            li.style.setProperty("opacity","0");
        });
    }
    function burgerDeactiv(){
        $burger.classList.toggle("#");
            document.getElementById("hambur-2").style.setProperty("opacity","0");
            document.getElementById("hambur-1").style.transform = "rotate(-45deg) translate(-.5rem, .5rem)";
            document.getElementById("hambur-3").style.transform = "rotate(45deg) translate(-.5rem, -.5rem)";
    }
    function navActive(){
        $navBurger.style.setProperty("transform","");
        $navBurger.querySelectorAll("li").forEach((li,index) => {
            li.style.setProperty("opacity","1");
        });
    }
    
    Object.entries(burgerStyle).forEach(el => {
        $burger.style.setProperty(el[0],el[1])
    })
    
    
    idDivs.forEach(id => {
        let $div = document.createElement("div");
        $div.setAttribute("id",id);
        Object.entries(burChilStyle).forEach(el => {
            $div.style.setProperty(el[0],el[1])
        });
        $burger.insertAdjacentElement("beforeend",$div);
    });

    Object.entries(navStyle).forEach(el => {
        $navBurger.style.setProperty(el[0],el[1])
    });

    $navBurger.querySelectorAll("li").forEach((li,index) => {
        li.style.setProperty("list-style","none");
        li.style.setProperty("opacity","0");
        li.style.setProperty("transition", `opacity 0.5s ease ${index / 7 + .3}s`);
    });

    $navBurger.querySelectorAll("a").forEach(a =>{
        Object.entries(aStyle).forEach(es => {
            a.style.setProperty(es[0],es[1]);
        })
    })

    Object.entries(ulStyle).forEach(es => {
        $navBurger.querySelector("ul").style.setProperty(es[0],es[1]);
    })

    $burger.addEventListener("click",()=>{
        if($burger.classList.contains("#")){
            burgerActive();
            navDeactiv();   
        }else{
            burgerDeactiv();
            navActive();
        }
    })
})();
/*Estructura del html para que funcione este codigo
<etiqueta class="nav-burger">
    <ul>
        <li>
            <a></a>
        </li>
    </ul>
</etiqueta>
<etiqueta class="burger">/<etiqueta>
*/


```
### Relog Digital y Alarma Sonora

los metodos de la etiqueta `audio` son:
- `.play`
- `.stop`
- `.pause`
- `.currentTime`: permite que el audio se reinice.
```js
const d = document;

export default function relog(){
    if (d.querySelector(".tempo")){
        const botonAll = ["Inciar Relog", "Detener Relog", "Iniciar Alarma", "Detener Alarma"];
        let varInverval;
        botones(botonAll);
        funcionalidad(botonAll,varInverval);
    }
}

function botones(botonAll){
    
    const $fragment = d.createDocumentFragment();

    botonAll.forEach(el => {
        let $button = d.createElement("button");
        $button.textContent = el;
        $button.setAttribute("id", el.split(" ").join(""));
        $fragment.appendChild($button);
    });
    d.querySelector(".tempo").appendChild($fragment);
};

function funcionalidad(botonAll,varInverval){
    
    d.querySelector(`#${botonAll[0].split(" ").join("")}`).addEventListener("click",()=>{
        varInverval = setInterval(()=>{
            d.querySelector(`#${botonAll[0].split(" ").join("")}`).disabled = true;
            let fecha = new Date();
            let hora = fecha.toLocaleTimeString();
            d.querySelector(`#${botonAll[0].split(" ").join("")}`).innerHTML = `${hora}`
        })
    });
    d.querySelector(`#${botonAll[1].split(" ").join("")}`).addEventListener("click",()=>{
        d.querySelector(`#${botonAll[0].split(" ").join("")}`).disabled = false;
        clearInterval(varInverval);
        d.querySelector(`#${botonAll[0].split(" ").join("")}`).innerHTML = `${botonAll[0]}`;
    });
    d.querySelector(`#${botonAll[2].split(" ").join("")}`).addEventListener("click",()=>{
        d.querySelector(`#${botonAll[2].split(" ").join("")}`).disabled = true;
        let $audio = `<audio id="audio" src="./css/javascript/musica/Mr.Kitty - After Dark.mp3"autoplay="autoplay" preload="">
        </audio>`
        d.querySelector(".tempo").insertAdjacentHTML("beforeend", $audio);
    });
    d.querySelector(`#${botonAll[3].split(" ").join("")}`).addEventListener("click",()=>{
        d.querySelector(`#${botonAll[2].split(" ").join("")}`).disabled = false;
        if(d.querySelector("#audio")){
            d.querySelector(".tempo").removeChild(d.querySelector("#audio"))
        }
    });
}// solo necesita: <div class="tempo"></div>
```

### Eventos de Teclado(atajos)

`.addEventListener("keydown")` :  evento que ocurre cuando presionamos una tecla. Es el mas utilizado.
`.addEventListener("keyup")` :  evento que ocurre cuando soltamos la tecla.
`.addEventListener("keypress")` :  evento que ocurre cuando mantenemos la trcla presionada sin soltarla.

`event.key` : retorna la llave del teclado que se presiono en el evento.

**ejerciico de la pelotita**
EL ejercicio de la pelotita tambien se puede hacer con:
`.getBoundingClientRect()` : que te permite saber la posicion de un objeto dentro de la ventana del navegador.
`transform: translate` : tambien para hacer el movimiento podemos usar `transform: translate` de css.
`event.preventDefault()` : previene los efectos por defecto del navegador.

```js
const d = document;

export default function atajos(){
    const d = document;
    if(d.querySelector(".espacio")){
        pelota();
        manejador();
    }

}

function pelota(){
    const $newDiv = d.createElement("div");
    $newDiv.setAttribute("id", "pelota");
    $newDiv.style.width = "10%";
    $newDiv.style.height = "10%";
    $newDiv.style.background = "rgb(214, 16, 16)";
    $newDiv.style.borderRadius = "50%";
    $newDiv.style.top = "0px";
    $newDiv.style.right = "0px";
    $newDiv.style.position = "relative"
    d.querySelector(".espacio").insertAdjacentElement("beforeend", $newDiv);
}

function manejador(){
    const $div = d.querySelector("#pelota")
    /*let valor = getComputedStyle($div).getPropertyValue("position");*/
    d.addEventListener("keydown", ()=>{
        if(event.key === "ArrowUp"){
            let pos = parseInt($div.style.top.replace("px",""));
            if(pos > 0){
                $div.style.top = `${pos - 10}px`;
            };
        };
        if(event.key === "ArrowDown"){
            let pos = parseInt($div.style.top.replace("px",""));
            if(pos < 260){
                $div.style.top = `${pos + 10}px`;
            };
        };
        if(event.key === "ArrowRight"){
            let pos = parseInt($div.style.right.replace("px",""));
            if(pos > -260){
                $div.style.right = `${pos - 10}px`;
            };
        };
        if(event.key === "ArrowLeft"){
            let pos = parseInt($div.style.right.replace("px",""));
            if(pos < 0){
                $div.style.right = `${pos + 10}px`;
            };
        };
    })
}
```

### Cuenta regresiva
```js
const d = document;
export default function cuentaRegresiva(clase,fecha){
  if(d.querySelector(`.${clase}`)){
      const selec = d.querySelector(`.${clase}`);
    const varInterval = setInterval(()=>{
    let seconds0 = new Date(fecha).getTime() - new Date().getTime();
    if( seconds0 > 0){let meses = new Date(seconds0).getUTCMonth() - new Date(0).getUTCMonth();
        let dias = new Date(seconds0).getUTCDate() - new Date(0).getUTCDate();
        let horas = new Date(seconds0).getUTCHours() - new Date(0).getUTCHours();
        let minutos = new Date(seconds0).getUTCMinutes() - new Date(0).getUTCMinutes();
        let segundos = new Date(seconds0).getUTCSeconds() - new Date(0).getUTCSeconds();
        selec.innerHTML = `<div>meses: ${meses},  dias : ${dias},  horas : ${horas},  minutos: ${minutos},  segundos: ${segundos}</div>`;
    }else{
        selec.innerHTML = `<div>FELIZ CUMPLE AÑOS!!!</div>`
        clearInterval(varInterval);
    }
    
    },1000)
}}

```

### Boton scroll
```js
const d = document;
export default function botonScroll(flecha,etqObj){
    if(d.querySelector(`.${flecha}`)){
        boton(flecha,etqObj);
        eventoScroll(flecha);
    }
}

function boton(flecha,etqObj){
    document.querySelector("html").style.scrollBehavior = "smooth";
    document.querySelector(`${etqObj}`).setAttribute("id", "main");
    const $selector = d.querySelector(`.${flecha}`);
    const $fragment = d.createDocumentFragment();
    $selector.style.height = "5rem";
    $selector.style.width = "5rem";
    $selector.style.background = "linear-gradient(145deg, #ffffff, #e6e6e6)"
    $selector.style.borderRadius = "50%";
    $selector.style.boxShadow = " 7px 7px 13px #999999,-7px -7px 13px #ffffff";
    $selector.style.position = "absolute";
    $selector.style.left = "85vw";
    $selector.style.top = "85vh";
    $selector.style.display = "flex";
    $selector.style.alignItems = "center";
    $selector.style.justifyContent = "center";
    $selector.setAttribute("href","#main");
    $selector.style.transform = "translateY(200%)";
    $selector.style.transition = "transform 0.5s ease";
    [1,2,3].forEach(n =>{
        let $div = d.createElement("div");
        $div.setAttribute("id", `div${n}`);
        $div.style.background = "rgb(71, 71, 71)";
        $div.style.width = ".6rem";
        $div.style.height = "3rem";
        $div.style.borderRadius = "50px";
        $fragment.appendChild($div);
    })
    $selector.appendChild($fragment);

    if(d.querySelector("#div1") && d.querySelector("#div2") && d.querySelector("#div3")){
    const $div1 = d.querySelector("#div1"),
    $div2 = d.querySelector("#div2"),
    $div3 = d.querySelector("#div3");
    $div1.style.height = "2.5rem";
    $div1.style.transform = `translateY(${$div2.getBoundingClientRect().y - $div1.getBoundingClientRect().y }px) rotate(39deg)`;
    $div3.style.height = "2.5rem";
    $div3.style.transform = `translateY(${$div2.getBoundingClientRect().y - $div3.getBoundingClientRect().y }px) rotate(-39deg)`;
    $div2.style.opacity = 0;
    }
    
}

function eventoScroll(flecha){
    const $selector = d.querySelector(`.${flecha}`);
    const scrolling = () => {
        let scroll = d.documentElement.scrollTop;
        if(scroll > 350){
            $selector.style.transform = "none";
        }
        if(scroll < 350){
            $selector.style.transform = "translateY(200%)";
        }
    }
    
    window.addEventListener("scroll", scrolling);
}
```

### localStorage

el `localStorage` nos permite almacenar una variable en el disco duro de el navegador del usuario. Tambien es un objeto que reconoce el navegador.

en el navegador hay `inspect` en la esta;a `Application`, ahi se encuentra la informacion del `Local Storage`. En el `local storage` puedes guardar hasta 5mb de informacion

tambien existe el `web storage` que es como una sesion php(un manejo de sesion), pero del lado del navegador.

- `localStorage.getItem()` : el metodo para obtener del local storage una variable de tipo local storage y de parametro es el nombre de la variable.

-`localStorage.setItem()` :  metodo para establecer una variable de tipo local storage y recibe dos parametros (el nombre de la varaible y el valor)

### Resposive con JavaScript
`Window.matchMedia()`: es el objeto que nos permite manejar las media queryes de css pero en js.
```js
const d = document;
const w = window;
export default function mediaQuerys(id,mq,mobileContent,deskContent){
    let breakpoint = w.matchMedia(mq);
    const responsive = (e) =>{
        if(e.matches){
            d.getElementById(id).innerHTML = mobileContent;
        }else{
            d.getElementById(id).innerHTML = deskContent;
        }
    }
    breakpoint.addListener(responsive)
    //ejecutamos de nuevo la funcion para que cuando carge el document verifique el width
    responsive(breakpoint); 
}
```
### Responsive Tester
```html
<form id="tester">
  <label>Responsive Tester</label>
  <br>
  <input name="direccion" type="url" placeholder="link" required>
  <br>
  <input name="ancho" type="text" placeholder="width" required>
  <br>
  <input name="alto" type="text" placeholder="height" required>
  <br>
  <input name="probar" type="submit" value="probar">
  <input name="cerrar" type="button" value="cerrar">
</form>

```
```js
const d = document;
export default function responsiveFrom(id){
    const $form = d.getElementById(id);
    let tester;
    d.addEventListener("submit",e=>{
        if(e.target === $form){
            e.preventDefault();
            tester = window.open($form.direccion.value, "tester", `innerWidth=${$form.ancho.value}`,`innerHeight=${$form.alto.value}`)
        }
    });
    d.addEventListener("click", (e)=>{
        if(e.target === $form.cerrar){
            tester.close();
        }
    })
```

### Detección de Dispositivos User Agent
```js
const d = document, 
n = navigator,
ua = n.userAgent;
export default function userDiviceInfo(id){
    console.log(ua)// una cadena de texto con informacion como:
    //el dispositivo desde el que nos esta visitando nuestro usuario
    const $id = d.getElementById(id);
    //para poder hacer validaciones de dispositivo
    const isMobile = {
        android: ()=> ua.match(/android/i),
        ios: ()=> ua.match(/iphone|ipad|ipod/i),
        windows: ()=> ua.match(/windows phone/i),
        any: function (){
            return this.android() || this.ios() ||this.windows();
        }
    };
    //para poder hacer validaciones de computador
    const isDesktop = {
        linux: ()=> ua.match(/linux/i),
        mac: ()=> ua.match(/mac os/i),
        windows: ()=> au.match(/windows nt/i),
        any: function (){
            return this.linux() || this.mac() ||this.windows();
        }
    };
    //para poder hacer validaciones de navegador
    const isBrowser = {
        chrome: () => ua.match(/chrome/i),
        safari:() => ua.match(/safari/i),
        firefox:() => ua.match(/firefox/i),
        opera: () => ua.match(/opera|opera mini/i),
        ie: () => ua.match(/msie|iemobile/i),
        edge: () => ua.match(/edge/i),
        any: function(){
            return this.ie()|| this.edge() || this.chrome() || this.safari() || this.firefox() || this.opera();
        }
    };

    $id.innerHTML = `
    <ul>
        <li>User Agent: <b>${ua}</b></li>
        <li>Plataforma: <b>${
            isMobile.any()? isMobile.any():isDesktop.any()
        }</b></li>
        <li>Navegador: <b>${is.isBrowser.any()}</b></li>
    </ul>
    `
}
```

### Detección del estado de la red

`navigator.onLine` : devuelve true si tenemos internet.
`window.addEventListener("online")`: se activa el evento cuando recuperamos la coneccion de internet
`window.addEventListener("offline")`: se activa el evento cuando perdemos la coneccion de internet.

con `inspect` del nagador en la pesta;a  `Aplication/service workers` existe una opcion  llamada `offline` y sirve para simular la desconeccion de internet.

### Deteccion de la WebCam
```html
<video id="steam"></video>
```
`navigator.mediaDevices` : es un objeto

`navigator.mediaDevices.getUserMedia` : recibe una serie de parametros como:
```js
const $video = d.getElementById("steam");
// esta funcion es una promesa
// en el `then` en caso de que tenga existo sera la ejecucion del stream 
navigator.mediaDevices.getUserMedia({video:true, audio:false}).then(stream =>{
console.log(stream);
$video.srcObject = stream;// si solo ponemos esta opcion el resultado sera una fotografia, si queremos que sea un stream entonces debemos ejecutar el metodo play:
$video.play();
}).catch(err =>{
  console.log(err)
})
```

### Detección de la Geolocalización
`navigator.geolocation` 
`navigator.geolocation.watchPosition()` : ver cualquier cambio en la localizacion.(cuando detecta un cambio de posicion)
`navigator.geolocation.getCurrentPosition()` : funcion para obtener la posicion actual. los parametros que necesitan son:
- una funcion que se va a ejecutar en caso de exito 
- una funcion en caso de error 
- las opciones
```js
const $id = document.getElementById(id), 
options = {
  enableHighAccuracy: true, //le estamos diciendo al dispositivo que trate de hacer la mejor lectura posible 
  timeout: 5000, // cuanto tiempo va estar esperando la respuesta para tomar la lectura, en milisegundos 
  maximumAge: 0 // para que no se guarde en cache las lecturas, para que cada vez que tome una lectura no tome de referencia la anterior 
};

const sucess = (position) => {
console.log(position);
let coords = position.coords; //coordenadas
coords.latitude
coords.longitude
coords.accuracy //pesicion(metros)

}

const error = (err) = > {
console.log(err);
};

navigator.geolocation.getCurrentPosition(success,error,options);
```

### Filtros de Busqueda 
```html
<div>
            <input type="search" placeholder="buscar..." class="card-filter">
            <article class="cards">
                <figure class="card">
                    <img src="https://placeimg.com/200/200/nature" alt="Nature">
                    <figcaption>Nature</figcaption>
                </figure>
                <figure class="card">
                    <img src="https://placeimg.com/200/200/any" alt="Any">
                    <figcaption>Any</figcaption>
                </figure>
                <figure class="card">
                    <img src="https://placeimg.com/200/200/tech" alt="Tech">
                    <figcaption>Tech</figcaption>
                </figure>
                <figure class="card">
                    <img src="https://placeimg.com/200/200/people" alt="People">
                    <figcaption>People</figcaption>
                </figure>
            </article>
</div>
```
```css
/* ****searchFilters**** */
.cads{
    display: grid;
    grid-template-columns: repeat(auto-fit,minmax(250,1fr));
}
.card {
  transition: all 0.3s ease-out;
}

.card figcaption{
    padding: 1rem;
}
/* los resultados que no coincidan se les dara el filter*/
.filter{
  /* el display no es animable con transition*/
    /*display: none;*/
    visibility: hidden;
    opacity: 0;
    order:1;
}
```
```js
const d = document;
export default function searchFilters(input,selector){
    d.addEventListener("keyup",e=>{
        if(e.target.matches(input)){
            //console.log(e.target.value); //esto muestra la letra que se puse y se va autocompleta automaticamnete formando las palabras
            if(e.key === "Escale"){
                e.target.value = "";
            }
            d.querySelectorAll(selector).forEach(el =>{
                // va evaluar si el texto de las tarjetas es igual al texto que se este ingresando 
                if(el.textContent.toLowerCase().includes(e.target.value)){
                    el.classList.remove("filter")
                }else{
                    el.classList.add("filter")
                }
            })
        }
    })
}
```
### Sorteo Digital 

```html
<div>
            <ul class="players">
                <li class="player">JavaScript</li>
                <li class="player">PHP</li>
                <li class="player">Java</li>
                <li class="player">C</li>
                <li class="player">Python</li>
                <li class="player">Ruby</li>
                <li class="player">Go</li>
                <li class="player">Visual Basic</li>
                <li class="player">Rust</li>
                <li class="player">Perl</li>
            </ul>
            <button id="winner-btn">Obtener Ganador</button>
        </div>
```
```js
const d = document;
export default function draw(btn,selector){
    const getWinner = (selector) =>{
        const $players = d.querySelectorAll(selector),
        random = Math.floor(Math.random() * $players.length),
        winner = $players[random];

        return `EL ganador es: ${winner.textContent}`
    }
    d.addEventListener("click", e => {
        if(e.target.matches(btn)){
            let result = getWinner(selector);
            alert(result);
        }
    })
}
```

### ScrollSpy con Intersection Observer
`IntersectionObserver()` : recibe de parametros una funcion y varias opciones
```js
const d = document;
function scrollSpy(){
  //data-scroll-spy es un data atribut inventado
  const $sectios = d.quetySelectorAll("section[data-scroll-spy]")
  //los entries son todos los objetos que estan entrando a las visualizaciones de viewport
  const cb = (entries) => {
    console.log(entries) //es un objeto con diferentes metodos, conteien las secciones totales
    entries.forEach(entry => {
      const id = entry.target.getAttribute("id")
      console.log(entry)//las secciones de manera individual
      //las entry y las entries contienen el `isIntersecting` que es si ya esta en el limite donde es visible conforme scrolleamos
      if(entry.isIntersecting){
        d.querySelector(`a[data-scroll-spy][href="#${id}"]`).classList.add("active");
      }else{
        d.querySelector(`a[data-scroll-spy][href="#${id}"]`).classList.remove("active");
      }
    })
  }

  const observer = new IntersectionObserver(cb,{
    //root hace referencia a el documento
    //rootMargin margen top rigth bottom left en pixeles forzosamente
    // con el rootMargin reducimos el harea de interaccion para que no nos marque dos selectores al mismo timpo, para ello le tenemos que car un valor negativo
    //rootMargin: "-250px"
    // threshold es la opcion del limite con un valor de 0 a 1
    //threshold: 0.5
    //con threshold: 0.5 cuando el elemento tenga 50% de su contenido ya visible en el viewport 
    // tambien podemos manejar maximos y minimos con threshold simplemente poniendoles en un arreglo
    threshold: [0.5,0.75]
  });
  console.log(observer)//un objeto que contiene varias opciones

  $sections.forEach(el => Observer.observe(el))
}

```
### Video Inteligente (IntersectionObserver & VisibilityChange) 
`document.visibilityState`
`window.addEventListener("visibilitychange")`

Video inteligente que al momento que detecte que esta siendo observado se va a reproducir
```html
<!--El atributo muted es para reproducir sin sonido.

El atributo loop es para reproducri en bucle el video-->
<video src="" muted controls loop>
</video>
```

```js
const d = document, w = window;

export default function smartVideo(){
  const $videos = d.querySelectorALL("video[data-smart-video]");

  const cb = (entries) => {
    entries.forEach(entry =>{
      if(entry.isIntersecting){
        entry.target.play();
      }else{
        entry.target.pause();
      }

      //para que en caso de que cambiemos de pesta;a se pause el video:
      window.addEventListener("visibilitychange". e =>{
        if(document.visibilityState === "visible"){
          entry.target.play();
        }else{
          entry.target.pause()
        }
      })
    })
  }

  const observer = new IntersectionObserver(cb,{threshold: 0.5});

  $videos.forEach(el => observer.observe(el))
}
```

## AJAX: Asynchronous JavaScript And XML

### AJAX
**AJAX** significa **Asynchronous JavaScript And XML**. En pocas palabras, es el uso del objeto XMLHttpRequest para comunicarse con los servidores.

Puede enviar y recibir información en varios formatos, incluidos JSON, XML, HTML y archivos de texto.

El atractivo de **AJAX** es su naturaleza "asíncrona", lo que significa que puede comunicarse con el servidor, intercambiar datos y actualizar la página sin tener que recargar el navegador.

**AJAX** no es una tecnología en sí mismo. En realidad, se trata de varias tecnologías independientes que se unen:

- **HTML** y **CSS**, para crear una presentación basada en estándares.
- **DOM**, para la interacción y manipulación dinámica de la presentación.
- **HTML**, **XML** y **JSON**, para el intercambio y la manipulación de información.
- **XMLHttpRequest** o **Fetch**, para el intercambio asíncrono de información.
- **JavaScript**, para unir todas las demás tecnologías.
Es importante también considerar los [Códigos de estado de respuesta HTTP](https://developer.mozilla.org/es/docs/Web/HTTP/Status) y los estados de la petición **AJAX**:

Estado | Valor
-------|--------
READY_STATE_UNINITIALIZED |	0
READY_STATE_LOADING | 1 
READY_STATE_LOADED | 2
READY_STATE_INTERACTIVE | 3
READY_STATE_COMPLETE | 4

### Métodos Nativos
- ActiveXObject (IE8 e inferiores, esta depreciado)
- [XMLHttpRequest](https://developer.mozilla.org/es/docs/Web/API/XMLHttpRequest)
- [API Fetch](https://developer.mozilla.org/es/docs/Web/API/Fetch_API)

### Librerías Externas
- [jQuery.ajax()](https://api.jquery.com/category/ajax/)
- [Axios](https://github.com/axios/axios)
- etc.

### Objeto XMLHttpRequest
Como ajax trabaja parte con el cliente pero tambien parte se ejecuta en el servidor, es muy importante que ajax se ejecute de manera local en un servidor web.

Hay una pagina muy famosa para practicar se llama [Json Placeholder](https://jsonplaceholder.typicode.com/). Este servicio es un api falsa para hacer pruebas y prototipos

```html
<h2>Objeto XMLHttpRequest</h2>
<ol id="xhr"></ol>

<script src="./ajax.js"></script>
```
```js
(()=>{
    // vamos ha crear una variable que haga una instancia del objeto httprequest
    const xhr = new XMLHttpRequest(),
    $xhr = document.getElementById('xhr'),
    $fragment = document.createDocumentFragment();

    // para que el objeto xmlhttprequest funcione neceita 4 cosas: 
    //1: la instancia (xhr en esta ocacion)
    //2: asignar un evento 
    // el evento que mas se utiliza en ajax es el "readystatechange"
    // readystatechange se lanza cuando detecta cualquier cambio de estado 
    //ya sea que la peticion s ehaya bortado, que haya lanzado un error , que se haya completado, etc.
    xhr.addEventListener("readystatechange",e=>{} )

    //3: tambien necesitamos la instruccion que va abrir la peticion 
    xhr.open("GET","https://jsonplaceholder.typicode.com/users");
    //4: enviar la peticion
    xhr.send();
})();
```
EL codigo completo:
```js
(()=>{
    const xhr = new XMLHttpRequest(),
    $xhr = document.getElementById('xhr'),
    $fragment = document.createDocumentFragment();

    xhr.addEventListener("readystatechange",e=>{
        //la primera validadion que se tiene que hacer es:
        if(xhr.readyState !== 4) return; // esto por que hasta que el readyState este "incompletado" nosotros podemos hacer una manipulacion en el dom de la informacion que tengamos en el servidor.
        if(xhr.status >= 200 && xhr.status < 300){
            //la respuesta de la peticion esta en: xhr.responseText
            // pero tenemos que parsear la respuesta de la api (es decir interpretarlo a objeto javascript)
            let json = JSON.parse(xhr.responseText);

            json.forEach(el =>{
                const $li = document.createElement('li');
                $li.innerHTML = `${el.name} -- ${el.email} -- ${el.phone}`;
                $fragment.appendChild($li);
            })

            $xhr.appendChild($fragment);
        }else{
          let message = xhr.statusText || "Ocurrio un error";
          $xhr.innerHTML = `Error ${xhr.status}: ${message}`;
        }
    });
    //tambien se puede hacer de manera local
    xhr.open("GET","https://jsonplaceholder.typicode.com/users");

    xhr.send();
})();
```

### API Fetch
```html
<h2>API Fetch</h2>
<ol id="fetch"></ol>

<script src="./ajax.js"></script>
```
```js
(() =>{
    const $fetch = document.getElementById('fetch'),
    $fragment = document.createDocumentFragment();

    // el primer parametro de fetch es la direccion del recurso
    // adicionalmente se le puede pasar un objeto con opciones
    //fetch es un mecanismo que trabaja con promesas
    // independientemente de que mi codigo se ejecute o no, nosotros necesitamamos que sierto codigo se resuelva, para eso podemos eejecutar una funcion de las promesas que se llama "finally()"

    fetch("https://jsonplaceholder.typicode.com/users").then(res =>{
    //res sera un objeto de tipo response
    // esta respuesta la tenemos que convertir a un objeto valido
    // el metodo fetch tiene un metodo llamado .json() para convertir la respuesta a texto json 
    //res.json();
    //pero dependiendo de lo que estemos recibiendo tambien lo podemos convertir a codigo html
    //res.text()
    // en caso de que recibamos una imagen en formato data uri podemos usar .blob()
    //res.blob()
    return res.ok ? res.json() : Promise.reject(res);
    //res.ok ? res.json() : Promise.reject(res); es una validacion para que en dado caso que la petichion falle se creara el error para pasarlo al catch
    // con return lo que estamos haciando es pasar el resultado al siguiente then
    }).then(json =>{
        json.forEach(el =>{
            const $li = document.createElement('li');
            $li.innerHTML = `${el.name} -- ${el.email} -- ${el.phone}`;
            $fragment.appendChild($li);
        })

        $fetch.appendChild($fragment);
    }).catch(err =>{
        let message = err.statusText || "Ocurrio un error";
        $fetch.innerHTML = `Error ${err.status}: ${message}`; 
    }).finally();
})();
```

### API Fetch + Async-Await
```html
<h2>API Fetch + Async-Await</h2>
<ol id="fetch-async"></ol>

<script src="./ajax.js"></script>
```
```js
(()=>{
    const $fetchAsync = document.getElementById('fetch-async'),
    $fragment = document.createDocumentFragment();

    async function getData(){
        try{
            let res = await fetch("https://jsonplaceholder.typicode.com/users"),
            json = await res.json();

            if(!res.ok){
                throw {status: res.status, statusText : res.statusText}
            }

            json.forEach(el =>{
                const $li = document.createElement('li');
                $li.innerHTML = `${el.name} -- ${el.email} -- ${el.phone}`;
                $fragment.appendChild($li);
            })
    
            $fetchAsync.appendChild($fragment);


        }catch(err){
            let message = err.statusText || "Ocurrio un error";
            $fetchAsync.innerHTML = `Error ${err.status}: ${message}`; 
        }finally{

        }
        
    }

})();
```

### Librería [Axios](https://github.com/axios/axios)


```html
<h2>Axios</h2>
<ol id="axios"></ol>

<script src="https://cdn.jsdelivr.net/npm/axios/dist/axios.min.js"></script>
<script src="./ajax.js"></script>
```
```js
(()=>{
    const $axios = document.getElementById('axios'),
    $fragment = document.createDocumentFragment();

    //axios es una api que trabaja en promesas
    axios.get("https://jsonplaceholder.typicode.com/users")
    .then(res =>{
        //res es un objeto que la libreria a creado
        //axios ya te da la manipulacion del error 
        let json = res.data;
        json.forEach(el =>{
            const $li = document.createElement('li');
            $li.innerHTML = `${el.name} -- ${el.email} -- ${el.phone}`;
            $fragment.appendChild($li);
        })

        $axios.appendChild($fragment);
    })
    .catch(err=>{
        let message = err.response.statusText || "Ocurrio un error";
            $axios.innerHTML = `Error ${err.response.status}: ${message}`; 
    })
    .finally();
})();
```

### Librería Axios + Async-Await 
```html
<h2>Axios + Async-Await</h2>
<ol id="axios-async"></ol>

<script src="https://cdn.jsdelivr.net/npm/axios/dist/axios.min.js"></script>
<script src="./ajax.js"></script>
```
```js
(()=>{
    const $axiosAsync = document.getElementById('axios-async'),
    $fragment = document.createDocumentFragment();

    async function getData(){
        try{
            let res = await axios.get("https://jsonplaceholder.typicode.com/users"),
            json = await res.data;

            json.forEach(el =>{
                const $li = document.createElement('li');
                $li.innerHTML = `${el.name} -- ${el.email} -- ${el.phone}`;
                $fragment.appendChild($li);
            })
    
            $axiosAsync.appendChild($fragment);
        }catch(err){
            let message = err.response.statusText || "Ocurrio un error";
            $axiosAsync.innerHTML = `Error ${err.response.status}: ${message}`; 
        }
    }
    getData();
})();
```

## APIs REST
### ¿Qué es una API?

Una **API** (**Application Programming Interface**), o Interfaz de Programación de Aplicaciones, es un conjunto de rutinas que provee acceso a funciones de un determinado software, para efectos de esta nota, acceso a las funciones de nuestros sitios y aplicaciones web.

Dentro de los navegadores web tenemos 2 tipos de APIs:

1. **APIs nativas**, como el DOM que es el API que nos permite acceder al código HTML de nuestros documentos a través de JavaScript o la de Geolocalización que no permite acceder a las coordendas terrestres de nuestra ubicación actual; y,
2. **APIs externas**, como la de Twitter que nos permite obtener los últimos tweets de un usuario, o la de GitHub que nos permite obtener la información de los repositorios de una cuenta o como la API de WordPress que nos permite acceder a la información de páginas y entradas de un sitio.
La mayoría de APIs externas del desarrollo web actual, funcionan con la Arquitectura **REST**.

### ¿Qué es REST?

El término **REST** (**Representational State Transfer**) o Transferencia de Estado Representacional, se originó en el año 2000, descrito en la tesis de Roy Fielding, padre de la especificación HTTP.

Un servicio **REST** es un conjunto de restricciones con las que podemos crear un estilo de arquitectura de software, la cual podremos usar para crear aplicaciones web respetando el protocolo HTTP.

Hoy en día la mayoría de las empresas utilizan **API REST** para crear servicios. Esto se debe a que es un estándar lógico y eficiente para la creación de servicios web.

Según Fielding las restricciones que definen a un sistema **API REST** o **RESTful** como también se le conoce, son:

- **Cliente-Servidor**, esta restricción mantiene al cliente y al servidor débilmente acoplados. Esto quiere decir que el cliente no necesita conocer los detalles de implementación del servidor y el servidor se olvida de entender cómo son usados los datos que envía al cliente.
- **Sin Estado**, significa que cada petición recibida por el servidor debería ser independiente, es decir, no es necesario mantener sesiones.
- **Cacheable**, debe admitir un sistema de almacenamiento en caché, lo que evitará repetir varias conexiones entre el servidor y el cliente para recuperar un mismo recurso.
- **Interfaz Uniforme**, significa una interfaz genérica para administrar cada interacción que se produzca entre el cliente y el servidor de manera uniforme, lo cual simplifica y separa la arquitectura. Esta restricción indica que cada recurso del servicio **REST** debe tener una única dirección (URL) web, a estas rutas se les da el nombre de **endpoints**.
- **Sistema de Capas**, el servidor puede disponer de varias capas para su implementación. Esto ayuda a mejorar la escalabilidad, el rendimiento y la seguridad.

Si creas aplicaciones web con JavaScript, las API REST probablemente serán la forma principal de obtener datos para tus aplicaciones, así como la de enviar datos hacia una base de datos.

Así que... ...sí las API REST, son el nuevo CRUD del desarrollo moderno, con la ventaja de que puedes desacoplar tu la lógica de tu cliente de la del servidor y la base de datos.

**CRUD**: CREATE READ UPDATE DELETE

Operaciones CRUD | Peticiones REST
-----------------|------------------
INSERT |	POST
SELECT |	GET
UPDATE |	PUT
DELETE |	DELETE

Otra ventaja de este modelo de desarrollo es que puedes usar un mismo origen de datos para distintos clientes, por ejemplo un cliente nativo (iOS, Android), un cliente de escritorio (Windows) o un cliente web (Navegadores).

### JSON Server - API falsa local
vamos a crear una api local falsa con una herramienta que se llama [json server](https://github.com/typicode/json-server).

En la terminal de comandos ejecutamos:
```
sudo npm install -g json-server
```
Despues vamos a la carpeta en la cual vamos a trabajar y creamos un nuevo archivo
```
touch db.json
```

En la documentacion de **json server** te indica que el unico requerimento es que cada uno de los elementos que se vayan a crear tengan un atributo **id** y apartir de ahi puedes ir definiendo las caracteristicas de tu base de datos ficticia.

db.json:
```json
{
    "santos": [
    {
        "id":1,
        "nombre":"Seiya",
        "constelacion":"Pegaso"
    },
    {
        "id":2,
        "nombre":"Shiryu",
        "constelacion":"Dragon"
    },
    {
        "id":3,
        "nombre":"Hyoga",
        "constelacion":"Cisne"
    },
    {
        "id":4,
        "nombre":"Shun",
        "constelacion":"Andromeda"
    },
    {
        "id":5,
        "nombre":"Ikki",
        "constelacion":"Fenix"
    }
    ],
    "dioses":[
        {
            "id":1,
            "nombre":"Athena",
            "de":"Tierra"
        },
        {
            "id":2,
            "nombre":"Poseidon",
            "de":"Mar"
        },
        {
            "id":3,
            "nombre":"Hades",
            "de":"Inframundo"
        },
        {
            "id":4,
            "nombre":"Zeus",
            "de":"Cielo"
        }
    ]
}

```

Despues ejecutamos en la termial:
```
json-server --watch db.json
```
el `--watch` es para que este observando cualquier cambio que tenga el archivo 

y en la consola saldra algo como esto
```
{^_^}/ hi!

  Loading db.json
  Done

  Resources
  http://localhost:3000/santos
  http://localhost:3000/dioses

  Home
  http://localhost:3000

  Type s + enter at any time to create a snapshot of the database
  Watching...

```

en el navegador podemos entrar a las rutas 
```
http://localhost:3000/santos
http://localhost:3000/dioses
```

para abortar el servir en la consola pusamos en el techado `CTRL + c`.

### Consumo de datos con cliente REST

Para el consumo de datos con cliente REST valos a usar [Insomnia](https://insomnia.rest/).

Cuando lo tengamos instalado creamos una carpeta y dentro de la carpeta escribimo el CRUD de prueba
```
#Eligimos la opcion GET
# de nombre le ponemos:
READ Santos
#despues le ponemos la direccion de nuestro host
http://localhost:5555/santos
```

###  CRUD 
El json-server tiene que estar activado
#### CRUD con AJAX
**Parte 1**
```html
<body>
    <h1>CRUD API REST AJAX</h1>
    <section class="crud">
        <article>
            <h2 class="crud-title">Agregar Santo</h2>
            <form action="" class="crud-form">
                <input type="text" name="nombre" placeholder="nombre" required>
                <br>
                <input type="text" name="constelacion" placeholder="constleacion" required>
                <br>
                <input type="submit" value="Enviar">
                <input type="hidden" name="id"> <!-- los elementos de tipo ocultos no se ven en el documento html, pero ese input me puede servir para mandar algo cuando se mande el formulario -->
            </form>
        </article>
        <article>
            <h2>Ver Santos</h2>
            <table class="crud-table">
                <thead>
                    <tr>
                        <th>Nombre</th>
                        <th>constelacion</th>
                        <th>Acciones</th>
                    </tr>
                </thead>
                <tbody>
                </tbody>
            </table>
        </article>
    </section>
    <template id="crud-template">
        <tr>
            <td class="name"></td>
            <td class="constellation"></td>
            <td>
                <button class="edit">Editar</button><button class="delete">Eliminar</button>
            </td>
        </tr>
    </template>
    <script>
        const d= document,
        $table = d.querySelector(".crud-table"),
        $form = d.querySelector(".crud-form"),
        $title = d.querySelector(".crud-title"),
        $template = d.getElementById("crud-template").content,
        $fragment = d.createDocumentFragment();

        const ajax = (options) => {
            //vamos a hacer uso de la destructuracion en las opciones
            let {url,method,success,error,data} = options;
            const xhr = new XMLHttpRequest();

            xhr.addEventListener("readystatechange",e=>{
                if(xhr.readyState !== 4)return;
                if(xhr.status >= 200 && xhr.status < 300){
            
                let json = JSON.parse(xhr.responseText);
                //la respuesta convertida a objeto:
                success(json);

                }else{
                let message = xhr.statusText || "Ocurrio un error";
                error(`Error ${xhr.status}: ${message}`);
                }
            });

            xhr.open(method || "GET", url);
            //para agregar una cabecera de la peticion
            // si nosotros no le especificamos es texto plano, por ello hay que especificar el tipo de contenido que vamos a enviar
            // si nosotros quitamos la cabecera el json server que esta esperando application/json no va a funcionar 
            xhr.setRequestHeader("Content-type","application/json; charset=utf-8");
            // nosotros vamos a  enviar un objeto javascript pero lo tener que convertir a cadena de texto
            xhr.send(JSON.stringify(data))
        };
        const getAll = () => {
            ajax({
                url: "http://localhost:5555/santos",
                success: (res) => {
                    console.log(res);
                    
                    res.forEach(el =>{
                        $template.querySelector(".name").textContent = el.nombre;
                        $template.querySelector(".constellation").textContent = el.constelacion;
                        //dataset = data atributs
                        $template.querySelector(".edit").dataset.id = el.id;
                        $template.querySelector(".edit").dataset.name = el.nombre;
                        $template.querySelector(".edit").dataset.constellation = el.constelacion;
                        $template.querySelector(".delete").dataset.id = el.id;

                        let $clone = d.importNode($template, true);
                        $fragment.appendChild($clone);

                        $table.querySelector("tbody").appendChild($fragment);
                    })
                },
                error: (err) => {
                    console.error(err);
                    $table.insertAdjacentHTML("afterbegin", 
                    `<p><b>${err}</b></p>`);
                }
            })
        }
        d.addEventListener("DOMContentLoaded", getAll);
    </script>
</body>
```

**Parte 2**
```html
<script>
        const d= document,
        $table = d.querySelector(".crud-table"),
        $form = d.querySelector(".crud-form"),
        $title = d.querySelector(".crud-title"),
        $template = d.getElementById("crud-template").content,
        $fragment = d.createDocumentFragment();

        const ajax = (options) => {
            let {url,method,success,error,data} = options;
            const xhr = new XMLHttpRequest();

            xhr.addEventListener("readystatechange",e=>{
                if(xhr.readyState !== 4)return;
                if(xhr.status >= 200 && xhr.status < 300){
            
                let json = JSON.parse(xhr.responseText);
                success(json);

                }else{
                let message = xhr.statusText || "Ocurrio un error";
                error(`Error ${xhr.status}: ${message}`);
                }
            });

            xhr.open(method || "GET", url);
            xhr.setRequestHeader("Content-type","application/json; charset=utf-8");
            xhr.send(JSON.stringify(data))
        };
        const getAll = () => {
            ajax({
                url: "http://localhost:5555/santos",
                success: (res) => {
                    
                    res.forEach(el =>{
                        $template.querySelector(".name").textContent = el.nombre;
                        $template.querySelector(".constellation").textContent = el.constelacion;
                        
                        $template.querySelector(".edit").dataset.id = el.id;
                        $template.querySelector(".edit").dataset.name = el.nombre;
                        $template.querySelector(".edit").dataset.constellation = el.constelacion;
                        $template.querySelector(".delete").dataset.id = el.id;

                        let $clone = d.importNode($template, true);
                        $fragment.appendChild($clone);

                        $table.querySelector("tbody").appendChild($fragment);
                    })
                },
                error: (err) => {
                    console.error(err);
                    $table.insertAdjacentHTML("afterbegin", 
                    `<p><b>${err}</b></p>`);
                }
            })
        }
        d.addEventListener("DOMContentLoaded", getAll);

        // create - update
        d.addEventListener("submit", e=>{
            if (e.target === $form){
                e.preventDefault();

                if (!e.target.id.value){
                    //POST - Create
                    // en el momento de que yo inserto una peticion de registo el solo le va asignando un id
                    ajax({
                        url: "http://localhost:5555/santos",
                        method: "POST",
                        success: (res) => location.reload(),
                        error: () => {
                            $form.insertAdjacentHTML("beforeend", `<p><b>${err}</b></p>`)
                        }, data: {
                            nombre : e.target.nombre.value,
                            constelacion : e.target.constelacion.value
                        }
                        
                    })
                }else{
                    //PUT - Update
                    ajax({
                        url: `http://localhost:5555/santos/${e.target.id.value}`,
                        method: "PUT",
                        success: (res) => location.reload(),
                        error: () => {
                            $form.insertAdjacentHTML("beforeend", `<p><b>${err}</b></p>`)
                        }, data: {
                            nombre : e.target.nombre.value,
                            constelacion : e.target.constelacion.value
                        }
                        
                    })
                }
            }
        });
        
        //boton editar - eliminar
        d.addEventListener("click", e=>{
            if (e.target.matches(".edit")){
                $title.textContent = "Editar Santo";
                $form.nombre.value = e.target.dataset.name; 
                $form.constelacion.value = e.target.dataset.constellation; 
                $form.id.value = e.target.dataset.id; 
            }

            if (e.target.matches(".delete")){
                let isDelete = confirm(`Estas seguro de eliminar el id ${e.target.dataset.id}`);
                if (isDelete){
                    ajax({
                        url: `http://localhost:5555/santos/${e.target.dataset.id}`,
                        method: "DELETE",
                        success: (res) => location.reload(),
                        error: () => {
                            $form.insertAdjacentHTML("beforeend", `<p><b>${err}</b></p>`)
                        }     
                    })
                }
            }
        })
</script>
```

#### CRUD con Fetch 

**Parte 1**
```html
<body>
    <h1>CRUD API REST FETCH</h1>
    <section class="crud">
        <article>
            <h2 class="crud-title">Agregar Santo</h2>
            <form action="" class="crud-form">
                <input type="text" name="nombre" placeholder="nombre" required>
                <br>
                <input type="text" name="constelacion" placeholder="constleacion" required>
                <br>
                <input type="submit" value="Enviar">
                <input type="hidden" name="id"> <!-- los elementos de tipo ocultos no se ven en el documento html, pero ese input me puede servir para mandar algo cuando se mande el formulario -->
            </form>
        </article>
        <article>
            <h2>Ver Santos</h2>
            <table class="crud-table">
                <thead>
                    <tr>
                        <th>Nombre</th>
                        <th>constelacion</th>
                        <th>Acciones</th>
                    </tr>
                </thead>
                <tbody>
                </tbody>
            </table>
        </article>
    </section>
    <template id="crud-template">
        <tr>
            <td class="name"></td>
            <td class="constellation"></td>
            <td>
                <button class="edit">Editar</button><button class="delete">Eliminar</button>
            </td>
        </tr>
    </template>
    <script>
        const d= document,
        $table = d.querySelector(".crud-table"),
        $form = d.querySelector(".crud-form"),
        $title = d.querySelector(".crud-title"),
        $template = d.getElementById("crud-template").content,
        $fragment = d.createDocumentFragment();

        const getAll = async () => {
            try {
                // cuando nosotros no especificamos el segundo parametro de fetch significa que estamos haciando una peticion por el metodo get  
                let res = await fetch("http://localhost:5555/santos"),
                json = await res.json();

                if (!res.ok) throw {status: res.status, statusText: res.statusText};

                json.forEach(el =>{
                    $template.querySelector(".name").textContent = el.nombre;
                        $template.querySelector(".constellation").textContent = el.constelacion;
                        
                        $template.querySelector(".edit").dataset.id = el.id;
                        $template.querySelector(".edit").dataset.name = el.nombre;
                        $template.querySelector(".edit").dataset.constellation = el.constelacion;
                        $template.querySelector(".delete").dataset.id = el.id;

                        let $clone = d.importNode($template, true);
                        $fragment.appendChild($clone);
                });

                $table.querySelector("tbody").appendChild($fragment);
            } catch (err) {
                let message = err.statusText || "Ocurrio un error";
                $table.insertAdjacentHTML("afterend", `<p><b>Error ${err.status}: ${message}</b></p>`);
            }
        }

        d.addEventListener("DOMContentLoaded", getAll);
    </script>
</body>
```

**Parte 2**
```html
<script>
        const d= document,
        $table = d.querySelector(".crud-table"),
        $form = d.querySelector(".crud-form"),
        $title = d.querySelector(".crud-title"),
        $template = d.getElementById("crud-template").content,
        $fragment = d.createDocumentFragment();

        const getAll = async () => {
            try {
                let res = await fetch("http://localhost:5555/santos"),
                json = await res.json();

                if (!res.ok) throw {status: res.status, statusText: res.statusText};

                json.forEach(el =>{
                    $template.querySelector(".name").textContent = el.nombre;
                        $template.querySelector(".constellation").textContent = el.constelacion;
                        
                        $template.querySelector(".edit").dataset.id = el.id;
                        $template.querySelector(".edit").dataset.name = el.nombre;
                        $template.querySelector(".edit").dataset.constellation = el.constelacion;
                        $template.querySelector(".delete").dataset.id = el.id;

                        let $clone = d.importNode($template, true);
                        $fragment.appendChild($clone);
                });

                $table.querySelector("tbody").appendChild($fragment);
            } catch (err) {
                let message = err.statusText || "Ocurrio un error";
                $table.insertAdjacentHTML("afterend", `<p><b>Error ${err.status}: ${message}</b></p>`);
            }
        }

        d.addEventListener("DOMContentLoaded", getAll);

        // create - update
        d.addEventListener("submit", async e=>{
            if(e.target === $form){
                e.preventDefault();

                if(e.target.value){
                    //Create - POST
                    try {
                        let options = {
                            method: "POST",
                            headers: {
                                "Content-type": "application/json; charset=utf-8"
                            },
                            body: JSON.stringify({
                                nombre: e.target.nombre.value,
                                constelacion : e.target.constelacion.value
                            })
                        },
                        res = await fetch("http://localhost:5555/santos", options),
                        json = await res.json();
                        if (!res.ok) throw {status: res.status, statusText: res.statusText};
                        location.reload();

                        
                    } catch (error) {
                        let message = err.statusText || "Ocurrio un error";
                        $form.insertAdjacentHTML("afterend", `<p><b>Error ${err.status}: ${message}</b></p>`);
                    }
                }else{
                    //UPDATE - PUT 
                    try {
                        let options = {
                            method: "PUT",
                            headers: {
                                "Content-type": "application/json; charset=utf-8"
                            },
                            body: JSON.stringify({
                                nombre: e.target.nombre.value,
                                constelacion : e.target.constelacion.value
                            })
                        },
                        res = await fetch(`http://localhost:5555/santos/${e.target.id.value}`, options),
                        json = await res.json();

                        if (!res.ok) throw {status: res.status, statusText: res.statusText};

                        location.reload();
                    } catch (error) {
                        let message = err.statusText || "Ocurrio un error";
                        $form.insertAdjacentHTML("afterend", `<p><b>Error ${err.status}: ${message}</b></p>`);
                    }
                }
            }
        });
        
        d.addEventListener("click",async e =>{
            if (e.target.matches(".edit")){
                $title.textContent = "Editar Santo";
                $form.nombre.value = e.target.dataset.name; 
                $form.constelacion.value = e.target.dataset.constellation; 
                $form.id.value = e.target.dataset.id; 
            }

            if (e.target.matches(".delete")){
                let isDelete = confirm(`Estas seguro de eliminar el id ${e.target.dataset.id}`);
                if (isDelete){
                    try {
                        let options = {
                            method: "DELETE",
                            headers: {
                                "Content-type": "application/json; charset=utf-8"
                            }
                        },
                        res = await fetch(`http://localhost:5555/santos/${e.target.dataset.id}`, options),
                        json = await res.json();

                        if (!res.ok) throw {status: res.status, statusText: res.statusText};

                        location.reload();
                    } catch (error) {
                        let message = err.statusText || "Ocurrio un error";
                        $form.insertAdjacentHTML("afterend", `<p><b>Error ${err.status}: ${message}</b></p>`);
                    }
                }
            }
        });

</script>
```

#### CRUD con Axios
**Parte 1**
```html
<body>
    <h1>CRUD API REST AXIOS</h1>
    <section class="crud">
        <article>
            <h2 class="crud-title">Agregar Santo</h2>
            <form action="" class="crud-form">
                <input type="text" name="nombre" placeholder="nombre" required>
                <br>
                <input type="text" name="constelacion" placeholder="constleacion" required>
                <br>
                <input type="submit" value="Enviar">
                <input type="hidden" name="id"> <!-- los elementos de tipo ocultos no se ven en el documento html, pero ese input me puede servir para mandar algo cuando se mande el formulario -->
            </form>
        </article>
        <article>
            <h2>Ver Santos</h2>
            <table class="crud-table">
                <thead>
                    <tr>
                        <th>Nombre</th>
                        <th>constelacion</th>
                        <th>Acciones</th>
                    </tr>
                </thead>
                <tbody>
                </tbody>
            </table>
        </article>
    </section>
    <template id="crud-template">
        <tr>
            <td class="name"></td>
            <td class="constellation"></td>
            <td>
                <button class="edit">Editar</button><button class="delete">Eliminar</button>
            </td>
        </tr>
    </template>
    <!-- Es importante este script para qe funcione axios-->
    <script src="https://cdn.jsdelivr.net/npm/axios/dist/axios.min.js"></script>
    <script>
        const d= document,
        $table = d.querySelector(".crud-table"),
        $form = d.querySelector(".crud-form"),
        $title = d.querySelector(".crud-title"),
        $template = d.getElementById("crud-template").content,
        $fragment = d.createDocumentFragment();

        const getAll = async () =>{
            try {
                let res = await axios.get("http://localhost:5555/santos"),
                json = await res.data;

                json.forEach(el =>{
                    $template.querySelector(".name").textContent = el.nombre;
                        $template.querySelector(".constellation").textContent = el.constelacion;
                        
                        $template.querySelector(".edit").dataset.id = el.id;
                        $template.querySelector(".edit").dataset.name = el.nombre;
                        $template.querySelector(".edit").dataset.constellation = el.constelacion;
                        $template.querySelector(".delete").dataset.id = el.id;

                        let $clone = d.importNode($template, true);
                        $fragment.appendChild($clone);
                });
                $table.querySelector("tbody").appendChild($fragment);
            } catch (err) {
                let message = err.statusText || "Ocurrio un error";
                $table.insertAdjacentHTML("afterend", `<p><b>Error ${err.status}: ${message}</b></p>`)
            }
        }
        
        d.addEventListener("DOMContentLoaded", getAll);
    </script>
</body>
```

**Parte 2**
```html
<script>
        const d= document,
        $table = d.querySelector(".crud-table"),
        $form = d.querySelector(".crud-form"),
        $title = d.querySelector(".crud-title"),
        $template = d.getElementById("crud-template").content,
        $fragment = d.createDocumentFragment();

        const getAll = async () =>{
            try {
                let res = await axios.get("http://localhost:5555/santos"),
                json = await res.data;

                json.forEach(el =>{
                    $template.querySelector(".name").textContent = el.nombre;
                        $template.querySelector(".constellation").textContent = el.constelacion;
                        
                        $template.querySelector(".edit").dataset.id = el.id;
                        $template.querySelector(".edit").dataset.name = el.nombre;
                        $template.querySelector(".edit").dataset.constellation = el.constelacion;
                        $template.querySelector(".delete").dataset.id = el.id;

                        let $clone = d.importNode($template, true);
                        $fragment.appendChild($clone);
                });
                $table.querySelector("tbody").appendChild($fragment);
            } catch (err) {
                let message = err.statusText || "Ocurrio un error";
                $table.insertAdjacentHTML("afterend", `<p><b>Error ${err.status}: ${message}</b></p>`)
            }
        }
        
        d.addEventListener("DOMContentLoaded", getAll);

        d.addEventListener("submit", async e=>{
            if(e.target === $form){
                e.preventDefault();

                if(!e.target.id.value){
                    //create- POST
                    try {
                        let options = {
                            method: "POST",
                            headers: {
                                "Content-type": "application/json; charset=utf-8"
                            },
                            data: JSON.stringify({
                                nombre: e.target.nombre.value,
                                constelacion : e.target.constelacion.value
                            })
                        },
                        res = await axios("http://localhost:5555/santos", options),
                        json = await res.data;

                        location.reload();
                    } catch (err) {
                        let message = err.statusText || "Ocurrio un error";
                        $form.insertAdjacentHTML("afterend", `<p><b>Error ${err.status}: ${message}</b></p>`)
                    }
                }else{
                    //Update - PUT
                    try {
                        let options = {
                            method: "PUT",
                            headers: {
                                "Content-type": "application/json; charset=utf-8"
                            },
                            data: JSON.stringify({
                                nombre: e.target.nombre.value,
                                constelacion : e.target.constelacion.value
                            })
                        },
                        res = await axios(`http://localhost:5555/santos/${e.target.id.value}`, options),
                        json = await res.data;

                        location.reload();
                    } catch (err) {
                        let message = err.statusText || "Ocurrio un error";
                        $form.insertAdjacentHTML("afterend", `<p><b>Error ${err.status}: ${message}</b></p>`)
                    }
                }
            }
        });

        d.addEventListener("click", async e=>{
            if(e.target.matches(".edit")){
                $title.textContent = "Editar Santo";
                $form.nombre.value = e.target.dataset.name; 
                $form.constelacion.value = e.target.dataset.constellation; 
                $form.id.value = e.target.dataset.id; 
            }

            if(e.target.matches(".delete")){
                let isDelete = confirm(`Estas seguro de eliminar el id ${e.target.dataset.id}`);
                if (isDelete){
                    //DELETE - delete
                    try {
                        let options = {
                            method: "DELETE",
                            headers: {
                                "Content-type": "application/json; charset=utf-8"
                            }
                        },
                        res = await axios(`http://localhost:5555/santos/${e.target.dataset.id}`, options),
                        json = await res.data;

                        location.reload();
                    } catch (err) {
                        let message = err.statusText || "Ocurrio un error";
                        $form.insertAdjacentHTML("afterend", `<p><b>Error ${err.status}: ${message}</b></p>`)
                    }
                }
            }

        })
</script>
```

## Reactividad
Para comprender el paradigma de la programación reactiva en JavaScript y entender cómo es que funcionan internamente librerías y frameworks como React, Angular, Vue, Svelte, Polymer, etc; es necesario comprender algunos conceptos importantes:

#### Reactividad
La reactividad de los datos, simplemente es que la interfaz de usuario de un sitio o aplicación se modifica a los cambios en los datos de la misma.

Cada vez que se actualizan los datos, la interfaz de usuario lo hace automáticamente para que coincida con la lógica de programación de la aplicación.

#### Estado
El estado son los datos de tu aplicación.

Entonces, ¿por qué se le llama estado en lugar de datos?

Porque tiene una duración determinada, el estado son datos en un momento particular de la aplicación, por ello decimos: **el estado actual de los datos de la aplicación**.

#### Interfaz basada en el estado
Una interfaz basada en el estado, es aquella que usa los datos de la aplicación en todo momento para pintar su elementos visuales.

Los elementos visuales de la interfaz suelen llamarse componentes.

#### Componentes

Para definir el término componente citaré la definición de Nicole Sullivan que dice:

```
“It's a repeating visual pattern, that can be abstracted into an independent snippet of HTML, CSS and possibly JavaScript.” Nicole Sullivan.
```

Traduciendo:

Es un patrón visual repetido, que se puede resumir en un fragmento independiente de HTML, CSS y posiblemente JavaScript.

Los componentes:

- Son un fragmento de la interfaz que cumple una única función.
- Son reutilizables ( principio DRY - Don´t Repeat Yourself ).
- Son independientes, tanto de su contexto como del resto de componentes.
- Son autocontenidos, no filtran estilos o funcionalidad a otros componentes.

#### Programación Reactiva orientada a Componentes

Con lo descrito anteriormente podemos decir que una aplicación reactiva y basada en componentes nos permiten separar el código y los elementos de la interfaz en pequeñas piezas independientes y reutilizables que estarán aisladas una de otras, y en lugar de intentar apuntar y manipular directamente los elementos del DOM cuando la aplicación **reaccioné** a las acciones del usuario, ésta actualizará su estado y luego la interfaz se repintará con los cambios en el estado.

### Manipulación NO Reactiva del DOM 

crearemos un archivo html para el ejemplo
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>00_dom_manipulacion</title>
</head>
<body>
    <h1>00_dom_manipulacion</h1>
    <form action="" id="todo-form">
        <input type="text" name="" id="todo-item" placeholder="tarea por hacer">
        <input type="submit" value="Agregar">
    </form>
    <h2>Lista de tareas</h2>
    <ul id="todo-list"></ul>
    <script>
        const d = document,
        $item = d.getElementById("todo-item"),
        $list = d.getElementById("todo-list");

        d.addEventListener("submit", e=>{
            if(!e.target.matches("#todo-form")) return false;

            e.preventDefault();
            //Agregar item a la lista
            let $li = d.createElement("li");
            $li.textContent = $item.value;
            $list.appendChild($li)

            //impiar el input
            $item.value = "";
            $item.focus();
        })

    </script>
</body>
</html>
```

Esta seria una programacion sin tomar en cuenta la reactividad

### Interfaz de Usuario (UI) basada en el Estado
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>01_ui-basada-estado</title>
</head>
<body>
    <h1>01_ui-basada-estado</h1>
    <form action="" id="todo-form">
        <input type="text" id="todo-item" placeholder="tarea por hacer">
        <input type="submit" value="Agregar">
    </form>
    <h2>Lista de tareas</h2>
    <ul id="todo-list"></ul>
    <script>
        const d = document;

        //lo primer que tenemos que hacer es crear una variable para implementar el concepto del estado
        // estado o como los frameworks reactivos lo conocen: el state
        // generalmente va a ser un objeto en donde por cada atributo que tenga este objeto son cada uno de los estados que quisieramos controlar
        // agregaremoos un todoList que como valor inicial sera un arreglo vacio
        // eso significa que por cada lista de tareas que le agregemos al ul en el dom se va a ir generando un elemento de este arrreglo
        const state = {
            todoList: []
        };
        //tendriamos que tener un mecanismo que justamente me genere esa intefaz basada en el estado
        // es decir, un template html
        const template = () => {
            if(state.todoList.length < 1) {
                return `<p><em>Lista sin tareas por hacer</em></p>`
            }

            //el join va a servir para que no salgan comas en la lista de tareas
            let todos = state.todoList.map(item => `<li>${item}</li>`).join("");

            return todos;
        }

        //ahora neceitamos un proceso que actue como renderizado
        const render = () => {
            console.log(state)

            const $list = d.getElementById("todo-list");
            if(!$list) return;
            $list.innerHTML = template();
        }

        d.addEventListener("DOMContentLoaded", render);

        d.addEventListener("submit", e=>{
            if(!e.target.matches("#todo-form")) return;

            e.preventDefault();

            const $item = d.getElementById("todo-item");
            if(!$item) return;

            //actualizar el state
            state.todoList.push($item.value);
            render();

            //impiar el input
            $item.value = "";
            $item.focus();
        })

    </script>
    
</body>
</html>
```
EL paso que faltaria seria hacer que nuestro estado sea realmente reactivo por que es una mala practica pegar directamente los valores al estado(`state.todoList.push(item.value);`).

### Estado Reactivo

El detalle en hacer reactivo y de actualizar de manera reactiva nuestro estado es evitar manipularlo directamente.
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>03_estado-inmutable</title>
</head>
<body>
    <h1>03_estado-inmutable</h1>
    <form action="" id="todo-form">
        <input type="text" name="" id="todo-item" placeholder="tarea por hacer">
        <input type="submit" value="Agregar">
    </form>
    <h2>Lista de tareas</h2>
    <ul id="todo-list"></ul>
    <script>
        const d = document;

        //el state
        const state = {
            todoList: []
        };
        
        // Template UI
        const template = () => {
            if(state.todoList.length < 1) {
                return `<p><em>Lista sin tareas por hacer</em></p>`
            };
            let todos = state.todoList.map(item => `<li>${item}</li>`).join("");

            return todos;
        }

        //Render UI
        const render = () => {
            const $list = d.getElementById("todo-list");
            if(!$list) return;
            $list.innerHTML = template();
        }

        //Actualizar el State de forma reactiva
        const setState = obj =>{
            // setState va a recibir un objeto 
            // y va a recorrer cada una de las llaves de este objeto 
            // y la que coincida con alguna llave de state original ahi es donde la va a asignar
            for(let key in obj){
                if(state.hasOwnProperty(key)){
                    state[key] = obj[key];
                }
            };

            render();
            // con esto estariamos actualizando el estado de nuestra aplicaccion de forma reactiva
        } 

        d.addEventListener("DOMContentLoaded", render);

        //Estableciendo valores por defecto al State
        setState({
            todoList:["tarea 1", "tarea 2"]
            //en este caso aun que agregaramos otra propiedad con un nombre que no este en el "state" entonces el programa la ignorara
        });

        //Aun falta que sea inmutable por que con la tecnica siguiente se puede modificar desde a fuera
        const items = state.todoList;
        items.push("tarea 3")
        // Estado Mutable, por que permite modificar el estado directamente creando una copia del objeto y agregando otro elemento


        d.addEventListener("submit", e=>{
            if(!e.target.matches("#todo-form")) return false;

            e.preventDefault();
            const $item = d.getElementById("todo-item");
            if(!$item) return;

            //actualizar el state
            state.todoList.push(item.value);
            render();

            //impiar el input
            $item.value = "";
            $item.focus();
        })

    </script>
    
</body>
</html>
```

### Estado Inmutable
Para poder hacer un estado inmutable lo que vamos a hacer es que antes de actualizar el estado vamos a obtener una copia de ese estado.
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>03_Estado-Inmutable</title>
</head>
<body>
    <h1>03_Estado-Inmutable</h1>
    <form action="" id="todo-form">
        <input type="text" name="" id="todo-item" placeholder="tarea por hacer">
        <input type="submit" value="Agregar">
    </form>
    <h2>Lista de tareas</h2>
    <ul id="todo-list"></ul>
    <script>
        const d = document;

        //el state
        const state = {
            todoList: []
        };
        
        // Template UI
        const template = () => {
            if(state.todoList.length < 1) {
                return `<p><em>Lista sin tareas por hacer</em></p>`
            };
            let todos = state.todoList.map(item => `<li>${item}</li>`).join("");

            return todos;
        }

        //Render UI
        const render = () => {
            const $list = d.getElementById("todo-list");
            if(!$list) return;
            $list.innerHTML = template();
        }

        //Actualizar el State de forma reactiva
        const setState = obj =>{
            for(let key in obj){
                if(state.hasOwnProperty(key)){
                    state[key] = obj[key];
                }
            };

            render();
        };

        //Obtenermos una copia inmutable de State
        // stringify convierte el estado original a cadena de texto, ahi ya hay desvinculacion total de la variable state original
        // y cuando esa cadena de texto la convertimos de nuevo a un objeto sera un objeto completamente diferente
        const getState = () => JSON.parse(JSON.stringify(state));

        d.addEventListener("DOMContentLoaded", render);

        //Estableciendo valores por defecto al State
        setState({
            todoList:["tarea 1", "tarea 2"]
            
        });

        //aqui vamos a tratar de inyectar una tarea adicional
        // si el estado es inmutanle entonces no se agregara la tarea adicional
        const items = getState();
        items.todoList.push("Tarea 4");

        d.addEventListener("submit", e=>{
            if(!e.target.matches("#todo-form")) return false;

            e.preventDefault();
            const $item = d.getElementById("todo-item");
            if(!$item) return;

            //Actualizar el State de foma reactiva 
            const lastState = getState()
            lastState.todoList.push($item.value);
            setState({todoList:lastState.todoList});

            //impiar el input
            $item.value = "";
            $item.focus();
        })

    </script>
    
</body>
</html>
```

### Componentes con Estado

En esta filosofia de programacion reactiva y orientada a componentes cada pedasito de la UI puede ser un componente y a su vez ede componente tener una UI propia.

Vamos a crear un componente local.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>04 componentes con estado</title>
</head>
<body>
    <h1>04 componentes con estado</h1>
    <form action="" id="todo-form">
        <input type="text" name="" id="todo-item" placeholder="tarea por hacer">
        <input type="submit" value="Agregar">
    </form>
    <h2>Lista de tareas</h2>
    <ul id="todo-list"></ul>
    <script>
        const d = document;

        //el state Global
        const state = {
            todoList: []
        };
        
        // Template UI
        const template = () => {
            if(template.data.todoList.length < 1) {
                return `<p><em>Lista sin tareas por hacer</em></p>`
            };
            let todos = template.data.todoList.map(item => `<li>${item}</li>`).join("");

            return todos;
        };

        //Agregar State al Template que genera el Componente de UI(state local)
        template.data = {
            todoList:[]
        }

        //Render UI
        const render = () => {
            const $list = d.getElementById("todo-list");
            if(!$list) return;
            $list.innerHTML = template();
        }

        //Actualizar el State de forma reactiva
        const setState = obj =>{
            for(let key in obj){
                if(template.data.hasOwnProperty(key)){
                    template.data[key] = obj[key];
                }
            };

            render();
        };

        const getState = () => JSON.parse(JSON.stringify(template.data));

        d.addEventListener("DOMContentLoaded", render);

        //Estableciendo valores por defecto al State
        setState({
            todoList:["tarea 1", "tarea 2"]
        });

        d.addEventListener("submit", e=>{
            if(!e.target.matches("#todo-form")) return false;

            e.preventDefault();
            const $item = d.getElementById("todo-item");
            if(!$item) return;

            //Actualizar el State de foma reactiva 
            const lastState = getState();
            lastState.todoList.push($item.value);
            setState({todoList:lastState.todoList});

            //impiar el input
            $item.value = "";
            $item.focus();
        });

    </script>
    
</body>
</html>
```