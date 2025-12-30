### Hierarchy of Mathematical Objects

|**Object (Visual)**|**Concept**|**Rank**|**Technical Description**|
|---|---|---|---|
|$$7$$|**Scalar**|0D|Magnitud única (**Single magnitude**). En código suele ser un `int` o `float`.|
|$$\begin{bmatrix} -1 \\ 0 \\ 1 \end{bmatrix}$$|**Vector**|1D|**1D Array** (row o column). Representa **direction** y **magnitude**.|
|$$\begin{bmatrix} -1 & 0 & 2 \\ 0 & 1 & 4 \\ 1 & 4 & 9 \end{bmatrix}$$|**Matrix**|2D|**2D Array** o Grid (rows $\times$ columns). Generalmente representa **datasets** o **weights**.|
|$$\mathbf{X}_{ijk...}$$|**Tensor**|n-D|**Mathematical generalization** para estructuras de más de 2 dimensiones.|

> [!NOTE] Containment Relationship
> 
> En **Deep Learning frameworks** (como PyTorch o TensorFlow), técnicamente todo es un **Tensor**:
> 
> - **Scalar:** Rank-0 Tensor.
>     
> - **Vector:** Rank-1 Tensor.
>     
> - **Matrix:** Rank-2 Tensor.
>     
> - **n-D Tensor:** Tensor of Rank $n$ ($n > 2$).
>     

### The Ambiguity of "Data Type"

Dependiendo del contexto, **Data Type** significa cosas distintas:

**A. In Computer Science**

- **Focus:** Estructura de **Storage** (memory & bits).
- **Implications:** Define el espacio en memoria y las **allowed operations**.
- **Examples:** `floating-point`, `boolean`, `string`.

**B. In Statistics**

- **Focus:** Categoría **conceptual** de la información.
- **Implications:** Determina los **statistical procedures** y pruebas válidas.
- **Examples:** **Categorical**, **Numerical**, **Ordinal**, **Ratio**.