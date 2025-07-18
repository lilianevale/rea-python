# Estruturas de repetição

## Introdução as estruturas de repetição

As estruturas de repetição são alternativas de código para criar instruções repetidas. Tal fato evita que o programador tenha que repetir blocos de códigos aumentando consideravelmente o tamanho do algoritmo \[1].\
\
Nas linguagens de programação essas estruturas normalmente são representadas pela instrução `for` e `while`. A instrução `for` é empregada quando se conhece o número de repetições necessárias para solução do problema, por exemplo a leitura e somatório de 20 notas de alunos de um curso. Já a instrução `while` é empregada quando não se tem conhecimento do número de repetições necessárias e então faz-se uso de uma chave para interromper a repetição.

### for&#xD;

```python
for numero in range(1, 6):
    print(numero)
```

```cmd
1
2
3
4
5
```

{% hint style="info" %}
Na instrução de repetição `for` os pontos de partida e finalização devem ser informados, lembrando que os iteradores do Python iniciam em 0 caso não seja informado nenhum valor de partida. Na instrução `for` a lista de valores a serem iterados são gerados pela instrução `range(a, n)`. Outra informação importante o Python trava o iterador no valor `n-1`. Por isso no exemplo acima a impressão parou no valor 5.
{% endhint %}

### while&#xD;

O loop `while` é usado quando você deseja repetir um bloco de código enquanto uma condição for verdadeira. Aqui está um exemplo simples de como usar `while` para contar até 5:

```python
contador = 1

while contador <= 5:
    print(contador)
    contador += 1
```

```cmd
1
2
3
4
5
```

{% hint style="warning" %}
É importante salientar que no Python é obrigatório o uso de `:` para finalizar comando da estrutura de controle `for while`.
{% endhint %}

## As outras estruturas de repetição

O Python permite a construção de estruturas de repetição em outros formatos. Vamos ver alguns destes casos:

### Iterando uma lista&#xD;

```python
# Definindo uma lista de carros
carros = ['Toyota', 'Honda', 'Ford']

# Usando um loop for para percorrer a lista e imprimir cada carro
for carro in carros:
    print(carro)
```

```cmd
Toyota
Honda
Ford
```

### Iterando uma string&#xD;

```python
for carro in 'carros':
    print(carro)
```

```cmd
c
a
r
r
o
s
```

### Rastreando o índice da lista&#xD;

```python
# Definindo uma lista de cores
cores = ['vermelho', 'verde', 'azul']

# Usando um loop for com enumerate para percorrer a lista e seus índices
for indice, cor in enumerate(cores):
    print(f'Índice {indice}: {cor}')
```

```cmd
Índice 0: vermelho
Índice 1: verde
Índice 2: azul
```

### Percorrendo um dicionário&#xD;

```python
notas = {
    'Potuguês': 7, 
    'Matemática': 9, 
    'Lógica': 7, 
    'Algoritmo': 7
}

for chave, valor in notas.items():
    print(f'{chave}: {valor}')
```

```cmd
Potuguês: 7
Matemática: 9
Lógica: 7
Algoritmo: 7
```

### Compressão de lista&#xD;

```python
a = [2,3,4,5,6]

b = [elemento ** 2 for elemento in a]

print(b)
```

```cmd
[4, 9, 16, 25, 36]
```

### Exemplo Resolvido 1&#xD;

_Você precisa escrever um programa em Python que calcule a soma dos números pares de_ $$1$$ _a_ $$n$$_, onde_ $$n$$ _é um número inteiro fornecido pelo usuário. O programa deve usar uma estrutura de repetição `for` para iterar sobre os números de_ $$1$$ _a_ $$n$$ _e somar apenas os números pares._

Lembrando que um número par é aquele que quando dividido por dois tem resto zero.

```python
# Solicitar ao usuário que insira um número inteiro positivo N
limite = int(input("Digite um número inteiro positivo N: "))

# Inicializar a variável para armazenar a soma dos números pares
somaPares = 0

# Usar um loop for para iterar de 1 a N (inclusive)
for numero in range(1, limite + 1):
    # Verificar se o número atual é par
    if numero % 2 == 0:
        # Se for par, adicionar à soma total
        somaPares += numero

# Exibir a soma total dos números pares
print(f"A soma dos números pares de 1 a {N} é: {somaPares}")
```

```cmd
Digite um número inteiro positivo N: 10
A soma dos números pares de 1 a 10 é: 30
```

## Referências

| Código | Referência                                                                                                |
| ------ | --------------------------------------------------------------------------------------------------------- |
| \[1]   | Lopes A, Garcia G. Introdução à programação: 500 algoritmos resolvidos. Rio de Janeiro (RJ): Campus; 2002 |
