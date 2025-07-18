# Deployment

## Introdução ao Streamlit

`Streamlit` é uma biblioteca Python que permite criar **aplicações web interativas** de forma extremamente simples e rápida.\
Ideal para criar **dashboards**, **protótipos de aplicações de machine learning** ou **interfaces para análise de dados**, sem precisar de conhecimentos avançados em desenvolvimento web.

***

### Instalando o Streamlit

Você pode instalar o Streamlit com o comando:

```bash
pip install streamlit
```

***

### Como rodar um aplicativo

1. Crie um arquivo Python, por exemplo `app.py`
2. No terminal, execute:

```bash
streamlit run app.py
```

Pronto! Seu app abrirá automaticamente no navegador.

***

### Exemplo básico de app

```python
import streamlit as st

st.title("Meu Primeiro App com Streamlit")
st.write("Streamlit facilita a criação de interfaces web com Python!")
```

***

### Adicionando textos e títulos

O Streamlit oferece várias funções para mostrar textos:

```python
st.title("Título Principal")         # Título grande
st.header("Cabeçalho")               # Cabeçalho menor
st.subheader("Subcabeçalho")         # Subcabeçalho
st.text("Texto simples")             # Texto puro
st.markdown("**Texto em negrito**")  # Formatação com Markdown
```

***

### Interação com o usuário

Você pode capturar entradas do usuário com facilidade:

```python
nome = st.text_input("Digite seu nome")
idade = st.number_input("Informe sua idade", min_value=0, max_value=120)
nota = st.slider("Nota da prova", 0, 10, 5)
cor = st.selectbox("Escolha sua cor favorita", ["Vermelho", "Verde", "Azul"])

if st.button("Enviar"):
    st.success(f"Olá, {nome}! Você tem {idade} anos e gosta da cor {cor}.")
```

***

### Exibindo gráficos

Você pode mostrar gráficos de forma automática com `line_chart`, `bar_chart`, entre outros:

```python
import numpy as np
import pandas as pd

dados = pd.DataFrame({
    "x": np.arange(10),
    "y": np.random.randn(10)
})

st.line_chart(dados.set_index("x"))
```

***

### Upload de arquivos

Permita que o usuário envie arquivos (como planilhas):

```python
arquivo = st.file_uploader("Envie um arquivo CSV")

if arquivo is not None:
    df = pd.read_csv(arquivo)
    st.write("Visualização dos dados:")
    st.dataframe(df)
```

***

### Organizando com colunas

Você pode dividir o layout em colunas:

```python
col1, col2 = st.columns(2)

with col1:
    st.write("📌 Esta é a coluna 1")

with col2:
    st.write("📌 Esta é a coluna 2")
```

***

### Mostrando imagens

Para exibir imagens diretamente na aplicação:

```python
from PIL import Image

imagem = Image.open("minha_foto.png")
st.image(imagem, caption="Exemplo de imagem", use_column_width=True)
```

***
