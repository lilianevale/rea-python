# SciPy

## SciPy: Raízes de Funções e Otimização

A biblioteca `SciPy` é amplamente utilizada para computação científica em Python. Neste tutorial, vamos explorar duas funcionalidades principais:

* Encontrar **raízes de funções** (pontos onde `f(x) = 0`)
* Resolver **problemas de otimização** (mínimos de funções)

***

### Como importar

```python
import numpy as np
from scipy import optimize
```

***

### Encontrando a raiz de uma função

A raiz de uma função é o ponto onde `f(x) = 0`.

Vamos usar o método `optimize.root_scalar()` para encontrar a raiz de `f(x) = x² - 4`.

```python
from scipy import optimize

# Definindo a função
def f(x):
    return x**2 - 4

# Encontrando a raiz usando o método de Brent
resultado = optimize.root_scalar(f, bracket=[0, 5], method='brentq')

print(f"Raiz encontrada: x = {resultado.root:.2f}")
```

`bracket=[0, 5]` define o intervalo onde a função muda de sinal (ou seja, onde a raiz existe).

Você também pode usar métodos como:

* `"brentq"` (recomendado)
* `"bisect"` (mais lento, mais seguro)
* `"newton"` (método de Newton, precisa da derivada)

***

### Otimizando uma função (mínimo local)

Vamos encontrar o mínimo da função `f(x) = x² + 3x + 5`.

```python
from scipy import optimize

# Função a ser minimizada
def f(x):
    return x**2 + 3*x + 5

# Encontrando o mínimo
resultado = optimize.minimize_scalar(f)

print(f"Mínimo encontrado em x = {resultado.x:.2f}")
print(f"Valor mínimo: f(x) = {resultado.fun:.2f}")
```

O método `minimize_scalar()` encontra o **mínimo local** de uma função escalar (com uma variável).

Ele usa métodos como:

* `"brent"` (padrão)
* `"bounded"` (com intervalo)

Você também pode otimizar funções multivariadas com `optimize.minimize()`.

***

### Comparativo

| Objetivo            | Método                   | Função usada                 |
| ------------------- | ------------------------ | ---------------------------- |
| Achar raiz          | Bissecção, Brent, Newton | `optimize.root_scalar()`     |
| Achar mínimo        | Brent, Bounded           | `optimize.minimize_scalar()` |
| Mínimo multivariado | L-BFGS-B, Nelder-Mead    | `optimize.minimize()`        |
