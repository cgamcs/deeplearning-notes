### The Mean

El **Mean** (o **Arithmetic Mean**) representa el promedio de un conjunto de datos. Matemáticamente, es el "centro de gravedad" de la distribución.

Sin embargo, el **Mean** puede ser engañoso: no necesariamente indica dónde se concentra la mayoría de los datos, ya que es muy sensible a valores extremos (`[[Outliers]]`).

#### Formula

$$\bar{x} = n^{-1}\sum_{i=1}^n x_i$$

#### Notation

$$\bar{x} = \mu = \mu_x$$

- **$\bar{x}$ (x-bar):** Usualmente se refiere al **Sample Mean** (promedio de una muestra).
- **$\mu$ (mu):** Se refiere al **Population Mean** (promedio de toda la población).

> **Note:** El uso del Mean es adecuado para datos con una **Normal Distribution** (Campana de Gauss), pero puede fallar en distribuciones sesgadas.

Example:

$$x = [-2, 0, 4, 1, 7]$$

$$ \bar{x} = \frac{-2+0+4+1+7}{5} = \frac{10}{5} = \mathbf{2}$$

#### The "Failure" Scenario

![[0018-IMG.png]]

En distribuciones **Bi-modal** (dos picos) o muy dispersas, el **Mean** puede caer en un punto donde _no existen datos_.

- _Técnicamente:_ La fórmula encuentra el centro matemático.
- _El problema:_ No representa el "valor típico" si la distribución no es uniforme o normal.

---

### Concept of Dispersion

Dos datasets pueden tener el mismo **Mean**, pero una forma totalmente distinta. Aquí entra el concepto de **Dispersion** (qué tan esparcidos están los datos).

![[0019-IMG.png]]

La medida de dispersión más común es la `[[Variance]]`.

#### Variance Formula

$$\sigma^2 = \frac{1}{n-1} \sum_{i=1}^n(x_i - \bar{x})^2$$

- Se puede usar en cualquier distribución numérica.
- Requiere calcular primero el **Mean** ($\bar{x}$).

**Example Calculation:**

$$\begin{aligned} x &= [2, 3, 4, 3, 4, 4] \\ \bar{x} &= 3.33 \dots \\ \text{Diffs}^2 &= [(2-3.33)^2, (3-3.33)^2, \dots] \\ \text{Sum of Diffs}^2 &= 2.66 \dots \\ \text{Variance} &= \frac{2.66}{5} \approx \mathbf{0.53} \end{aligned}$$

#### Why Mean-Center?

La **Variance** mide la dispersión _alrededor_ del promedio, sin importar la magnitud absoluta de los datos. Esta propiedad se llama **Translation Invariance**.

$$\begin{aligned} d1 &= [1, 2, 3, 3, 2, 1] \\ d2 &= [101, 102, 103, 103, 102, 101] \end{aligned}$$

> **Conclusion:** Ambos datasets tienen exactamente la **misma Variance**, aunque sus valores sean muy distintos.

#### Why are differences squared?

Queremos medir la distancia sin importar el signo. Si no eleváramos al cuadrado, la suma de las diferencias con el promedio siempre sería **cero**.

$$\begin{aligned} d1 &= [1, 2, 3] \quad (\text{Mean}=2) \\ \text{Mean-centered} &= [-1, 0, 1] \ \rightarrow \ \text{Sum} = 0 \end{aligned}$$

Al elevar al cuadrado ($(x-\bar{x})^2$), todos los valores se vuelven positivos y penalizamos más los errores grandes.

(Nota: También existe el Mean Absolute Deviation, que usa valor absoluto $|x - \bar{x}|$, pero es menos común en estadística clásica).

---

### Standard Deviation

La **Variance** deja las unidades al cuadrado (ej. "metros cuadrados"). Para volver a las unidades originales de los datos, aplicamos la raíz cuadrada, obteniendo la [[Standard Deviation]] ($\sigma$).

$$\sigma = \sqrt{\sigma^2} = \sqrt{\frac{1}{n-1} \sum_{i=1}^n(x_i - \bar{x})^2}$$

---

### Code Implementation

En Python, es vital entender la diferencia entre **Population Variance** y **Sample Variance** controlada por los [[Degrees of Freedom]].

Python

```
# import libraries
import numpy as np

# create a list of numbers
x = [1,2,4,6,5,4,0]
n = len(x)

# --- MEAN ---
# compute the mean
mean1 = np.mean(x)
mean2 = np.sum(x) / n

print(mean1)
print(mean2)

# --- VARIANCE ---
# Numpy default (Population Variance, ddof=0)
var1 = np.var(x)

# Manual calculation of Sample Variance (n-1)
var2 = (1/(n-1)) * np.sum( (x-mean1)**2 )

print(f"Numpy Default (Pop): {var1}")
print(f"Manual Sample formula: {var2}")

# --- THE FIX ---
# Using the correct parameter for Sample Variance
var3 = np.var(x, ddof=1)

print(f"Numpy with ddof=1: {var3}")

# --- DOES IT MATTER? ---
# Does it matter for large N? 
N = 10000
x = np.random.randint(0, high=20, size=N)

var0 = np.var(x, ddof=0) # Biased (Population)
var1 = np.var(x, ddof=1) # Unbiased (Sample)

print(f"Large N Difference: {var1 - var0}") 
# Note: As N gets larger, the difference becomes negligible.
```

> [!WARNING] Numpy vs. Statistics
> 
> El código np.var(x) por defecto usa ddof=0 (Population).
> 
> Para obtener la varianza "insesgada" (Unbiased Variance) que se enseña en estadística clásica, debes especificar np.var(x, ddof=1), aplicando la corrección de [[Degrees of Freedom]] ($n-1$).