# Problemas aplicados a la industria

Como vimos en la clase anterior, los algoritmos son una secuencia de pasos que nos permiten resolver un problema. En esta clase, veremos cómo aplicar el pensamiento computacional para resolver problemas aplicados a la industria.

Es muy común que en la industria se necesite resolver problemas que involucren manipular estructuras de datos combinadas como un array de objetos. Por ejemplo, en un e-commerce, se necesita mostrar una lista ordenada de productos. Cada producto tiene un nombre, una descripción, un precio y una imagen. Para mostrar la lista de productos, se necesita combinar todos estos datos. Además, debe seguir un criterio de orden, en este caso por precio.

Antes de continuar definiremos un array de objetos que representan productos. Cada producto tiene un nombre, una descripción, un precio y una imagen.

```js
    const products = [
        {   
            id: 1,
            name: 'Camisa unicornio',
            price: 30000,
            description: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Cupiditate, asperiores?',
            category: 'clothes',
            img: 'https://arepa.s3.amazonaws.com/camisa_unicornio.png',
        },
        {
            id: 2,
            name: 'Pantalon Hombre',
            price: 40000,
            category: 'clothes',
            description: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Cupiditate, asperiores?',
            img: 'https://arepa.s3.amazonaws.com/pantalon_hombre.png',
        },     
        {
            id: 3,
            name: 'Pantalon dama',
            price: 50000,
            category: 'clothes',
            description: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Cupiditate, asperiores?',
            img: 'https://arepa.s3.amazonaws.com/pantalon_dama.png',
        },
        {
            id: 4,
            name: 'Camisa de dama',
            price: 31000,
            category: 'clothes',
            description: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Cupiditate, asperiores?',
            img: 'https://arepa.s3.amazonaws.com/camisa_dama.png',
        },
    ]
```

## Planteamiento del problema

Vamos a resolver el siguiente problema: **Ordenar una lista de productos por precio**

### Definir el problema

El problema consiste en ordenar una lista de productos por precio. Ya sea de menor a mayor o de mayor a menor.

### Analizar el problema

Para resolver el problema, debemos conocer el algoritmo de ordenamiento por selección. Este algoritmo consiste en buscar el elemento más pequeño de la lista y colocarlo en la primera posición, luego buscar el segundo elemento más pequeño y colocarlo en la segunda posición, y así sucesivamente hasta ordenar toda la lista.

### Identificar las entradas

Las entradas son los datos que necesitamos para resolver el problema. En este caso, necesitamos la lista de productos.

### Identificar las salidas

Las salidas son los resultados que esperamos obtener al resolver el problema. En este caso, necesitamos la lista de productos ordenada por precio.

### Identificar el proceso

Utilizaremos la variable products ya definida y le asignaremos la lista de productos ordenada por precio. Utiliza el algoritmo de ordenamiento por selección para ayudarte a ordenar la lista de productos.

### Diseñar el algoritmo

Plantearemos el algoritmo usando un diagrama de flujo.


### Codificar el algoritmo

```js
    const products = [
        {   
            id: 1,
            name: 'Camisa unicornio',
            price: 30000,
            description: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Cupiditate, asperiores?',
            category: 'clothes',
            img: 'https://arepa.s3.amazonaws.com/camisa_unicornio.png',
        },
        {
            id: 2,
            name: 'Pantalon Hombre',
            price: 40000,
            category: 'clothes',
            description: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Cupiditate, asperiores?',
            img: 'https://arepa.s3.amazonaws.com/pantalon_hombre.png',
        },     
        {
            id: 3,
            name: 'Pantalon dama',
            price: 50000,
            category: 'clothes',
            description: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Cupiditate, asperiores?',
            img: 'https://arepa.s3.amazonaws.com/pantalon_dama.png',
        },
        {
            id: 4,
            name: 'Camisa de dama',
            price: 31000,
            category: 'clothes',
            description: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Cupiditate, asperiores?',
            img: 'https://arepa.s3.amazonaws.com/camisa_dama.png',
        },
    ]

    const selectionSort = (list, prop) => {
        for (let i = 0; i < list.length - 1; i++) {
            let min = i;
            for (let j = i + 1; j < list.length; j++) {
                if (list[j][prop] < list[min][prop]) {
                    min = j;
                }
            }
            if (i !== min) {
                [list[i], list[min]] = [list[min], list[i]];
            }
        }
        return list;
    }

    console.log(selectionSort(products, 'price'));
```

