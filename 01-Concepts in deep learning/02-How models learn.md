## The Learning Process

¿Cómo ajusta el modelo sus [[Parameters]]? Usando la analogía de la preparación de un sándwich:

**The Formula (Hypothesis):**

$$\hat{y} = x_0 w_0 + x_1 w_1 + x_2 w_2$$

- $\hat{y}$: El sándwich final ([[Output]]).
- $x_1, x_2$: Ingredientes ([[Inputs]] - Peanut butter, Jelly).
- $w_1, w_2$: Proporciones ([[Weights]] to adjust).

### Training Cycle

![[0003-IMG.png]]

1. **[[Forward Propagation]] (Prediction):**
    - El modelo toma los [[Inputs]] ($x$), los multiplica por los [[Weights|initial weights]] ($w$) y genera un resultado.
    - _Analogy:_ Preparar el sándwich con las proporciones actuales.
  
2. **[[Loss Function|Loss Calculation]] (Error):**
    - Se compara la [[Prediction]] ($\hat{y}$) con el valor real ([[Ground Truth]] $y$).        
    - _Analogy:_ El cliente prueba el sándwich y da **feedback** (muy dulce, muy seco).

3. **[[Backpropagation]] (Adjustment):**
    - Se utiliza el valor del [[Loss Function|Loss]] para ajustar los [[Weights]] ($w$) en dirección opuesta al error.
    - Aquí es donde entra el [[Gradient Descent]]: el algoritmo matemático para decidir si subir o bajar la cantidad de "jalea" ($w_2$).