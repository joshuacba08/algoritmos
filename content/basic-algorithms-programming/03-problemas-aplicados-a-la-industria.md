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

## Ordenar una lista de productos por precio

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

## Retornar el producto más caro

### Definir el problema

El problema consiste en retornar el producto más caro de una lista de productos.

### Analizar el problema

Para resolver el problema, debemos conocer el algoritmo de ordenamiento por selección. Este algoritmo consiste en buscar el elemento más pequeño de la lista y colocarlo en la primera posición, luego buscar el segundo elemento más pequeño y colocarlo en la segunda posición, y así sucesivamente hasta ordenar toda la lista.

### Identificar las entradas

Las entradas son los datos que necesitamos para resolver el problema. En este caso, necesitamos la lista de productos.

### Identificar las salidas

Las salidas son los resultados que esperamos obtener al resolver el problema. En este caso, necesitamos el producto más caro.

### Identificar el proceso

Utilizaremos la variable products ya definida y le asignaremos el producto más caro. Utiliza el algoritmo de ordenamiento por selección para ayudarte a ordenar la lista de productos.

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

    const mostExpensive = (list, prop) => {
        const listOrdered = selectionSort(list, prop);
        return listOrdered[listOrdered.length - 1];
    }

    console.log(mostExpensive(products, 'price'));
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

    // Definimos la función mostExpensive
    const mostExpensive = (list, prop) => {
        // Definimos la variable listOrdered y le asignamos el valor de la lista ordenada
        const listOrdered = selectionSort(list, prop);
        // Devolvemos el último elemento de la lista ordenada
        return listOrdered[listOrdered.length - 1];
    }

    // Mostramos el resultado por consola
    console.log(mostExpensive(products, 'price'));
```

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

    const mostExpensive = (list, prop, order) => {
        const listOrdered = selectionSort(list, prop, order);
        return listOrdered[listOrdered.length - 1];
    }

    console.log(mostExpensive(products, 'price', 'asc'));

```


## Filtrar los productos de un array de acuerdo a un rango determinado de precios

### Definir el problema

El problema consiste en filtrar los productos de un array de acuerdo a un rango determinado de precios. 

### Analizar el problema

Para resolver el problema, debemos conocer el algoritmo de ordenamiento por selección. Este algoritmo consiste en buscar el elemento más pequeño de la lista y colocarlo en la primera posición, luego buscar el segundo elemento más pequeño y colocarlo en la segunda posición, y así sucesivamente hasta ordenar toda la lista.

### Identificar las entradas

Las entradas son los datos que necesitamos para resolver el problema. En este caso, necesitamos la lista de productos y el rango de precios.

### Identificar las salidas

Las salidas son los resultados que esperamos obtener al resolver el problema. En este caso, necesitamos la lista de productos filtrada por el rango de precios.

### Identificar el proceso

Utilizaremos la variable products ya definida y le asignaremos la lista de productos filtrada por el rango de precios. Utiliza el algoritmo de ordenamiento por selección para ayudarte a ordenar la lista de productos.

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

    const filterByPrice = (list, prop, min, max) => {
        const listOrdered = selectionSort(list, prop);
        const listFiltered = listOrdered.filter(item => item[prop] >= min && item[prop] <= max);
        return listFiltered;
    }

    console.log(filterByPrice(products, 'price', 40000, 50000));

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

    // Definimos la función filterByPrice
    const filterByPrice = (list, prop, min, max) => {
        // Definimos la variable listOrdered y le asignamos el valor de la lista ordenada
        const listOrdered = selectionSort(list, prop);
        // Definimos la variable listFiltered y le asignamos el valor de la lista filtrada
        const listFiltered = listOrdered.filter(item => item[prop] >= min && item[prop] <= max);
        // Devolvemos la lista filtrada
        return listFiltered;
    }

    // Mostramos el resultado por consola
    console.log(filterByPrice(products, 'price', 40000, 50000));
```

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

    // Definimos la función filterByPrice
    const filterByPrice = (list, prop, min, max, order) => {
        const listOrdered = selectionSort(list, prop, order);
        // Definimos la variable listFiltered y le asignamos el valor de la lista filtrada
        const listFiltered = listOrdered.filter(item => item[prop] >= min && item[prop] <= max);
        return listFiltered;
    }

    console.log(filterByPrice(products, 'price', 40000, 50000, 'asc'));

```

