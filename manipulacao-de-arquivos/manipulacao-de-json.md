# Manipulação de json

## O que é um arquivo .json

Um arquivo JSON (JavaScript Object Notation) é um formato leve e legível por humanos usado para armazenar e trocar dados estruturados. Ele é frequentemente usado em comunicações entre um servidor e um cliente, armazenamento de configurações, intercâmbio de informações em APIs (interfaces de programação de aplicativos) e muito mais.

Ele é composto por uma coleção de pares chave-valor. Cada chave é uma sequência de caracteres que atua como um identificador exclusivo para um valor associado. O valor pode ser uma string (texto), número, booleano, objeto, array ou "null". Essa estrutura torna o JSON muito flexível para representar uma variedade de tipos de dados.

### Exemplo

```json
{
  "nome": "João",
  "idade": 30,
  "casado": false,
  "hobbies": ["leitura", "ciclismo"],
  "endereco": {
    "rua": "Rua das Flores",
    "numero": 123,
    "cidade": "Catalão"
  }
}
```

{% hint style="info" %}
Neste exemplo, temos um objeto JSON com várias chaves, cada uma delas mapeada para um valor correspondente. A chave "nome" tem o valor "João", a chave "idade" tem o valor numérico 30, a chave "casado" tem o valor booleano false e assim por diante. Além disso, a chave "hobbies" está associada a um array de strings e a chave "endereco" está associada a um objeto aninhado com suas próprias chaves e valores.
{% endhint %}

A simplicidade e legibilidade do JSON tornaram-no uma escolha popular para troca de dados entre diferentes plataformas e linguagens de programação. Ele é frequentemente usado em conjunto com JavaScript, mas também é amplamente suportado por várias outras linguagens de programação por meio de bibliotecas e APIs.

## Biblioteca json

Manipular JSON em Python é uma tarefa bastante comum, e a linguagem oferece bibliotecas embutidas que facilitam esse processo. A biblioteca principal para lidar com JSON em Python é a biblioteca json.

Aqui estão os passos básicos para manipular JSON em Python usando a biblioteca json:

### 1. Importar a biblioteca

```python
import json
```

### 2. Carregar JSON a partir de uma string ou arquivo

#### Carregar a partir de string

```python
json_string = '{"nome": "João", "idade": 30}'
data = json.loads(json_string)
```

#### Carregar a partir de arquivo

```json
{
  "nome": "João",
  "idade": 30,
  "casado": false,
  "hobbies": ["leitura", "ciclismo"],
  "endereco": {
    "rua": "Rua das Flores",
    "numero": 123,
    "cidade": "Catalão"
  }
}
```

{% hint style="info" %}
arquivo.json
{% endhint %}

```python
with open('arquivo.json', 'r') as file:
    data = json.load(file)
```

### 3. Acessar e modificar dados

Após carregar o JSON em uma estrutura de dados Python (geralmente um dicionário ou uma lista, dependendo do JSON), você pode acessar e modificar os valores da seguinte maneira:

```python
import json

# JSON fornecido
json_data = '''
{
  "nome": "João",
  "idade": 30,
  "casado": false,
  "hobbies": ["leitura", "ciclismo"],
  "endereco": {
    "rua": "Rua das Flores",
    "numero": 123,
    "cidade": "Catalão"
  }
}
'''

# Carregando o JSON em uma estrutura de dados Python (dicionário)
data = json.loads(json_data)

# Acessando valores do JSON
nome = data['nome']
idade = data['idade']
casado = data['casado']
hobbies = data['hobbies']
endereco = data['endereco']

print("Nome:", nome)
print("Idade:", idade)
print("Casado:", casado)
print("Hobbies:", hobbies)
print("Endereço:", endereco)

# Modificando valores
data['idade'] = 31
data['casado'] = True
data['hobbies'].append("música")  # Adicionando um novo hobby

# Convertendo de volta para JSON
json_string = json.dumps(data, indent=2)  # indent para tornar a saída mais legível

# Imprimindo o JSON modificado
print("\nJSON modificado:")
print(json_string)
```

Saída:

```cmd
Nome: João
Idade: 31
Casado: Verdadeiro
Hobbies: ['leitura', 'ciclismo', 'música']
Endereço: {'rua': 'Rua das Flores', 'numero': 123, 'cidade': 'Catalão'}
```
