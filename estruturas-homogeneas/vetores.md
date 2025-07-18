# Vetores

## Vetores

Em Python, um vetor geralmente se refere a uma estrutura de dados que armazena uma coleção ordenada de valores, também conhecidos como elementos. Esses elementos podem ser de tipos de dados diversos, como números inteiros, números de ponto flutuante, strings, objetos personalizados, ou até mesmo outras estruturas de dados. Os vetores em Python são frequentemente implementados usando listas.

{% hint style="warning" %}
Um vetor é uma coleção sequencial de elementos do mesmo tipo de dados com um único nome identificador. As listas Python são semelhantes aos vetores em outras linguagens, mas não estão restritas a um único tipo de dados. O termo "vetor" conforme usado neste capítulo geralmente também se aplica a listas Python, salvo indicação em contrário.
{% endhint %}

Por exemplo, você pode criar um vetor de números inteiros em Python da seguinte forma:

```python
vetor = [1, 2, 3, 4, 5]
```

Neste exemplo, `vetor` é uma lista que contém cinco elementos inteiros. Você pode acessar os elementos individuais do vetor usando índices, como `vetor[0]` para obter o primeiro elemento, `vetor[1]` para obter o segundo elemento, e assim por diante.\
\
Os vetores em Python são flexíveis e podem conter elementos de tipos diferentes, tornando-os uma estrutura de dados versátil para muitos cenários de programação. Além disso, você pode realizar várias operações, como adicionar elementos, remover elementos, fazer iterações sobre os elementos, e muito mais com listas em Python.

```python
# Crie um vetor de notas
notas = [8.5, 9.0, 7.5, 6.0]

# Calcule a média das notas
soma = sum(notas)  # Soma de todas as notas
quantidade = len(notas)  # Número de notas
media = soma / quantidade  # Cálculo da média

# Exiba a média
print("Notas:", notas)
print("Média das notas:", media)
```

```cmd
Notas: [8.5, 9.0, 7.5, 6.0]
Média das notas: 7.75
```

Neste exemplo, primeiro criamos um vetor chamado `notas` que contém as notas de um conjunto de alunos. Em seguida, usamos a função `sum()` para calcular a soma de todas as notas e a função `len()` para obter o número de notas no vetor. Finalmente, calculamos a média dividindo a soma pelo número de notas e a exibimos na tela.

{% hint style="info" %}
Você pode modificar o vetor `notas` e adicionar quantas notas desejar para calcular a média de diferentes conjuntos de notas.
{% endhint %}

## Listas

Uma lista em Python é uma estrutura de dados que permite armazenar uma coleção ordenada de elementos semelhante a um vetor. Esses elementos podem ser de diferentes tipos de dados, como números, strings, objetos personalizados, entre outros. As listas são mutáveis, o que significa que você pode adicionar, remover e modificar elementos após a criação da lista. Elas são representadas por colchetes `[ ]` e os elementos são separados por vírgulas. Por exemplo:

```python
minhaLista = [1, 2, 3, 'quatro', 5.0]
```

Neste exemplo, `minhaLista` é uma lista que contém uma variedade de tipos de dados. Você pode acessar os elementos da lista por meio de índices (para acessar o primeiro elemento o índice é 0). As listas são uma estrutura de dados fundamental em Python e são amplamente utilizadas para armazenar e manipular conjuntos de dados.

### Os métodos aplicáveis a listas

### append&#xD;

O método `append` é usado para adicionar um elemento ao final de uma lista. Não é necessário especificar um índice, pois o elemento é sempre adicionado ao final da lista. Exemplo:

```python
minhaLista = [1, 2, 3]
minhaListaNova = minhaLista
minhaLista.append(4)
print('lista antes: ', minhaLista, '\nlista agora: ', minhaListaNova)
```

```cmd
lista antes:  [1, 2, 3, 4] 
lista agora:  [1, 2, 3, 4]
```

{% hint style="warning" %}
Veja que o resultado ficou estranho e a lista apresentou o mesmo valor antes e depois. Com a atribuição `minhaListaNova = minhaLista` você está atribuindo a referência da lista `minhaLista` à variável `minhaListaNova`. Isso significa que ambas as variáveis apontam para a mesma lista na memória, em vez de criar uma cópia separada da lista. Para isso vamos usar o método `.copy()` para fazer a copia da lista e não do caminho.&#x20;
{% endhint %}

