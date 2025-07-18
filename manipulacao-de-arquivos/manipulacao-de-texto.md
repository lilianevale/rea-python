# Manipulação de texto

## O que é um arquivo .txt

Arquivos `.txt` são documentos de texto simples que contêm pouca ou nenhuma formatação. Eles são usados para armazenar notas, instruções passo a passo, manuscritos e outras informações baseadas em texto.

A função primordial para trabalhar com arquivos externos em Python é a função `open()`. Ela retorna para nós um objeto do tipo arquivo e recebe dois parâmetros: O nome do arquivo e o modo. Existem quatro modos diferentes ao se abrir um arquivo, são eles:

* Leitura (`"r"`): Valor padrão;
* Acrescentar (`"a"`): Abre o arquivo para acrescentar texto;
* Escrever (`"w"`): Abre o arquivo para escrita;
* Criar (`"x"`): Cria o arquivo especificado e retorna um erro se ele já existir.

### Exemplo Resolvido 1&#xD;

_Crie um arquivo .txt chamado `meu_arquivo` e verifique o tipo do retorno da função._

```python
arq = open("meuarquivo.txt", mode = "r")
type(arq)
```

```cmd
_io.TextIOWrapper
```

{% hint style="info" %}
O objeto `_io.TextIOWrapper` armazena todo o texto do arquivo.
{% endhint %}

Aqui é válido salientar que pode se utilizar qualquer uma das duas sintaxes. Porém o mod padrão do função `open()` é o de leitura. Também ressaltamos que no caso deste exemplo o argumento `mode` será encarregado por informar o modo desejado na função `open()` confomre escrito anteriormente.

{% hint style="warning" %}
É importante lembrar que o arquivo aberto deve se encontrar na mesma pasta do arquivo Python que será executado. Caso contrário é necessário inserir o destino do arquivo dentro do nome do arquivo.\
`Ex: file = open("C:/python/meuarquivo.txt")`
{% endhint %}

### Fazendo operações com o arquivo

Para realizar a leitura de arquivos primeiro é necessário criar o arquivo de entrada que desejamos operar. Para isto vamos usar o \[arquivo exemplo AQUI LINK PARA O ARQUIVO EXEMPLO]. Após fazer o download do arquivo podemos fazer a aberuta conforme exemplo 1.

```python
arquivo = open("meuarquivo.txt", mode = "r")
```

Feito isso é possível realizar a leitura completa do arquivo. Para isso nós temos 3 métodos diferentes:

* `read()`: Método que retorna o texto todo. É possível definir a quantidade de caracteres a ser retornada;
* `readline()`: Método que retorna apenas uma linha. Chamadas subsequentes retornaram as linhas seguintes;
* `readlines()`: Método que retorna todas as linhas e as armazenas dentro de uma lista. Este método adiciona um `"\n"` ao fim de cada linha exceto a última.

```python
#Leitura do arquivo por inteiro
file = open("meuarquivo.txt")
print(file.read())
```

CADE UMA AMOSTRA DE COMO É A SAÍDA

```cmd
output:
Digite o seu nome: Wanderlei
Digite a sua altura em metros: 1.72
Digite o seu peso em quilogramas: 90
Wanderlei, o seu IMC é: 30.42
```

```python
#Leitura de duas linhas do arquivo
file = open("meuarquivo.txt")
print(file.readline())
print(file.readline())
```

CADE UMA AMOSTRA DE COMO É A SAÍDA

```cmd
output:
Digite o seu nome: Wanderlei
Digite a sua altura em metros: 1.72
Digite o seu peso em quilogramas: 90
Wanderlei, o seu IMC é: 30.42
```

```python
#Leitura de todas as linhas do arquivo
file = open("meuarquivo.txt")
print(file.readlines())
```

CADE UMA AMOSTRA DE COMO É A SAÍDA

```cmd
output:
Digite o seu nome: Wanderlei
Digite a sua altura em metros: 1.72
Digite o seu peso em quilogramas: 90
Wanderlei, o seu IMC é: 30.42
```

É boa prática você sempre fechar o arquivo após manipulá-lo. Para isso usamos o método `close()`

```python
# Leitura de todas as linhas do arquivo
arquivo = open("meuarquivo.txt")
print(file.readlines())
# Fechando o arquivo após a leitura
arquivo.close()
```

Também é possível já realizar o fechamento do arquivo de maneira mais fácil se utilizarmos a função `open()` junto com a instrução with

```python
with open("meuarquivo.txt") as file:
      print(file.read())
```

