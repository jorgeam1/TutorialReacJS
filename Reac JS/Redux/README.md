# Uso e instalacion de Redux

## (1) Instalacion y Creacion del archivo Store.
1. Debemos instalar redux desde npm de la siguinete manera desde la terminal dentro de nuestro proyecto
```
npm install @reduxjs/toolkit react-redux
```

2. Creamos un archivo store.js en la siguiente ruta `src/app/store.js`.

3. Ingresamos en nuestro archivo store.js(Paso 2), y debemos importar `configureStore` quedaría de la siguiente manera.
```
import { configureStore } from '@reduxjs/toolkit'
```

4. En el mismo archivo store.js Debemos crear nuestro configureStroe `configureStore({})` quedando de la siguiente manera:
```
  import { configureStore } from '@reduxjs/toolkit'

  configureStore({

  })
```

5. Exportamos nuestro configureStore del paso 4 con export default quedando de la siguiente manera:
```
import { configureStore } from '@reduxjs/toolkit'

export default configureStore({
  reducer: {},
})
```
## (2) Uso de nuestro archivo Store
1. Nos dirigimos a nuestro archivo index.js

2. Importamos Provider desde react-redux quedando de la siguiente manera:
```
import { Provider } from 'react-redux'
```

3. Debemos contener nuestro `<App/>` dentro de las etiquetas Provider de la siguiente manera:
```
<Provider>
    <App />
</Provider>
```

4. Tambien debemos importar nuestro `store.js` creado en la Seccion 1(Instalacion y Creacion del archivo Store.) quedando de la siguiente manera:
```
 import store from './app/store'
```

 5. Agregamos la propiedad Store a nuestra etiqueta Provider(Paso 3) y le pasamos nuestro archivo `store.js`(paso 4) quedando de la siguiente manera:
```
 <Provider store={store}>
    <App />
  </Provider>
```
6. Ejemplo Final  

```
import React from 'react';
import ReactDOM from 'react-dom/client';
import './assets/css/index.css';
import App from './App';
import reportWebVitals from './reportWebVitals';

//5. exportamos el contenedor Provaider desde react-redux linea de abajo.
import { Provider } from 'react-redux';
import store from './app/store';

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(
 <React.StrictMode>
   <Provider Store={store}>
     <App />
   </Provider>
 </React.StrictMode>
);

// If you want to start measuring performance in your app, pass a function
// to log results (for example: reportWebVitals(console.log))
// or send to an analytics endpoint. Learn more: https://bit.ly/CRA-vitals
reportWebVitals();

```
## (3) Creacion de Redux State Slice
1. Creamos un archivo `counterSlice.js` en la siguiente ruta `src/features/<NAME>/<NAME>Slice.js`

2. Ingresamos a nuestro archivo `<NAME>Slice.js` e importamos createSlice desde @reduxjs/toolkit quedando de la siguiente manera:
```
 import { createSlice } from '@reduxjs/toolkit';
```

3. Invocamos la funcion createSlice de la siguinete manera:
```
 createSlice({

 })
```

4. Debemos ponerle un nombre a nuestro `createSlice` de la siguiente manera:
   Nota: este puede ser cualquier nombre en este ejemplo lo llamaremos tasks
```
 createSlice({
   name : 'tasks'
 })
```

5. Despues debemos agregar otro parametro que se llama `initialState` de la siguiente manera:
   NOTA: este state es parecido a useState, este parametro es el valor inicial que tenda nuestro Slice como el useState (useStete(VALOR INICIAL)).
```
    createSlice({
      name : 'tasks',
      initialState : []
    })
```

6. Exportamos nuestro Slice de la siguiente manera
```
    export const taskSlice = createSlice({
      name : 'tasks',
      initialState : []
    })
```

7. Nuestro Slice tiene un tercer parametro llamada reducers que dentro de este llevara funcines que actualizaran o cambiaran el valor de nuestro Slice de la siguiente manera:
```
    export const taskSlice = createSlice({
      name : 'tasks',
      initialState : [],
      reducers: {
        //FUNCIONES QUE ACTUALIZARAN EL VALOR DE NUESTRO SLICE
      }
    })
```

Nota: Dentro de los reducers va nuestras funciones que actulizaran o cambiaran nuestro valor del Slice que tambien se tendran que exportar para el uso en cualquier componente de la aplicacion. Referecia : https://react-redux.js.org/tutorials/quick-start


## (4) Uso del Redux State Slice

1. Nos dirigimos a nuestro archivo `store.js` e importamos nuestro Slice que creamos anteriormente.
```
import { taskSlice } from '../features/tasks/taskSlice';
```

2. Lo agregamos a nuestro configureStore de la siguiente manera:
   Nota: lo que espera el configureStore es los reducer de nuestro Slice Creado anteriormente, pero en la seccion anterior se exporto el objeto, entonces debemos dirigimos a nuestro archivo Slice creado en la seccion anterior y colocar: ` export default taskSlice.reducer` esto solo exportar los reducer del Slice. Cambiara la importacion tambien.
```
  import taskReducer  from '../features/tasks/taskSlice';

  export const store = configureStore({
      tasks:  taskReducer
    })
```

## (5) Probar nuestros Archivos
1. Nos dirigimos a nuestro archivo `App.js` e importamos dos librerias desde react-redux llamadas useDispatch y useSelector
   **NOTA:** useDispatch= hace llamado a las funciones de nuestro Slice(reducers) para actualizar nuestro estado del Slice.
             useSelector= Es la forma en la que podremos traer los datos de nuestro estados del Slice(tiene acceso a todo nuestro estado)
```
  import { useSelector } from 'react-redux';
```

2. Hacemos uso del nuestro useSelector dentro de la funcion App
    **NOTA:** state.tasks hace referencia a nuestro estado del archivo store en este ejemplo dentro del reducer del archivo store.js(Seccion 4) hemos declarado un estado llamado tasks que hacer referencia al Slice taskSlice que tendra acceso a todas las caracteristicas de ese Slice.
```
  useSelector( state => state.tasks )
```
Ejmplo Final:
```
import './assets/css/App.css';

//import de REDUX
import { useSelector } from 'react-redux';

function App() {
  useSelector( state => state.tasks )

  return (
    <div>
        <p>  HOLA MUNDO    </p>
    </div>
  );
}

export default App;
```

3. Ahora podemos accedear a nuestro Slice tasks desde userSelector de la forma anterior podemos acceder a nuestro slice desde cualquier otro componentes siguiendo estos mismos pasos de importar el selector y usar nuestro useSelector seleccionando el slide que queremos acceder. Para poder visualizar el slice metemos en una constante el useSelector y lo mostramos enconsola:
 ```
 import './assets/css/App.css';

 //import de REDUX
 import { useSelector } from 'react-redux';

 function App() {
   const tasksState = useSelector( state => state.tasks )
   console.log(tasksState);

   return (
     <div>
         <p>  HOLA MUNDO    </p>
     </div>
   );
 }

 export default App;

 ```
