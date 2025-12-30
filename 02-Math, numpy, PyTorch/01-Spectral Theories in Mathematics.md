El concepto central de las **Spectral Theories** en matemáticas es la descomposición: tomar un sistema complicado y dividirlo en múltiples partes simples y comprensibles.

Los **Deep Learning models** siguen este principio. Aunque visualmente parecen redes complejas, podemos descomponerlos en **units** (o **nodes**) fundamentales.

![[0002-IMG.png]]

Cada **node** en la gráfica anterior esconde una operación simple y repetitiva, generalmente una **linear equation** seguida de una **non-linear activation function**:

$$\hat{y} = \sigma(x_1 w_1 + x_2 w_2)$$

![[0004-IMG.png]]

> **Conclusión:** **Deep Learning** es _complicated_ por la gran cantidad de operaciones simultáneas, pero matemáticamente se reduce a una colección masiva de **arithmetic operations** muy simples.

### Difference between Complicated and Complex

Podemos clasificar los sistemas según su arquitectura y comportamiento:

|**Feature**|**Complicated**|**Complex**|
|---|---|---|
|**Components**|Gran cantidad de **parts**.|Pocos o múltiples componentes.|
|**Math**|**Linear** o con pocas **non-linearities**.|**High non-linearity** (Múltiples).|
|**Interpretation**|**Intuitive** y comprensible.|**Counter-intuitive**, difícil de interpretar.|

**El Deep Learning es un sistema híbrido:**

1. **Simple:** Construido sobre matemática básica (sumas y multiplicaciones).
2. **Complicated:** Posee una enorme cantidad de **parameters** (partes).
3. **Complex:** La infinidad de **non-linearities** lo hace difícil de interpretar intuitivamente (es una "Black Box").