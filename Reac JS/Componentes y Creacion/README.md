# Creación y Agregar Componentes

## Actualizamos Node Js 
1. Ingresamos el comando `npm install -g npm@latest` esto es para actualizar npm a su ultima version.
2. borramos la cache de npm para que no nos genere un proyecto en antiguas version. ingesammos el siguiente comando `npm cache clean --force`.

## Crear proyecto de React.
1. Instalamos Reac con el comando `npx create-react-app <NOMBRE>`.
2. Ingresamos a la carpeta con `cd <NOMBRE>`
3. Para poder ejecutar el proyecto ingresaom `npm start`

## Crear un componente
1. Crear un archivo js con cualquier nombre Ejemplo: `<NOMBRE>.js` para este ejemplo le pondremos MiComponente.js

2. Importamos React a nuestro modulo creado quedando de la siguiente manera.
```
import React from 'react';
```

3. creamos una clase con el nombre del archivo y heredar de React component, se tendria lo siguiente(utilizaremos el nombre del Paso 1. MiComponente):
```
import React from 'react';

class MiComponente extends React.Component{
}
```
   3.1 Manera alternativa para Heredar de Reac.Component quedaria de la siguinete manera:
    ```
        import React, {Component} from 'react';

        class MiComponente extends Component{
            render(){
                return(
                    // CODIGO JSX
                );
            }
        }
    ```

4. agregarmos el codigo render que es el que visualizara los componentes quedaria de la siguiente manera:
```
import React from 'react';

class MiComponente extends React.Component{
    render(){
        return(
            // CODIGO JSX
        );
    }
}
```

5. Para este ejemplo utilizaremos el siguinete codigo JSX para pobrar nuestro componente(esto va dentro del return):
```
<h1> Hola, soy el componente llamado: MiComponente </h1>
```

6. Luego exportamos nuestro componente ponemos el siguinte codigo de preferencia hasta el final del archivo:
```
export default MiComponente;
```

### Llamar el Componente
7. Nos dirijimos al archivo `App.js` y lo importamos 
```
import MiComponente from '<RUTA>'; //ruta es la dirreccion de nuestro archivo en el paso 3
```

8. Llamamos el componenete en el archivo donde lo queremos mostrar en este ejemplo lo llamaremos en el modulo principal (App.js). Para hacerle referencai al modulo se le encierra enter <> y nombre del componente como lo importamos y diagonal al final Ejemplo(tomaremos el nombre creado en el paso 1 MiComponente): `<MiComponente/>`
```
return (
    <div className="App">
      <header className="App-header">
        <img src={logo} className="App-logo" alt="logo" />
        <p>
          Edit <code>src/App.js</code> and save to reload.
        </p>
      </header>
      <seccion className="Componentes">
        <MiComponente/>   
      </seccion>
    </div>
  );
```
9. Posibles Errores
En el componente a la hora de retornar no puede retornar mas de dos etiquetas Ejemplo:
```
return(
    <h1>  Hola, soy el componente llamada: MiComponente </h1>
    <h2>  Etiqueta 2 prueba </h2>
);
```
Esto lanzara error porque no puede retornar dos etiquetas y hay dos formas de solucionarlo usamos una etiqueta Fragment los enseramos en esta etiqueta `<React.Fragment> ETIQUETAS </React.Fragment> `
```
return(
    <React.Fragment>
        <h1>  Hola, soy el componente llamada: MiComponente </h1>
        <h2>  Etiqueta 2 prueba </h2>
    </React.Fragment>
);
```
Otra manera de corregirlo es contenerlo en un div Ejemplo:
```
return(
    <div>
        <h1>  Hola, soy el componente llamada: MiComponente </h1>
        <h2>  Etiqueta 2 prueba </h2>
    </div>
);
```