Recuerda que el método filter devuelve un nuevo array con los elementos que cumplan la condición. En este caso, la condición es que el precio del producto sea mayor o igual que el precio mínimo y menor o igual que el precio máximo.

## Encontrar un producto de acuerdo al valor de una de sus propiedades

### Definir el problema

El problema consiste en encontrar un producto de acuerdo al valor de una de sus propiedades.

### Analizar el problema

Para resolver el problema, vamos a aplicar directamente el método find de los arrays.

### Identificar las entradas

Las entradas son los datos que necesitamos para resolver el problema. En este caso, necesitamos la lista de productos y el valor de la propiedad.

### Identificar las salidas

Las salidas son los resultados que esperamos obtener al resolver el problema. En este caso, necesitamos el producto que cumpla la condición.

### Identificar el proceso

Utilizaremos la variable products ya definida y le asignaremos el producto que cumpla la condición. Utiliza el método find para ayudarte a encontrar el producto.

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

    const product = products.find(item => item.id === 3);

    console.log(product);
```

### Probar el algoritmo

Para probar el algoritmo, podemos ejecutar el código en la consola del navegador o en la consola de Node.js.

### Documentar el algoritmo

Para documentar el algoritmo, podemos agregar comentarios al código para explicar qué hace cada línea.

```js
    // Definimos la variable product y le asignamos el valor del producto que cumpla la condición
    const product = products.find(item => item.id === 3);

    // Mostramos el resultado por consola
    console.log(product);
```

Recuerda que el método find devuelve el primer elemento que cumpla la condición. En este caso, la condición es que el id del producto sea igual a 3.

### Mejorar el algoritmo

Vamos a crear una función que devuelva el elemento que contenga la propiedad deseada. Además podremos reutilizarlo para distintas propiedades.

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

    const findProduct = (list, prop, value) => {
        return list.find(item => item[prop] === value);
    }

    console.log(findProduct(products, 'id', 3));
```

Como se puede observar, la función recibe tres parámetros: la lista de productos, la propiedad y el valor de la propiedad. En este caso, la propiedad es id y el valor es 3.


## Obtener el total del precio de todos los productos en el array

### Definir el problema

El problema consiste en obtener el total del precio de todos los productos en el array.

### Analizar el problema

Para resolver el problema, vamos a aplicar directamente el método reduce de los arrays.

### Identificar las entradas

Las entradas son los datos que necesitamos para resolver el problema. En este caso, necesitamos la lista de productos.

### Identificar las salidas

Las salidas son los resultados que esperamos obtener al resolver el problema. En este caso, necesitamos el total del precio de todos los productos.

### Identificar el proceso

Utilizaremos la variable products ya definida y le asignaremos el total del precio de todos los productos. Utiliza el método reduce para ayudarte a obtener el total.

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
        },
        {
            id: 2,
            name: 'Pantalon Hombre',
            price: 40000,
            category: 'clothes',
        },   
        {
            id: 3,
            name: 'Pantalon dama',
            price: 50000,
            category: 'clothes',
        },
        {
            id: 4,
            name: 'Camisa de dama',
            price: 31000,
            category: 'clothes',
        },
    ]

    const totalPrice = products.reduce((total, item) => total + item.price, 0);

    console.log(totalPrice);
```

### Probar el algoritmo

Para probar el algoritmo, podemos ejecutar el código en la consola del navegador o en la consola de Node.js.

### Documentar el algoritmo

Para documentar el algoritmo, podemos agregar comentarios al código para explicar qué hace cada línea.

```js
    // Definimos la variable totalPrice y le asignamos el valor del total del precio de todos los productos
    const totalPrice = products.reduce((total, item) => total + item.price, 0);

    // Mostramos el resultado por consola
    console.log(totalPrice);
