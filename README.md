# Tensor++

## Autor

Creado por: Maxwell Lupo Gregorio Collazos Solis

Implementación de una librería de tensores en C++ que soporta hasta 3 dimensiones.

## Descripción

Clase `Tensor` para manejar datos multidimensionales y realizar operaciones matemáticas básicas, incluyendo una simulación de red neuronal.

## Funcionalidades

### Creación de tensores

* `Tensor::zero(shape)`: Crea un tensor lleno de ceros.
* `Tensor::ones(shape)`: Crea un tensor lleno de unos.
* `Tensor::random(shape, min, max)`: Genera valores aleatorios en el rango [min, max).
* `Tensor::arange(start, end)`: Genera valores secuenciales desde start hasta end (no inclusivo).

### Operaciones

* `A + B`: Suma elemento a elemento (con soporte básico de broadcasting).
* `A - B`: Resta elemento a elemento.
* `A * B`: Multiplicación elemento a elemento.
* `A * escalar`: Multiplica cada elemento por un número.

### Transformaciones

* `apply(ReLU)`: Reemplaza valores negativos por 0.
* `apply(Sigmoid)`: Aplica la función sigmoide a cada elemento.

### Manipulación de dimensiones

* `view(new_shape)`: Cambia la forma del tensor manteniendo los mismos datos.
* `unsqueeze(dim)`: Agrega una dimensión de tamaño 1 en la posición indicada.

### Otras funciones

* `concat(tensors, axis)`: Une varios tensores en un eje específico.
* `dot(a, b)`: Calcula el producto punto entre tensores compatibles.
* `matmul(a, b)`: Realiza multiplicación matricial entre tensores 2D.

## Gestión de memoria

Incluye:

* Constructor de copia
* Constructor de movimiento
* Operadores de asignación
* Destructor

## Red neuronal

El programa implementa el siguiente flujo:

1. Entrada: 1000 x 20 x 20
2. view → 1000 x 400
3. matmul → 1000 x 100
4. suma bias → 1000 x 100
5. ReLU
6. matmul → 1000 x 10
7. suma bias → 1000 x 10
8. Sigmoid

## Compilación

```bash
g++ main.cpp -o main
```

## Ejecución

```bash
./main
```

## Archivos

* `main.cpp`
* `Tensor.h`
