### Classification of Reality

1. **Continuous Data (Reality):** Representación numérica con valores infinitos o muy granulares.
    - _Examples:_ Height, income, exam scores.

2. **Categorical Data (Reality):** Representación discreta con valores limitados y distintos (**discrete values**).
    - _Examples:_ Dog/Cat, Mountain/Sea, Alive/Dead.

### Computer Encoding

Para que una **Neural Network** entienda **Categorical Data**, debemos transformarlos numéricamente:

**1. Dummy Coding**
- Usa **0 o 1** (False/True).
- Crea un solo **Vector**.
- _Usage:_ **Binary Classification** (Pass/Fail, Fraud Yes/No).

**2. One-Hot Encoding**
- Asigna un **0 o 1** por cada posible categoría.
- Crea una **Sparse Matrix** (muchos ceros, pocos unos).
- _Usage:_ **Multi-class Classification** (Digit recognition, Movie genres).

**Example: Genre Classification (One-Hot)**

|**Movie**|**History (y1​)**|**Sci-Fi (y2​)**|**Kids (y3​)**|
|---|---|---|---|
|**A**|0|1|0|
|**B**|0|0|1|
|**C**|1|0|0|