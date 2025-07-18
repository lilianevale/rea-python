# Processamento Paralelo

## Processamento Paralelo em Python

Este tutorial ensina como usar a biblioteca `multiprocessing` do Python para acelerar tarefas executadas em paralelo utilizando múltiplos núcleos da CPU.

***

### Conceitos Iniciais

* Processamento Síncrono: Tarefas são executadas **uma de cada vez**, em sequência.
* Processamento Assíncrono (Paralelo): Tarefas são executadas **ao mesmo tempo**, utilizando múltiplos processos independentes que aproveitam o poder dos diferentes núcleos da CPU.

A biblioteca `multiprocessing` permite executar **múltiplas instâncias de uma função simultaneamente**, cada uma em um processo separado.

***

### Exemplo Síncrono (sem paralelismo)

Simularemos uma tarefa demorada (2 segundos), executada 4 vezes de forma sequencial utilizando a bliblioteca `time` para simular o atraso:

```python
import time

def tarefa_simples(n):
    print(f"Iniciando tarefa {n}")
    time.sleep(2) # Simula uma tarefa que demora 2 segundos
    print(f"Tarefa {n} concluída")

start = time.time()

for i in range(4):
    tarefa_simples(i)

end = time.time()
print(f"Tempo total (síncrono): {end - start:.2f} segundos")
```

**Saída esperada:** Tempo total ≈ 8 segundos (4 tarefas × 2s).

***

### Exemplo Assíncrono com `multiprocessing.Process`

Abaixo, usamos a classe `Process` para rodar cada tarefa em paralelo. **Cada processo é iniciado e depois aguardamos todos com `.join()`**.

```python
import time
import multiprocessing

def tarefa_simples(n):
    print(f"Iniciando tarefa {n}")
    time.sleep(2)
    print(f"Tarefa {n} concluída")

if __name__ == '__main__':
    start = time.time()

    processos = []

    # Criando e iniciando processos
    for i in range(4):
        p = multiprocessing.Process(target=tarefa_simples, args=(i,))
        processos.append(p)
        p.start()

    # Esperando todos os processos terminarem
    for p in processos:
        p.join()

    end = time.time()
    print(f"Tempo total (paralelo): {end - start:.2f} segundos")
```

**Saída esperada:** Tempo total ≈ 0.34 segundos (as 4 tarefas são executadas em paralelo).

***

### Explicação passo a passo

| Etapa                          | Descrição                                             |
| ------------------------------ | ----------------------------------------------------- |
| `import multiprocessing`       | Importa o módulo necessário                           |
| `multiprocessing.Process(...)` | Cria um novo processo para executar a função          |
| `target=...`                   | Define qual função será executada no novo processo    |
| `args=(...)`                   | Define os argumentos que serão passados para a função |
| `p.start()`                    | Inicia o processo (ele começa a rodar em paralelo)    |
| `p.join()`                     | Espera o processo terminar antes de prosseguir        |

{% hint style="warning" %}
&#x20;Toda a lógica que usa `multiprocessing` deve estar dentro do bloco `if __name__ == '__main__':`, especialmente no Windows.
{% endhint %}

***

### Comparação de Desempenho

| Modo de Execução | Nº de Tarefas | Tempo Estimado |
| ---------------- | ------------- | -------------- |
| Síncrono         | 4             | 8 segundos     |
| Paralelo         | 4             | 0,34 segundos  |

***

### Boas práticas e cuidados

* Use `if __name__ == '__main__':` para proteger seu script
* Use `join()` para garantir que todos os processos terminem antes de calcular o tempo total
* Cada processo roda isoladamente — evite depender de variáveis compartilhadas
* Para muitos processos, considere usar `multiprocessing.Pool` ou `concurrent.futures`

***