{% hint style="warning" %}
Aqui existe uma observação importante de contexto de variáveis ao usar a instrução with. Neste caso o arquivo já será fechado automaticamente após a saída do escopo.
{% endhint %}

### Escrita em arquivo

Ao abrir o arquivo pode-se então fazer operações de escrita de novas seções de texto. Relembrando os conceitos apresentados anteriormente teremos os modos `"w"` e `"a"` que correspondem a escrito e acréscimo respectivamente.

### Exemplo Resolvido 2&#xD;

_Crie um arquivo .txt chamado `meu_arquivo` e verifique o tipo do retorno da função._

```python
file = open("meuarquivo.txt")
file2 = open("meuarquivo.txt", mode = "r")
type(file)
```

```cmd
_io.TextIOWrapper
```

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

Para excluir um arquivo é necessário importar a biblioteca OS e executar a função `os.remove()`

```python
#Importando a biblioteca
import os
#Exclusão do arquivo chamado meuarquivo.txt
os.remove("meuarquivo.txt")
```

### Conclusão

Todas as manipulações que vimos sobre arquivos tratam de realizar o CRUD (Create, Read, Update and Delete). Podemos usar funções para agilizar esses processos que são realizados múltiplas vezes.

### Exemplo Resolvido 1&#x20;

```python
#Função para criar um arquivo (Create)
def criar_arquivo(nome_do_arquivo):
    try:
        with open(nome_do_arquivo, 'w') as arquivo:
            print(f"Arquivo '{nome_do_arquivo}' created.")
    except Exception as e:
        print(f"Erro ao criar o arquivo: {e}")

#Função para leitura de um arquivo (Read)
def ler_arquivo(nome_do_arquivo):
    try:
        with open(nome_do_arquivo, 'r') as arquivo:
            conteudo = arquivo.read()
            print(f"Conteúdo do arquivo:\n{content}")
    except Exception as e:
        print(f"Erro ao ler o arquivo: {e}")

#Função para escrever no arquivo (Update)
def atualizar_arquivo(nome_do_arquivo, novo_conteudo):
    try:
        with open(nome_do_arquivo, 'w') as file:
            file.write(novo_conteudo)
            print(f"Arquivo '{nome_do_arquivo}' foi atualizado.")
    except Exception as e:
        print(f"Erro ao atualizar arquivo: {e}")

#Função para excluir arquivo
def excluir_arquivo(nome_do_arquivo):
    try:
        import os
        os.remove(nome_do_arquivo)
        print(f"Arquivo '{nome_do_arquivo}' foi excluido.")
    except Exception as e:
        print(f"Erro ao excluir arquivo file: {e}")

# Programa principal
nome_do_arquivo = "exemplo.txt"

criar_file(nome_do_arquivo)

novo_conteudo = "Olá, esse é o conteúdo atualizado."
atualizar_arquivo(nome_do_arquivo, novo_conteudo)

ler_arquivo(nome_do_arquivo)

#output: Olá, esse é o conteúdo atualizado

excluir_arquivo(nome_do_arquivo)
```

{% hint style="warning" %}
Lembrando que é sempre importante verificar se você tem permissões no diretório onde se encontra o script python.
{% endhint %}

E como seria possível armazenar informações de diversas pessoas em um arquivo `.txt`?\
Seria necessário realizar 3 coisas:

1. Cada linha será uma tupla - Um cadastro do que queremos armazenar.
2. Cada campo deverá ser separado por um delimitador - Este pode ser qualquer coisa desde que seja único para esse uso
3. Para depois separar cada campo usaremos a função split()

Exemplo da função split()

```python
txt = "Olá mundo"

x = txt.split()

print(x)

#output: [Olá, mundo]
```

{% hint style="warning" %}
Lembrando que a função `split()` pode receber o argumento.
{% endhint %}

### Exemplo Resolvido 2&#xD;

```python
#Criando o arquivo meuarquivo.txt se não existir e adicionando o primeiro cadastro
#Cada cadastro vai conter os seguintes Campos - Nome, Idade e CPF
#O delimitador a ser utilizado será o "-"
with open("meuarquivo.txt","w") as f:
  f.write("Andre-18-57515108444")

#Leitura do arquivo e a divisão do texto em segmentos pela função split()
with open("meuarquivo.txt","r") as f:
  texto = f.read()
  v_txt = texto.split("-")
  nome = v_txt[0]
  idade = v_txt[1]
  cpf = v_txt[2]
```
