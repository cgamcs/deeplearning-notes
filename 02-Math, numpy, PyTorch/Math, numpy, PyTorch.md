## 1. Teorías Espectrales y la Simplicidad del Deep Learning

El concepto central de las **teorías espectrales** en matemáticas es la descomposición: tomar un sistema complicado y dividirlo en múltiples partes simples y comprensibles.

Los modelos de Deep Learning siguen este principio. Aunque visualmente parecen redes complejas, podemos descomponerlos en unidades fundamentales.

![[0002-IMG.png]]

Cada nodo o círculo en la gráfica anterior esconde una operación simple y repetitiva, generalmente una ecuación lineal seguida de una activación no lineal:

$$\hat{y} = \sigma(x_1 w_1 + x_2 w_2)$$

![[0004-IMG.png]]

> **Conclusión:** Deep Learning es complicado por la cantidad de operaciones simultáneas, pero matemáticamente se reduce a una colección masiva de operaciones aritméticas muy simples.

### Diferencia entre Complicado y Complejo

Podemos clasificar los sistemas según su arquitectura y comportamiento:

|**Característica**|**Complicado (Complicated)**|**Complejo (Complex)**|
|---|---|---|
|**Componentes**|Gran cantidad de partes.|Pocos o múltiples componentes.|
|**Matemática**|Lineal o con pocas no linealidades.|**Alta no linealidad** (Múltiples).|
|**Interpretación**|Intuitivo y comprensible.|Contraintuitivo, difícil de interpretar.|

**El Deep Learning es híbrido:**

1. **Simple:** Construido sobre matemática básica (sumas y multiplicaciones).
2. **Complicado:** Posee una enorme cantidad de partes (parámetros).
3. **Complejo:** La infinidad de no linealidades lo hace difícil de interpretar/entender intuitivamente.

## 2. Términos y Tipos de Datos (Matemáticas vs. Computación)

### Jerarquía de Objetos Matemáticos

| **Objeto (Visual)**                                                    | **Concepto** | **Rango (Rank)** | **Descripción Técnica**                                                                            |
| ---------------------------------------------------------------------- | ------------ | ---------------- | -------------------------------------------------------------------------------------------------- |
| $$7$$                                                                  | **Scalar**   | 0D               | Magnitud única. (`int` o `float`).                                                                 |
| $$\begin{bmatrix} -1 \\ 0 \\ 1 \end{bmatrix}$$                         | **Vector**   | 1D               | Arreglo unidimensional (fila o columna). Representa dirección y magnitud.                          |
| $$\begin{bmatrix} -1 & 0 & 2 \\ 0 & 1 & 4 \\ 1 & 4 & 9 \end{bmatrix}$$ | **Matrix**   | 2D               | Hoja de cálculo bidimensional (filas $\times$ columnas). Generalmente representa datasets o pesos. |
| $$\mathbf{X}_{ijk...}$$                                                | **Tensor**   | n-D              | Generalización matemática ($>2$ dimensiones).                                                      |

> [!NOTE] Relación de Contención
> 
> En frameworks como PyTorch o TensorFlow, todo es un tensor:
> 
> - **Escalar:** Tensor de rango 0.
>     
> - **Vector:** Tensor de rango 1.
>     
> - **Matriz:** Tensor de rango 2.
>     
> - **Tensor-nD:** Tensor de rango $n$ ($n > 2$).
>     

### La Ambigüedad del término "Tipo de Dato"

Dependiendo del contexto, "tipo de dato" significa cosas distintas:

**A. En Ciencias de la Computación**
- **Enfoque:** Estructura de **almacenamiento** (memoria y bits).
- **Implicaciones:** Define el espacio en disco y las operaciones permitidas.
- **Ejemplos:** `floating-point`, `boolean`, `string`.

**B. En Estadística**
- **Enfoque:** Categoría **conceptual** de la información.
- **Implicaciones:** Determina los procedimientos y pruebas analíticas válidas.
- **Ejemplos:** Categóricos, numéricos, ordinales, de razón (ratio).

## 3. Tipos de Realidad y su Representación

### Clasificación de la Realidad

1. **Realidad Continua:** Representación numérica con valores infinitos o muy granulares.
    - _Ejemplos:_ Altura, ingresos, puntaje de examen.

2. **Realidad Categórica:** Representación discreta con valores limitados y distintos.
    - _Ejemplos:_ Perro/Gato, Montaña/Mar, Vivo/Muerto.
### Codificación para Computadora (Encoding)

Para que una red neuronal entienda datos categóricos, debemos transformarlos numéricamente:

**1. Dummy-coding**

- Usa **0 o 1** (Falso/Verdadero).
- Crea un solo vector.
- _Uso:_ Estados binarios (Pasó/Falló, Fraude Si/No).

**2. One-hot encoding**

- Asigna un **0 o 1** por cada posible categoría.
- Crea una **matriz** dispersa (muchos ceros, pocos unos).
- _Uso:_ Clasificación multiclase (Reconocimiento de dígitos, géneros de películas).

**Ejemplo: Clasificación de Géneros**

| **Película** | **Historia (y1​)** | **Ciencia Ficción (y2​)** | **Niños (y3​)** |
| ------------ | ------------------ | ------------------------- | --------------- |
| **A**        | 0                  | 1                         | 0               |
| **B**        | 0                  | 0                         | 1               |
| **C**        | 1                  | 0                         | 0               |

## 4. Producto Escalar (Dot Product)

El producto escalar es una operación fundamental que reduce dos secuencias de números a un único valor escalar, reflejando la **similitud** entre ellas.

Definición Matemática

Sumatoria de los productos elemento a elemento correspondientes.

> **Requisito:** Los vectores deben tener la misma longitud.

$$\alpha = a \cdot b = \langle a, b \rangle = a^T b = \sum_{i=1}^{n} a_i b_i$$

### Ejemplo 1: Vectores

|**Elemento**|**V**|**W**|**Cálculo Parcial (vi​∗wi​)**|
|---|---|---|---|
|1|1|2|$1*2 = 2$|
|2|0|8|$0*8 = 0$|
|3|2|-6|$2*-6 = -12$|
|4|5|1|$5*1 = 5$|
|5|-1|0|$-1*0 = 0$|

$$V^T W = 2 + 0 - 12 + 5 + 0 = \mathbf{-5}$$

### Ejemplo 2: Matrices

Si tratamos las matrices como una colección plana de números, podemos calcular su producto escalar para medir similitud.

**Matriz M1** vs **Matriz M2**

$$\begin{bmatrix} 0 & 3 & 2 \\ -3 & -3 & 1 \\ 1 & 0 & 2 \end{bmatrix} \cdot \begin{bmatrix} 1 & 0 & 6 \\ 2 & -1 & 0 \\ 5 & 1 & 4 \end{bmatrix}$$

**Cálculo:**

$$(0\cdot1) + (3\cdot0) + (2\cdot6) + (-3\cdot2) + (-3\cdot-1) + (1\cdot0) + (1\cdot5) + (0\cdot1) + (2\cdot4)$$

$$= 0 + 0 + 12 - 6 + 3 + 0 + 5 + 0 + 8$$

$$= \mathbf{22}$$

> **Interpretación:** El resultado es un valor único que indica qué tan similares son los dos objetos (vectores, matrices, imágenes, etc.).

### Multiplicación de Matriz

