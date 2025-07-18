# Numpy

## Introdução ao NumPy

`NumPy` (Numerical Python) é uma das bibliotecas mais importantes da computação científica com Python.\
Ela fornece:

* Arrays e matrizes multidimensionais
* Operações matemáticas rápidas e eficientes
* Recursos para manipular e analisar dados numéricos

***

### Como importar o NumPy

A convenção mais comum é importar como `np`:

```python
import numpy as np
```

***

### Criando Arrays

#### Vetor (1D)

```python
a = np.array([1, 2, 3])
```

#### Matriz (2D)

```python
b = np.array([[1, 2],
              [3, 4]])
```

***

### Inspecionando arrays

```python
a.shape      # Dimensões (linhas, colunas)
a.ndim       # Número de dimensões
a.dtype      # Tipo dos dados (int, float, etc.)
a.size       # Quantidade total de elementos
```

***

### Criando arrays com valores específicos

```python
np.zeros((2, 3))         # Matriz 2x3 preenchida com zeros
np.ones((3, 2))          # Matriz 3x2 preenchida com uns
np.eye(3)                # Matriz identidade 3x3
np.full((2, 2), 7)       # Matriz 2x2 preenchida com o valor 7
np.arange(0, 10, 2)      # Sequência de 0 a 8, pulando de 2 em 2
np.linspace(0, 1, 5)     # 5 valores igualmente espaçados entre 0 e 1
```

***

### Repetição e replicação de arrays

```python
a = np.array([[1, 2]])

np.repeat(a, 3, axis=0)    # Repete a linha 3 vezes
np.tile(a, (2, 3))         # Repete o array em blocos 2x3
```

***

### Operações matemáticas com arrays

```python
a = np.array([1, 2, 3])
b = np.array([4, 5, 6])

a + b      # Soma elemento a elemento → [5 7 9]
a * b      # Multiplicação elemento a elemento → [4 10 18]
a ** 2     # Potência de cada elemento → [1 4 9]
a.mean()   # Média dos valores
a.std()    # Desvio padrão
```

***

### Indexação e fatiamento

#### Array 1D

```python
a = np.array([10, 20, 30, 40, 50])

a[0]        # Primeiro elemento (10)
a[1:4]      # Elementos do índice 1 ao 3 → [20 30 40]
a[-1]       # Último elemento (50)
```

#### Array 2D (matriz)

```python
mat = np.array([[1, 2, 3],
                [4, 5, 6]])

mat[0, 1]   # Linha 0, coluna 1 → 2
mat[:, 1]   # Todas as linhas, coluna 1 → [2 5]
mat[1, :]   # Linha 1 inteira → [4 5 6]
```

***

### Alterando o formato do array

```python
a = np.arange(6)           # [0 1 2 3 4 5]
a.reshape((2, 3))          # Torna 2x3
a.flatten()                # Torna 1D novamente
```

***

### Concatenando arrays

```python
a = np.array([[1, 2]])
b = np.array([[3, 4]])

np.concatenate([a, b], axis=0)  # Empilha verticalmente
np.concatenate([a, b], axis=1)  # Empilha horizontalmente
```

***

### Removendo elementos

```python
a = np.array([1, 2, 3, 4, 5])

np.delete(a, [0, 2])  # Remove os elementos nos índices 0 e 2 → [2 4 5]
```

***
