# Métodos de ordenamiento y búsqueda

## Introducción

En este documento se explica cómo implementar los métodos de ordenamiento y búsqueda. En un eComerce, es muy común que se implementen estos métodos para ordenar y buscar productos. Por ejemplo, se puede implementar un método de ordenamiento para ordenar los productos por precio. Además, se puede implementar un método de búsqueda para buscar un producto por nombre.

Es muy probable que hayas usado estos algorítmos en tu vida diaria. Por ejemplo, cuando buscas un producto en Mercado Libre, el sistema te muestra los productos que coinciden con tu búsqueda. Además, te permite ordenar los productos por precio, por relevancia, etc.

El objetivo es que el estudiante aprenda a implementar los métodos de ordenamiento y búsqueda usando lo visto hasta ahora sobre arreglos. Para ello, se explica cómo implementar los métodos de ordenamiento y búsqueda usando un ejemplo.

## Ejemplo práctico

Continuando con nuestro primer día de trabajo en una empresa de desarrollo de software. Nuestro jefe nos pide que desarrollemos un sistema para administrar los productos de la empresa. Para ello, nos pide que implementemos los métodos de ordenamiento y búsqueda.

Es decir, debemos crear funciones que retornen un arreglo de productos ordenados y que retornen un producto que coincida con la búsqueda. A continuación se muestra un ejemplo de cómo implementar los métodos de ordenamiento y búsqueda usando funciones flecha:

```javascript
    let productos = [
        {
            nombre: "Televisor",
            precio: 1000,
            descripcion: "Televisor Samsung 50 pulgadas"
        },
        {
            nombre: "Celular",
            precio: 500,
            descripcion: "Celular Samsung Galaxy S10"
        },
        {
            nombre: "Laptop",
            precio: 1500,
            descripcion: "Laptop Lenovo Thinkpad T480"
        }
    ];

    // Ordenar productos por precio
    const ordenarPorPrecio = () => {
        return productos.sort((a, b) => a.precio - b.precio);
    };

    // Buscar producto por nombre
    const buscarPorNombre = (nombre) => {
        return productos.find(producto => producto.nombre === nombre);
    };
```

Perfecto, hemos implementado los métodos de ordenamiento y búsqueda. Un ejercicio muy práctico sería intentar implementar los métodos de ordenamiento y búsqueda usando otros algoritmos. Por ejemplo, se puede implementar el método de ordenamiento por selección.


## Añadiendo un identificador a nuestro modelo de producto

En el ejemplo anterior, hemos modelado la entidad Producto a través de un objeto. Sin embargo, es muy probable que necesitemos añadir un identificador a nuestro modelo de producto. Por ejemplo, si queremos almacenar los productos en una base de datos, necesitamos añadir un identificador a nuestro modelo de producto. 

A este tipo de propiedad se le conoce como id por sus siglas en inglés. A continuación se muestra un ejemplo de cómo añadir un identificador a nuestro modelo de producto:

```javascript
    let productos = [
        {
            id: 1,
            nombre: "Televisor",
            precio: 1000,
            descripcion: "Televisor Samsung 50 pulgadas"
        },
        {
            id: 2,
            nombre: "Celular",
            precio: 500,
            descripcion: "Celular Samsung Galaxy S10"
        },
        {
            id: 3,
            nombre: "Laptop",
            precio: 1500,
            descripcion: "Laptop Lenovo Thinkpad T480"
        }
    ];
```

En este caso hemos añadido un identificador a nuestro modelo de producto. Este identificador es un número que se incrementa por cada producto que se añade al arreglo de productos. Por ejemplo, el primer producto tiene un identificador de 1, el segundo producto tiene un identificador de 2, etc.

Este tipo de identificador incremental es muy usado en las bases de datos relacionales. Por ejemplo, en una base de datos de MySQL, se puede crear una tabla de productos con un campo id que se autoincrementa por cada producto que se añade a la tabla.

## Método sort a detalle

El método `sort` ordena los elementos de un arreglo. Este método recibe por parámetro una función de comparación que se encarga de comparar los elementos del arreglo. A continuación se muestra un ejemplo de cómo ordenar los productos por precio usando el método `sort`:

```javascript
    let productos = [
        {
            id: 1,
            nombre: "Televisor",
            precio: 1000,
            descripcion: "Televisor Samsung 50 pulgadas"
        },
        {
            id: 2,
            nombre: "Celular",
            precio: 500,
            descripcion: "Celular Samsung Galaxy S10"
        },
        {
            id: 3,
            nombre: "Laptop",
            precio: 1500,
            descripcion: "Laptop Lenovo Thinkpad T480"
        }
    ];

    productos.sort((a, b) => a.precio - b.precio);
```

## Criterio de ordenamiento

El criterio de ordenamiento es la función de comparación que se encarga de comparar los elementos del arreglo. Esta función recibe por parámetro dos elementos del arreglo y retorna un número. A continuación se muestra un ejemplo de cómo implementar el criterio de ordenamiento para ordenar los productos por precio:

```javascript
    productos.sort((a, b) => a.precio - b.precio);
```

En el ejemplo anterior, la función de comparación recibe por parámetro dos productos y retorna la diferencia entre los precios de los productos. Si la diferencia es negativa, el primer producto es menor que el segundo producto. Si la diferencia es positiva, el primer producto es mayor que el segundo producto. Si la diferencia es cero, el primer producto es igual que el segundo producto.

Si queremos hacer que el orden se invierta de mayor a menor, debemos retornar la diferencia entre los precios de los productos multiplicada por -1. A continuación se muestra un ejemplo de cómo implementar el criterio de ordenamiento para ordenar los productos de mayor a menor:

```javascript
    productos.sort((a, b) => (a.precio - b.precio) * -1);
```

## Método find a detalle

El método `find` retorna el primer elemento del arreglo que cumpla con la condición de búsqueda. Este método recibe por parámetro una función de búsqueda que se encarga de buscar un elemento del arreglo. A continuación se muestra un ejemplo de cómo buscar un producto por su id con `find`:

```javascript
    let productos = [
        {
            id: 1,
            nombre: "Televisor",
            precio: 1000,
            descripcion: "Televisor Samsung 50 pulgadas"
        },
        {
            id: 2,
            nombre: "Celular",
            precio: 500,
            descripcion: "Celular Samsung Galaxy S10"
        },
        {
            id: 3,
            nombre: "Laptop",
            precio: 1500,
            descripcion: "Laptop Lenovo Thinkpad T480"
        }
    ];

    productos.find(producto => producto.id === 1);
```

Vamos a crear una función que busque un producto por su id. Esta función recibe por parámetro el id del producto y retorna el producto que coincida con el id. A continuación se muestra un ejemplo de cómo implementar la función que busca un producto por su id:

```javascript
    const buscarPorId = (id) => {
        return productos.find(producto => producto.id === id);
    };
```
De esta forma, el algoritmo de búsqueda por id queda encapsulado en una función. Esto nos permite reutilizar el algoritmo de búsqueda por id en cualquier parte del código.

Es recomendable usar funciones para encapsular algoritmos. De esta forma, el código es más fácil de leer y de mantener. Además, se evita la repetición de código.

## Conclusiones

- Los métodos de ordenamiento y búsqueda son muy utilizados en el desarrollo de software.
- Dominar los métodos de los arreglos es fundamental para trabajar con métodos de ordenamiento y búsqueda.
- Podemos estar seguros de que los métodos que vimos son los mismos que se usan en las grandes compañías de desarrollo de software.

