## Experimental Methodology in Deep Learning

La **Data Science** combina teoría y experimentación empírica.

### Research Approaches

|**Approach**|**Description**|
|---|---|
|**Theoretical**|Desarrollo de nuevas **math**, **architectures** y **foundations** (no datos).|
|**Applied (Ecologist)**|Uso de **pre-trained models** o existentes para resolver problemas reales.|
|**Experimental**|Manipulación sistemática de **hyperparameters** para optimizar el **performance**.|
### Experimental Design

Para encontrar el mejor modelo, se realizan **controlled iterations**:

- **Independent Variables (Inputs):** **Hyperparameters** (**Learning Rate**, **Batch Size**, **Optimizer**, **Architecture**).
- **Dependent Variables (Outputs):** **Performance Metrics** (**Accuracy**, **Loss**, **Inference Speed**).

### Interpretation of Results

> [!WARNING] Correct vs. Incorrect Interpretation
> 
> - **Correct:** "Estos **parameters** funcionan mejor para _esta_ **architecture** con _este_ **dataset** específico."
>     
> - **Correct:** "Observo un **general pattern** que _podría_ transferirse a otros contextos."
>     
> - **Incorrect:** "Este es el **universal hyperparameter** para todos los modelos."
>     

### Challenges of Experimental Approach

1. **Feasibility:** Los modelos grandes (**LLMs**, **Vision Transformers**) requieren tiempo y **massive compute**, dificultando la **rapid iteration**.
2. **Generalizability:** Una optimización específica para un **dataset** puede no funcionar en otro (**Overfitting** a la configuración).

> _"Science is more an art than a science."_ — En **Deep Learning**, la intuición ganada mediante la experimentación es clave.