```

Recuerda que el método reduce recibe dos parámetros: una función de reducción y el valor inicial. En este caso, la función de reducción recibe dos parámetros: el total y el elemento actual. El valor inicial es 0.

### Mejorar el algoritmo

Vamos a crear una función que devuelva el total de una propiedad de todos los elementos de un array. Además podremos reutilizarlo para distintas propiedades.

```js
    const products = [
        {   
            id: 1,
            name: 'Camisa unicornio',
            price: 30000,
            description: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Cupiditate, asperiores?',
            category: 'clothes',
        },
        {
            id: 2,
            name: 'Pantalon Hombre',
            price: 40000,
            category: 'clothes',
        },   
        {
            id: 3,
            name: 'Pantalon dama',
            price: 50000,
            category: 'clothes',
        },
        {
            id: 4,
            name: 'Camisa de dama',
            price: 31000,
            category: 'clothes',
        },
    ]

    const getTotal = (list, prop) => {
        return list.reduce((total, item) => total + item[prop], 0);
    }

    console.log(getTotal(products, 'price'));
```

Como se puede observar, la función recibe dos parámetros: la lista de productos y la propiedad. En este caso, la propiedad es price.


## Eliminar un producto por id

### Definir el problema

El problema consiste en eliminar un producto por id.

### Analizar el problema

Para resolver el problema, vamos a aplicar directamente el método filter de los arrays.

### Identificar las entradas

Las entradas son los datos que necesitamos para resolver el problema. En este caso, necesitamos la lista de productos y el id del producto.

### Identificar las salidas

Las salidas son los resultados que esperamos obtener al resolver el problema. En este caso, necesitamos la lista de productos sin el producto eliminado.

### Identificar el proceso

Utilizaremos la variable products ya definida y le asignaremos la lista de productos sin el producto eliminado. Utiliza el método filter para ayudarte a eliminar el producto.

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
        },
        {
            id: 2,
            name: 'Pantalon Hombre',
            price: 40000,
            category: 'clothes',
        },   
        {
            id: 3,
            name: 'Pantalon dama',
            price: 50000,
            category: 'clothes',
        },
        {
            id: 4,
            name: 'Camisa de dama',
            price: 31000,
            category: 'clothes',
        },
    ]

    const deleteProduct = (list, id) => {
        return list.filter(item => item.id !== id);
    }

    console.log(deleteProduct(products, 3));
```

### Probar el algoritmo 

Para probar el algoritmo, podemos ejecutar el código en la consola del navegador o en la consola de Node.js.

### Documentar el algoritmo

Para documentar el algoritmo, podemos agregar comentarios al código para explicar qué hace cada línea.

```js
    // Definimos la función deleteProduct
    const deleteProduct = (list, id) => {
        // Definimos la variable listFiltered y le asignamos el valor de la lista filtrada
        const listFiltered = list.filter(item => item.id !== id);
        // Devolvemos la lista filtrada
        return listFiltered;
    }

    // Mostramos el resultado por consola
    console.log(deleteProduct(products, 3));
```

Recuerda que el método filter devuelve un nuevo array con los elementos que cumplan la condición. En este caso, la condición es que el id del producto sea diferente del id que pasamos como parámetro. Es decir, que el producto no sea el que queremos eliminar, por lo tanto excluimos el producto que queremos eliminar.

### Mejorar el algoritmo

Vamos a crear una función que elimine un elemento de un array de acuerdo a una propiedad y su valor. Además podremos reutilizarlo para distintas propiedades.

```js
    const products = [
        {   
            id: 1,
            name: 'Camisa unicornio',
            price: 30000,
            description: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Cupiditate, asperiores?',
            category: 'clothes',
        },
        {
            id: 2,
            name: 'Pantalon Hombre',
            price: 40000,
            category: 'clothes',
        },   
        {
            id: 3,
            name: 'Pantalon dama',
            price: 50000,
            category: 'clothes',
        },
        {
            id: 4,
            name: 'Camisa de dama',
            price: 31000,
            category: 'clothes',
        },
    ]

    const deleteProduct = (list, prop, value) => {
        return list.filter(item => item[prop] !== value);
    }

    console.log(deleteProduct(products, 'id', 3));
```

Como se puede observar, la función recibe tres parámetros: la lista de productos, la propiedad y el valor de la propiedad. En este caso, la propiedad es id y el valor es 3.


## Conclusiones de la unidad

En esta unidad aprendimos a resolver problemas usando los métodos de los arrays. Aprendimos a ordenar, filtrar, encontrar, obtener el total y eliminar elementos de un array. Además aprendimos a crear funciones que nos ayuden a reutilizar el código.






