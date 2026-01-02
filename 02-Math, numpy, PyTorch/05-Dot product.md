El **Dot Product** es una operación fundamental que reduce dos secuencias de números a un único **Scalar value**, reflejando la **similarity** (similitud) entre ellas.

### Mathematical Definition

Es la **summation** de los productos **element-wise** (elemento a elemento) de dos estructuras.

> **Requirement:** Los [[02-Terms and datatypes in math and computers|Vectors]] deben tener la misma **length**.

$$\alpha = \mathbf{a} \cdot \mathbf{b} = \langle \mathbf{a}, \mathbf{b} \rangle = \mathbf{a}^T \mathbf{b} = \sum_{i=1}^{n} a_i b_i$$

### Example 1: Vectors

|**Index**|**V**|**W**|**Calculation (vi​⋅wi​)**|
|---|---|---|---|
|1|1|2|$1*2 = 2$|
|2|0|8|$0*8 = 0$|
|3|2|-6|$2*-6 = -12$|
|4|5|1|$5*1 = 5$|
|5|-1|0|$-1*0 = 0$|

$$\mathbf{V}^T \mathbf{W} = 2 + 0 - 12 + 5 + 0 = \mathbf{-5}$$

### Example 2: Matrices (Flattened view)

Si tratamos las **Matrices** como una colección plana de números, podemos calcular su **Dot Product** para medir similitud.

**Matrix M1** vs **Matrix M2**

$$\begin{bmatrix} 0 & 3 & 2 \\ -3 & -3 & 1 \\ 1 & 0 & 2 \end{bmatrix} \cdot \begin{bmatrix} 1 & 0 & 6 \\ 2 & -1 & 0 \\ 5 & 1 & 4 \end{bmatrix}$$

**Calculation:**

$$(0\cdot1) + (3\cdot0) + (2\cdot6) + (-3\cdot2) + (-3\cdot-1) + (1\cdot0) + (1\cdot5) + (0\cdot1) + (2\cdot4)$$

$$= 0 + 0 + 12 - 6 + 3 + 0 + 5 + 0 + 8$$

$$= \mathbf{22}$$

> **Interpretation:** El resultado es un valor único (**Scalar**) que indica qué tan similares son los dos objetos (**Vectors**, **Matrices**, Images, etc.).