# Estruturas de seleção

## O comando `if-else`

Durante o processo de programação, é comum nos depararmos com a necessidade de executar determinada parte do bloco de código somente caso uma condição espeficia seja atendida. Nestes casos, faz-se necessário utilizar estruturas da linguaguem de programação que permitam realizar verificações e decisões lógicas. Em Python, tais estruturas são denominadas estruturas condicionais e alternativas, e permitem com que um programa tome decisões lógicas com base em condições especificadas. O Quadro 4.1 apresenta um resumo dessa estrutura no Python.

Quadro 4.1. Estrutura de seleção.

| Comando | Conceito                                                                                                 |
| ------- | -------------------------------------------------------------------------------------------------------- |
| `if`    | Se a condição for verdadeira executa o bloco de código.                                                  |
| `else`  | Executa um bloco de código alternativo se a condição do `if` não for verdadeira.                         |
| `elif`  | Verifica múltiplas condições sequencialmente e executa o bloco associado à primeira condição verdadeira. |

### if&#xD;

```python
idade = 18
if idade >= 18:
    print("Você é maior de idade.")
```

```cmd
Você é maior de idade.
```

### if-else&#xD;

```python
idade = 15
if idade >= 18:
    print("Você é maior de idade.")
else:
    print("Você é menor de idade.")
```

```cmd
Você é menor de idade.
```

### if-elif-else&#xD;

```python
nota = 85
if nota >= 90:
    print("sua nota é: A")
elif nota >= 80:
    print("sua nota é: B")
elif nota >= 70:
    print("sua nota é: C")
else:
    print("sua nota está abaixo de C")
```

```cmd
sua nota é: B
```

Estas estruturas de seleção podem apresentar seleção simples ou seleção compostas (também chamadas de encadeadas). As estruturas simples foram apresentadas acima. Agora vamos ver exemplos de estruturas encadeadas que são mais complexas.

```python
varA = 40
varB = 40
a = 10
b = 10

if (varA > 50):
    if (varB > 50):
        a = b + 80 
    else:
        a = b - 80
elif (varA <= 50):
    a += 35
    b += 35
    
print('valor de a: ', a, '\nvalor de b: ', b)
```

```cmd
valor de a:  45 
valor de b:  45
```

### Exemplo Resolvido 1&#xD;

_Crie um algoritmo que receba a idade de um jogador de futebol e classifique-o da seguinte forma:_

* 5 a 8 anos: Infantil;
* 9 a 13 anos: Juvenil A;
* 14 a 17 anos: Juvenil B;
* Maiores de 18 anos: Adulto.

Primeiro vamos usar a função `input` para permitir a digitação da idade pelo usuário.

```python
idade = int(input('Digite a idade do usuário: '))
```

Criando a regra da seleção dos atletas.

```python
if idade < 5:
    print("Classificação: Não pode ser atelta")
elif idade >= 5 and idade < 14: 
    print("Classificação: Juvenil A")
elif idade >= 14 and idade < 18: 
    print("Classificação: Juvenil B")
elif idade >= 18: 
    print("Classificação: Adulto")
```

Para um jogador de **20 anos** a resposta seria `Classificação: Adulto`.

{% hint style="warning" %}
É importante salientar que no Python é obrigatório o uso de `:` para finalizar comando da estrutura de controle `if else`.
{% endhint %}

## Dicas com `if-else`

O Python permite a colocação de uma instrução ternária para a condição `if-else`. Um operador ternário tem o seguinte padrão: `caso verdadeiro if condicao else caso falso`.

### Operador ternário&#xD;

```python
idade = 20

status = "Adulto" if idade >= 18 else "Menor de idade"
print(status)
```

```cmd
Adulto
```

### Exemplo Resolvido 1&#xD;

_Suponha que você está criando um programa para uma fábrica que produz peças de equipamentos eletrônicos. O programa precisa verificar a qualidade de cada peça produzida com base em determinados critérios (tamanho, peso, defeitos) e decidir se a peça está "aprovada" ou "rejeitada". A condição de validação "aprovada" é:_ $$tamanho \geq 10\text{ cm}$$ _`and`_ $$peso \geq 100\text{ g}$$  _`and`_ $$defeitos = 0\text{ rep}$$_._

```python
# Coleta de dados da peça produzida
tamanho = float(input("Digite o tamanho da peça (em cm): "))
peso = float(input("Digite o peso da peça (em gramas): "))
defeitos = int(input("Digite o número de defeitos na peça: "))

# Critérios para aprovação ou rejeição
if tamanho >= 10.0 and peso >= 100.0 and defeitos == 0:
    status = "Aprovada"
else:
    status = "Rejeitada"

# Exibição do status da peça
print(f"A peça está {status}.")
```

```cmd
Digite o tamanho da peça (em cm): 11
Digite o peso da peça (em gramas): 99
Digite o número de defeitos na peça: 0
A peça está Rejeitada.
```
