## El Proceso de Aprendizaje

¿Cómo ajusta el modelo sus parámetros? Usando la analogía de la preparación de un sándwich:

La Fórmula (Hipótesis):

$$\hat{y} = x_0 w_0 + x_1 w_1 + x_2 w_2$$

- $\hat{y}$: El sándwich final (Output).
- $x_1, x_2$: Ingredientes (Mantequilla de maní, Jalea).
- $w_1, w_2$: Proporciones (Pesos a ajustar).

### Ciclo de Entrenamiento

![[0003-IMG.png]]

1. **Forward Propagation (Predicción):**
    - El modelo toma los inputs ($x$), los multiplica por los pesos iniciales ($w$) y genera un resultado.
    - _Analogía:_ Preparar el sándwich con las proporciones actuales.
    
2. **Cálculo del Error (Loss):**
    - Se compara $\hat{y}$ con el valor real $y$.
    - _Analogía:_ El cliente prueba el sándwich y da feedback (muy dulce, muy seco).
    
3. **Backpropagation (Ajuste):**
    - Se utiliza el feedback (error) para ajustar los pesos $w$ en dirección opuesta al error.
    - Aquí es donde entra el **Gradient Descent**: el algoritmo matemático para decidir si subir o bajar la cantidad de "jalea" ($w_2$).