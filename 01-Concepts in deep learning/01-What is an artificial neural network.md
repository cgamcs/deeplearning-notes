## 1. Introduction to Artificial Neural Networks (ANN)

Una **Artificial Neural Network (ANN)** es un modelo computacional diseñado para transformar **Input Data** () en un **Output** deseado (), imitando vagamente el **biological learning**.

Aunque el proceso interno puede parecer una **[[Black Box]]** debido a su complejidad, matemáticamente es una serie de transformaciones algorítmicas para encontrar **non-linear patterns**.

**Common Use Case:** **Probability Prediction** (ej. CTR - Click Through Rate basado en historial de búsqueda).

### Example: Structured Dataset

| **ID** | ** (Study/h)** | ** (Sleep/h)** | ** (Ground Truth)** |
| ------ | -------------- | -------------- | ------------------- |
| 1      | 5              | 6              | Pass                |
| 2      | 10             | 7              | Pass                |
| ...    | ...            | ...            | ...                 |
| N      | 7              | 5              | Fail                |

> **Note:** Para **Simple Problems** se utiliza **Classical Machine Learning** (ej. **Logistic Regression**). Para **Complex/Non-linear Problems**, se utiliza **Deep Learning (ANN)**.

### Graphical Representation

![[0001-IMG.png]]

* **[[Inputs|Input Features]]** (Horas de estudio, sueño).
* **[[Bias Unit]]**. Permite desplazar la **Activation Function**.
* **[[Weights]]**. Determinan la importancia de cada **input**.

El flujo consiste en calcular una **[[Weighted Sum]]** (suma ponderada) de los inputs y aplicar una **[[Activation Function]]** () para obtener la **[[Prediction]]** ().

## 2. Mathematics of the Model

### Linear Model (Base)

La base fundamental es la **Linear Combination** de inputs y weights:

* **([[Prediction]]):** La estimación del modelo sobre el mundo real.
* **([[Features]]):** Datos de entrada (**Input Data**).
* **([[Weights]]):** **Learned parameters** que indican la relevancia de cada dato.
* *Example:* Si  representa "cantidad de toronjas consumidas", el modelo aprenderá que es irrelevante asignando .

### Introducing Non-Linearity

Una **Linear Equation** solo puede resolver **Linear Problems**. Para modelar la **complexity** del mundo real, aplicamos una **Non-linear Activation Function** ():

> [!TIP] Activation Functions
> Normalmente se prefieren funciones no lineales simples y **differentiable** (como **ReLU** o **Sigmoid**) sobre funciones complejas, ya que facilitan el cálculo del **Gradient**.

### Deep Learning Architecture

Una sola **neuron** tiene limitaciones. El poder del **Deep Learning** reside en conectar múltiples neuronas en **Layers**:

![[0002-IMG.png]]

* **Artificial Neuron:** **Building block** elemental que contiene la ecuación .
* **Deep Learning:** Transformación jerárquica de datos mediante múltiples **layers** de estas neuronas.

### Architectures by Problem Type

| **Data Type** | **Recommended Architecture** | **Acronym** |
| --- | --- | --- |
| **Tabular Data** | Artificial Neural Network | **ANN** |
| **Images / Vision** | Convolutional Neural Network | **CNN** |
| **Audio / Text / Sequences** | Recurrent Neural Network | **RNN** |