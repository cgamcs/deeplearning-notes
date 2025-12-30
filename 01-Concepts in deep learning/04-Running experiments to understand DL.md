## Metodología Experimental en Deep Learning

La ciencia de datos combina teoría y experimentación empírica.

### Tipos de Investigación

|**Enfoque**|**Descripción**|
|---|---|
|**Teórico**|Desarrollo de nuevas matemáticas, arquitecturas y fundamentos.|
|**Aplicado (Ecólogo)**|Uso de modelos pre-entrenados o existentes para resolver problemas reales.|
|**Experimental**|Manipulación sistemática de hiperparámetros para optimizar el rendimiento.|
### Diseño de Experimentos

Para encontrar el mejor modelo, se iteran pruebas controladas:

- **Variables Independientes (Inputs):** Hiperparámetros (Learning rate, Batch size, Optimizador, Arquitectura).
- **Variables Dependientes (Outputs):** Métricas de desempeño (Accuracy, Loss, Velocidad de inferencia).

### Interpretación de Resultados

> [!WARNING] Interpretación Correcta vs. Incorrecta
> 
> -  **Correcto:** "Estos parámetros funcionan mejor para _esta_ arquitectura con _este_ dataset específico."
>
> - **Correcto:** "Observo un patrón general que _podría_ transferirse a otros contextos."
>     
> - **Incorrecto:** "Este es el hiperparámetro universal para todos los modelos."
>     

### Desafíos del Enfoque Experimental

1. **Viabilidad (Feasibility):** Los modelos grandes (LLMs, Vision Transformers) requieren tiempo y cómputo masivo, dificultando la iteración rápida.
2. **Generalización:** Una optimización específica para un dataset puede no funcionar en otro ("Overfitting" a la configuración).

> _"Science is more an art than a science."_ — En DL, la intuición ganada mediante la experimentación es clave.