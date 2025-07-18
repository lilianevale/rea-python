# Manipulação de planilhas

## O que é um arquivo .csv

Um arquivo CSV (Comma-Separated Values, ou Valores Separados por Vírgulas) é um formato de arquivo amplamente utilizado para armazenar dados tabulares de forma simples e legível. Nesse formato, os dados são organizados em linhas e colunas, sendo que cada linha representa um registro ou entrada, e os valores dentro de cada linha são separados por vírgulas. Cada linha normalmente corresponde a um conjunto de informações relacionadas, enquanto as vírgulas delimitam as diferentes colunas. Os arquivos CSV são frequentemente utilizados para importar e exportar dados entre aplicativos e sistemas, devido à sua simplicidade e compatibilidade. Eles podem ser abertos e manipulados em diversas ferramentas, incluindo planilhas eletrônicas e linguagens de programação, facilitando a análise e o processamento de dados estruturados.

### Exemplo&#xD;

```cmd
Nome,Idade,Cidade
Alice,25,Brasília
João,30,Goiânia
Ricardo,28,Catalão
David,22,Uberlândia
```

{% hint style="info" %}
Neste exemplo, a primeira linha é chamada de "cabeçalho" e contém os nomes das colunas. As linhas subsequentes representam os registros individuais, onde cada valor é separado por vírgulas.
{% endhint %}

## Biblioteca csv

A biblioteca csv do Python é um módulo integrado que facilita a manipulação de arquivos CSV (Comma-Separated Values). Ela oferece funções e classes para ler e escrever dados em formato CSV, permitindo o processamento eficiente de informações tabulares.

### Lendo um arquivo CSV

Suponha que você tenha um arquivo chamado `dados.csv` com o seguinte conteúdo:

```cmd
Alice,25,Brasília
João,30,Goiânia
Ricardo,28,Catalão
David,22,Uberlândia
```

Você pode ler esse arquivo e processar os dados usando a biblioteca csv da seguinte forma:

```python
import csv

with open('dados.csv', 'r') as arquivo_csv:
    leitor_csv = csv.reader(arquivo_csv)
    for linha in leitor_csv:
        nome, idade, cidade = linha
        print(f'Nome: {nome}, Idade: {idade}, Cidade: {cidade}')
```

Saída:

```cmd
Nome: Alice, Idade: 25, Cidade: Brasília
Nome: João, Idade: 30, Cidade: Goiânia
Nome: Ricardo, Idade: 28, Cidade: Catalão
Nome: David, Idade: 22, Cidade: Uberlândia
```

### Escrevendo em um arquivo CSV

Suponha que você deseje criar um arquivo CSV para armazenar dados de funcionários:

```python
import csv

dados_funcionarios = [
    ['João', 30, 'São Paulo'],
    ['Maria', 25, 'Rio de Janeiro'],
    ['Pedro', 28, 'Belo Horizonte']
]

with open('funcionarios.csv', 'w', newline='') as arquivo_csv:
    escritor_csv = csv.writer(arquivo_csv)
    for linha in dados_funcionarios:
        escritor_csv.writerow(linha)
```

### Lendo um CSV com cabeçalho

Muitas vezes, um arquivo CSV tem uma linha de cabeçalho que descreve as colunas. Você pode usar o `csv.DictReader` para ler o arquivo e acessar os valores por meio dos nomes das colunas

Suponha que você tenha um arquivo chamado `dados.csv` com o seguinte conteúdo:

```cmd
Nome,Idade,Cidade
Alice,25,Brasília
João,30,Goiânia
Ricardo,28,Catalão
David,22,Uberlândia
```

```python
import csv

with open('dados_com_cabecalho.csv', 'r') as arquivo_csv:
    leitor_csv = csv.DictReader(arquivo_csv)
    for linha in leitor_csv:
        nome = linha['Nome']
        idade = linha['Idade']
        cidade = linha['Cidade']
        print(f'Nome: {nome}, Idade: {idade}, Cidade: {cidade}')
```

### Escrevendo um CSV com cabeçalho

Você também pode escrever um arquivo CSV com cabeçalho usando o `csv.DictWriter`:

```python
import csv

dados_funcionarios = [
    {'Nome': 'João', 'Idade': 30, 'Cidade': 'São Paulo'},
    {'Nome': 'Maria', 'Idade': 25, 'Cidade': 'Rio de Janeiro'},
    {'Nome': 'Pedro', 'Idade': 28, 'Cidade': 'Belo Horizonte'}
]

with open('funcionarios_com_cabecalho.csv', 'w', newline='') as arquivo_csv:
    nomes_colunas = ['Nome', 'Idade', 'Cidade']
    escritor_csv = csv.DictWriter(arquivo_csv, fieldnames=nomes_colunas)
    escritor_csv.writeheader()
    for linha in dados_funcionarios:
        escritor_csv.writerow(linha)
```

{% hint style="info" %}
Esses exemplos demonstram algumas das funcionalidades básicas da biblioteca csv em Python para ler e escrever arquivos CSV. Ela oferece muitas outras opções para personalizar o comportamento da leitura e escrita de acordo com suas necessidades. Link para documentação da biblioteca: `https://docs.python.org/3/library/csv.html`
{% endhint %}
