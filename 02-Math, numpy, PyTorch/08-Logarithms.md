El **Logarithm** (`log`) es la operación inversa al [[07-Softmax|Natural Exponent]] ($e^x$).
### Monotonicity

Log es una [[Monotonic Function]] de $x$.

Esto significa que preserva el orden: cuando el valor de $x$ incrementa, el valor de $log(x)$ también incrementa (aunque mucho más despacio debido a su naturaleza non-linear).

¿Por qué es esto fundamental en Deep Learning?

Porque el punto mínimo de una curva en la escala original $x$ está en la misma ubicación que en la escala $log(x)$.

Por lo tanto, minimizing $x$ (el error) es matemáticamente equivalente a minimizing $log(x)$ (para $x > 0$).

> **Key Property:** **Log** "estira" (stretches) el espacio de los valores muy pequeños de $x$ (entre 0 y 1), haciendo más fácil para el modelo distinguir diferencias sutiles entre probabilidades bajas.

![[0014-IMG.png]]
### Log Bases & Natural Log

Existen logs con diferentes bases (comúnmente $log_2$ en informática o $log_{10}$), pero en **Deep Learning** usamos casi exclusivamente el **Natural Logarithm** (denotado como $ln$ o simplemente $log$).

- **Base:** $e$ (Euler's number).
- **Reason:** Se relaciona perfectamente con el **Natural Exponent**. Como $ln(e^x) = x$, el uso de logs simplifica enormemente el cálculo de derivadas (gradients) cuando trabajamos con [[Activation Function|Sigmoid Functions]] y [[07-Softmax|Softmax]].

### Why use Log in ML? ([[Numerical Stability]])

El **Machine Learning** y **Deep Learning** involucran multiplicar muchas [[07-Softmax#Numerical Example|Probabilities]] (números pequeños entre 0 y 1).

1. **Floating-point Precision:** Las computadoras tienen límites de precisión. Si multiplicas muchos números pequeños (ej. $0.001 \times 0.001 \dots$), el resultado se acerca tanto a cero que la computadora lo redondea erróneamente a $0$ (**Arithmetic Underflow**).
2. **The Log Trick:** Al aplicar log, convertimos **multiplicaciones** de números pequeños en **sumas** de números negativos manejables.

$$log(a \cdot b) = log(a) + log(b)$$

> [!TIP] Conclusion
> 
> Logs make ML work better. Transforman problemas de multiplicación propensos a errores en problemas de suma estables y numéricamente seguros.
