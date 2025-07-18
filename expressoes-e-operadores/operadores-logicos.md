# Operadores lógicos

## Os operadores Lógicos

Em Python, assim como em muitas outras linguagens de programação, os operadores lógicos são usados para realizar operações de lógica booleana em expressões condicionais. Os operadores lógicos mais comuns em Python são `and`, `or` e `not`. O Quadro 3.3 apresenta o conceito de cada um dos operadores.

Quadro 3.3. Operadores lógicos.

| Operador Python | Função                                                                                                                                                 |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `and`           | O operador `and` retorna True se ambas as expressões condicionais forem verdadeiras.Se qualquer uma das expressões for falsa, o resultado será False.  |
| `or`            | O operador `or` retorna True se pelo menos uma das expressões condicionais for verdadeira.Se ambas as expressões forem falsas, o resultado será False. |
| `not`           | O operador `not` inverte o valor de uma expressão booleana. Se a expressão for verdadeira, `not` a tornará falsa, e vice-versa.                        |

Os operadores lógicos e possíveis combinações booleanas podem ser representados por meio do Quadro 3.4.

Quadro 3.4. Tabela verdade.

| p    | q     | p `and` q | p `or` q |
| ---- | ----- | --------- | -------- |
| True | True  | True      | False    |
| True | False | False     | False    |
| True | False | False     | False    |
| True | True  | True      | False    |

### and&#xD;

```python
# Exemplo 1: Combinação V e F
a = True
b = False
resultado = a and b
print(resultado)

# Exemplo 2: Combinação V e V
a = True
b = True
resultado = a and b
print(resultado)
```

```cmd
False
True
```

### or&#xD;

```python
a = True
b = False
resultado = a or b
print(resultado)
```

```cmd
True
```

### not&#xD;

```python
a = True
resultado = not a
print(resultado)
```

```cmd
False
```

### Exemplo Resolvido 1&#xD;

_Monte diversas sentenças booleanas_ $$p$$ e $$q$$ _e a partir disso construa a tabela verdade para o operador lógico `and`._

```python
p = 2 + 2 == 4
q = 2 + 1 == 3
print(f'{p}  and {q}:  ', p and q)
p = 2 + 2 == 8
q = 2 + 1 == 3
print(f'{p} and {q}:  ', p and q)
p = 2 + 2 == 4
q = 2 + 1 == 5
print(f'{p}  and {q}: ', p and q)
p = 2 + 2 == 8
q = 2 + 1 == 5
print(f'{p} and {q}: ', p and q)
```

```cmd
True  and True:   True
False and True:   False
True  and False:  False
False and False:  False
```

### Exemplo Resolvido 2&#xD;

_Monte diversas sentenças booleanas_ $$p$$ e $$q$$  _e a partir disso construa a tabela verdade para o operador lógico `or`._

```python
p = 2 + 2 == 4
q = 2 + 1 == 3
print(f'{p}  and {q}:  ', p or q)
p = 2 + 2 == 8
q = 2 + 1 == 3
print(f'{p} and {q}:  ', p or q)
p = 2 + 2 == 4
q = 2 + 1 == 5
print(f'{p}  and {q}: ', p or q)
p = 2 + 2 == 8
q = 2 + 1 == 5
print(f'{p} and {q}: ', p or q)
```

```cmd
True  and True:   True
False and True:   True
True  and False:  True
False and False:  False
```
