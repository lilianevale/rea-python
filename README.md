# Seja bem-vindo!

## O que vamos ver?!

Este é o curso de Métodos Computacionais parte 1 (_MCOMP0001_) e tem como objetivo central oferecer aos alunos uma introdução a programação em Python que será a linguagem empregada ao longo de todo o curso.

Este curso é ministrado foi produzido pelo Grupo de Pesquisa e Estudos em Engenharia (GPEE) que é liderado pelo professor [Wanderlei Malaquias Pereira Junior](http://lattes.cnpq.br/2268506213083114).

Nesta etapa que chamaremos esse curso pelo código _MCOMP1_. Este espaço será destinado a apresentação do seguinte conteúdo:

<table data-header-hidden><thead><tr><th width="495.5999755859375"></th><th></th></tr></thead><tbody><tr><td><ol><li>Introdução à lógica;</li><li>Expressões e operadores;</li><li>Estrutras de controle;</li><li>Estrutras homogêneas;</li><li>Estrutras especiais;</li><li>Manipulação de arquivos;</li><li>Paradigmas.</li></ol></td><td><div><figure><img src=".gitbook/assets/fig001.png" alt="" width="256"><figcaption></figcaption></figure></div></td></tr></tbody></table>

## Instalação da linguagem e IDE

Vamos iniciar o curso pela instalação da linguagem de programação e dos ambientes que que devem/podem ser utilizados ao longo do curso. A lista não é extensa porém vamos fazer uso destas ferramentas para facilitar o nosso desempenho no curso.

1. [Anaconda _Environment_](https://www.anaconda.com/download);

Antes disso vamos testar o ambiente Anaconda Navigator. Nas nossas aplicações vamos usar a IDE (_Integrated Development Environment_) notebook Jupyter. Esse ambiente é bastante prático pois fornece suporte para linguagem além de permitir anotações em formato de linguagem de marcação Markdown.\
\
A Figura 1.1 apresenta uma imagem da posição da IDE notebook Jupyter na plataforma Anaconda Navigator.

<div align="center" data-full-width="true"><figure><img src=".gitbook/assets/fig11.svg" alt=""><figcaption><p>Figura 1.1 <em>Home</em> da plataforma Anaconda Navigator.</p></figcaption></figure></div>

### Um pouco sobre o uso da IDE notebook Jupyter

O notebook Jupyter é muito parecido com um caderno digital. Ele permite que você faça seus códigos e também gere comentários usando a linguagem de marcação Markdown. Você pode acessar o conteúdo de [Mayer e Zeviani](http://cursos.leg.ufpr.br/prr/capMarkdown.html) \[1] para entender um pouco do funcionamento desta linguagem de marcação.

Ao abrir o ambiente notebook Jupyter podemos criar um novo notebook conforme indicação na Figura 1.2 e então poderemos utilizar a linguagem Python.

<div data-full-width="true"><figure><img src=".gitbook/assets/fig12.svg" alt=""><figcaption><p>Figura 1.2 Tela inicial da interface Jupyter.</p></figcaption></figure></div>

A estrutura interna de um notebook é apresentada na Figura 1.3 e então poderemos utilizar a linguagem Python.

<figure><img src=".gitbook/assets/fig13.png" alt=""><figcaption><p>Figura 1.3 Tela inicial de um notebook Jupyter.</p></figcaption></figure>

Na Figura 1.3 podemos observar o campo `In` onde poderá ser escrito um código Python ou um código de marcação para edição do texto. Para controlar o modelo de campo basta acessar o menu Cell e alterar o tipo de célula.

O menu File contém informações de abertura, salvamento e _download_ de arquivos. É válientar que o notebook libera _download_ de modelos como .pdf, .html e .py.

O menu Kernel é o pesçao destinado aos comandos de execução do código que em um notebook Jupyter permite a execução célula a célula.

## Um pouco sobre a linguagem

Pode-se dizer que o Python é uma liguagem meio compilada e meio interpretada. A parte da compilação fica escondida do programador. Não iremos abordar isso no curso mas para ficar mais claro linguagens interpretadas são aquelas em que o código fonte é lido linha por linha e executado diretamente pelo interpretador em tempo de execução. O interpretador traduz cada instrução ou bloco de instruções para código de máquina em tempo real e executa-o imediatamente.

Além disso vale comentar que o Python é uma linguagem de tipagem dinâmica e forte. A tipagem dinâmica permite que você altere o tipo da variável em tempo de execução. O Python detectará automaticamente o tipo da variável e atribuirá o tipo. Vejamos um exemplo:

```python
valor = 'wanderlei'
print('tipo :', type(valor))
valor = 12
print('tipo :', type(valor))
valor = 12.45
print('tipo :', type(valor))
```

```cmd
tipo : <class 'str'>
tipo : <class 'int'>
tipo : <class 'float'>
```

Já a tipagem forte diz respeito ao padrão conversão para realizar operações. Por exemplo se em Python tentarmos somar um nome com um valor inteiro, essa soma não será possível sendo retornado um erro na interface. Vejamos um exemplo:

```python
nome = 'Wanderlei Junior'
idade = 33
print(nome + " " + idade)
```

```cmd
---------------------------------------------------------------------------
TypeError                                 Traceback (most recent call last)
Cell In[3], line 4
      1 nome = "Wanderlei Junior"
      2 idade = 33
----> 4 print(nome + " " + idade)

TypeError: can only concatenate str (not "int") to str
```

{% hint style="info" %}
Em outras linguagens como o JavaScript a linguagem faria a uma conversão implícita e a combinação `Wanderlei Junior 33` iria aparecer no console.
{% endhint %}

### Função print e o _Hello World_

A função print é nativa da linguagem Python e permite que possamos apresentar em tela valores de algumas variáveis para o usuário. O comando é muito importante na ocnstrução de um código pois ele permitirá que o desenvolvedor cheque em parte o seu codigo e irá permitir que o usuário possa ver os resultados de um _software_.\
\
Aqui vamos usar o conceito da função `print()` para escrever nosso primeiro algoritmo Python. A função `print()` tranforma tudo que está dentro do objeto principal em uma _string_.\
\
Na Figura 1.4 o passo 1 é dado pela digitação do que desejamos imprimir na tela. Para isso colocamos a informação _hello world_ dentro de aspas simples `'texto aqui'` ou aspas duplas `"texto aqui"`. No passo 2 fazemos a execução do algoritmo que resultada na Figura 1.5

<figure><img src=".gitbook/assets/fig14.png" alt=""><figcaption><p>Figura 1.4 Escrevendo o <em>hello world</em>.</p></figcaption></figure>

<figure><img src=".gitbook/assets/fig15.png" alt=""><figcaption><p>Figura 1.5 <em>hello world</em> executado.</p></figcaption></figure>

Na Figura 1.5 o passo 1 mostra o que foi impresso em tela e o passo 2 mostra que a célular `In[1]` foi executada.

{% hint style="info" %}
Lembre-se de que a função `print()` é muito flexível e pode ser usada de diversas maneiras para formatar a saída de acordo com suas necessidades.
{% endhint %}

### A sintaxe do Python

O Python utiliza a identação para delimitar blocos de código em vez de chaves, parênteses ou palavras-chave como em C, C++, Java e muitas outras linguagens. Isso significa que a consistência na indentação é crucial para o funcionamento do código Python. Por exemplo, um bloco condicional `if` é definido pela indentação adequada e não por chaves:

```python
if x > 5:
    print("x é maior que 5")
```

Em Java a mesma função seria marcada pelo uso de chaves.

```java
if (x > 5) {
    System.out.println("x é maior que 5");
}
```

O Python não requer ponto e vírgula (;) no final de cada sentença como muitas outras linguagens. A nova linha é usada para indicar o fim de uma sentença.

O Python usa o símbolo `#` para comentários de linha única e aspas triplas `'''` ou `"""` para comentários de várias linhas.

```python
# Isso é um comentário de linha única

"""
Isso é um comentário de
múltiplas linhas
"""
```

## Referências

| Código | Referência                                                                                  |
| ------ | ------------------------------------------------------------------------------------------- |
| \[1]   | Mayer F, Zeviani W. Markdown e Pandoc 2023. http://cursos.leg.ufpr.br/prr/capMarkdown.html. |

> Como citar
>
> PEREIRA JUNIOR, Wanderlei Malaquias; SEABRA, Eduardo Veloso Manhães; DE OLIVEIRA, Jessyca Batista Marques; RODRIGUES, Murilo Carneiro. Python: Introdução a linguagem. 1. ed. Catalão, 2023. (Curso de Python). Disponível em: [https://doi.org/10.5281/zenodo.8352294](https://doi.org/10.5281/zenodo.8352294).
