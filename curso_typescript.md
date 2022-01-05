# REACT Y TYPESCRIPT

## instalacion
```
npx create-react-app@5.0.0 react-tasks-app --template typescript
```
Con esto se creara todo un entorno configurado de typescript para react.

Se creara en la carpeta un archivo llamado `tsconfing.jon` aqui es donde se configura typescritp.

Otro cambio es que en lugar de archivos `js` o `jsx` van a ser archivos `tsx`, basicamente es lo mismo solo que ahora vamos a tener acceso a declarar tipos de datos y algunas otras caracteristicas mas que nos da typescript.

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

https://www.youtube.com/watch?v=bmZKIMjJTjs

13:30