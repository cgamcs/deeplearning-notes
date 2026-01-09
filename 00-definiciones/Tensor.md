La generalización matemática de escalares, vectores y matrices a $N$ dimensiones. Es la estructura de datos fundamental en frameworks como **PyTorch** y **TensorFlow**.

- **Rank-0:** [[Scalar]].
- **Rank-1:** [[Vector]]`.
- **Rank-2:** [[Matrix]].
- **Rank-3+:** Tensor n-D.

- **Ejemplo:** Un lote (**Batch**) de 64 imágenes a color. Cada imagen tiene altura, anchura y 3 canales de color (RGB). La dimensión del tensor sería $(64, 256, 256, 3)$.