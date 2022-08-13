# Tutorial React

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
```
