# Manipulação de arquivos

## Arquivos externos

No contexto de algoritmos é muito comum que necessitemos manipular informações em arquivos que estão distribuídos em partes aleatórias do nosso computador. Logo as linguagens de programação habilitam funções/métodos que permitam essa manipulação de arquivos externo ao que estão escritos dentro do algoritmo.\
\
A manipulação de arquivos habilita uma série de facilidades no ato de se construir um algoritmo. Vamos utilizar alguns exemplos atuais: O tratamento de informações de um banco de dados que salva os ingredientes da dosagem de um concreto ou por exemplo o endereço e características de edificações. Como seria complexo armazenar uma matriz com todas essas informações?!\
\
Logo esta seção tem como objetivo principal mostrar estes recursos de manipulação de arquivos externos pela linguagem Python. Aqui teremos exemplos de tipos básicos de arquivos que são amplamente empregados no dia a dia da computação, são eles: (a) `.txt`; (b) `.xlsx`; e (c) `.json`. Na sequência deste texto são abordadas as possibilidades de manipulação destes tipos de arquivo.

### Função `open()`

A função primordial para trabalhar com arquivos em python é a função `open()`.\
Ela retorna para nós um objeto do tipo arquivo e recebe dois parâmetros: O nome do arquivo e o modo.\
Existem quatro modos diferentes ao se abrir um arquivo.

* `"r"` - Leitura(Read): valor padrão. Abre o arquivo para leitura. Gera erro se ele não existir
* `"a"` - Acrescentar(Append): abre o arquivo para acrescentar texto. Cria o arquivo se ele não existir
* `"w"` - Escrever(Write): abre o arquivo para escrita. Cria o arquivo se ele não existir
* `"c"` - Criar(Create): cria o arquivo especificado e retorna um erro se ele já existir

Exemplos:

```python
# Exemplo de leitura de Arquivo
file = open("meuarquivo.txt")
file2 = open("meuarquivo.txt","r")
# Pode se utilizar qualquer um dos dois já que o modo padrão do função open() é o de leitura
```

{% hint style="info" %}
Obs: É importante lembrar que o arquivo aberto deve se encontrar na mesma pasta do arquivo python executado. Caso contrário é necessário inserir o destino do arquivo dentro do nome do arquivo.\
`Ex: file = open("C:/python/meuarquivo.txt")`
{% endhint %}

Ambos os modos _**Append**_ e _**Write**_ são para realizar escrita sobre o arquivo sendo a diferença a seguinte:

* `"a"` - Append: acrescenta texto ao final do arquivo
* `"w"` - Write: irá sobrescreve qualquer conteúdo do arquivo

### Leitura de Arquivo

Para realizar a leitura de arquivos primeiro é necessário abrir o arquivo em modo de leitura `"r"`

```python
file = open("meuarquivo.txt")
file = open("meuarquivo.txt", "r")
```

Após feito isso é possível realizar a leitura do arquivo. Para isso nós temos 3 métodos diferentes:

* `read()` Método que retorna o texto todo. É possível definir a quantidade de caracteres a ser retornada
* `readline()` Método que retorna apenas uma linha. Chamadas subsequentes retornaram as linhas seguintes
* `readlines()` Método que retorna todas as linhas e as armazenas dentro de uma lista. Este método adiciona um "\n" ao fim de cada linha exceto a última

```python
#Leitura do arquivo por inteiro
file = open("meuarquivo.txt")
print(file.read())

#Leitura de duas linhas do arquivo
file = open("meuarquivo.txt")
print(file.readline())
print(file.readline())

#Leitura de todas as linhas do arquivo
file = open("meuarquivo.txt")
print(file.readlines())
```

É boa prática você sempre fechar o arquivo após manipulá-lo. Para isso usamos o método `close()`

```python
#Leitura de todas as linhas do arquivo
file = open("meuarquivo.txt")
print(file.readlines())
#Fechando o arquivo após a leitura
file.close()
```

Também é possível já realizar o fechamento do arquivo de maneira mais fácil se utilizarmos a função `open()` junto com a instrução `with`:

```python
#Assim que sair do escopo o arquivo já é fechado automaticamente
with open("meuarquivo.txt") as file:
    print(file.read())
```

### Criação e Escrita em arquivo

Para criar um novo arquivo em Python usa-se a função open() com um dos seguintes parâmetros:

* `"x"` - Create(Criar): criar o arquivo e retorna um erro caso ele já exista.
* `"a"` - Append(Acrescentar): escreve ao final do arquivo e o cria caso não exista.
* `"w"` - Write(Escrita): sobrescreve qualquer conteúdo existente e o cria caso não exista.

Para escrever a um arquivo já existente é necessário adicionar o parâmetro a função `open()`.

* `"a"` - Append (Acrescentar): escreve ao final do arquivo.
* `"w"` - Write (Escrita): sobrescreve qualquer conteúdo existente.

```python
# Criando um arquivo (Se não existir) e o abrindo em modo de Escrita - Write 
with open("meuarquivo.txt","w") as file:
  # Escrevendo no arquivo
  file.write("Primeira frase escrita.")

#Abrindo o arquivo em modo de Leitura - Read
with open("meuarquivo.txt","r") as file:
  #Leitura do arquivo
  print(file.read())
#Saída: Primeira frase escrita.

#Abrindo o arquivo em modo de Acrescentar - Append
with open("meuarquivo.txt","a") as file:
  # Escrevendo ao final do arquivo
  file.write("Segunda frase escrita.")

#Abrindo o arquivo em modo de Leitura - Read
with open("meuarquivo.txt","r") as file:
  #Leitura do arquivo
  print(file.read())
#Saída: Primeira frase escrita.
        Segunda frase escrita.

#Abrindo o arquivo em modo de Escrita - Write
with open("meuarquivo.txt","w") as file:
  # Escrevendo no arquivo
  file.write("Todo o texto anterior foi apagado.")

#Abrindo o arquivo em modo de Leitura - Read
with open("meuarquivo.txt","r") as file:
  #Leitura do arquivo
  print(file.read())
#Saída: Todo o texto anterior foi apagado.
```

### Exclusão de Arquivo

Para excluir um arquivo é necessário importar a biblioteca **OS** e executar a função `os.remove()`

```python
#Importando a biblioteca
import os
#Exclusão do arquivo chamado meuarquivo.txt
os.remove("meuarquivo.txt")
```
