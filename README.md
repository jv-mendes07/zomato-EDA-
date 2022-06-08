# Zomato (EDA)

![](./img/b1.jpg)

Tal análise de dados irá expor uma exploração e explanação detalhada das informações presentes em um dataset do aplicativo Zomato, que é um dos aplicativos de pesquisa mais utilizados para a procura de bares e restaurantes em todos os países. 

Neste caso, o conjunto de dados do aplicativo Zomato estará restrito à cidade de Bangalore na Índia, assim às informações expostas se referem estritamente aos restaurantes, lanchonetes, bares e sorveterias dos bairros da cidade indiana. 

Um dos principais focos da análise é expor o quão bem os serviços alimentícios e secundários de tais estabelecimentos são avaliados pela região.

###### Obs :. As ferramentas utilizadas para tal análise foram a linguagem de programação Python, Pandas para a manipulação de dados, Matplotlib e Seaborn para a visualização gráfica dos dados informativos.

Antes de exportarmos o conjunto de dados, iremos exportar às bibliotecas que serão ferramentárias durante este processo de análise:

## Importação de Bibliotecas

```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```
## Fonte de dados

O dataset [Zomato Bangalore Restaurants](https://www.kaggle.com/datasets/himanshupoddar/zomato-bangalore-restaurants) utilizado em tal análise exploratória está hospedado disponivelmente no Kaggle para uso gratuito.

## Importação do dataset

```
df_restaurantes = pd.read_csv('/content/drive/MyDrive/BangaloreZomatoData.csv')
```

Após importarmos a base de dados, verificamos a quantidade de linhas e colunas contidas em tal dataset pelo atributo .shape, e assim descobrimos que há 
8 mil e 923 linhas, e 19 colunas disponíveis para a exploração analítica.

## Colunas do dataset

Abaixo são os nomes das colunas que serão analisadas:

```
'name', 'url', 'tipo_de_comida', 'area', 'tempo', 'endereco_completo',
       'numero_tel', 'servico_de_entrega', 'take_away', 'jantar_interno',
       'comida_vegana', 'avaliacao_jantar', 'qtd_avaliacoes_jantar',
       'avaliacao_entrega', 'qtd_avaliacoes_entrega', 'conhecido_por',
       'pratos_populares', 'pessoas_conhecem_por', 'custo_medio'
``` 

## Processo de exploração dos dados

### **(1)** Tratamento dos dados

* Renomeação das colunas:

  **(1)** As colunas estavam originalmente escritas em inglês, para facilitar o entendimento informacional de cada coluna, os nomes das colunas foram traduzidos do inglês para o português em um formato mais entendível em relação ao que cada coluna trata.
  
* Dados nulos:

 **(1)** Foi verificável que às colunas tempo, conhecido_por, pratos_populares e pessoas_conhecem_por contêm dados nulos, neste caso não fizemos nada para sanar essa ausência de informações por não termos opções viáveis que facilitassem no preencimento de tais dados nulos.
 
 Basicamente, esses dados nulos significam que há restaurantes que foram registrados no dataset que não sabemos o horário comercial em que tais estabelecimentos estão abertos, há restaurantes em que não sabemos quais são os pratos popularmente mais pedidos, e também não sabemos às avaliações e os julgamentos dos clientes em relação à alguns restaurantes específicos da cidade de Bangalore.
 
### **(2)** Conhecimento exploratório dos dados

À partir desta fase, começamos à explorar em detalhes o conjunto de dados relativo aos restaurantes registrados na cidade de Bangalore pelo aplicativo Zomato, e primeiramente antes de inicializarmos com perguntas mais complexas sobre tal dataset, poderemos nos perguntar **(a)** quantos restaurantes e bairros estão dispersamente localizáveis na cidade de Bangalore? 

Para 
