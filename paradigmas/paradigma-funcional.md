# Paradigma funcional

## Paradigma funcional

Watt \[ISBN 0-470-85320-4] define que linguagem funcional é aquela onde a unidade báisca são as funções, normalmente unidades menores de um determinado problema. A atribuição de valores das variáveis se dá por meio destas funções e/ou combinação de funções. Aqui no Python as funções podem ser passadas como argumentos de outras funções e assim por diante. Fato que facilita bastante a programação e modelagem de arquiteturas de um _softwares_.

Para construir funções em Python é necessário usar a sintaxe `def nome_funcao(args,):`. Além disso utilizaremos o padrão `snake_case` para declarar funções em Python. Para exemplificar o uso deste paradigma vamos construir uma função que devolve a soma de dois números.

```python
def soma_dois_numeros(x, y):
    return x + y
```

Aqui faremos uma observação da instrução `return`. Esta instrução tem como objetivo devolver ao código principal o objeto de referência declarado na sequência da instrução. No caso deste exemplo o código devolve um objeto do tipo _float_. É válido salientar que em Python funções não precisam sempre ter retornos. Por exemplo você poderia utilizar uma função para retornar uma impressão ao longo de um processo. Vejamos um caso:

```python
# Construção da função
def aviso_codigo():
    print("eu passei por aqui")

# Chamada da função
aviso_codigo()
```

```cmd
eu passei por aqui
```

### Exemplo Resolvido 1&#xD;

_Construa uma função em Python que permita especificar ou não o argumento de entrada para dizer uma msg de Olá para um usuário._

```python
def saudacao(nome = "Usuário"):
    print(f"Olá, {nome}!")

saudacao()           
saudacao("Maria")    
```

```cmd
Olá, Usuário!
Olá, Maria!
```

Podemos verificar que o Python permite que você atribua um valor padrão aos argumentos de entrada da função. Neste caso basta utilizar a sintaxe `nome = valorDesejado` na criação da função. Logo se o usuário necessitar a atribuição de um argumento específico ele será declarado na chamada do função no código principal.

JESSY AQUI VOCÊ PODE FAZER ASSIM PARA FICAR MAIS LEGAL\
VOCÊ CONTA UMA PEQUENA TEORIA SOBRE O ARGS E FAZ O EXEMPLO DO KWARGS..\
AQUI O ESSNECIAL É VOCÊ MOSTRAR ESSA DIFERENÇA ENTRE ARGS E KWARGS E CLARO O EXEMPLO\
VEJA COMO FIZ ACIMA\
Funções com número variável de argumentos:\
Em Python, args (argumentos posicionais) e kwargs (argumentos nomeados) são usados para passar argumentos para funções de diferentes maneiras.

#### Argumentos Posicionais (args):

Os argumentos posicionais são passados para uma função na ordem em que são definidos. Eles são armazenados em uma tupla dentro da função. Isso significa que a orde\
em que você os passa é crucial.

```python
def somar_numeros(*args):
    total = 0
    for num in args:
        total += num
    return total

print(somar_numeros(1, 2, 3, 4, 5))  # Output: 15
```

#### Argumentos Nomeados (kwargs):

Os argumentos nomeados são passados para uma função usando um formato de chave-valor, onde você especifica o nome do argumento ao passá-lo para a função. Eles são armazenados em um dicionário dentro da função.

```python
def saudacao(nome, mensagem):
    return f"Olá, {nome}! {mensagem}"

mensagem_personalizada = saudacao(nome="Alice", mensagem="Como você está?")
print(mensagem_personalizada) 
```

```cmd
Saída: Olá, Alice! Como você está?
```

### Exemplo usando \*args e \*\*kwargs:

Você também pode usar \*args (asterisco args) e \*\*kwargs (dois asteriscos kwargs) para passar um número variável de argumentos posicionais e nomeados, respectivamente.

```python
def imprimir_argumentos(*args, **kwargs):
    print("Argumentos posicionais:", args)
    print("Argumentos nomeados:", kwargs)

imprimir_argumentos(1, 2, 3, nome="Alice", idade=30)
```

```cmd
Argumentos posicionais: (1, 2, 3)
Argumentos nomeados: {'nome': 'Alice', 'idade': 30}
```

