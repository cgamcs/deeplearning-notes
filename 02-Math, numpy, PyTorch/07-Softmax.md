Para entender la Softmax Function primero hay que entender el **Natural Exponent** ($e$).

Es un [[Scalar]] (número constante) fundamental en cálculo, similar a $\pi$. Su valor es aproximadamente $2.71828...$, es irracional y nunca es igual a 0.

### The Formula

La función toma un vector de entrada $z$ y produce un vector de salida $\sigma(z)$ donde cada elemento es positivo y la suma total es 1.

$$\sigma_i = \frac{e^{z_i}}{\sum_{j=1}^K e^{z}}$$

### Numerical Example

Supongamos que tenemos un **Input Vector** (llamado técnicamente [[Logits]]) $z = [1, 2, 3]$.

1. Calculamos el exponente natural de cada elemento ($e^z$).
2. Sumamos todos los exponentes (el denominador).
3. Dividimos cada exponente individual por la suma total.

|**z (Logits)**|**ez (Unnormalized)**|**σ(z) (Probabilities)**|
|---|---|---|
|1|$2.71$|$2.71 / 30.19 \approx \mathbf{0.09}$|
|2|$7.38$|$7.38 / 30.19 \approx \mathbf{0.24}$|
|3|$20.08$|$20.08 / 30.19 \approx \mathbf{0.67}$|
|**Sum**|$\approx 30.19$|**1.00**|
![[0010-IMG.png]]
> **Interpretación:** Aunque la probabilidad aleatoria de elegir 1, 2 o 3 sería $1/3$ ($0.33$), la **Softmax** enfatiza los valores más altos. El input $3$ se transformó en una probabilidad del $67\%$.


![[0011-IMG.png]]

### The "Softmaxerizer" Analogy

Podemos imaginar la función como una máquina ("The Softmaxerizer") que interpreta la salida de un modelo de **Deep Learning**.

El modelo realiza muchas operaciones lineales y no lineales (`[[01-What is an artificial neural network#Introducing Non-Linearity|Layers]]`) y arroja una colección de números que suelen ser difíciles de interpretar (negativos, positivos, sin escala definida). Estos números se llaman **Logits**.

El **Softmaxerizer** toma esos [[Logits]] y los convierte en probabilities.

**Ejemplo de Clasificación de Imágenes:**

- **Raw Output (Logits):** `[2.5, -0.1, 8.2]` (Valores arbitrarios e ininterpretables).
- **Softmax Output:** `[0.003, 0.000, 0.997]`.
- **Interpretación:** "Esta imagen tiene un 99.7% de probabilidad de ser un Lobo".

![[0012-IMG.png]]
### Input/Output Properties

Como se explicó, una propiedad estricta es que la **Summation** de los outputs debe ser igual a **1**.

Esto implica una relación entre la cantidad de clases y los valores resultantes:

- Mientras más **Inputs** (categorías) tenga el modelo, los valores individuales de **Output** tenderán a ser más pequeños ("se diluye la probabilidad"), ya que todos deben caber en la unidad 1.

![[0013-IMG.png]]