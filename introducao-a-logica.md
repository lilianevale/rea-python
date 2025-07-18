# Introdução à lógica

## Representação de algoritmos

A lógica pode ser explicada como uma sequência coerente de ideias, ou um modo pelo qual acontecimentos se encadeiam naturalmente \[1]. Então o que seria a lógica de programação?

{% hint style="info" %}
Segundo Forbellone e Eberspächer \[2] a lógica de programação poderia ser descrita como um uso correto, da ordem da razão e de processos de raciocínio e simbolizações formais na programação de computadores.
{% endhint %}

Normalmente a utilização de computadores sempre envolve de forma direta ou indireta o uso dos chamados algoritmos. Estes podem ser definidos como um procedimento computacional bem definido que toma algum valor ou conjunto de valores como entrada e produz algum valor ou conjunto de valores como saída \[3].\
\
Imaginemos que desejamos montar um computador desktop \[2]. Qual seria uma forma lógica de fazer está montagem do equipamento?\
\
Para isso vamos utilizar a função `print` para montar esse algoritmo em formato de pseudocódigo.

```python
print("1. Receber as peças")
print("2. Montar o CPU")
print("3. Montar os periféricos")
print("4. Ligar o estabilizador")
print("5. Testar o computador")
```

```cmd
1. Receber as peças
2. Montar o CPU
3. Montar os periféricos"
4. Ligar o estabilizador
5. Testar o computador
```

Os algoritmos podem ser escritos em diversos paradigmas. Nesse curso utilizaremos na maioria dos casos o paradigma procedural (também chamado de paradigma imperativo) por ser de uso geral e amplamente empregado para aqueles que desejam iniciar na área de métodos numéricos.\
\
Basicamente neste modelo de programação nosso algoritmo conterá uma lista de instruções que são executadas passo a passo na ordem previamente descrita. Logo para um algoritmo atingir o seu funcionamento pleno deve ser baseado em uma lógica, ou um conjunto de passos que tornem aquela sequência adequada ao problema estudado.\
\
A representação dos algoritmos pode ser feita de diversas formas, são exemplos: (a) Fluxograma; (b) Pseudocódigo; e (c) Diagrama de Chapin. Neste texto as formas mais utilizadas serão o fluxograma e o pseudocódigo.

## Dados e tipos de variáveis

Trabalhar com algoritmos está intuitivamente ligado a manipulação de dados. Segundo Lopes e Garcia \[4] uma variável é um local na memória principal, isto é, um endereço que armazena um conteúdo. Em linguagens de alto nível é permitido dar nome a esse endereço de forma a facilitar o processo de programação. Chamaremos esse local que endereça esse espaço na memória de variável.\
\
Em Python podemos determinar o endereço de memória com a função `id()`. Vejamos um exemplo:

```python
h = 50
enderecoRam = id(h)
print("Endereço de memória = ", enderecoRam)
```

```cmd
Endereço de memória = 94820313464864
```

O Python suporta diversos tipos de variáveis, porém vamos comentar aqui 6 tipos de variáveis que são bastante empregados no dia dia dessa linguagem:

1. Valores numéricos: Nesse tipo o Python suporta inteiros, ponto flutuante e complexos;
2. Texto;
3. Dicionários;
4. Listas;
5. Tuplas;
6. Booleanos.

### Exemplo Resolvido 1&#xD;

_Crie duas variáveis_ **x** _e **y** na linguagem Python e transforme os valores de inteiros para ponto flutuante._

```python
# Criando duas variáveis x e y com valores inteiros
x = 10
y = 20

# Convertendo os valores de inteiros para ponto flutuante
k = float(x)
m = float(y)

# Imprimindo os valores atualizados das variáveis
print("Valor de x:", x, "tipo: ", type(x), "Valor de k:", k, "tipo: ", type(k))
print("Valor de y:", y, "tipo: ", type(y), "Valor de m:", m, "tipo: ", type(m))
```

```cmd
Valor de x: 10 tipo:  <class 'int'> Valor de k: 10.0 tipo:  <class 'float'>
Valor de y: 20 tipo:  <class 'int'> Valor de m: 20.0 tipo:  <class 'float'>
```

