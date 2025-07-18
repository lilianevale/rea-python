# Matrizes

## Matrizes

Em Python, uma matriz é uma coleção bidimensional de elementos organizados em linhas e colunas, semelhante a uma tabela ou grade. Você pode pensar em uma matriz como uma lista de listas, onde cada elemento é acessado por meio de dois índices: um para a linha e outro para a coluna.\
\
Matrizes em Python geralmente são implementadas usando listas aninhadas, onde cada lista interna representa uma linha da matriz. Por exemplo:

```python
matriz = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
```

Neste exemplo, `matriz` é uma matriz 3x3, com três linhas e três colunas. Você pode acessar elementos individuais da matriz usando notação de índice duplo, por exemplo, `matriz[1][2]` para acessar o elemento na segunda linha e terceira coluna (que é 6 no exemplo acima).\
\
As matrizes são amplamente usadas em Python para representar dados tabulares, realizar cálculos matemáticos, processar imagens, resolver problemas de álgebra linear e muito mais.

{% hint style="info" %}
Bibliotecas como NumPy também fornecem suporte avançado para operações de matriz em Python.
{% endhint %}

### Exemplo Resolvido 1&#xD;

_Dada uma lista de notas de alunos utilize o conceito de matrizes para representar as notas de cada um deles. Após o armazenamento das notas determine o valor médio por avaliação._

| Aluno     | Nota 1 | Nota 2 | Nota 3 |
| --------- | ------ | ------ | ------ |
| Wanderlei | 8,5    | 7,0    | 9,5    |
| Eduardo   | 6,0    | 7,5    | 8,0    |
| Jéssica   | 9,0    | 8,0    | 7,5    |

```python
# Declarando as notas
notas = [
        [8.5, 7.0, 9.5],
        [6.0, 7.5, 8.0],
        [9.0, 8.0, 7.5]
        ]

# Calculando a média da matéria 1
mediaMat1 = (notas[0][0] + notas[1][0] + notas[2][0]) / 3
print("média matéria 1 - método 1: ", mediaMat1)

# Formato automatizado para obter as médias por disciplina
# Exemplo disciplina 1
medias = []
for i in range(len(notas)):
    medias.append(notas[i][0])
mediaMat1 = sum(medias) / 3
print("média matéria 1 - método 2: ", mediaMat1)
```

```cmd
média matéria 1 - método 1:  7.833333333333333
média matéria 1 - método 2:  7.833333333333333
```

Neste exemplo, temos uma matriz `notas` representando as notas de um conjunto de alunos em várias matérias. Em seguida, um loop percorre as colunas da matriz (cada matéria), extrai as notas dessa matéria e calcula a média. As médias de todas as matérias são exibidas na tela.\
\
Você pode alterar a matriz `notas` com as notas das diferentes matérias e alunos conforme necessário.
