# Orientação a objetos

## Orientação a Objetos

A **Programação Orientada a Objetos (POO)** é uma forma de organizar o código que se inspira diretamente no mundo real. Ao invés de criar apenas funções soltas que manipulam dados, a POO propõe que tudo seja representado por **objetos**, cada um com suas próprias **características** (atributos) e **ações** (métodos).

Essa abordagem torna o código mais organizado, reutilizável e fácil de manter, principalmente em projetos maiores. É por isso que linguagens modernas como Python, Java e C++ adotam esse paradigma como base.

***

### O que é Programação Orientada a Objetos?

A Programação Orientada a Objetos é um **paradigma de programação** que organiza o software em torno de **objetos** — estruturas que encapsulam dados e comportamentos relacionados.

Você literalmente traduz elementos do mundo real para o código. Por exemplo, uma `ContaBancaria` tem atributos como `dono` e `saldo`, e métodos como `depositar()` e `sacar()`.

Vamos agora explorar os principais conceitos que formam a base da POO.

***

### Conceitos Básicos

#### Classe

Uma **classe** é como um projeto ou um molde para criar objetos. Ela define quais informações (atributos) e comportamentos (métodos) um objeto daquele tipo terá.

Imagine que você está criando um jogo. Você pode definir uma classe `Personagem` que sempre terá nome, vida e ataque. Cada personagem do jogo será uma instância dessa classe.

```python
class Pessoa:
    def __init__(self, nome, idade):
        self.nome = nome
        self.idade = idade

    def apresentar(self):
        print(f"Olá, meu nome é {self.nome} e tenho {self.idade} anos.")
```

***

#### Instância

Uma **instância** é um objeto real criado a partir de uma classe. Enquanto a classe é o molde, a instância é o produto final, com dados específicos.

No exemplo abaixo, criamos uma pessoa com nome "Ana" e idade 30. `p1` é uma instância da classe `Pessoa`.

```python
p1 = Pessoa("Ana", 30)
p1.apresentar()
```

***

#### Método

**Métodos** são funções definidas dentro de uma classe. Eles representam ações que os objetos daquela classe podem realizar. Todo método que manipula dados do próprio objeto usa `self` como primeiro parâmetro, que representa a instância atual.

```python
def apresentar(self):
    print(f"Olá, meu nome é {self.nome}")
```

Esse método faz parte da classe `Pessoa`, e quando chamado, acessa os atributos do próprio objeto.

***

#### Herança

A **herança** permite criar uma nova classe baseada em outra. Isso facilita a reutilização de código e a criação de estruturas mais organizadas. A classe "filha" herda os atributos e métodos da classe "pai" e ainda pode adicionar ou modificar comportamentos.

No exemplo abaixo, `Funcionario` herda de `Pessoa`, ou seja, todo funcionário também é uma pessoa, mas com um cargo adicional:

```python
class Funcionario(Pessoa):
    def __init__(self, nome, idade, cargo):
        super().__init__(nome, idade)
        self.cargo = cargo

    def apresentar(self):
        super().apresentar()
        print(f"Eu sou {self.cargo}.")
```

***

#### Polimorfismo

O **polimorfismo** é a capacidade de objetos de diferentes classes responderem de maneira diferente ao mesmo método. Isso permite usar uma interface comum para diferentes tipos de objetos, tornando o código mais flexível e reutilizável. Dessa forma, o polimorfismo permite que métodos com o mesmo nome se comportem de maneira diferente em classes distintas, simplificando o design do software e promovendo uma maior modularidade.

Por exemplo, podemos ter uma classe `Animal` com um método `fazer_som()`, e cada animal implementa esse método de maneira diferente:

```python
# Definindo a classe base
class Animal:
    def fazer_som(self): # método a ser sobrescrito
        pass

# Definindo classes filhas
class Cachorro(Animal):
    def fazer_som(self):
        return "Au Au!" # som do cachorro

class Gato(Animal):
    def fazer_som(self):
        return "Miau!" # som do gato
```

#### Métodos Estáticos e de Classe

Nem todos os métodos precisam acessar atributos da instância (`self`) ou da classe (`cls`). Quando isso acontece, usamos **métodos estáticos**, que são apenas funções organizadas dentro da classe.

Já os **métodos de classe** usam `cls` como primeiro argumento, e são úteis quando você quer modificar ou acessar a classe em si, não uma instância.

```python
class Util:
    @staticmethod
    def somar(a, b):
        return a + b

print(Util.somar(3, 4))  # 7
```

***

### Exemplo Prático: Conta Bancária

#### Passo 1: Criar a Classe Base

Vamos modelar uma **conta bancária**, com titular, saldo e métodos para sacar, depositar e ver o extrato:

```python
class ContaBancaria:
    def __init__(self, titular, saldo=0):
        self.titular = titular
        self.saldo = saldo

    def depositar(self, valor):
        if valor > 0:
            self.saldo += valor
            print(f"Depósito de R${valor:.2f} realizado.")
        else:
            print("Valor inválido para depósito.")

    def sacar(self, valor):
        if 0 < valor <= self.saldo:
            self.saldo -= valor
            print(f"Saque de R${valor:.2f} realizado.")
        else:
            print("Saldo insuficiente ou valor inválido.")

    def extrato(self):
        print(f"Titular: {self.titular} | Saldo: R${self.saldo:.2f}")
```

***

#### Testando

Criamos uma conta e usamos os métodos para realizar operações bancárias:

```python
conta1 = ContaBancaria("Maria")
conta1.depositar(500)
conta1.sacar(100)
conta1.extrato()
```

***

#### Herança: Conta Corrente com Limite

Agora, criamos uma nova classe `ContaCorrente`, que herda de `ContaBancaria`, mas permite saque com limite adicional:

```python
class ContaCorrente(ContaBancaria):
    def __init__(self, titular, saldo=0, limite=500):
        super().__init__(titular, saldo)
        self.limite = limite

    def sacar(self, valor):
        if valor <= self.saldo + self.limite:
            self.saldo -= valor
            print(f"Saque de R${valor:.2f} realizado com limite.")
        else:
            print("Saldo e limite insuficientes.")
```

#### Aplicando o Polimorfismo

Agora, podemos criar uma lista de contas e chamar o método `sacar()` de forma polimórfica. Cada conta sabe como se comportar, mesmo que o método tenha o mesmo nome:

```python
contas = [
    ContaBancaria("Carlos", 1000),
    ContaCorrente("Fernanda", 1000, 300)
]

for conta in contas:
    conta.sacar(1100)  # Chama o método sacar da classe correspondente
```

***

#### Método Estático para Validação

Métodos estáticos são úteis para funções auxiliares. Aqui, criamos um validador de valores:

```python
class Validador:
    @staticmethod
    def validar_valor(valor):
        return valor > 0
```

E usamos assim:

```python
if Validador.validar_valor(100):
    conta1.depositar(100)
```

***

### Recapitulando

| Conceito  | Explicação        | Exemplo                      |
| --------- | ----------------- | ---------------------------- |
| Classe    | Molde             | `class Pessoa:`              |
| Instância | Objeto criado     | `p1 = Pessoa("Ana", 30)`     |
| Método    | Função na classe  | `def apresentar(self):`      |
| Herança   | Reutilizar código | `class Funcionario(Pessoa):` |
| Estático  | Função utilitária | `@staticmethod`              |

***
