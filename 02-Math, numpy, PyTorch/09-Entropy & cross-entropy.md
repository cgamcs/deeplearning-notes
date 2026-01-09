El término **Entropy** tiene diferentes significados según la disciplina:

1. **Physics (Thermodynamics):** Relacionado con la Segunda Ley de la Termodinámica. Describe la tendencia natural del universo a pasar del orden al desorden.
2. **Information Theory (Deep Learning):** Definida por **Claude Shannon**. Es una medida de la **Uncertainty** (incertidumbre) o **Surprise** asociada a una variable aleatoria.

> **Key Concept:** La [[Entropy]] cuantifica cuánta información hay en un evento.
> - **High Entropy:** Eventos impredecibles (Probabilidad $\approx 0.5$). Máxima incertidumbre.
> - **Low Entropy:** Eventos predecibles (Probabilidad $\approx 0$ o $\approx 1$). Mínima incertidumbre (sabemos qué va a pasar o qué no va a pasar).
### Entropy in Information Theory

> _"Surprising things convey more information."_

El concepto de **Surprise** en teoría de la información difiere de la intuición humana.

**Ejemplo de la Moneda:**

Si tiramos una moneda al aire 99 veces y nos da cara, pero cuando la tiramos una vez más nos da cruz, nosotros como humanos estaríamos sorprendidos, pero para la entropy no seria algo sorprendente seria algo totalmente probable.  Por lo tanto, el dataset tiene **Low Entropy**. Un sistema con **High Entropy** sería una moneda justa donde no tienes idea de qué saldrá (50/50).

![[0015-IMG.png]]
### Formula for Entropy (Shannon Entropy)

$$H(p) = -\sum_{i=1}^n p(x_i) \cdot log_2(p(x_i))$$

- $x$: **Data values** (Eventos).
- $p$: **Probability** del evento.

En términos simples: Multiplicamos la probabilidad de cada evento por el `[[08-Logarithms in Deep Learning|Logarithm]]` (base 2) de esa misma probabilidad, sumamos todo y negamos el resultado (para obtener un valor positivo, ya que los logs de probabilidades < 1 son negativos).
### Interpreting Entropy

|**Nivel de Entropy**|**Interpretación del Dataset**|**Características**|
|---|---|---|
|**High Entropy**|Alta variabilidad.|Distribución plana (uniforme). Todos los eventos son igual de probables.|
|**Low Entropy**|Baja variabilidad.|Datos redundantes y predecibles. Picos claros en la distribución.|
#### Entropy vs. Variance

A menudo se confunden, pero miden cosas distintas:

| **Concepto** | **Descripción Técnica**                                                                            |
| ------------ | -------------------------------------------------------------------------------------------------- |
| **Entropy**  | **Non-linear**. No asume una forma específica de los datos (funciona con distribuciones raras).    |
| [[Variance]] | Depende del promedio y la desviación. Es óptima para **Normal Distributions** pero falla en otras. |

### Units of Measurement

La unidad depende de la base del logaritmo utilizado:

- **Bits:** Si usamos $log_2$ (Estándar en computación).
$$H = -\sum p(x) \log_2(p(x)) \quad (\text{Bits})$$
- **Nats:** Si usamos $ln$ (Logaritmo natural, estándar en matemáticas y [[Backpropagation]]).

$$H = -\sum p(x) \ln(p(x)) \quad (\text{Nats})$$

### Cross-Entropy

Mientras que la **Entropy** mide la incertidumbre de una sola [[Probability Distribution]], la **Cross-Entropy** mide la diferencia entre dos distribuciones de probabilidad: la distribución real ($P$ o Ground Truth) y la distribución predicha por el modelo ($Q$).

$$H(P, Q) = -\sum_{i=1}^n P(x_i) \cdot log(Q(x_i))$$

En Deep Learning:

Se utiliza fundamentalmente como [[Loss Function]] para medir el rendimiento del modelo.

- **$P$ (Ground Truth):** La probabilidad real (ej. 100% Gato, 0% Perro).
- **$Q$ (Prediction):** La probabilidad predicha por el modelo (ej. 0.8 Gato, 0.2 Perro).

El objetivo del entrenamiento es minimizar la **Cross-Entropy**, haciendo que la distribución $Q$ (modelo) sea lo más parecida posible a la distribución $P$ (realidad).

> [!TIP] Conclusion
> 
> En problemas de clasificación en DL, los eventos son binarios (pasan o no pasan):
> 
> - **Ground Truth ($p$):** Siempre es 0 o 1 (One-hot encoding).
>     
> - Esto simplifica la fórmula y la hace computacionalmente eficiente.
>     
