# Operadores aritméticos

## Os operadores aritméticos

O Quadro 3.1 apresenta os operadores aritméticos e sua ordem de precedência. Porém, deve-se salientar que o usuário no momento da escrita de uma expressão ainda deverá levar em consideração os parênteses internos como os primeiros na ordem de precedência global de uma expressão aritmética.

Quadro 3.1. Operadores aritméticos.

| Operador Python | Função        | Hierarquia |
| --------------- | ------------- | ---------- |
| `+`             | Adição        | 4º         |
| `-`             | Subtração     |            |
| `*`             | Multiplicação | 3º         |
| `/`             | Divisão       |            |
| `**`            | Exponenciação | 2º         |
| `sqrt`          | Radiciação    |            |
| `%`             | Resto         |            |
| `//`            | Quociente     |            |
| `()`            | Parênteses    | 1º         |

Para exemplificar os níveis de hierarquia do computador segue um exemplo simples:

```python
"""
primeiro: 9 * 2 = 18
segundo:  8 + 18 = 26
"""

x = 8 + 9 * 2
print('valor: ', x)
```

```cmd
valor:  26
```

O seguinte exemplo  $$(5 + 3)^2 \cdot (5 - 2) + 8$$ resulta no valor _**200**_.

### Exemplo Resolvido 1&#xD;

_Construa uma Progressão Aritmética (P.A.) usando os operadores ensinados. Calcule o 10° termo da P.A. (26, 31, 36, 41, ...)._

A equação geral de uma P.A. é dada por $$a_n = a_1 + (n-1) \cdot r$$ . Onde $$a_1$$ é o primeiro termo, $$n$$ é a posição do termo desejado e $$r$$ é a razão de crescimento da progressão.

```python
# Lógica 1

aO = 26
n = 10
r = 31 - 26
aN = aO + (n - 1) * r
print('aO (lógica 1): ', aN)

# Lógica 2 com operador incremental +

aN = aO
aN += (n - 1) * r
print('aO (lógica 2): ', aN)
```

```cmd
aO (lógica 1):  71
aO (lógica 2):  71
```

{% hint style="info" %}
O Python permite o uso de operadores de incremento e decremento igual outras linguagens. No exemplo 1 foi empregado o operador incremental `+`. Também pode ser usado o operador de decremento `-`.
{% endhint %}

### Exemplo Resolvido 2&#xD;

_Você é um aluno e precisa criar um programa Python para solução de equações do 2º grau do tipo_$$a\cdot x^2 + b\cdot x + c$$

A equação (1) apresenta a formulação de Bhaskara para solução de equações do 2º grau.

| $$x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}$$ | (1) |
| ------------------------------------------ | --- |

```python
# Biblioteca
import math

a = 1
b = 12
c = -13

# Raízes
xO = (-b + math.sqrt(b ** 2 - 4 * a * c)) / (2 * a)
xL = (-b - math.sqrt(b ** 2 - 4 * a * c)) / (2 * a)
print(' x_0: ', xO, '\n','x_1: ', xL)  
```

```cmd
 x_0:  1.0 
 x_1:  -13.0
```