Ao trabalhar com algoritmos é importante entendermos o escopo das variáveis. O escopo determinará onde a variável pode ser empregada no algoritmo. Em suma, variáveis definidas dentro de uma função normalmente têm um escopo local, o que significa que elas só existem dentro da função em que ela foi definida. Variáveis definidas fora da função, na `main` por exemplo, têm escopo global. Vejamos o exemplo:

```python
# Variável global
globalVar = 10

def minha_funcao():
    # Acessando a variável global dentro da função
    print("Dentro da função:", globalVar)

# Chamando a função
minha_funcao()

# Acessando a variável global fora da função
print("Fora da função:", globalVar)
```

```cmd
Dentro da função: 10
Fora da função: 10
```

Agora veremos a situação de um escopo local para uma variável qualquer que está alocada dentro de uma função.

```python
def minha_funcao():
    # Variável local
    localVar = 5
    print("Dentro da função:", localVar)

# Chamando a função
minha_funcao()

# Tentando acessar a variável local fora da função causará um erro
print("Fora da função:", localVar)
```

```cmd
Dentro da função: 5
---------------------------------------------------------------------------
NameError                                 Traceback (most recent call last)
/tmp/ipykernel_4869/4002507309.py in <module>
      8 
      9 # Tentando acessar a variável local fora da função causará um erro
---> 10 print("Fora da função:", localVar)

NameError: name 'localVar' is not defined
```

{% hint style="warning" %}
Quando o Python tentar acessar a variável localVar o interpretador acursará um erro informando que a variável não está definida.
{% endhint %}

### Exemplo Resolvido 2&#xD;

_Utilize o conceito de escopo de variável para alterar o valor de uma variável global dentro de uma função._

```python
def saudacao(nome="Usuário"):
    print(f"Olá, {nome}!")

saudacao()          
saudacao("Maria")              
```

```cmd
Output: Olá, Usuário!
Output: Olá, Maria!
```

O Python suporta recursão, que é uma propriedade interessante para construção de algoritmos com reaproveitamento de código. O conceito básico é permitir que uma função chame a ela mesmo dentro dentro de si, porém para entendermos o conceito de recursividade precisamos nos concentrar na pilha de execução do algoritmo.

{% hint style="warning" %}
A chave do conceito de recursividade é encontrar o caso básico e assim definir o critério de parada.
{% endhint %}

Imaginemos um caso de recursividade com uma contagem regressiva. Primeiramente vamos considerar o caso básico

```python
def contagem_regressiva(n):
    while(n):
        print(n)
        n = n - 1
    print('Decolar!')

contagem_regressiva(5)
```

```cmd
5
4
3
2
1
Decolar!
```

A recursividade segue o mesmo padrão de uma pilha em estrutura de dados. A lógica é do tipo LIFO (_Last In First Out)_), logo o primeiro elemento é o último a sair da pilha. Vamos ver o exemplo de uma calculadora.

```python
def calc():                             # Pilha de execução 1
    x = 1; y = 2                        # Pilha de execução 3
    impress()                           # Pilha de execução 4
    print('soma: ', x + y)              # Pilha de execução 5
    print('soma realizada')             # Pilha de execução 6
                                        # Pilha de execução 7
def impress():                          # Pilha de execução 8
    print('vou passar na soma')         # Pilha de execução 9
                                        # Pilha de execução 10
calc()                                  # Pilha de execução 11
```

$$t = 1:$$`__main__`\\

$$t = 2:$$ `__main__ linha 11`

$$t = 3:$$ `__main__ linha 11 linha 8`&#x20;

{% hint style="warning" %}
O Python cria sempre uma função **main** que sempre será a primeira a entrar na pilha de execução e em sequência as outras funções são chamadas. No caso do exemplo dado a pilha de execução irá eliminar a linha 8 e linha 11 dá pilha até voltar a **main** e encerrar a execução.
{% endhint %}

Depois de entender a questão da pilha temos que lembrar que para qualquer processo recursivo deverá existir sempre o caso básico e o critério de interrupção para finalização da chamada. Retomando o algoritmo de contagem regressiva.

```python
def contagem_regressiva(n):
    if n == 0:
        print('Decolar!')
    else:
        print(n)
        contagem_regressiva(n - 1)

contagem_regressiva(5)
```

```cmd
5
4
3
2
1
Decolar!
```

### Exemplo Resolvido 3&#xD;

