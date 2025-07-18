# SymPy

## Introdução ao SymPy

`SymPy` é uma biblioteca de álgebra simbólica em Python.\
Ela permite fazer **cálculos matemáticos simbólicos** como derivadas, integrais, simplificações, fatorações e muito mais — tudo de forma exata (sem arredondamentos).

***

### Como importar o SymPy

```python
import sympy as sp
sp.init_printing()  # Para exibir expressões de forma bonita
```

***

### Criando variáveis simbólicas

Antes de usar SymPy, criamos variáveis simbólicas com `symbols`:

```python
x, y = sp.symbols("x y")
```

***

### Derivadas

A derivada de uma função é calculada com `diff()`:

```python
f = x**2 + 3*x + 5

df = sp.diff(f, x)
print(df)  # Saída: 2*x + 3
```

#### Derivadas de ordem superior:

```python
segunda = sp.diff(f, x, 2)  # Segunda derivada
```

#### Derivada parcial (função multivariável):

```python
z = sp.symbols("z")
g = x**2 * y + sp.sin(z)

dg_dx = sp.diff(g, x)
dg_dy = sp.diff(g, y)
dg_dz = sp.diff(g, z)
```

***

### Integrais (∫)

Use `integrate()` para calcular integrais indefinidas e definidas.

#### Integral indefinida:

```python
f = x**2

intf = sp.integrate(f, x)
print(intf)  # Saída: x**3 / 3
```

#### Integral definida:

```python
area = sp.integrate(f, (x, 0, 2))
print(area)  # Resultado da integral de x² de 0 a 2
```

***

### Outras funcionalidades úteis

#### Simplificação:

```python
expr = (x**2 + 2*x + 1)/(x + 1)
simplificado = sp.simplify(expr)
```

#### Expansão:

```python
exp = sp.expand((x + 1)**3)
```

#### Fatoração:

```python
fact = sp.factor(x**2 + 2*x + 1)
```

#### Substituição:

```python
f = x**2 + 1
f_sub = f.subs(x, 2)  # Substitui x por 2
```

***
