# Estruturas de controle

## Controlando o fluxo do algoritmo

Durante o processo de programação, é comum nos depararmos com a necessidade de executar determinada parte do bloco de código somente caso uma condição especifica seja atendida. Nestes casos, faz-se necessário utilizar estruturas da linguagem de programação que permitam realizar essas verificações de fluxo.\
\
As principais estruturas de controle são:

* Estrutura sequencial;
* Estrutura condicional;
* Estrutura de repetição.

## Estrutura sequencial

A estrutura sequencial é a mais básica das estruturas. As instruções são executadas em sequência linear obedecendo as identações da linguagem Python. A Figura 4.1 apresenta o fluxo de funcionamento desta estrutura sequencial.

<figure><img src="../.gitbook/assets/fig41.svg" alt=""><figcaption><p>Figura 4.1. Representação estrutural sequencial.</p></figcaption></figure>

Vejamos um exemplo:

```python
h = 50                        # instrução 1
j = 20                        # instrução 2
x = 10                        # instrução 3
media = (x + j + x) / 3       # instrução 4
print('valor médio: ', media) # instrução 5
```

```cmd
valor médio:  13.333333333333334
```

Na sequência vamos avliar os outros padrões de controle de fluxo de um algoritmo em linguagem Python.
