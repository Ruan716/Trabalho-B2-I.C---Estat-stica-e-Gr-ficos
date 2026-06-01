# Trabalho de Estatística e Gráfico
>### O trabalho tem o objetivo de fazer uma análise dos índices pluviométricos dos municípios de Alagoas utilizando Python, através de cálculos estatísticos e gráficos para identificar padrões de precipitação ao longo do ano.

### 1º - Importação das bibliotecas
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
### 2º - Leitura e visualização inicial dos dados

```python
df = pd.read_csv("chuvas_AL_2023.csv", sep=";")
df.head()
```

- `read_csv()` foi utilizado para ler o arquivo CSV contendo os dados pluviométricos dos municípios.

- `sep=";"` define os dados do arquivo separados por ponto e vírgula.

- `df` é o DataFrame principal utilizado no trabalho, onde estão as principais informações.

- `head()` foi utilizado para visualizar as primeiras 5 linhas da tabela e verificar se os dados foram carregados corretamente.
