La operación de **Transpose** ($^T$) consiste fundamentalmente en intercambiar **rows** (filas) por **columns** (columnas).

Si tenemos un **row vector** y le aplicamos **transpose**, este se convierte en un **column vector** (y viceversa), preservando el orden de los elementos.

$$\begin{bmatrix} 1 \\ 0 \\ 2 \\ 5 \\ -2 \end{bmatrix}^T = \ \begin{bmatrix} 1 & 0 & 2 & 5 & -2 \end{bmatrix}$$

Para las **Matrices**, la lógica se mantiene: las **columns** de la matriz original se convierten en las **rows** de la matriz transpuesta. Visualmente, es como rotar los datos sobre su diagonal principal.

$$\begin{bmatrix} 1 & 5 \\ 0 & 6 \\ 2 & 8 \\ 5 & 3 \\ -2 & 0 \end{bmatrix}^T = \ \begin{bmatrix} 1 & 0 & 2 & 5 & -2 \\ 5 & 6 & 8 & 3 & 0 \end{bmatrix}$$

### Code Implementation

En librerías como `numpy` y `pytorch`, esta es una operación muy común para ajustar las **dimensions** de los datos antes de operar con ellos.

Python

```
# import libraries
import numpy as np
import torch

#------
# numpy
#------

# create a vector (2D array in numpy concept)
nv = np.array([ [1,2,3,4] ])
print(nv), print(' ')

# transpose it
print(nv.T), print(' ')

# transpose the transpose! (returns to original state)
nvT = nv.T
print(nvT.T)

#------
# torch
#------

# repeat for a matrix
tM = torch.tensor([ [1,2,3,4],[5,6,7,8] ])
print(tM), print(' ')

# transpose it
print(tM.T), print(' ')

# transpose the transpose!
tMT = tM.T
print(tMT.T)
```