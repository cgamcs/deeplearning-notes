## Matrix Dimensions ($M \times N$)

La forma estándar de describir el tamaño de una `[[Matrix]]` es con las letras **M** y **N**:

- **M**: Identifica el número de `[[Rows]]` (filas).
- **N**: Identifica el número de `[[Columns]]` (columnas).

![[0005-IMG.png]]

> [!TIP] Mnemonic: "MR. Nice guy"
> 
> Una forma fácil de recordar el orden:
> 
> - **M** $\rightarrow$ **R**ows.
>     
> - **N** $\rightarrow$ (Next / Columns).
>     
> - Siempre es **Rows** $\times$ **Columns**.
>     

## Rules for Validity

Para realizar una [[Matrix Multiplication]] válida, debemos cumplir reglas estrictas sobre las dimensiones.

1. Inner Dimensions Match:

El número de columns de la primera matriz debe ser idéntico al número de rows de la segunda matriz.

2. Resulting Dimensions:

El [[Output]] resultante tendrá las dimensiones externas ($M$ de la primera por $N$ de la segunda).

$$(M \times \mathbf{N}) \cdot (\mathbf{N} \times K) \rightarrow (M \times K)$$

![[0006-IMG.png]]

![[0007-IMG.png]]

### Examples of Validity

|**Matriz 1 (A)**|**Matriz 2 (B)**|**Valid?**|**Resulting Shape**|
|---|---|---|---|
|$5 \times 2$|$2 \times 7$|**Yes**|$5 \times 7$|
|$2 \times 7$|$5 \times 2$|**No**|N/A (Mismatch $7 \neq 5$)|
|$5 \times 7$|$5 \times 2$|**No**|N/A (Mismatch $7 \neq 5$)|

> **Note:** Si dos matrices no son compatibles, a menudo podemos aplicar [[Vector and matrix transpose|Transpose]] a una de ellas para alinear las dimensiones y hacer la multiplicación posible (algo muy común en **Deep Learning**).

## How Matrix Multiplication Works

La operación no es elemento a elemento. En realidad, es una serie de [[05-Dot product|Dot Products]]:

Se multiplica cada row de la primera matriz por cada column de la segunda matriz.

![[0008-IMG.png]]

![[0009-IMG.png]]

### Code Implementation

En Python (tanto `numpy` como `pytorch`), el operador estándar para la multiplicación matricial es `@`.

Python

```
# import libraries
import numpy as np
import torch

#------------
# Using numpy
#------------

# create some random matrices
A = np.random.randn(3,4)  # 3 rows, 4 cols
B = np.random.randn(4,5)  # 4 rows, 5 cols
C = np.random.randn(3,7)  # 3 rows, 7 cols

# try some multiplications...
# Valid: (3x4) @ (4x5) -> (3x5)
print(np.round( A@B , 2)), print(' ')

# Invalid: (3x4) @ (3x7) -> Inner dims 4 != 3
# print(np.round( A@C , 2)), print(' ')

# Invalid: (4x5) @ (3x7) -> Inner dims 5 != 3
# print(np.round( B@C , 2)), print(' ')

# Valid with Transpose: C.T is (7x3). So (7x3) @ (3x4) -> (7x4)
print(np.round( C.T@A , 2))

#--------------
# Using PyTorch
#--------------

# create some random matrices
A  = torch.randn(3,4)
B  = torch.randn(4,5)
C1 = np.random.randn(4,7) # Numpy array
C2 = torch.tensor( C1, dtype=torch.float ) # Converted to Tensor

# try some multiplications...
# Valid mixed types (Torch @ Numpy works in recent versions, but usually requires Tensor @ Tensor)
print(np.round( A@C2 , 2))
```