# Trabalho de Estatística e Gráfico
>### O trabalho tem o objetivo de fazer uma análise dos índices pluviométricos dos municípios de Alagoas utilizando Python, através de cálculos estatísticos e gráficos para identificar padrões de precipitação ao longo do ano.

### Importação das bibliotecas
```python
import pandas as pd
import matplotlib.pyplot as plt
import plotly.express as px
```
- Pandas (`pd`): utilizada para leitura e manipulação dos dados.

- Matplotlib (`plt`): utilizada para criação dos gráficos.

- Plotly Express (`px`): utilizada para criação de gráficos interativos.

- Os apelidos (`pd`, `plt`, `px`) facilitam a escrita dos comandos.
#
### Leitura e visualização inicial dos dados
### O arquivo utilizado neste trabalho pode ser acessado abaixo:
[chuvas_AL_2023.csv](dados/chuvas_AL_2023.csv)

```python
df = pd.read_csv("chuvas_AL_2023.csv", sep=";")
df.head()
```
### Resultado obtido:

![Visualização inicial da tabela](head_tabela.png.png)
- `read_csv()` foi utilizado para ler o arquivo CSV contendo os dados pluviométricos dos municípios.
  
- `sep=";"` define os dados do arquivo separados por ponto e vírgula.
  
- `df` é o DataFrame principal utilizado no trabalho, onde estão as principais informações.
  
- `head()` foi utilizado para visualizar as primeiras 5 linhas da tabela e verificar se os dados foram carregados corretamente.
#
## Perguntas Norteadoras:
### Volume total de precipitação registrado no estado de Alagoas no mês de Junho:

```python
round(df["JUN"].sum(), 2)
```

- `df["JUN"]` seleciona apenas a coluna do mês de Junho.
  
- `sum()` foi utilizado para somar todos os valores de precipitação presentes nessa coluna.
  
- `round(valor, 2)` foi utilizado para arredondar o resultado para 2 casas decimais.

### Resultado obtido:
    17785.00

### Média de chuvas ocorrida nos municípios alagoanos durante o mês de Janeiro:

```python
round(df["JAN"].mean(), 2)
```

- `df["JAN"]` seleciona apenas a coluna do mês de Janeiro.

- `mean()` foi utilizado para calcular a média aritmética dos valores da coluna.

- `round(valor, 2)` foi utilizado para arredondar o resultado para 2 casas decimais.

### Resultado obtido:
    72.19

### Município obteve o maior e qual obteve o menor índice pluviométrico no mês de Fevereiro:

```python
df.loc[df["FEV"].idxmax(), "MUNICIPIO"]

df.loc[df["FEV"].idxmin(), "MUNICIPIO"]
```

- `df["FEV"]` seleciona apenas a coluna do mês de Fevereiro.

- `idxmax()` retorna o índice onde está localizado o maior valor da coluna.

- `idxmin()` retorna o índice onde está localizado o menor valor da coluna.

- `loc[linha, coluna]` foi utilizado para localizar informações específicas dentro da tabela.

### Resultado obtido:

    Maior índice pluviométrico:
    Joaquim Gomes

    Menor índice pluviométrico:

### Análise do comportamento das chuvas em Maceió ao longo do ano

```python
meses=["JAN","FEV","MAR","ABR","MAI","JUN","JUL","AGO","SET","OUT","NOV","DEZ"]

cidade = df[df["MUNICIPIO"] == "Maceió"]

plt.plot(meses, cidade[meses].values[0])

plt.title("Chuvas ao longo do ano")

plt.xlabel("Meses")

plt.ylabel("Precipitação")

plt.show()
```

- A lista `meses` foi criada para armazenar os meses utilizados no eixo horizontal do gráfico.

- `df[df["MUNICIPIO"] == "Maceió"]` filtra a tabela e seleciona apenas os dados referentes ao município escolhido.

- A variável `cidade` foi utilizada para armazenar os dados filtrados.

- `plt.plot()` cria um gráfico de linhas utilizando os meses no eixo X e os valores de precipitação no eixo Y.

- `cidade[meses].values[0]` seleciona os valores numéricos que serão utilizados no gráfico.

- `plt.title()` adiciona um título ao gráfico.

- `plt.xlabel()` define o nome do eixo horizontal (X).

- `plt.ylabel()` define o nome do eixo vertical (Y).

- `plt.show()` exibe o gráfico gerado.

- O objetivo desta etapa foi visualizar como a precipitação variou durante os meses do ano em Maceió.

### Resultado obtido:

(inserir print do gráfico)