```python
def fatorial(n):
    if n == 0 or n == 1:
        return 1
    else:
        return n * fatorial(n - 1)

# Exemplo de uso
numero = 5
resultado = fatorial(numero)
print(f"O fatorial de {numero} é: {resultado}")

# O fatorial de 5 é: 120
```

O Python tbm suporta outros tipos de funções, como por exemplo a função lambda (também conhecidas como funções anônimas) que podem ser definidas em uma única linha. São úteis para tarefas simples e rápidas. Em Python, as funções anônimas são funções sem um nome associado. Diferentemente das funções tradicionais definidas com a palavra-chave `def`, as funções anônimas são criadas usando a palavra-chave padrão `lambda`. Vejamos um exemplo de aplicação:

```python
dobro = lambda x: x * 2
print(dobro(5))
```

```cmd
10
```

### Type Hints

Type hints (dicas de tipo) em Python são uma maneira de adicionar informações sobre os tipos de dados esperados nas funções, métodos e variáveis, tornando o código mais legível e ajudando os desenvolvedores a entenderem o que é esperado em termos de tipos. Embora Python seja uma linguagem de tipagem dinâmica, as type hints não afetam o comportamento do código em tempo de execução, mas são ferramentas poderosas para melhorar a clareza e a manutenção do código.

As type hints foram introduzidas na PEP 484 e foram expandidas nas versões posteriores do Python. Você pode usar type hints usando a sintaxe de anotação de tipo, que informa quais tipos de dados são esperados ou retornados.

Aqui estão alguns exemplos de como usar type hints:

#### Anotações de Tipo Básicas:

```python
def somar(a: int, b: int) -> int:
    return a + b

resultado = somar(3, 5)
```

#### Tipos Compostos:

```python
from typing import List, Tuple

def processar_lista(lista: List[int]) -> Tuple[int, int]:
    soma = sum(lista)
    media = soma / len(lista)
    return soma, media
```

#### Valores Opcionais:

```python
def cumprimentar(nome: str, sobrenome: str = "") -> str:
    if sobrenome:
        return f"Olá, {nome} {sobrenome}!"
    else:
        return f"Olá, {nome}!"
```

#### Tipos Personalizados:

```python
class Pessoa:
    def __init__(self, nome: str, idade: int):
        self.nome = nome
        self.idade = idade
```

Dicas de Tipos para Funções e Métodos:

```python
from typing import Callable

def aplicar_funcao(funcao: Callable[[int, int], int], a: int, b: int) -> int:
    return funcao(a, b)
```

#### Union Types (Tipos de União):

```python
from typing import Union

def dobrar(numero: Union[int, float]) -> Union[int, float]:
    return numero * 2
```

As type hints são uma ferramenta valiosa para melhorar a legibilidade, a manutenção e a detecção de erros no código, especialmente em projetos maiores e em colaborações entre desenvolvedores.

Em Python, as palavras "funções" e "métodos" são frequentemente usadas para descrever blocos de código reutilizáveis que executam tarefas específicas. No entanto, há uma diferença fundamental entre esses dois conceitos:

### Funções:

Uma função em Python é um bloco de código nomeado que pode receber argumentos, executar um conjunto de instruções e retornar um valor. Funções são usadas para organizar o código em tarefas individuais e reutilizáveis. Elas podem ser definidas em qualquer lugar no código e chamadas sempre que necessário. Funções não estão ligadas a nenhuma classe específica e são independentes.

Exemplo de definição e uso de função:

```python
def somar(a, b):
    return a + b

resultado = somar(3, 5)
print(resultado) 
```

```cmd
8
```

### Métodos:

Um método em Python é uma função que pertence a um objeto específico (instância de classe) e opera nesse objeto. Métodos são definidos dentro de uma classe e podem acessar os atributos e outros métodos daquela classe. Eles têm acesso implícito ao objeto no qual estão sendo chamados, o que permite que eles trabalhem com dados específicos da instância.

Exemplo de definição e uso de método:

```python
class Calculadora:
    def somar(self, a, b):
        return a + b

calc = Calculadora()
resultado = calc.somar(3, 5)
print(resultado)
```

```cmd
8
```

Em resumo, a principal diferença entre funções e métodos é que as funções são blocos de código reutilizáveis e independentes, enquanto os métodos são funções específicas para um objeto (instância de classe) e operam em seu contexto, podendo acessar seus atributos e outros métodos.
