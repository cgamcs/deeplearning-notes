La medida de dispersión más utilizada en estadística y Deep Learning. Cuantifica la cantidad de variación o "spread" de un conjunto de valores respecto a su **mean**. Matemáticamente, es la **Square Root** (raíz cuadrada) de la [[Variance]].

A diferencia de la varianza (que deja las unidades al cuadrado, dificultando la interpretación), la **Standard Deviation** devuelve la métrica a la **misma escala** y **unidad** que los datos originales.

- **Símbolo:** $\sigma$ (para población) o $s$ (para muestra).
- Fórmula:
$$\sigma = \sqrt{\sigma^2} = \sqrt{\frac{1}{N} \sum_{i=1}^N (x_i - \mu)^2}$$

- **Ejemplo:**
    - Si mides la altura de estudiantes, la [[Variance]] podría ser $100 \ cm^2$ (una unidad cuadrada difícil de visualizar).
    - La **Standard Deviation** sería $\sqrt{100} = 10 \ cm$. Esto te dice que, en promedio, la altura de los estudiantes varía 10 cm arriba o abajo del promedio.

- **En Deep Learning:** Es crucial para la **Weight Initialization** (ej. Kaiming/Xavier init) y para técnicas de normalización como **Batch Normalization**, donde forzamos a que las activaciones tengan $\sigma \approx 1$ para estabilizar el entrenamiento.