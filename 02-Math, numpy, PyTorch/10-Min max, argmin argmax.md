Es crucial distinguir entre obtener el **valor** extremo y obtener la **posición** (índice) de ese valor.
### Min & Max (Values)

Retornan el valor mínimo o máximo contenido en un conjunto o `[[Vector]]`.
$$
\begin{aligned}
\min \{1, -1, 3, 0, 4, 3\} &= -1
\\
\max \{1, -1, 3, 0, 4, 3\} &= 4
\end{aligned}
$$
### ArgMin & ArgMax (Indices)

Retornan el Argument (o Index) en el que se encuentra ese valor mínimo o máximo.
$$
\begin{aligned} 
\operatorname*{arg\,min} \{1, -1, 3, 0, 4, 3\} &= 1 \quad (\text{Index del valor } -1) 
\\ 
\operatorname*{arg\,max} \{1, -1, 3, 0, 4, 3\} &= 4 \quad (\text{Index del valor } 4) 
\end{aligned}
$$
### Formula

Generalmente buscamos el argumento $x$ que maximiza una función $f(x)$:
$$\hat{x} = \operatorname*{arg\,max}_x f(x)$$
### Application in Deep Learning

La aplicación más común de **argmax** es interpretar la salida de la [[07-Softmax|Softmax Function]] o los [[Logits]].

El modelo nos da probabilidades, pero nosotros queremos saber qué clase ganó.

![[0016-IMG.png]]

![[0017-IMG.png]]

1. **Model Output:** `[0, 0.05, 0.8, 0.1, 0.05]`.
2. **ArgMax:** Retorna el índice `2` (la lista empieza desde el índice 0).
3. **Interpretation:** La predicción final es la clase en la posición 3 ("Señal de Alto").