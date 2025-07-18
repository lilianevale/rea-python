# Estruturas especiais

## Uma estrutura chave valor

Em Python é muito comum a utilização de outras estruturas de dados que facilitam o nosso trabalho dentro da linguagem. Especificamente neste ponto falaremos dos dicionários que é uma estrutura bastante empregada na computação.\
\
A estrutura denominada dicionário é uma estrutura que contém um conjunto de chaves e valores.

Em Python é muito comum a utilização de outras estruturas de dados que facilitam o nosso trabalho dentro da linguagem. Especificamente neste ponto falaremos dos dicionários que é uma estrutura bastante empregada na computação.\
\
A estrutura denominada dicionário é uma estrutura que contém um conjunto de chaves e valores.

## Dicionários

Os dicionários em Python são estruturas de dados que permitem armazenar pares chave-valor, onde cada valor é associado a uma chave única. Isso significa que você pode acessar um valor a partir de sua chave correspondente. Vamos ver um exemplo:

```python
# Criando um dicionário
meu_dicionario = {'chave1': 'valor1', 'chave2': 'valor2', 'chave3': 'valor3'}

# Acessando valores pelo nome da chave
print(meu_dicionario['chave1'])  # Output: 'valor1'
print(meu_dicionario['chave2'])  # Output: 'valor2'
```

## Estruturas Chave-Valor

Dicionários são um exemplo de estrutura chave-valor. Em uma estrutura chave-valor, você tem um par de elementos: uma chave que é usada para buscar um valor associado. Esta estrutura é amplamente utilizada em programação para armazenar e recuperar dados de forma eficiente.

## Exemplos com Loop e Condicionais

```python
meu_dicionario = {'chave1': 'valor1', 'chave2': 'valor2', 'chave3': 'valor3'}

# Iterando sobre as chaves e valores
for chave, valor in meu_dicionario.items():
    if chave == 'chave2':
        print(f'A chave {chave} tem o valor {valor}')
    else:
        print(f'A chave {chave} tem um valor diferente de "chave2"')

# Output:
# A chave chave1 tem um valor diferente de "chave2"
# A chave chave2 tem o valor valor2
# A chave chave3 tem um valor diferente de "chave2"
```
