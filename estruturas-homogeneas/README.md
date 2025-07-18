# Estruturas homogêneas

## Vetores e matrizes

Aqui vamos introduzir o conceito de estruturas homogêneas que permitem o agrupamento de vários dados em uma única variável. Vamos exemplificar uma situação: Precisamos armazenar 100 números inteiros e sabe-se que cada um deles ocupa 2 bytes na memória, como ocupar um único endereço de memória e não 200?\
\
Para isso criou-se os modelos de estruturas homogêneas que permitem que o programador acesse diversas posições da memória, de maneira controlada. Estas estruturas são conhecidas na álgebra linear e são chamadas de vetores e matrizes. No Python 3 o algoritmo permite essa diferenciação, porém matrizes e vetores são listas, sendo que o primeiro é um conjunto de listas.\
\
Um exemplo da construção de vetores e matrizes em Python 3 é apresentado a seguir, perceba que a sintaxe padrão é a escrita por meio de colchetes (`[ ]`) com valores separados por vírgulas.

```python
vetor = [1, 2, 3, 4]
matriz = [[1, 2, 3, 4], [5, 6, 7, 8]]
```

{% hint style="info" %}
Existem bibliotecas matemáticas no Python 3 que também permitem a utilização de matrizes, até mesmo as matrizes linhas (matriz com apenas uma linha e (n) colunas) ou colunas (matriz com (n) linhas e uma coluna). Exemplo disso é a biblioteca matemática Numpy.
{% endhint %}
