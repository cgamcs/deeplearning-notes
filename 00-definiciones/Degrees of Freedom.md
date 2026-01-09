En estadística, los **Degrees of Freedom** (grados de libertad) representan el número de valores en un cálculo que son "libres de variar".

En el contexto de `numpy.var` (y `numpy.std`), este concepto se controla mediante el parámetro `ddof` (**Delta Degrees of Freedom**). Este parámetro modifica el divisor en la fórmula de la `[[Variance]]` y determina si estamos calculando una estadística descriptiva o una inferencia sobre una población.

#### The Formula Context

La fórmula general de la varianza es $\frac{\sum (x - \mu)^2}{N - ddof}$.

1. **Population Variance (`ddof=0`):**
    - Asumimos que tenemos **todos** los datos existentes (la población completa).
    - Dividimos por $N$.
    - **NumPy Default:** `np.var(x)` usa `ddof=0` por defecto.

2. **Sample Variance (`ddof=1`):**
    - Tenemos solo una **Sample** (muestra) y queremos estimar la varianza de la población real.
    - Dividimos por $N-1$ (conocido como **Bessel's Correction**).
    - Esto corrige el **Bias** (sesgo), ya que usar solo $N$ en una muestra tiende a subestimar la variabilidad real.

```
import numpy as np

data = np.array([10, 12, 23, 23, 16, 23, 21, 16])

# 1. Population Variance (NumPy Default)
# "Tengo todos los datos del mundo, solo quiero describir ESTOS datos"
pop_var = np.var(data, ddof=0) 
print(f"Population Variance: {pop_var}")

# 2. Sample Variance (Unbiased Estimator)
# "Esto es solo una muestra, quiero estimar la varianza real del mundo"
# Es lo que usan Pandas y R por defecto.
samp_var = np.var(data, ddof=1)
print(f"Sample Variance: {samp_var}")
```

> [!WARNING] Common Pitfall
> 
> Si calculas la varianza manualmente en una calculadora o en Excel (`VAR.S`), usualmente obtendrás el resultado de `ddof=1`. Si usas `np.var()` sin argumentos, obtendrás `ddof=0`. ¡Cuidado con esa discrepancia!

