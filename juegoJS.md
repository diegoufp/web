# Juegos JS

## Introduccion [p5.js](https://p5js.org/)

[p5.js](https://p5js.org/), en `get Started` podras ver como usarla, si buscamos *CDN* podemos ver el script que tenemos que pegar en el html:
```
<script src="https://cdn.jsdelivr.net/npm/p5@[p5_version]/lib/p5.js"></script>
```

- `setup()`: Solamente se ejecuta una vez cuando inicia el archivo, es como una funcion constructora.

- `draw()` : la function draw se ejectua por siempre 

- `createCanvas()` : Crea un canvas los parametros que se le pasan son width y heidth en pixeles. 

- `background( , , )`: permite pintar el fondo con colores rgb (red,green,blue).

- `rect()`:  permite dibujar un rectangulo, los parametros son coordenadaX, coordenadaY,anchoRectangulo,altoRectangulo


## [threejs](https://threejs.org/) con React

### INSTALACION
En la carpeta en la que estemos trabajando con react le ponemos en la terminal de comandos:
```
npm install three react-three-fiber
```

Para importarla:
```js
import * as THREE from "three";
import {Canvas} from "react-three-fiber";

```

### Caracteristicas de ThreeJs

- Contiene metodos especializados en:
    - escenas,luces,sombras,materiales, texturas, matematicas 3D.

- Es un escene graph (Estructura de datos).

- Se asemeja mucho a un Virtual DOM.

- Compartible en la mayoria de los navegadores.

**Efectos y animaciones**

- Renderizadores(WebGL/ Canvas)

- Escenas

- Luces

- Materiales

- Objetos

- Geometrias

- Cargadores de datos

- Efectos

- Animaciones

- Shaders

- Exportacion e Imporacion de objetos

**[React Three Fiber](https://docs.pmnd.rs/react-three-fiber/getting-started/introduction) (R3F)**

- Es un poderoso render hecho para React para visualizar las escenas de ThreeJS (web y Native)

- Es un reconciliador de React para ThreeJS.

- React Fiber = nuevo motor de reconciliacion en React 16.

**Que es Reconciliacion?**

- El algoritmo que usa React para diferenciar un arbol con otro para determinar que partes deben cambiarse.

- Hace que las actualizaciones de los componentes sea predecibles y al mismo tiempo sean lo suficientemente rapidas para las aplicaciones de alto rendimiento.

**Por que deberia de usarlo?**

- Escenas Basadas en Componentes.

- Built-in Helpers.

- Hooks.

- Re-render solo cuando es necesario.

Parte de las figuras y objetos que vemos es la combinacion de una **Geometry** y un **Material** y a esta combinacion se le conoce como un **Mesh**.

### Ejercicio

**Inicializacion**
```js
import React from 'react';
import {Canvas} from "react-three-fiber";

export default function HyperCubo(){
    return(
        <Canvas>
            <mesh>
                {/*dentro de mesh vamos a poner nuestra geometria y el material */}
                {/*un cubo en threejs es un box y necesitamos unos props obrilagorios que en este caso es "attach" que sirve para indicarle que es ese objeto o ese componente y otros prop que se llama "args" que viene siendo la representacion de un constructor */}
                {/*en este ocacion las "args" para el cubo los podremos como un arreglo para indicarle el tama;o en el ejeX y el ejeY y ejeZ */}
                <boxGeometry attach="geometry" args={[1,1,1]} />
                {/*AHora necesitamos un material para poder visualizar a ese objeto, en  el "attach" indicaremos que es un material y tambien le podemos indicar un color con la prop "color"*/}
                <meshBasicMaterial attach="material" color="red"/>
            </mesh>
        </Canvas>
    )
}
```
En este caso cuando lo tratemos de visualizar se vera como un cuadrado por que lo estamos viendo de frente, pero en realidad es un cubo.

**Iluminacion**
```js
import React from 'react';
import {Canvas} from "react-three-fiber";

/*Podemos guardar los mesh en hooks para reutilizarlos */
function Box(){
    return(
        <>
        {/*el mesh es el que agrupa el material y la geometria asi que si le agregamos la prop "position" podemos poderlo de lugar el conjunto */}
        {/*En el mesh le podemos decir que queremos que rote */}
        <mesh rotation={[1,0,0]} position={[-2,0,0]}>
            <boxGeometry attach="geometry" args={[1,1,1]} />
                {/*podemos usar otros tipo de materiales, meshBasicMaterial lo cambiamos a MeshStandardMaterial */}
            <meshStandardMaterial attach="material" color="red"/>
        </mesh>
        </>
    )
}

export default function HyperCubo(){
    return(
        <Canvas>
            {/*Podemos poner luces con ambienteLight , con el parametros de intensity para controlar la intensidad*/}
            <ambientLight intensity={0.3}/>
            {/*Tambien tenemos otros tipo de luces como pueden ser las pointLight, tienen que tener una prop "position" donde va a recibir las coordenadas */}
            <pointLight position={[10,10,10]} />
            <Box/>
            
        </Canvas>
    )
}
```

**Animacion**
```js
import React, {useRef} from 'react';
import {Canvas, useFrame} from "react-three-fiber";

function Box({position,color}){
    /* no hay que instanciar de forma repetitiva los objetos, es mejor usar referencias(useRef) por que le estamos exigiendo un poco mas al orgenador al estar trabajando con graficos*/ 
    /*Como vamos a empezar a animar si no usamos "useRef" se va a estar instanciando almenos 60 veces cada vez que que reinicie el ciclo de animacion */
    let refBox = useRef();
    /*Ahora mandamos a llamar al hook de animacion llamado useFrame */
    useFrame(()=>{
        refBox.current.rotation.x = refBox.current.rotation.y += 0.01;
        /* ahora le quitamos la propiedad rotation al mesh por que ya lo vamos a estar animando por aqui*/
    })
    return(
        <mesh ref={refBox} position={position}>
                <boxGeometry attach="geometry" args={[1,1,1]} />
                <meshStandardMaterial attach="material" color={color}/>
        </mesh>
    )
}


export default function HyperCubo(){
    return(
        <Canvas>
            <ambientLight intensity={0.3}/>
            <pointLight position={[10,10,10]} />
            <Box color="red" position={[0,0,0]}/>
        </Canvas>
    )
}
```

**Eventos**
```js
import React, {useRef, useState} from 'react';
import {Canvas, useFrame} from "react-three-fiber";

function Box({position,color}){
    /*Tambien podemos hacer uso de las variables de estado */
    const [expand, setExpand] = useState(false);
    let refBox = useRef();
    useFrame(()=>{
        refBox.current.rotation.x = refBox.current.rotation.y += 0.01;
    });

    const handleClick = () =>{
        setExpand(!expand);
        /*el mejor poner el scale en el mesh directamente que en el evento, asi tenemos mejor control del el en caso de que tengamos mas de un Box*/
    };

    return(
        <mesh ref={refBox} scale={expand ? [2,2,2] : [1,1,1]} position={position} onClick={handleClick}>
        {/*Al mesh le podemos poner eventos */}
            <boxGeometry attach="geometry" args={[1,1,1]} />
            <meshStandardMaterial attach="material" color={color}/>
        </mesh>
    )
};

export default function HyperCubo(){
    return(
        <Canvas>
            <ambientLight intensity={0.3}/>
            <pointLight position={[10,10,10]} />
            <Box color="red" position={[0,0,0]}/>
        </Canvas>
    )
};
```

### [react-spring](https://react-spring.io/basics)
```
npm install @react-three/drei react-spring
```
- [drei](https://docs.pmnd.rs/drei/introduction): son helpers, componentes ya hechos como lo son los cubos.
- [react-spring](https://docs.pmnd.rs/react-spring/introduction) : libreria de animacion, nos va ayudar para hacer las animaciones mas amigables y que no se vean toscas.

```js
import { MeshWobbleMaterial } from '@react-three/drei';
import React, {useRef, useState} from 'react';
import {Canvas, useFrame} from "react-three-fiber";
import { useSpring, animated } from 'react-spring';
;

function Box({position,color}){
    const [expand, setExpand] = useState(false);
    let refBox = useRef();
    useFrame(()=>{
        refBox.current.rotation.x = refBox.current.rotation.y += 0.01;
    });

    const handleClick = () =>{
        setExpand(!expand);
    };

    const props = useSpring({
        scale: expand ? [2,2,2] : [1,1,1]
    });

    return(
        <animated.mesh ref={refBox} scale={props.scale} position={position} onClick={handleClick}>
        {/*Para animar un componente le tenemos que nombrar animate.mesh */}
            <boxBufferGeometry attach="geometry" args={[1,1,1]} />
            {/*para empezar a trabjar con drei lo que vamos a usar es uno de sus materiales, este material se llama MeshWobbleMaterial, ademas del attach y el color le tenemos que dar las props de velocidad(speed) y un factor de que tan notable va a ser*/}
            <MeshWobbleMaterial attach="material" color={color} speed={3} factor={0.5}/>
        </animated.mesh>
    )
};

export default function HyperCubo(){
    return(
        <Canvas>
            <ambientLight intensity={0.3}/>
            <pointLight position={[10,10,10]} />
            <Box color="red" position={[0,0,0]}/>
        </Canvas>
    )
};
```

## three.js

### Inicializacion
```js
import React, {useRef, useState, useEffect} from 'react';
import * as THREE from "three"; 


export default function HyperCubo(){
    const refMount = useRef(null);

    useEffect(() => {
        const currentRef = RefMount.current;
        const {clientWidth: width, clientHeight: height} = currentRef; // estos de aqui son los que nos ayudaran a sacar el especto de la camara y el tama;o del render.

        const scene = new THREE.Scene(); // con esto crearemos una escena
        // hay diferentes tipos de camaras dependiendo del proyecto que queramos hacer, en este caso usaremos una camara de perspectiva
        const camera = new THREE.PerspectiveCamera(25, width/height,0.01, 1000);
        /* la camara perspectiva recibe 4 parametros
        1.- view
        2.- aspecto de la camara, ese ascpecto esta dividido entre un width y un height
        3- que tan cerca puede ver los objetos 
        4.- que tan lejos los puede ver
        */

        // el siguiente paso es agregar la camara a la escena:
        scene.add(camera);

        //ahora tenemos que declarar lo que es el renderer
        const renderer = new THREE.WebGLRenderer();
        //ahora tenemos que ponerle un tama;o al renderer
        renderer.setSize(width, height);

        //ahora tenemos aque agregar este renderer a una referencia o un canvas
        currentRef.appendChild(renderer.domElement);//de esta manera ya se agregaria a nuestro div
        return() =>{
            currentRef.removeChild(renderer.domElement)
        }
    },[])
    return(
        <div ref={refMount} style={{width: "100%", height: "100%"}}>

        </div>
    )
};
```

### Agregar cubo
```js
import React, {useRef, useState, useEffect} from 'react';
import * as THREE from "three"; 


export default function HyperCubo(){
    const refMount = useRef(null);

    useEffect(() => {
        const currentRef = refMount.current;
        const {clientWidth: width, clientHeight: height} = currentRef; 

        const scene = new THREE.Scene(); 
        const camera = new THREE.PerspectiveCamera(25, width/height,0.01, 1000);
        
        scene.add(camera);

        const renderer = new THREE.WebGLRenderer();
       
        renderer.setSize(width, height);

        currentRef.appendChild(renderer.domElement);

        //ahora vamos a agregar la geometria
        // hay muchos tipos de geometrias, en este caso vamos a crear un cubo, la cual recibe los parametros de x,y,z
        const geometry = new THREE.BoxGeometry(1,1,1);
        // ahora vamos a crear un material, existen muchos tipos de materiales en este caso usaremos el material basico, puede recibir varios parametros, uno de ellos es el parametro de color
        const material = new THREE.MeshBasicMaterial({color: 0x0f2c64});
        //ahora se uniran la geometria y el material para crear el cubo
        const cube= new THREE.Mesh(geometry, material);
        //ahora solamente faltaria agregarlo a la escena
        scene.add(cube)
        

        return() =>{
            currentRef.removeChild(renderer.domElement)
        }
    },[])
    return(
        <div ref={refMount} style={{width: "100%", height: "100%"}}>

        </div>
    )
};
```
En este punto si aun no se ve el cubo a pesar de que ya lo agregamos a la escena, eso es por que cuando creamos la camara no le hemos dado posiciones en ninguna parte de los ejes por lo tanto la camara por defecto se va a situar en la posicion `0,0,0` al igual que el cubo, al cubo no le hemos dado ninguna posicion por lo tanto igualmente va a estar en la posicion origen.

Los ejes en three se declaran de manera distinta a los de blender:
- `three`:  z = ancho, x = largo, y = alto
- `blender` : y = ancho, x = largo,  z = alto
```js
import React, {useRef, useState, useEffect} from 'react';
import * as THREE from "three"; 


export default function HyperCubo(){
    const refMount = useRef(null);

    useEffect(() => {
        const currentRef = refMount.current;
        const {clientWidth: width, clientHeight: height} = currentRef; 

        const scene = new THREE.Scene(); 
        const camera = new THREE.PerspectiveCamera(25, width/height,0.01, 1000);
        scene.add(camera);
        // si queremos que la camara sea la vista del monitor:
        camera.position.z = 6;
        //si queremos que se vea la perpectiva del cubo en lugar de solamente verlo de frente podemos agregar mas posiciones a la camera
        camera.position.x = 6;

        const renderer = new THREE.WebGLRenderer();
        renderer.setSize(width, height);
        currentRef.appendChild(renderer.domElement);

        const geometry = new THREE.BoxGeometry(1,1,1);
        const material = new THREE.MeshBasicMaterial({color: 0x0f2c64});
        const cube= new THREE.Mesh(geometry, material);
        scene.add(cube);
        //si al agregar la position x a la camera hace que desaparesca el cubo significa que solemente el cubo no se encuentra dentros del campo de vista de la camara
        // si queremos que la camara este en la posicion donde vea el cubo podemos usar camera.lookAt
        // camera.lookAt recibe cooredanas x,y,z de donde queremos que vea la camara podemos usar un 
        // camera.lookAt(new Vector3(x,y,z))
        // pero otra forma de hacerlo es pasarle las corrernadas del cubo
        camera.lookAt(cube.position);


        
        //ahora faltaria crear la funcion que se encarge de hacer el render y le vamos a pasar la scena y la camara
        renderer.render(scene, camera)
        return() =>{
            currentRef.removeChild(renderer.domElement)
        }
    },[])
    return(
        <div ref={refMount} style={{width: "100%", height: "100%"}}>

        </div>
    )
};
```

### controles orbitales
tenemos que importar:
```js
import { OrbitControls } from 'three/examples/jsm/controls/OrbitControls';
```

```js
import React, {useRef, useState, useEffect} from 'react';
import * as THREE from "three"; 
import { OrbitControls } from 'three/examples/jsm/controls/OrbitControls';


export default function HyperCubo(){
    const refMount = useRef(null);

    useEffect(() => {
        const currentRef = refMount.current;
        const {clientWidth: width, clientHeight: height} = currentRef; 

        const scene = new THREE.Scene(); 
        const camera = new THREE.PerspectiveCamera(25, width/height,0.01, 1000);
        scene.add(camera);
        camera.position.z = 6;
        camera.position.x = 6;

        const renderer = new THREE.WebGLRenderer();
        renderer.setSize(width, height);
        currentRef.appendChild(renderer.domElement);

        //OrbitCOntrols recibe como parametros la camara y un elemento del dom donde va hacer referencia para girar,etc.
        const controls = new OrbitControls(camera,renderer.domElement);
        //si queremos dar el ejecto de fuerza en el objeto(Es decir que cuando lo rotemos tarde en detenerse):
        controls.enableDamping = true;

        const geometry = new THREE.BoxGeometry(1,1,1);
        const material = new THREE.MeshBasicMaterial({color: 0x0f2c64});
        const cube= new THREE.Mesh(geometry, material);
        scene.add(cube);
        camera.lookAt(cube.position);

        //ahora para poder hacer que los orbit controls funcionen tenemos que declarar una funcion que se encarge de repintar el cubo cada vez que hacemos esto:
        const animate =() =>{
            controls.update();//esto actualizara el estado del cubo al usar: controls.enableDamping = true;

            renderer.render(scene, camera);
            // esta funcion se llama a si misma
            requestAnimationFrame(animate);
        };

        animate();//como ahora dentros del animate se encuentra el render entonces podemos quitar el de abajo

        //renderer.render(scene, camera);

        return() =>{
            currentRef.removeChild(renderer.domElement)
        }
    },[])
    return(
        <div ref={refMount} style={{width: "100%", height: "100%"}}>

        </div>
    )
};
```

### animaciones
```js
import React, {useRef, useState, useEffect} from 'react';
import * as THREE from "three"; 
import { OrbitControls } from 'three/examples/jsm/controls/OrbitControls';


export default function HyperCubo(){
    const refMount = useRef(null);

    useEffect(() => {
        const currentRef = refMount.current;
        const {clientWidth: width, clientHeight: height} = currentRef; 

        const scene = new THREE.Scene(); 
        const camera = new THREE.PerspectiveCamera(25, width/height,0.01, 1000);
        scene.add(camera);
        camera.position.z = 6;
        camera.position.x = 6;

        const renderer = new THREE.WebGLRenderer();
        renderer.setSize(width, height);
        currentRef.appendChild(renderer.domElement);

        const controls = new OrbitControls(camera,renderer.domElement);
        controls.enableDamping = true;

        const geometry = new THREE.BoxGeometry(1,1,1);
        const material = new THREE.MeshBasicMaterial({color: 0x0f2c64});
        const cube= new THREE.Mesh(geometry, material);
        scene.add(cube);
        camera.lookAt(cube.position);


        const clock = new THREE.Clock(); //frame en base de tiempo.
        const animate =() =>{
            //para crear una peque;a animacion de rotacional cupo podemos usar:
            //cube.rotation.x = cube.rotation.y += 0.01;
            //sin embargo esta forma de hacerlo puede ser un poco demantante y puede haber problemas de frames, para resolver esto podemos usar frames en base de tiempo
            const elapsedTime = clock.getElapsedTime();
            cube.rotation.x = elapsedTime;
            cube.rotation.y = elapsedTime;

            //podemos hacer animaciones con funciones como la de seno, coseno.etc.
            cube.position.y = Math.sin(elapsedTime);
            
            controls.update();
            renderer.render(scene, camera);
            requestAnimationFrame(animate);
        };

        animate();
        return() =>{
            currentRef.removeChild(renderer.domElement)
        }
    },[])
    return(
        <div ref={refMount} style={{width: "100%", height: "100%"}}>

        </div>
    )
};
```

### luces
```js
import React, {useRef, useState, useEffect} from 'react';
import * as THREE from "three"; 
import { OrbitControls } from 'three/examples/jsm/controls/OrbitControls';


export default function HyperCubo(){
    const refMount = useRef(null);

    useEffect(() => {
        const currentRef = refMount.current;
        const {clientWidth: width, clientHeight: height} = currentRef; 

        const scene = new THREE.Scene(); 
        const camera = new THREE.PerspectiveCamera(25, width/height,0.01, 1000);
        scene.add(camera);
        camera.position.z = 6;
        camera.position.x = 6;

        const renderer = new THREE.WebGLRenderer();
        renderer.setSize(width, height);
        currentRef.appendChild(renderer.domElement);

        const controls = new OrbitControls(camera,renderer.domElement);
        controls.enableDamping = true;

        const geometry = new THREE.BoxGeometry(1,1,1);
        // cambiaremos el material MeshBasicMaterial por MeshPhongMaterial para que refleje mas la luz
        //hay materiales que se ven mayor o menor afectados por la luz
        const material = new THREE.MeshPhongMaterial({color: 0x0f2c64});
        const cube= new THREE.Mesh(geometry, material);
        scene.add(cube);
        camera.lookAt(cube.position);

        //agregaremos la luces ambientales
        const lightAm = new THREE.AmbientLight(0xff0000, 5);
        scene.add(lightAm);

        //agregaremos la luz de punto
        const light = new THREE.PointLight(0xff0000, 15);
        light.position.set(8,8,8);
        scene.add(light);
        // si agregamos la luz y no se nota en el cubo puede ser por el tipo del material del cubo


        const clock = new THREE.Clock();
        const animate =() =>{
            const elapsedTime = clock.getElapsedTime();
            cube.rotation.x = elapsedTime;
            cube.rotation.y = elapsedTime;
            cube.position.y = Math.sin(elapsedTime);
            
            controls.update();
            renderer.render(scene, camera);
            requestAnimationFrame(animate);
        };

        animate();
        return() =>{
            currentRef.removeChild(renderer.domElement)
        }
    },[])
    return(
        <div ref={refMount} style={{width: "100%", height: "100%"}}>

        </div>
    )
};
```

### Resize el render
```js
import React, {useRef, useState, useEffect} from 'react';
import * as THREE from "three"; 
import { OrbitControls } from 'three/examples/jsm/controls/OrbitControls';


export default function HyperCubo({divRef}){
    const refMount = useRef(null);

    useEffect(() => {
        const currentRef = refMount.current;
        const {clientWidth: width, clientHeight: height} = currentRef; 

        const scene = new THREE.Scene(); 
        //para cambiar el color de la escena podemos usar:
        scene.background = new THREE.Color(0x5b00ff);
        const camera = new THREE.PerspectiveCamera(25, width/height,0.01, 1000);
        scene.add(camera);
        camera.position.z = 6;
        camera.position.x = 6;

        const renderer = new THREE.WebGLRenderer();
        renderer.setSize(width, height);
        currentRef.appendChild(renderer.domElement);

        const controls = new OrbitControls(camera,renderer.domElement);
        controls.enableDamping = true;

        const geometry = new THREE.BoxGeometry(1,1,1);
        const material = new THREE.MeshPhongMaterial({color: 0x0f2c64});
        const cube= new THREE.Mesh(geometry, material);
        scene.add(cube);
        camera.lookAt(cube.position);

        const lightAm = new THREE.AmbientLight(0xff0000, 5);
        scene.add(lightAm);

        const light = new THREE.PointLight(0xff0000, 15);
        light.position.set(8,8,8);
        scene.add(light);


        const clock = new THREE.Clock();
        const animate =() =>{
            const elapsedTime = clock.getElapsedTime();
            cube.rotation.x = elapsedTime;
            cube.rotation.y = elapsedTime;
            cube.position.y = Math.sin(elapsedTime);
            
            controls.update();
            renderer.render(scene, camera);
            requestAnimationFrame(animate);
        };

        const resize = () => {
            //se va  a encargar de cambiar el width y el heidth cuando se modifique el tama;o de la ventana
            const updatedWidth = currentRef.clientWidth;
            const updateHeight = currentRef.clientHeight;
            renderer.setSize(updatedWidth,updateHeight);
            //cambiaremos el aspecto de la camara para que no se deforme el objeto
            camera.aspect = updatedWidth/updateHeight;
            // tambien vamos a actualizar la proyeccion de la camara
            camera.updateProjectionMatrix();
        }
        window.addEventListener("resize",resize);

        animate();
        return() =>{
            currentRef.removeChild(renderer.domElement);
            window.removeEventListener("resize",resize);
        }
    },[])
    return(
        <div ref={refMount} style={{width: "100%", height: "100%"}}>

        </div>
    )
};
```

### Axis Helper and Grid 
```js
import React, {useRef, useState, useEffect} from 'react';
import * as THREE from "three"; 
import { OrbitControls } from 'three/examples/jsm/controls/OrbitControls';


export default function HyperCubo({divRef}){
    const refMount = useRef(null);

    useEffect(() => {
        const currentRef = refMount.current;
        const {clientWidth: width, clientHeight: height} = currentRef; 

        const scene = new THREE.Scene(); 
        scene.background = new THREE.Color(0x5b00ff);
        const camera = new THREE.PerspectiveCamera(25, width/height,0.01, 1000);
        scene.add(camera);
        camera.position.z = 6;
        camera.position.x = 6;

        const renderer = new THREE.WebGLRenderer();
        renderer.setSize(width, height);
        currentRef.appendChild(renderer.domElement);

        const controls = new OrbitControls(camera,renderer.domElement);
        controls.enableDamping = true;

        const geometry = new THREE.BoxGeometry(1,1,1);
        const material = new THREE.MeshPhongMaterial({color: 0x0f2c64});
        const cube= new THREE.Mesh(geometry, material);
        scene.add(cube);
        camera.lookAt(cube.position);

        const lightAm = new THREE.AmbientLight(0xff0000, 5);
        scene.add(lightAm);

        const light = new THREE.PointLight(0xff0000, 15);
        light.position.set(8,8,8);
        scene.add(light);


        const clock = new THREE.Clock();
        const animate =() =>{
            const elapsedTime = clock.getElapsedTime();
            cube.rotation.x = elapsedTime;
            cube.rotation.y = elapsedTime;
            cube.position.y = Math.sin(elapsedTime);
            
            controls.update();
            renderer.render(scene, camera);
            requestAnimationFrame(animate);
        };

        const resize = () => {
            const updatedWidth = currentRef.clientWidth;
            const updateHeight = currentRef.clientHeight;
            renderer.setSize(updatedWidth,updateHeight);
            camera.aspect = updatedWidth/updateHeight;
            camera.updateProjectionMatrix();
        }
        window.addEventListener("resize",resize);

        animate();

        // Axes helper
        // lo que nos ayuda es a agregar a escena las lineas de ejes x,y,z
        // THREE.AxesHelper toma como parametro que tanto van a medir las lineas de los ejes
        const axesHelper = new THREE.AxesHelper(2);
        scene.add(axesHelper);

        //Grid Helper
        //la grilla que se dibuja en la base
        const size = 10;
        const divisions = 10;
        const gridHelper = new THREE.GridHelper(size,divisions);
        scene.add(gridHelper);

        return() =>{
            currentRef.removeChild(renderer.domElement);
            window.removeEventListener("resize",resize);
        }
    },[])
    return(
        <div ref={refMount} style={{width: "100%", height: "100%"}}>

        </div>
    )
};
```

### Geometry
```js
import React, {useRef, useState, useEffect} from 'react';
import * as THREE from "three"; 
import { OrbitControls } from 'three/examples/jsm/controls/OrbitControls';


export default function HyperCubo({divRef}){
    const refMount = useRef(null);

    useEffect(() => {
        const currentRef = refMount.current;
        const {clientWidth: width, clientHeight: height} = currentRef; 

        const scene = new THREE.Scene(); 
        scene.background = new THREE.Color(0x5b00ff);
        const camera = new THREE.PerspectiveCamera(25, width/height,0.01, 1000);
        scene.add(camera);
        camera.position.z = 10;

        const renderer = new THREE.WebGLRenderer();
        renderer.setSize(width, height);
        currentRef.appendChild(renderer.domElement);

        const controls = new OrbitControls(camera,renderer.domElement);
        controls.enableDamping = true;

        const geometry = new THREE.BoxGeometry(1,1,1,2,2,2);
        const material = new THREE.MeshPhongMaterial({color: 0x0f2c64, wireframe: true});
        const cube= new THREE.Mesh(geometry, material);
        scene.add(cube);
        //podemos mover al cubo:
        cube.position.set(1,1,1);
        // cada geometria tiene divisiones
        // si queremos agregar mas subdiviones en el cubo, podemos hacerlo de la siguiente manera:
        // const geometry = new THREE.BoxGeometry(1,1,1,2,2,2);
        // por defecto el cubo tiene una subdivision de 1 pero se puede modificar a 2 o mas subdiviones, este parametros se agregan despues de agregar las medidas del cubo, subtivisionx,subdivisiony,subdivisionz
        // activar las opcion de wareframe ayudara a que se vean mejor las subdivisiones
        //const material = new THREE.MeshPhongMaterial({color: 0x0f2c64, wireframe: true});
        camera.lookAt(cube.position);

        const lightAm = new THREE.AmbientLight(0xff0000, 5);
        scene.add(lightAm);

        const light = new THREE.PointLight(0xff0000, 15);
        light.position.set(8,8,8);
        scene.add(light);


        const clock = new THREE.Clock();
        const animate =() =>{
            controls.update();
            renderer.render(scene, camera);
            requestAnimationFrame(animate);
        };

        const resize = () => {
            const updatedWidth = currentRef.clientWidth;
            const updateHeight = currentRef.clientHeight;
            renderer.setSize(updatedWidth,updateHeight);
            camera.aspect = updatedWidth/updateHeight;
            camera.updateProjectionMatrix();
        }
        window.addEventListener("resize",resize);

        animate();

        const axesHelper = new THREE.AxesHelper(2);
        scene.add(axesHelper);

        const size = 10;
        const divisions = 10;
        const gridHelper = new THREE.GridHelper(size,divisions);
        scene.add(gridHelper);

        return() =>{
            currentRef.removeChild(renderer.domElement);
            window.removeEventListener("resize",resize);
        }
    },[])
    return(
        <div ref={refMount} style={{width: "100%", height: "100%"}}>

        </div>
    )
};
```

### BufferGeometry
```js
import React, {useRef, useState, useEffect} from 'react';
import * as THREE from "three"; 
import { OrbitControls } from 'three/examples/jsm/controls/OrbitControls';


export default function HyperCubo({divRef}){
    const refMount = useRef(null);

    useEffect(() => {
        const currentRef = refMount.current;
        const {clientWidth: width, clientHeight: height} = currentRef; 

        const scene = new THREE.Scene(); 
        //scene.background = new THREE.Color(0x5b00ff);
        const camera = new THREE.PerspectiveCamera(25, width/height,0.01, 1000);
        scene.add(camera);
        camera.position.z = 10;

        const renderer = new THREE.WebGLRenderer();
        renderer.setSize(width, height);
        currentRef.appendChild(renderer.domElement);

        const controls = new OrbitControls(camera,renderer.domElement);
        controls.enableDamping = true;

        //cubo con Buffer Geometry
        // buffer geometry es mucho mas facil para nuestro equipo manejarla, si la escena sencilla se recomienda usar geometry y si la escena es mas compleja entonces se recomienda usar bufferGeometry, incluso cuando importamos modelos 3d como blender se utiliza buffergeometry
        const geometry = new THREE.BoxBufferGeometry(1,1,1,2,2,2);
        const material = new THREE.MeshBasicMaterial({color: 0x0f2c64, wireframe: true});
        const cube= new THREE.Mesh(geometry, material);
        scene.add(cube);
        cube.position.set(1,1,1);
        camera.lookAt(cube.position);


        const lightAm = new THREE.AmbientLight(0xff0000, 5);
        scene.add(lightAm);

        const light = new THREE.PointLight(0xff0000, 15);
        light.position.set(8,8,8);
        scene.add(light);


        const clock = new THREE.Clock();
        const animate =() =>{
            controls.update();
            renderer.render(scene, camera);
            requestAnimationFrame(animate);
        };

        const resize = () => {
            const updatedWidth = currentRef.clientWidth;
            const updateHeight = currentRef.clientHeight;
            renderer.setSize(updatedWidth,updateHeight);
            camera.aspect = updatedWidth/updateHeight;
            camera.updateProjectionMatrix();
        }
        window.addEventListener("resize",resize);

        animate();

        const axesHelper = new THREE.AxesHelper(2);
        scene.add(axesHelper);

        const size = 10;
        const divisions = 10;
        const gridHelper = new THREE.GridHelper(size,divisions);
        scene.add(gridHelper);

        return() =>{
            currentRef.removeChild(renderer.domElement);
            window.removeEventListener("resize",resize);
        }
    },[])
    return(
        <div ref={refMount} style={{width: "100%", height: "100%"}}>

        </div>
    )
};
```

Si observamos mejor el objeto js del `geometry` podemos ver que tiene varios atributos:
- `normal`: ES para saber donde esta apuntando cada cara 
- `position` : indica donde esta colocado cada punto de nuestro cubo, es decir cada vertise
- `uv` :son coordenadas uv que nos ayudan a asignarle texturas.

### Vertexs

```js
import React, {useRef, useState, useEffect} from 'react';
import * as THREE from "three"; 
import { OrbitControls } from 'three/examples/jsm/controls/OrbitControls';


export default function HyperCubo({divRef}){
    const refMount = useRef(null);

    useEffect(() => {
        const currentRef = refMount.current;
        const {clientWidth: width, clientHeight: height} = currentRef; 

        const scene = new THREE.Scene(); 
        //scene.background = new THREE.Color(0x5b00ff);
        const camera = new THREE.PerspectiveCamera(25, width/height,0.01, 1000);
        scene.add(camera);
        camera.position.z = 10;

        const renderer = new THREE.WebGLRenderer();
        renderer.setSize(width, height);
        currentRef.appendChild(renderer.domElement);

        const controls = new OrbitControls(camera,renderer.domElement);
        controls.enableDamping = true;

        //vertices
        const material = new THREE.MeshBasicMaterial({color: 0x0f2c64, wireframe: true});
        //aqui no estamos inficando si es un cubo, una esfera, etc. Solamente estamos declarando BufferGeometry, necesitamos crearle atributos a este tipo de geometria
        const faceGeometry = new THREE.BufferGeometry();
        //para generarle este tipo actributos necesitamos declarar un tipo especial de array el cual se llama Float32Array
        // este tipo de array somanete acepta tipos de valor flotante, en este caso le hemos puesto valores tipo entero pero se les puede poner valores flotantes
        // los valores del array es donde va a ser colocado cada vertice, normalmente esta dividido por coordenadas de 3 puntos, cada uno de estos puntos reprecenta x,y,z
        const facePoints = new Float32Array([
            0,0,0,
            0,1,0,
            1,1,0
        ]);
        //despues de crear la posicion de los puntos ahora necesitamos crear el atributo
        // recibe dos parametros, los puntos y cuantos datos va a utilizar para generar una cordenada, en este caso son 3 uno para x, otro para y , otro para z
        const facePointsPosition = new THREE.BufferAttribute(facePoints, 3);
        // y finalmente a faceGeometry tenemos que asignarle este atributo
        // debemos de llamarlo psoition, si lo llamamos de otro nombre no va a funcionar
        faceGeometry.setAttribute("position", facePointsPosition);
        //ahora necitamos crear lo que es la mesh
        const cube= new THREE.Mesh(faceGeometry, material);
        scene.add(cube);
        // se ha generado un triangulo
        camera.lookAt(cube.position);


        const lightAm = new THREE.AmbientLight(0xff0000, 5);
        scene.add(lightAm);

        const light = new THREE.PointLight(0xff0000, 15);
        light.position.set(8,8,8);
        scene.add(light);


        const clock = new THREE.Clock();
        const animate =() =>{
            controls.update();
            renderer.render(scene, camera);
            requestAnimationFrame(animate);
        };

        const resize = () => {
            const updatedWidth = currentRef.clientWidth;
            const updateHeight = currentRef.clientHeight;
            renderer.setSize(updatedWidth,updateHeight);
            camera.aspect = updatedWidth/updateHeight;
            camera.updateProjectionMatrix();
        }
        window.addEventListener("resize",resize);

        animate();

        const axesHelper = new THREE.AxesHelper(2);
        scene.add(axesHelper);

        const size = 10;
        const divisions = 10;
        const gridHelper = new THREE.GridHelper(size,divisions);
        scene.add(gridHelper);

        return() =>{
            currentRef.removeChild(renderer.domElement);
            window.removeEventListener("resize",resize);
        }
    },[])
    return(
        <div ref={refMount} style={{width: "100%", height: "100%"}}>

        </div>
    )
};
```

La desventaja es que es muy tedioso crear figuras de esta manera, la mejor foma es crear una figura en un mejor programa 3d.

### Particles
```JS
import React, {useRef, useState, useEffect} from 'react';
import * as THREE from "three"; 
import { OrbitControls } from 'three/examples/jsm/controls/OrbitControls';


export default function HyperCubo({divRef}){
    const refMount = useRef(null);

    useEffect(() => {
        const currentRef = refMount.current;
        const {clientWidth: width, clientHeight: height} = currentRef; 

        const scene = new THREE.Scene(); 
        //scene.background = new THREE.Color(0x5b00ff);
        const camera = new THREE.PerspectiveCamera(25, width/height,0.01, 1000);
        scene.add(camera);
        camera.position.z = 10;

        const renderer = new THREE.WebGLRenderer();
        renderer.setSize(width, height);
        currentRef.appendChild(renderer.domElement);

        const controls = new OrbitControls(camera,renderer.domElement);
        controls.enableDamping = true;

        //Particles
        const count = 1000; // numero de particulas que queremos en escena.
        const particlesPositions = new Float32Array(count * 3);// una particula utiliza 3 datos para generar una coordenada
        for (let i = 0;i< count * 3; i++){
            particlesPositions[i] = Math.random() * (-5 - 5 + 1) + 5;
        };
        //finalmente declaramos el atributo, las posiciones y cuantos datos va a tulizar cada coordenada
        const particlesAttribute = new THREE.BufferAttribute(particlesPositions,3);
        //creamos la geometria
        const particlesGeometry = new THREE.BufferGeometry();
        particlesGeometry.setAttribute("position", particlesAttribute);

        // la creacion del material es diferente para este caso
        const particlesMaterial = new THREE.PointsMaterial({color: 0xff0000});

        //la mesh en esta ocacion se declara como POINTS
        const particles = new THREE.Points(particlesGeometry, particlesMaterial);
        scene.add(particles);
        camera.lookAt(particles.position);


        const lightAm = new THREE.AmbientLight(0xff0000, 5);
        scene.add(lightAm);

        const light = new THREE.PointLight(0xff0000, 15);
        light.position.set(8,8,8);
        scene.add(light);


        const clock = new THREE.Clock();
        const animate =() =>{
            controls.update();
            renderer.render(scene, camera);
            requestAnimationFrame(animate);
        };

        const resize = () => {
            const updatedWidth = currentRef.clientWidth;
            const updateHeight = currentRef.clientHeight;
            renderer.setSize(updatedWidth,updateHeight);
            camera.aspect = updatedWidth/updateHeight;
            camera.updateProjectionMatrix();
        }
        window.addEventListener("resize",resize);

        animate();

        const axesHelper = new THREE.AxesHelper(2);
        scene.add(axesHelper);

        const size = 10;
        const divisions = 10;
        const gridHelper = new THREE.GridHelper(size,divisions);
        scene.add(gridHelper);

        return() =>{
            currentRef.removeChild(renderer.domElement);
            window.removeEventListener("resize",resize);
        }
    },[])
    return(
        <div ref={refMount} style={{width: "100%", height: "100%"}}>

        </div>
    )
};
```

### MeshBasicMaterial

```js
import React, {useRef, useState, useEffect} from 'react';
import * as THREE from "three"; 
import { OrbitControls } from 'three/examples/jsm/controls/OrbitControls';


export default function HyperCubo({divRef}){
    const refMount = useRef(null);

    useEffect(() => {
        try {
            const currentRef = refMount.current;
        const {clientWidth: width, clientHeight: height} = currentRef; 

        const scene = new THREE.Scene(); 
        //scene.background = new THREE.Color(0x5b00ff);
        const camera = new THREE.PerspectiveCamera(25, width/height,0.01, 1000);
        scene.add(camera);
        camera.position.z = 10;

        const renderer = new THREE.WebGLRenderer();
        renderer.setSize(width, height);
        currentRef.appendChild(renderer.domElement);

        const controls = new OrbitControls(camera,renderer.domElement);
        controls.enableDamping = true;

        //Material
        const material = new THREE.MeshBasicMaterial();
        // al material podemos pasarle un color:
        material.color = new THREE.Color(0x5b00ff);
        //podemos activar la opcion de wireframe, la cual nos permiten ver las aristas
        //material.wireframe =  true;
        // tambien tenemos las opciones de transparent y opacity, si los usamos juntos podemos ver atravez de los objetos
        //material.transparent = true;
        //material.opacity = 0.5;

        //cube
        const cubeGeopetry = new THREE.BoxBufferGeometry(1,1,1);
        const cube = new THREE.Mesh(cubeGeopetry, material);
        cube.position.set(-3,0,0);

        const torusGeopetry = new THREE.TorusBufferGeometry(0.5,0.2,16,32);
        const torus = new THREE.Mesh(torusGeopetry, material);
        torus.castShadow = true;

        const torusKnotGeopetry = new THREE.TorusKnotBufferGeometry(0.7,0.2,50,32);
        const torusknot = new THREE.Mesh(torusKnotGeopetry, material);
        torusknot.position.set(3,0,0);

        scene.add(cube,torus,torusknot);
        


        const lightAm = new THREE.AmbientLight(0xff0000, 5);
        scene.add(lightAm);

        const light = new THREE.PointLight(0xff0000, 15);
        light.position.set(8,8,8);
        scene.add(light);


        const animate =() =>{
            controls.update();
            renderer.render(scene, camera);
            requestAnimationFrame(animate);
        };

        const resize = () => {
            const updatedWidth = currentRef.clientWidth;
            const updateHeight = currentRef.clientHeight;
            renderer.setSize(updatedWidth,updateHeight);
            camera.aspect = updatedWidth/updateHeight;
            camera.updateProjectionMatrix();
        }
        window.addEventListener("resize",resize);

        animate();

        } catch (error) {
            console.log(error)
        }
        return() =>{
            currentRef.removeChild(renderer.domElement);
            window.removeEventListener("resize",resize);
        }
    },[])
    return(
        <div ref={refMount} style={{width: "100%", height: "100%"}}>

        </div>
    )
};
```

### MeshNormalMaterial

```js
import React, {useRef, useState, useEffect} from 'react';
import * as THREE from "three"; 
import { OrbitControls } from 'three/examples/jsm/controls/OrbitControls';


export default function HyperCubo({divRef}){
    const refMount = useRef(null);

    useEffect(() => {
        try {
            const currentRef = refMount.current;
        const {clientWidth: width, clientHeight: height} = currentRef; 

        const scene = new THREE.Scene(); 
        //scene.background = new THREE.Color(0x5b00ff);
        const camera = new THREE.PerspectiveCamera(25, width/height,0.01, 1000);
        scene.add(camera);
        camera.position.z = 10;

        const renderer = new THREE.WebGLRenderer();
        renderer.setSize(width, height);
        currentRef.appendChild(renderer.domElement);

        const controls = new OrbitControls(camera,renderer.domElement);
        controls.enableDamping = true;

        //Material
        // puedes crear efectos interesantes usantos este marerial como degradados de colores
        const material = new THREE.MeshNormalMaterial();
        // podemos hacer que los angulos se vean mas marcados:
        material.flatShading =  true;
        
        //cube
        const cubeGeopetry = new THREE.BoxBufferGeometry(1,1,1);
        const cube = new THREE.Mesh(cubeGeopetry, material);
        cube.position.set(-3,0,0);

        const torusGeopetry = new THREE.TorusBufferGeometry(0.5,0.2,16,32);
        const torus = new THREE.Mesh(torusGeopetry, material);
        torus.castShadow = true;

        const torusKnotGeopetry = new THREE.TorusKnotBufferGeometry(0.7,0.2,50,32);
        const torusknot = new THREE.Mesh(torusKnotGeopetry, material);
        torusknot.position.set(3,0,0);

        scene.add(cube,torus,torusknot);
        


        const lightAm = new THREE.AmbientLight(0xff0000, 5);
        scene.add(lightAm);

        const light = new THREE.PointLight(0xff0000, 15);
        light.position.set(8,8,8);
        scene.add(light);


        const animate =() =>{
            controls.update();
            renderer.render(scene, camera);
            requestAnimationFrame(animate);
        };

        const resize = () => {
            const updatedWidth = currentRef.clientWidth;
            const updateHeight = currentRef.clientHeight;
            renderer.setSize(updatedWidth,updateHeight);
            camera.aspect = updatedWidth/updateHeight;
            camera.updateProjectionMatrix();
        }
        window.addEventListener("resize",resize);

        animate();

        } catch (error) {
            console.log(error)
        }
        return() =>{
            currentRef.removeChild(renderer.domElement);
            window.removeEventListener("resize",resize);
        }
    },[])
    return(
        <div ref={refMount} style={{width: "100%", height: "100%"}}>

        </div>
    )
};
```

### MeshMatcapMaterial

[Matcaps](https://github.com/nidorx/matcaps)

```js
import React, {useRef, useState, useEffect} from 'react';
import * as THREE from "three"; 
import { OrbitControls } from 'three/examples/jsm/controls/OrbitControls';


export default function HyperCubo({divRef}){
    const refMount = useRef(null);

    useEffect(() => {
        try {
            const currentRef = refMount.current;
        const {clientWidth: width, clientHeight: height} = currentRef; 

        const scene = new THREE.Scene(); 
        //scene.background = new THREE.Color(0x5b00ff);
        const camera = new THREE.PerspectiveCamera(25, width/height,0.01, 1000);
        scene.add(camera);
        camera.position.z = 10;

        const renderer = new THREE.WebGLRenderer();
        renderer.setSize(width, height);
        currentRef.appendChild(renderer.domElement);

        const controls = new OrbitControls(camera,renderer.domElement);
        controls.enableDamping = true;

        //Material
        //por si solor MeshMatcapMaterial no tiene ningun color ni tectura para ello tenemos que descargar un matcaps
        const material = new THREE.MeshMatcapMaterial();
        // para usar los matcaps primero los tenemos que descargar y despues tenemos que crear una isntancia donde carge la textura
        const textureLoader = new THREE.TextureLoader();
        //despues tenemos que indicar la carpeta donde esta el matcap
        const matcap = textureLoader.load("https://raw.githubusercontent.com/nidorx/matcaps/master/1024/C7C7D7_4C4E5A_818393_6C6C74.png");
        material.matcap = matcap;
        
       
        //cube
        const cubeGeopetry = new THREE.BoxBufferGeometry(1,1,1);
        const cube = new THREE.Mesh(cubeGeopetry, material);
        cube.position.set(-3,0,0);

        const torusGeopetry = new THREE.TorusBufferGeometry(0.5,0.2,16,32);
        const torus = new THREE.Mesh(torusGeopetry, material);
        torus.castShadow = true;

        const torusKnotGeopetry = new THREE.TorusKnotBufferGeometry(0.7,0.2,50,32);
        const torusknot = new THREE.Mesh(torusKnotGeopetry, material);
        torusknot.position.set(3,0,0);

        scene.add(cube,torus,torusknot);
        


        const lightAm = new THREE.AmbientLight(0xff0000, 5);
        scene.add(lightAm);

        const light = new THREE.PointLight(0xff0000, 15);
        light.position.set(8,8,8);
        scene.add(light);


        const animate =() =>{
            controls.update();
            renderer.render(scene, camera);
            requestAnimationFrame(animate);
        };

        const resize = () => {
            const updatedWidth = currentRef.clientWidth;
            const updateHeight = currentRef.clientHeight;
            renderer.setSize(updatedWidth,updateHeight);
            camera.aspect = updatedWidth/updateHeight;
            camera.updateProjectionMatrix();
        }
        window.addEventListener("resize",resize);

        animate();

        } catch (error) {
            console.log(error)
        }
        return() =>{
            currentRef.removeChild(renderer.domElement);
            window.removeEventListener("resize",resize);
        }
    },[])
    return(
        <div ref={refMount} style={{width: "100%", height: "100%"}}>

        </div>
    )
};
```

### MeshStandarMaterial

Tenemos que ir a la pagina y descargar un en formato **HDR** [Environment Map](https://polyhaven.com/hdris) despues de descargarlo tenemos que convertirlo a formato cubemap que es el formato que acepta three.js

```js
import React, {useRef, useState, useEffect} from 'react';
import * as THREE from "three"; 
import { OrbitControls } from 'three/examples/jsm/controls/OrbitControls';


export default function HyperCubo({divRef}){
    const refMount = useRef(null);

    useEffect(() => {
        try {
            const currentRef = refMount.current;
        const {clientWidth: width, clientHeight: height} = currentRef; 

        const scene = new THREE.Scene(); 
        //scene.background = new THREE.Color(0x5b00ff);
        const camera = new THREE.PerspectiveCamera(25, width/height,0.01, 1000);
        scene.add(camera);
        camera.position.z = 10;

        const renderer = new THREE.WebGLRenderer();
        renderer.setSize(width, height);
        currentRef.appendChild(renderer.domElement);

        const controls = new OrbitControls(camera,renderer.domElement);
        controls.enableDamping = true;

        //Material
        // es un tipo de material que necesita luces en escena para poder verse 
        const material = new THREE.MeshStandardMaterial();
        material.color.set("#ff000");
        scene.background = new THREE.Color(0xeeeeee)
        // material.metalness entre mas cercano a 1 sea su valor mas apariencia a metal va a tener
        // cuando damos una apariencia de metal tienda a hacerse oscuro y necesita una luz para poder verse
        // para tratar con los materiales metaliscos y evitar que se opaquen , al material necesitamos aplicarle algo que se llama  y despues convertir el formato hdri a formato cubemap
        material.metalness = 1;
        //material.roughness entre mas cercano a cero va a terner una apariencia mas lisa y mas cercano a 1 una apariencia mas rugosa.
        material.roughness = 0;
        const cubeTextureLoader = new THREE.CubeTextureLoader();
        const evm = cubeTextureLoader.load([
            "px",
            "nx",
            "py",
            "ny",
            "pz",
            "nz"
        ]);//aqui tenemos que cargar un array de imagenes
        material.envMap =  evm;//con esto el material metalico ya estaria reflejando mas


        //cube
        const cubeGeopetry = new THREE.BoxBufferGeometry(1,1,1);
        const cube = new THREE.Mesh(cubeGeopetry, material);
        cube.position.set(-3,0,0);

        const torusGeopetry = new THREE.TorusBufferGeometry(0.5,0.2,16,32);
        const torus = new THREE.Mesh(torusGeopetry, material);
        torus.castShadow = true;

        const torusKnotGeopetry = new THREE.TorusKnotBufferGeometry(0.7,0.2,50,32);
        const torusknot = new THREE.Mesh(torusKnotGeopetry, material);
        torusknot.position.set(3,0,0);

        scene.add(cube,torus,torusknot);
        

        const lightAm = new THREE.AmbientLight(0xff0000, 500);
        scene.add(lightAm);

        const light = new THREE.PointLight(0xff0000, 150);
        light.position.set(8,8,8);
        scene.add(light);


        const animate =() =>{
            controls.update();
            renderer.render(scene, camera);
            requestAnimationFrame(animate);
        };

        const resize = () => {
            const updatedWidth = currentRef.clientWidth;
            const updateHeight = currentRef.clientHeight;
            renderer.setSize(updatedWidth,updateHeight);
            camera.aspect = updatedWidth/updateHeight;
            camera.updateProjectionMatrix();
        }
        window.addEventListener("resize",resize);

        animate();

        } catch (error) {
            console.log(error)
        }
        return() =>{
            currentRef.removeChild(renderer.domElement);
            window.removeEventListener("resize",resize);
        }
    },[])
    return(
        <div ref={refMount} style={{width: "100%", height: "100%"}}>

        </div>
    )
};
```

### Texturas

Para las texturas donde todas las caras son lo mismo esta bien este metodo, pero si necesitamos algo mas especifico entonces es mejor cargar las texturas en blender y exportar el objeto
```js
import React, {useRef, useState, useEffect} from 'react';
import * as THREE from "three"; 
import { OrbitControls } from 'three/examples/jsm/controls/OrbitControls';


export default function HyperCubo({divRef}){
    const refMount = useRef(null);

    useEffect(() => {
        try {
            const currentRef = refMount.current;
        const {clientWidth: width, clientHeight: height} = currentRef; 

        const scene = new THREE.Scene(); 
        //scene.background = new THREE.Color(0x5b00ff);
        const camera = new THREE.PerspectiveCamera(25, width/height,0.01, 1000);
        scene.add(camera);
        camera.position.z = 10;

        const renderer = new THREE.WebGLRenderer();
        renderer.setSize(width, height);
        currentRef.appendChild(renderer.domElement);

        const controls = new OrbitControls(camera,renderer.domElement);
        controls.enableDamping = true;

        //Material
        const material = new THREE.MeshStandardMaterial();
        //para cargar texturas:
        const textureLoader = new THREE.TextureLoader();
        const iron = textureLoader.load("https://lh3.googleusercontent.com/pXG5ZF3jR2cK_ZKsqOr4FH4CTSV8rbp4dQY0ri2uOmxSc8BbgiZlViWFo8SSHDJBjqKRtC0L0TzdZRGltOED4kM=s400");//tiene que tener la ruta del material
        //despues tenemos que acceder a la propiedad map
        material.map = iron;
        

        //cube
        const cubeGeopetry = new THREE.BoxBufferGeometry(1,1,1);
        const cube = new THREE.Mesh(cubeGeopetry, material);

        scene.add(cube);
        

        const lightAm = new THREE.AmbientLight(0xffffff, 0.5);
        scene.add(lightAm);

        /*const light = new THREE.PointLight(0xff0000, 1);
        light.position.set(8,8,8);
        scene.add(light);*/


        const animate =() =>{
            controls.update();
            renderer.render(scene, camera);
            requestAnimationFrame(animate);
        };

        const resize = () => {
            const updatedWidth = currentRef.clientWidth;
            const updateHeight = currentRef.clientHeight;
            renderer.setSize(updatedWidth,updateHeight);
            camera.aspect = updatedWidth/updateHeight;
            camera.updateProjectionMatrix();
        }
        window.addEventListener("resize",resize);

        animate();

        } catch (error) {
            console.log(error)
        }
        return() =>{
            currentRef.removeChild(renderer.domElement);
            window.removeEventListener("resize",resize);
        }
    },[])
    return(
        <div ref={refMount} style={{width: "100%", height: "100%"}}>

        </div>
    )
};
```