### Probar el algoritmo

Para probar el algoritmo, podemos ejecutar el código en la consola del navegador o en la consola de Node.js.

### Documentar el algoritmo

Para documentar el algoritmo, podemos agregar comentarios al código para explicar qué hace cada línea.

```js
    // Definimos la función selectionSort
    const selectionSort = (list, prop) => {
        // Recorremos la lista
        for (let i = 0; i < list.length - 1; i++) {
            // Definimos la variable min y le asignamos el valor de i
            let min = i;
            // Recorremos la lista
            for (let j = i + 1; j < list.length; j++) {
                // Comparamos si el elemento actual es menor que el elemento mínimo
                if (list[j][prop] < list[min][prop]) {
                    // Si es menor, asignamos el valor de j a min
                    min = j;
                }
            }
            // Comparamos si i es diferente de min
            if (i !== min) {
                // Si es diferente, intercambiamos los elementos
                [list[i], list[min]] = [list[min], list[i]];
            }
        }
        // Devolvemos la lista ordenada
        return list;
    }

    // Mostramos el resultado por consola
    console.log(selectionSort(products, 'price'));
```

Esta función recibe dos parámetros: la lista de productos y la propiedad por la cual se va a ordenar. En este caso, la propiedad es price. El criterio de ordenamiento es de menor a mayor. En el caso de que sea de mayor a menor, solo debemos cambiar el signo de menor a mayor en la línea 7.

### Mejorar el algoritmo

En lugar de usar un loop como el ciclo for, podríamos usar los métodos iteradores de los array como vimos anteriormente. Además, podemos optimizar el algoritmo para que sea más eficiente al indicarle el criterio de ordenamiento de manera dinámica.

```js
    const products = [
        {   
            id: 1,
            name: 'Camisa unicornio',
            price: 30000,
            description: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Cupiditate, asperiores?',
            category: 'clothes',
            img: 'https://arepa.s3.amazonaws.com/camisa_unicornio.png',
        },
        {
            id: 2,
            name: 'Pantalon Hombre',
            price: 40000,
            category: 'clothes',
            description: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Cupiditate, asperiores?',
            img: 'https://arepa.s3.amazonaws.com/pantalon_hombre.png',
        },     
        {
            id: 3,
            name: 'Pantalon dama',
            price: 50000,
            category: 'clothes',
            description: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Cupiditate, asperiores?',
            img: 'https://arepa.s3.amazonaws.com/pantalon_dama.png',
        },
        {
            id: 4,
            name: 'Camisa de dama',
            price: 31000,
            category: 'clothes',
            description: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Cupiditate, asperiores?',
            img: 'https://arepa.s3.amazonaws.com/camisa_dama.png',
        },
    ]

    const selectionSort = (list, prop, order) => {
       // usaremos el método sort de los arrays

        list.sort((a, b) => {
            if (order === 'asc') {
                return a[prop] - b[prop];
            }
            if (order === 'desc') {
                return b[prop] - a[prop];
            }
        });
        return list;
    }

    console.log(selectionSort(products, 'price', 'asc'));
```

Vamos a explicar qué hace el método sort. Este método recibe como parámetro una función de comparación. Esta función recibe dos parámetros que representan dos elementos de la lista. La función de comparación devuelve un número negativo si el primer elemento es menor que el segundo, un número positivo si el primer elemento es mayor que el segundo, y cero si ambos elementos son iguales.

En este caso, la función de comparación recibe dos parámetros a y b. Si el orden es ascendente, la función devuelve la resta de `a[prop] - b[prop]`. Si el orden es descendente, la función devuelve la resta de `b[prop] - a[prop]`.








