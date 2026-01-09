Un [[Hyperparameters|Hyperparameter]] crítico (usualmente denotado como $\alpha$ o $\eta$) que controla el tamaño del paso que da el algoritmo de [[Gradient Descent]] en cada iteración. Escala la magnitud del gradiente antes de actualizar los [[Weights]].

- **Ejemplo:** Imagina que el [[Gradient Descent]] te dice que debes moverte 10 metros cuesta abajo para reducir el error. Si tu **Learning Rate** es $0.01$, en realidad solo te mueves $10 \times 0.01 = 0.1$ metros.
    - **Si es muy alto:** El modelo puede "saltarse" el mínimo (overshooting) y nunca converger.
    - **Si es muy bajo:** El entrenamiento será extremadamente lento.