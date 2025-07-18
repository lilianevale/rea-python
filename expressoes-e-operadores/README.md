# Expressões e operadores

## Criando expressões

Nesta seção vamos focar na escrita de expressões usando a linguagem Python. Segundo Lopes e Garcia \[1] uma expressão é um conjunto de variáveis e constantes numéricas que se relacionam por meio de operadores, compondo uma fórmula que, uma vez avaliada, resulta em um valor.\
\
Dentre os vários operadores que temos nas linguagens o primeiro operador que vamos avaliar é o operador de atribuição dado em Python pela sintaxe `=`.\
\
Vejamos um exemplo dessa atribuição:

```python
valor = 1 + 2
print('soma: ', valor)
```

```cmd
soma: 3
```

Exemplos mais complexos podem ser empregados para escrita de uma expressão e para isso vamos começar a fazer uso de bibliotecas no Python. Aqui vamos começar pela biblioteca [math](https://docs.python.org/pt-br/3/library/numeric.html) que é a biblioteca para cálculos matemáticos do Python. Maiores detalhes podem ser vistos na documentação da biblioteca [math](https://docs.python.org/pt-br/3/library/numeric.html).\
\
Para fazer uso da biblioteca basta importar a biblioteca com o seguinte comando `import math`. Vejamos um exemplo de uma expressão usando a [math](https://docs.python.org/pt-br/3/library/numeric.html) para escrever a relação fundamental da trigonometria para um determinado valor de ângulo.

```python
# importanto a biblioteca
import math

# ângulo em radianos
a = math.pi

# a relação trigonometrica
relacao = math.sin(a) ** 2 + math.cos(a) ** 2 - 1
print('valor: ', relacao)
```

```cmd
valor:  0.0
```

## Mais algumas dicas sobre a `math` e outras funções matemáticas

### Potenciação e radiação&#xD;

```python
"""
2^3
"""

valor = math.pow(2, 3)
print('valor: ', valor)
```

```cmd
valor:  8.0
```

### Raiz quadrada&#xD;

```python
"""
16^0.5
"""

valor = math.sqrt(16)
print('valor: ', valor)
```

```cmd
valor:  4.0
```

### Potenciação e radiação na base _e_&#xD;

```python
"""
e^3
"""

valor = math.exp(3)
print('valor: ', valor)
```

```cmd
valor:  20.085536923187668
```

### Controle de precisão&#xD;

```python
"""
maior inteior possível que não seja maior do x
"""

print("math.floor(23.11): ", math.floor(23.11))
print("math.floor(23.50): ", math.floor(23.50))
print("math.floor(23.99): ", math.floor(23.99))
```

```cmd
math.floor(23.11):  23
math.floor(23.50):  23
math.floor(23.99):  23
```

```python
"""
maior inteior logo após x
"""
 
print("math.ceil(23.11): ", math.ceil(23.11))
print("math.ceil(23.50): ", math.ceil(23.50))
print("math.ceil(23.99): ", math.ceil(23.99))
```

```cmd
math.ceil(23.11):  24
math.ceil(23.50):  24
math.ceil(23.99):  24
```

```python
"""
controle de arredondamento com precisão delimitada
"""
 
print("round(23.11, 1): ", round(23.11, 1))
print("round(23.54, 1): ", round(23.54, 1))
print("round(23.55, 1): ", round(23.55, 1))
print("round(23.56, 1): ", round(23.56, 1))
print("round(23.99, 1): ", round(23.99, 1))
```

```cmd
round(23.11, 1):  23.1
round(23.54, 1):  23.5
round(23.55, 1):  23.6
round(23.56, 1):  23.6
round(23.99, 1):  24.0
```

{% hint style="warning" %}
Em Python a potenciação é representada pela sintaxe `**` e não `^` igual em outras linguagens como Matlab por exemplo.
{% endhint %}

Após esse apanhado inicial vamos agora aprofundar nos conceitos de operadores exemplificando o uso de operadores: (a) aritméticos, (b) relacionais e (c) lógicos.

## Referências

| Código | Referência                                                                                                |
| ------ | --------------------------------------------------------------------------------------------------------- |
| \[1]   | Lopes A, Garcia G. Introdução à programação: 500 algoritmos resolvidos. Rio de Janeiro (RJ): Campus; 2002 |
