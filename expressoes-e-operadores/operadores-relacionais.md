# Operadores relacionais

## Relação entre variáveis

Em Python, os operadores relacionais são usados para comparar dois valores. Eles retornam um valor booleano (**True** ou **False**) dependendo da comparação efetuada. O Quadro 3.2 apresenta os operadores.

Quadro 3.2. Operadores relacionais.

| Operador Python | Função                                                                    |
| --------------- | ------------------------------------------------------------------------- |
| `==`            | Verifica se dois valores são iguais.                                      |
| `!=`            | Verifica se dois valores são diferentes.                                  |
| `>`             | Verifica se o valor da esquerda é estritamente maior ao valor da direita. |
| `>=`            | Verifica se o valor da esquerda é maior ou igual ao valor da direita.     |
| `<`             | Verifica se o valor da esquerda é estritamente menor ao valor da direita. |
| `<=`            | Verifica se o valor da esquerda é menor ou igual ao valor da direita.     |

{% hint style="info" %}
Não podemos confundir `==` com o operador de atribuição `=`.
{% endhint %}

### Os operadores&#xD;

```python
# ==

a = 5
b = 5
resultado = (a == b)
print('resultado: a == b', resultado)

# !=
a = 5
b = 3

resultado = (a != b)
print('resultado: a != b', resultado)

# >
a = 5
b = 3

resultado = (a > b)
print('resultado: a > b ', resultado)

# >=
a = 5
b = 5

resultado = (a >= b)
print('resultado: a >= b', resultado)

# <
a = 5
b = 5

resultado = (a < b)
print('resultado: a < b ', resultado)

# <=
a = 5
b = 5

resultado = (a <= b)
print('resultado: a <= b', resultado)
```

```cmd
resultado: a == b True
resultado: a != b True
resultado: a > b  True
resultado: a >= b True
resultado: a < b  False
resultado: a <= b True
```

Os operadores relacionais são frequentemente usados em estruturas de controle de fluxo, como condicionais (`if-elif-else`) e estruturas de repetição.

{% hint style="info" %}
Os operadores relacionais são frequentemente usados em estruturas de controle de fluxo, como condicionais `if-elif-else` e estruturas de repetição como `for` e `while`.
{% endhint %}

Os operadores relacionais têm todos o mesmo grau de prioridade porém comparado a operadores aritméticos estes tem uma prioridade menor, vejamos um exemplo teste de comparação entre 3 variáveis.

```python
a = 1
b = 1
c = 1
resultado = a > b + c

print('comparação: ', resultado)
```

```cmd
comparação:  False
```

{% hint style="info" %}
Em escrita matemática a expressão ficaria assim: (a > (b + c)).
{% endhint %}
