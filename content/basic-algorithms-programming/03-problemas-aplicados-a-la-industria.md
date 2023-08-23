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

### 




