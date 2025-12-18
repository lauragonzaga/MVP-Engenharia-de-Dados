# MVP: Análise Histórica do Desmatamento no Brasil (MapBiomas)

Trabalho desenvolvido para a sprint de **Engenharia de Dados** do curso de pós-graduação em Ciência de Dados & Analytics da PUC-Rio.

Você pode conferir:
- o notebook completo [clicando aqui](https://github.com/lauragonzaga/MVP-Engenharia-de-Dados/blob/main/Notebook%20Mapbiomas.ipynb)  
- o dashboard interativo [clicando aqui](https://dbc-b08da042-4e74.cloud.databricks.com/dashboardsv3/01f0d08344e91b4791a28f4d268be1dd/published?o=1041144495999733)

---

## Descrição do projeto

O projeto tem como objetivo analisar a evolução do **desmatamento no Brasil entre 1987 e 2024**, a partir dos dados públicos do **MapBiomas (Coleção 10)**.  
A análise é apoiada por um pipeline de Engenharia de Dados implementado na plataforma **Databricks**, cobrindo desde a ingestão e transformação até a modelagem em camadas (Bronze–Silver–Gold) e visualização em dashboard.

As principais perguntas que o projeto busca responder são:
- Quais biomas concentram as maiores áreas desmatadas ao longo do tempo?
- Quais municípios apresentaram os maiores volumes de desmatamento acumulado?
- Como evoluiu o desmatamento no Brasil ao longo dos anos?
- Que tipos de vegetação foram mais afetados?
- Qual a proporção de supressão de vegetação primária em relação à secundária?

---

## Pipeline de Engenharia de Dados

O fluxo segue a arquitetura **Medalhão (Bronze - Silver - Gold)**:

- **Camada Bronze:** ingestão dos dados originais do MapBiomas e criação de tabelas.  
- **Camada Silver:** limpeza, normalização e reestruturação, enriquecendo os dados com a legenda oficial de classes do MapBiomas.  
- **Camada Gold:** modelagem estrela com tabelas fato e dimensões.  
- **Integração externa:** incorporação das áreas territoriais oficiais do IBGE (2024) para cálculo de indicadores proporcionais.

<img width="3552" height="1666" alt="Diagrama ER" src="https://github.com/lauragonzaga/MVP-Engenharia-de-Dados/blob/main/diagrama_ER.png?raw=true" />

---

## Dashboard Interativo

- KPIs principais de área desmatada total e nativa (em hectares e proporção sobre o estado).  
- Evolução temporal (1987–2024) do desmatamento total e por bioma.  
- Ranking de estados com maior desmatamento absoluto e relativo.  
- Comparativo entre supressão de vegetação primária e secundária.
- Permite filtragem por faixa de anos e por estados.

<a href="https://dbc-b08da042-4e74.cloud.databricks.com/dashboardsv3/01f0d08344e91b4791a28f4d268be1dd/published?o=1041144495999733.html" target="_blank" rel="noopener noreferrer">
  <img width="3552" height="1666" alt="Dashboard" src="https://github.com/user-attachments/assets/4431148c-214f-4d94-97a9-c6f6f3c72803" />
</a>


---

## Principais conclusões

- A Amazônia é o bioma que concentra a maior parte do desmatamento acumulado no país. No entanto, em 2023 e 2024, seu desmatamento caiu drasticamente e o Cerrado a ultrapassou como bioma mais desmatado do ano.
- O desmatamento da Caatinga tem crescido bastante desde 2020, também superando a Amazônia em 2024.
- A Formação Florestal é a classe de vegetação mais afetada.  
- O estado do Mato Grosso lidera tanto em desmatamento absoluto quanto proporcional.  
- A supressão de vegetação primária representa a maior parcela do desmatamento anual, mas a supressão de vegetação secundária tem crescido proporcionalmente nas últimas décadas, indicando expansão de áreas já degradadas.  

---

## Ferramentas e tecnologias

- Databricks Free Edition
- Pandas, PySpark,  SQL, Delta Tables 
- Databricks SQL Dashboards
