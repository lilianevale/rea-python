# Teste do Algoritmo

## Testes Unitários com `unittest` em Python

Testes unitários são uma prática essencial na programação moderna.\
Eles servem para **verificar automaticamente se cada parte do seu código está funcionando corretamente** — principalmente funções e métodos.

O Python já vem com a biblioteca `unittest`, que facilita a criação desses testes.

***

### Como importar o módulo

```python
import unittest
```

***

### Por que testar?

Imagine que você tenha uma função chamada `soma(a, b)` que deveria retornar a soma de dois números. Como garantir que ela funciona corretamente com números positivos, negativos ou zero? Por causa disso, é importante escrever testes para verificar se a função se comporta como esperado.\
A seguir, vamos aprender a criar testes unitários para funções simples usando o módulo `unittest`.

***

### Funções que vamos testar

Vamos definir duas funções simples:

```python
def soma(a, b):
    return a + b

def eh_par(n):
    return n % 2 == 0
```

Essas funções fazem o seguinte:

* `soma(a, b)`: retorna a soma de `a` e `b`
* `eh_par(n)`: retorna `True` se `n` for par, ou `False` se for ímpar

***

### Estrutura de um teste

Para testar essas funções, criamos uma **classe de teste** que herda de `unittest.TestCase`.\
Cada teste é um método da classe cujo nome começa com `test_`.

```python
import unittest

class TestFuncoesSimples(unittest.TestCase):

    def test_soma(self):
        self.assertEqual(soma(2, 3), 5)
        self.assertEqual(soma(-2, 2), 0)
        self.assertEqual(soma(0, 0), 0)

    def test_eh_par(self):
        self.assertTrue(eh_par(4))
        self.assertFalse(eh_par(7))

if __name__ == '__main__':
    unittest.main()
```

***

### Métodos de asserção comuns

Métodos de asserção são funções fornecidas pelo framework de testes que ajudam a verificar se o código que está sendo testado se comporta como esperado. Eles comparam o resultado real de uma operação com o resultado esperado e geram um relatório indicando se o teste foi bem-sucedido ou falhou. Aqui estão alguns exemplos:

* `assertEqual(a, b)`: Verifica se `a` é igual a `b`.
* `assertNotEqual(a, b)`: Verifica se `a` não é igual a `b`.
* `assertTrue(x)`: Verifica se `x` é verdadeiro.
* `assertFalse(x)`: Verifica se `x` é falso.
* `assertRaises(exception, func, *args, **kwargs)`: Verifica se `func` levanta a exceção especificada.

***

### Exemplo com erro esperado: fatorial

```python
def fatorial(n):
    if n < 0:
        raise ValueError("Número negativo não possui fatorial")
    if n == 0:
        return 1
    return n * fatorial(n - 1)
```

#### Testando a função `fatorial()`

```python
class TestFatorial(unittest.TestCase):

    def test_fatorial_valores(self):
        self.assertEqual(fatorial(0), 1)
        self.assertEqual(fatorial(4), 24)

    def test_fatorial_negativo(self):
        with self.assertRaises(ValueError):
            fatorial(-5)
```

***

### Como executar os testes

#### Forma direta (modo script):

Salve seu arquivo como `testes.py` e execute:

```bash
python testes.py
```

#### Forma modular (projetos maiores):

```bash
python -m unittest discover
```

Essa forma busca todos os arquivos `test_*.py` e executa os testes automaticamente.

***

### Gerando Relatórios

Para gerar relatórios de teste mais detalhados, você pode usar ferramentas adicionais como o `coverage` para medir a cobertura do código:

```bash
pip install coverage
coverage run -m unittest nome_do_arquivo.py
coverage report
```

### 7. Links Úteis

* [Documentação do `unittest`](https://docs.python.org/3/library/unittest.html)
* [Tutorial de Testes Unitários](https://realpython.com/python-testing/)

***
