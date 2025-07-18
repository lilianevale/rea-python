# Analisando KPI de uma industria de leite

## Analisando o KPI de uma indústria

_Você é o chefe do departamento de TI em uma indústria de laticínios. Diariamente, você precisa extrair os dados de produção de leite do sistema ERP e transformá-los em um relatório claro e conciso para apresentar ao seu chefe. Neste desafio, você receberá os dados de produção em um dicionário Python e terá que calcular alguns KPIs essenciais para avaliar a produtividade da indústria. Para tanto criei um relatório padrão para essa indústria onde estão determinados: (a) a produtividade horário de leite; (b) a quantidade em litros de leite que apresentaram falha e (c) percentuais de produção e rejeição totais._

#### Dados de Produção de Leite

```python
dados_producao_leite = {
    "hora00": {
        "producao_litros": 1500,
        "rejeitados_litros": 30
    },
    "hora01": {
        "producao_litros": 1550,
        "rejeitados_litros": 25
    },
    "hora02": {
        "producao_litros": 1600,
        "rejeitados_litros": 20
    },
    "hora03": {
        "producao_litros": 1650,
        "rejeitados_litros": 18
    },
    "hora04": {
        "producao_litros": 1700,
        "rejeitados_litros": 15
    },
    "hora05": {
        "producao_litros": 1750,
        "rejeitados_litros": 12
    },
    "hora06": {
        "producao_litros": 1800,
        "rejeitados_litros": 10
    },
    "hora07": {
        "producao_litros": 1850,
        "rejeitados_litros": 8
    },
    "hora08": {
        "producao_litros": 1900,
        "rejeitados_litros": 5
    },
    "hora09": {
        "producao_litros": 1950,
        "rejeitados_litros": 3
    },
    "hora10": {
        "producao_litros": 2000,
        "rejeitados_litros": 2
    },
    "hora11": {
        "producao_litros": 2050,
        "rejeitados_litros": 1
    },
    "hora12": {
        "producao_litros": 2100,
        "rejeitados_litros": 0
    },
    "hora13": {
        "producao_litros": 2150,
        "rejeitados_litros": 0
    },
    "hora14": {
        "producao_litros": 2200,
        "rejeitados_litros": 0
    },
    "hora15": {
        "producao_litros": 2250,
        "rejeitados_litros": 0
    },
    "hora16": {
        "producao_litros": 2300,
        "rejeitados_litros": 0
    },
    "hora17": {
        "producao_litros": 2350,
        "rejeitados_litros": 0
    },
    "hora18": {
        "producao_litros": 2400,
        "rejeitados_litros": 0
    },
    "hora19": {
        "producao_litros": 2450,
        "rejeitados_litros": 0
    },
    "hora20": {
        "producao_litros": 2500,
        "rejeitados_litros": 0
    },
    "hora21": {
        "producao_litros": 2550,
        "rejeitados_litros": 0
    },
    "hora22": {
        "producao_litros": 2600,
        "rejeitados_litros": 0
    },
    "hora23": {
        "producao_litros": 2650,
        "rejeitados_litros": 0
    }
}
```

### Requisitos

Use estruturas de repetição para percorrer a base de dados e realizar o cálculo do KPI. Os resultados devem ser armazenados em listas ou matrizes.

### Saída esperada

É esperado um arquivo de saída `.txt` que apresente cabeçalho e um relatório com os KPI's informados.