Aqui precisamos fazer algumas observações sobre a função `print`. Está função pode ter vários modelos de sintaxe e padrões. Por exemplo se desejássemos pular uma linha a cada texto utilizariamos a sintaxe  no local que precisamos pular a linha.

```python
print("Valor de x:", x, "\n tipo: ", type(x), "\n Valor de k:", k, "\n tipo: ", type(k))
print("Valor de y:", y, "\n tipo: ", type(y), "\n Valor de m:", m, "\n tipo: ", type(m))
```

```cmd
Valor de x: 10 
 tipo:  <class 'int'> 
 Valor de k: 10.0 
 tipo:  <class 'float'>
Valor de y: 20 
 tipo:  <class 'int'> 
 Valor de m: 20.0 
 tipo:  <class 'float'>
```

### Exemplo Resolvido 2&#xD;

_Escreva um algoritmo que permita inserir o nome de um usuário, seu peso e sua altura e seja então informado o **IMC** do usuário. Determine que as variáveis numéricas possuam formatação tipo ponto flutuante._

```python
# Entrada dos dados
nome = input("Digite o seu nome: ")
altura = float(input("Digite a sua altura em metros: "))
peso = float(input("Digite o seu peso em quilogramas: "))

# IMC
imc = peso / altura ** 2

# Imprimindo os valores atualizados das variáveis
print(f"{nome}, o seu IMC é: {imc:.2f}")
```

```cmd
Digite o seu nome: Wanderlei
Digite a sua altura em metros: 1.72
Digite o seu peso em quilogramas: 90
Wanderlei, o seu IMC é: 30.42
```

{% hint style="info" %}
Veja que ao utilizar a função `input()` foi necessário converter o tipo de dado. Neste caso a função supracitada lê qualquer dado digitado via teclado como uma _string_. Portanto é necessário fazer a conversão quando um tipo numérico for empregado.
{% endhint %}

### Exemplo Resolvido 3&#xD;

_Crie uma única variável que armazene os metadados (autores, ISBN, edição, etc) de um livro qualquer. Para este exemplo utilize o a referência Lopes e Garcia \[4]._

Para criar estes metadados vamos usar uma variável do tipo dicionário. Esta variável é uma coleção de elementos chave-valor. Os dicionários são uteis para sair de problemas de listas encadeadas que dependendo do problema a ser resolvido pode gerar uma "algoritmização" bem complexa.\
\
A estrutura do dicionário será descrita da seguinte forma `dicionario = {'chave': valor}`. Vamos aplicar ao nosso exemplo.

```python
# Criando os metadados do livro

biblioteca = {
                'livro1': {
                           'autores': 'Lopes A - Garcia G', 
                           'editora': 'GENLTC', 
                           'pag': 488, 
                           'ISBN': 8535210199
                           }
             }
```

Veja que neste exemplo encadeamos dois dicionários para proposição dos metadados. Caso eu usuário quisesse adiconar mais livros era possível?

{% hint style="info" %}
Sim, pois bastaria criar a chave `'livro2'` e dar seguimento ao preenchimento de novos dicionários contendo outros metadados.
{% endhint %}

Como eu poderia por exemplo fazer a verificação do valor de uma chave dentro do dicionário?!

```python
# Buscando a chave livro1

livro1 = biblioteca['livro1']
print(livro1)
```

```cmd
{'autores': 'Lopes A - Garcia G', 'editora': 'GENLTC', 'pag': 488, 'ISBN': 8535210199}
```

E se precisarmos buscar uma informação dentro da chave `'livro1'`. Como poderiamos fazer isso sem criar uma variável extra?! Neste caso vamos usar o exemplo da busca dos autores do livro 1.

```python
autores = biblioteca['livro1']['autores']
print(autores)
```

```cmd
Lopes A - Garcia G
```

### Exemplo Resolvido 4&#xD;

_Crie uma sequência de valores numéricos pares sem usar diversas variáveis para armazenar essa sequência. Use apenas uma variável._

Para este exemplo vamos usar o conceito de lista que também é uma coleção de valores ordenados e separados por vírgula. Vejamos a resolução do exemplo.

```python
# Lista de valores pares

pares = [2, 4, 6, 8, 10]
print(pares[2])
```

