## 1. Introducción a Artificial Neural Networks (ANN)

Una **Artificial Neural Network (ANN)** es un modelo computacional diseñado para transformar datos de entrada ($input$) en una salida ($output$) deseada, imitando vagamente el aprendizaje biológico.

Aunque el proceso interno puede parecer una "caja negra" (black box) debido a su complejidad, matemáticamente es una serie de transformaciones algorítmicas para encontrar patrones no lineales.

**Caso de uso común:** Predicción de probabilidad (ej. CTR - Click Through Rate basado en historial de búsqueda).

### Ejemplo de Dataset Estructurado

|**ID**|**x1​ (Estudio/h)**|**x2​ (Sueño/h)**|**y (Resultado Real)**|
|---|---|---|---|
|1|5|6|Pass|
|2|10|7|Pass|
|...|...|...|...|
|$n$|7|5|Fail|

> **Nota:** Para problemas simples se utiliza **Machine Learning clásico** (ej. Regresión Logística). Para problemas complejos y no lineales, se utiliza **Deep Learning (ANN)**.

### Representación Gráfica

![[0001-IMG.png]]

- **$x_1, x_2$**: Características de entrada (Inputs: horas de estudio, sueño).
- **$x_0$**: Unidad de sesgo (_Bias_). Permite desplazar la función de activación.
- **$w_i$**: Pesos (_Weights_). Determinan la importancia de cada entrada.

El flujo consiste en calcular una **suma ponderada** de las entradas y aplicar una **función de activación** ($\sigma$) para obtener la predicción ($\hat{y}$).

## 2. Matemáticas del Modelo

### Modelo Lineal (Base)

La base fundamental es la combinación lineal de entradas y pesos:

$$\hat{y} = x_1 w_1 + x_2 w_2$$

- **$\hat{y}$ (Predicción):** La estimación del modelo sobre el mundo real.
- **$x$ (Features):** Datos de entrada.
- **$w$ (Weights):** Parámetros aprendidos que indican la relevancia de cada dato.
    - _Ejemplo:_ Si $x_z$ representa "cantidad de toronjas consumidas", el modelo aprenderá que es irrelevante asignando $w_z \approx 0$.

### Introduciendo No-Linealidad

Una ecuación lineal solo puede resolver problemas lineales. Para modelar la complejidad del mundo real, aplicamos una **Función de Activación** no lineal ($\sigma$):

$$\hat{y} = \sigma(x_1 w_1 + x_2 w_2)$$

> [!TIP] Funciones de Activación
> 
> Normalmente se prefieren funciones no lineales simples y derivables (como ReLU o Sigmoide) sobre funciones complejas, ya que facilitan el cálculo del gradiente.

### Arquitectura Deep Learning

Una sola neurona tiene limitaciones. El poder del Deep Learning reside en conectar múltiples neuronas en capas:

![[0002-IMG.png]]

- **Neurona Artificial:** Bloque de construcción elemental que contiene la ecuación $\sigma(\sum xw)$.
- **Deep Learning:** Transformación jerárquica de datos mediante múltiples capas de estas neuronas.

### Tipos de Arquitecturas según el Problema

| **Tipo de Datos**      | **Arquitectura Recomendada** | **Siglas** |
| ---------------------- | ---------------------------- | ---------- |
| Datos Tabulares        | Artificial Neural Network    | **ANN**    |
| Imágenes / Visión      | Convolutional Neural Network | **CNN**    |
| Audio / Texto / Series | Recurrent Neural Network     | **RNN**    |