Vejamos:

```python
minhaLista = [1, 2, 3]
minhaListaNova = minhaLista.copy()
minhaLista.append(4)
print('lista antes: ', minhaLista, '\nlista agora: ', minhaListaNova)
```

```cmd
lista antes:  [1, 2, 3, 4] 
lista agora:  [1, 2, 3]
```

### insert&#xD;

O método `insert` é usado para adicionar um elemento em uma posição específica da lista. Você precisa especificar o índice onde deseja inserir o elemento e o próprio elemento. Vejamos um exemplo:

```python
minhaLista = [1, 2, 3]
indice = 1
valor = 4
minhaLista.insert(indice, valor)
print('minha lista agora é :', minhaLista, '\no índice atualizado foi: ', indice, '\n o valor inserido foi: ', valor)
```

```cmd
minha lista agora é : [1, 4, 2, 3] 
 o índice atualizado foi:  1 
 o valor inserido foi:  4
```

### pop&#xD;

O método `pop` é usado para remover um elemento de uma lista com base no índice especificado. Ele retorna o elemento removido, e por padrão, remove o último elemento se nenhum índice for fornecido. Exemplo:

```python
minhaLista = [1, 2, 3, 4]
elemento_removido = minhaLista.pop(1)
print('minha lista agora é: ', minhaLista)
```

```cmd
minha lista agora é:  [1, 3, 4]
```

### remove&#xD;

O método `remove` é usado para eliminar a primeira ocorrência de um elemento específico da lista. Você precisa especificar o valor que deseja remover. Vejamos um exemplo:

```python
minhaLista = [1, 2, 3, 2, 4]
minhaLista.remove(2)
print('minha lista agora é :', minhaLista)
```

```cmd
minha lista agora é : [1, 3, 2, 4]
```

### Exemplo Resolvido 1&#xD;

_Dada uma lista de_ $$n$$ _elementos você deve criar um algoritmo que separa os números pares e ímpares em outras listas diferentes._

Lembrando que um número par é aquele que quando dividido por dois tem resto zero.

```python
# lista inicial
lista = [2, 3, 6, 8, 9, 10, 12, 15]

# novas listas onde vão ser separados os valores
pares = []
impares = []

for numero in lista:
    if numero % 2 == 0:
        pares.append(numero)
    else:
        impares.append(numero)

# Exibir listas
print("Números pares:", pares)
print("Números ímpares:", impares)
```

```cmd
Números pares: [2, 6, 8, 10, 12]
Números ímpares: [3, 9, 15]
```

### Exemplo Resolvido 2&#xD;

_Dado uma lista de convidados para uma festa faça um algoritmo que remove os nomes dos convidados desta lista a medida que eles chegam na festa. É necessário que o processo seja repetido até a lista esgotar ou que o administrador encerre o programa._

```python
# lista de convidados
convidados = ["Alice", "Bob", "Charlie", "David", "Eve"]

while True:
    # Exibe a lista de convidados atual
    print("\nLista de Convidados: ", convidados)

    # Solicita ao usuário que digite o nome a ser removido
    nomeRemover = input("Digite o nome que deseja remover (ou 'fim' para sair): ")

    if nomeRemover.lower() == 'fim':
        print("Programa encerrado.")
        break

    # Verifica se o nome está na lista
    if nomeRemover in convidados:
        convidados.remove(nomeRemover)
        print(nomeRemover, "foi removido da lista.")
    else:
        print("Nome não encontrado na lista.")
```

```cmd
Lista de Convidados:  ['Alice', 'Bob', 'Charlie', 'David', 'Eve']
Digite o nome que deseja remover (ou 'fim' para sair): Alice
Alice foi removido da lista.

Lista de Convidados:  ['Bob', 'Charlie', 'David', 'Eve']
Digite o nome que deseja remover (ou 'fim' para sair): Bob
Bob foi removido da lista.

Lista de Convidados:  ['Charlie', 'David', 'Eve']
Digite o nome que deseja remover (ou 'fim' para sair): fim
Programa encerrado.
```

{% hint style="info" %}
Neste exemplo foi usado o operador de pertencimento `in` que detecta se o nome existe na lista. O comando `break` é utilizado para sair do _looping_ visto que a condição do `while` é sempre verdadeira. O método `.lower()` serve para deixar a digitação do usário em caixa baixa.
{% endhint %}