```cmd
6
```

{% hint style="info" %}
Veja que o valor acessado foi a posição **2** da lista ou seja a terceira posição.
{% endhint %}

Existem outras possibilidades para se trabalhar com listas aqui vamos exemplificar o método `.append()`. Este métodos nos ajudará a adicionar itens a lista. No caso todo item adicionado será colocado ao final dessa lista. Vejamos a adição do valor 12 a lista.

```python
# Lista de valores pares

pares.append(12)
print('nova lista completa: ', pares, 'valor adicionado: ', pares[-1])
```

```cmd
nova lista completa:  [2, 4, 6, 8, 10, 12] valor adicionado:  12
```

{% hint style="info" %}
A referência `lista[-1]` é o acesso a última posição da lista. A visualização regressiva também é valida: `lista[-2] = 10` e `lista[-3] = 8`.
{% endhint %}

### Exemplo Resolvido 5&#xD;

_Crie uma variável que armazene a latitude e longitude de uma cidade. Use apenas uma variável e além disso considere que estes valores não podem ser alterados._

Para este exemplo vamos usar o conceito de tupla que também é uma coleção de valores porém estes valores são "imutáveis". Vejamos a resolução do exemplo.

```python
# Lista de valores de latitude e longitude da cidade de Catalão - GO

coordenadas = (-18.1721, -47.9415)
print(' longitude: ', coordenadas[1], '\n', 'tipo variável: ', type(coordenadas))
```

```cmd
longitude:  -47.9415 
tipo variável:  <class 'tuple'>
```

{% hint style="info" %}
Tuplas não podem ter seus valores modificados. Caso desejamos mudar o valor da posição `[0]` da lista aparecerá um erro em tela do seguinte tipo `'tuple' object does not support item assignment`.
{% endhint %}

```python
# Modificando a posição [0]

coordenadas = (-18.1721, -47.9415)
coordenadas[0] = 10
```

```cmd
---------------------------------------------------------------------------
TypeError                                 Traceback (most recent call last)
<ipython-input-20-a868f0f769eb> in <cell line: 2>()
      1 coordenadas = (-18.1721, -47.9415)
----> 2 coordenadas[0] = 10

TypeError: 'tuple' object does not support item assignment
```

## Mais algumas dicas

Algumas das variáveis apresentadas anteriormente permitem a utilização de métodos e funções que podem facilitar o trabalho. Vamos ver alguns destes exemplos nesta seção.

### Contagem de itens em uma tupla&#xD;

```python
"""
Contando os itens dentro de uma tupla com o método .count()
"""

tuplaMeses = ('janeiro', 'janeiro', 'fevereiro', 'fevereiro', 'janeiro', 'janeiro', 'março')
print('contagem de itens de janeiro: ', tuplaMeses.count('janeiro'))
```

```cmd
contagem de itens de janeiro:  4
```

### Verificação do índice em uma tupla&#xD;

```python
"""
Verificando o índice do mês de fevereiro em uma tupla com o método .index()
"""

tuplaMeses = ('janeiro', 'fevereiro', 'março', 'abril')
indice = tuplaMeses.index('fevereiro')
print ('indice fevereiro: ', indice)
```

```cmd
índice fevereiro:  1
```

### Tamanho de tuplas e listas&#xD;

```python
"""
Verificando o tamanho de uma tupla ou lista com a função len()
"""

estudante = ('Miguel', 29, 1990, 'Brasil')
print('tamanho: ', len(estudante))
```

```cmd
tamanho: 4
```

## Referências

| Código | Referência                                                                                                                                              |
| ------ | ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| \[1]   | Michaelis. Dicionário escolar língua portuguesa. 2018.                                                                                                  |
| \[2]   | Forbellone ALV, Eberspächer HF. Lógica de programação: a construção de algoritmos e estruturas de dados. 3. ed. São Paulo: Pearson Prentice Hall; 2007. |
| \[3]   | Cormen TH. Algoritmos: teoria e prática. Rio de Janeiro: Campus; 2012                                                                                   |
| \[4]   | Lopes A, Garcia G. Introdução à programação: 500 algoritmos resolvidos. Rio de Janeiro (RJ): Campus; 2002                                               |
