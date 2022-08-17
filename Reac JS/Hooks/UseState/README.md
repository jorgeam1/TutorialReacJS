# Ejemplo de Hooks(UseState)

## Importar Hooks(useState)

1. Para poder utlizar hooks se debe de importar una libreria de reac llamada `useState` de la siguiente manera:
   Nota: la libreria React siempre se debe de Importar.
```
import React, {useState} from 'react';
```

2. Se debre de crear una constante como la siguiente(este es solo el uso base de Hooks):
```
  const [] = useState();
```

 3. Debemos tener un nombre de estado este puede llevar cualquier nombre quedaria de la siguiente manera:
```
 const [numero] = useState();
```

 4. Creamos otra varible que nos ayudara a actualizar o cambiar el estado ya creado en el paso anterior.
```
 const [numero, setNumero] = useState();
```

 5. Debemos inicializar el stado en este cado numero(Paso 3) dentro de useState de la siguiente manera.
    Nota: este valor incial puede ser cualquier valor int, string, booleano, objeto, array, etc.
```
  const [numero, setNumero] = useState(0);
```

 6. la siguiente manera es la forma de llamar o pintar un hook se hace referencia a el estado(Paso 3, en este caso llamado numero) luego solo lo llamas a nuestro archivo App.js:
    Nota: este ejemplo es un contador.
```
  import React, {useState} from 'react';

  const Contador = () => {
    const [numero,setNumero] = useState(0);

    return(
      <h3>  Mi primer Componente {numero}  </h3>
    );
  }
```


7. Actualizar valor del estado(numero), debemos llamar a nuestra variable de actualizacion(llamada setNumero) y dentro de parentesis hacemos nuestra actualizacion.
```
 setNumero(numero + 1);
```
Ejmplo Final:
Nota: en este caso se creo un boton para actualizar nuestro estado.
```
import React, { useState } from "react";

const Contador = () => {
    const [numero, setNumero] = useState(2);

    const aumentar = () =>{
        setNumero(numero+1);
    }

    return(
        <div>
            <h3> Mi primer Compaonete {numero}  </h3>
            <button onClick={aumentar}> Aumentar </button>
        </div>
    );
}

export default Contador;
```
