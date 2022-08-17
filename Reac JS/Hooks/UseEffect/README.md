# Ejemplo de Hooks(UseEffect)

## Importar Hooks(UseEffect)

NOTA: Al usar este Hook, le estamos indicando a React que el componente tiene que hacer algo despues de renderizarce. Se usa mayormente para consumir una api.

1. Para poder utlizar hooks se debe de importar una libreria de reac llamada `UseEffect` de la siguiente manera:
   Nota: la libreria React siempre se debe de Importar.
```
import React, {UseEffect} from 'react';
```

2. Este hook lleva dos parametros la primera es una funcion flecha y la otra un vector de variables que se actualizan, el siguiente ejemplo solo se mostra con el primer parametro quedaria lo siguiente `UseEffect( () =>{ //CODIGO }  )` dentro de nuestra funcion flecha estra nuestro codigo a ejecutar, el siguiente ejemplo mostrar como se veria completo.
```
  import React, {UseEffect} from 'react';

  cost Nosotros = () => {
    UseEffect( () =>{
        console.log('Ejemplo');
      } )
  }
```

3. El segundo parametro que tiene este hook es la variable que se actualiza. este es un vector que lleva quedaria de la siguiente manera `UseEffect( () =>{ //CODIGO } , []  )` en el siguiente ejemplo se mostrara completo.

```
  import React, {useEffect , useState} from 'react';

  cost Nosotros = () => {

    cost datos = [
      {id:1, nombre: 'ReactJs'},
      {id:2, nombre: 'VueJs'},
      {id:3, nombre: 'AngularJs'},
    ]

    const [equipo, setEquipo] =  useState(null);

    UseEffect( () =>{
        setEquipo(datos)
      } , [])

    return(
      <div>
        <h1> Nosotros </h1>
      </div>
    );
  }
```
