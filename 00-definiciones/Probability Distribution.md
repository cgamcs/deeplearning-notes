Una función matemática que describe la probabilidad de ocurrencia de todos los posibles **outcomes** (resultados) de una variable aleatoria. En **Deep Learning**, es fundamental porque la salida final de un modelo de clasificación (normalmente procesada por [[07-Softmax|softmax]]) se interpreta como una distribución sobre las posibles clases, donde la suma total de valores debe ser siempre igual a 1.

- **Ejemplo:** Imagina un modelo que clasifica una imagen en 3 categorías.
    - **Distribución Predicha ($Q$):** `[Gato: 0.1, Perro: 0.7, Barco: 0.2]`. (El modelo cree al 70% que es un perro).
    - **Distribución Real ($P$ - Ground Truth):** `[Gato: 0, Perro: 1, Barco: 0]`. (Es, de hecho, un perro).
    - La [[Loss Function]] (específicamente [[09-Entropy & cross-entropy#Cross-Entropy|cross-entropy]]) se encarga de calcular qué tan diferente es la distribución predicha de la distribución real.