# Distribuited Data Processing — MBA em Engenharia de Dados | FIAP

**Disciplina:** Distribuited Data Processing<br>
**Professor:** Fabio Gomes Jardim<br>
**Instituição:** FIAP<br>

## Autores

Alef Anderson Fernandes Clarindo da Silva<br>
Thiago Félix da Silva<br>

---

## Sobre o projeto

Este repositorio apresenta uma entrega pratica da disciplina Distribuited Data Processing do MBA em Engenharia de Dados da FIAP.

O trabalho foi desenvolvido em notebook com PySpark, com foco em processamento distribuido e analise exploratoria sobre partidas internacionais de futebol. A base utilizada contem historico de jogos com informacoes de data, selecoes, placares e local da partida.

## Objetivo da entrega

Demonstrar, na pratica, o uso de processamento distribuido para:

- carregar dados em formato CSV
- criar uma visao temporaria para consultas SQL
- responder perguntas analiticas com Spark SQL
- validar consistencia dos resultados

## Dataset utilizado

Arquivo de entrada:

- data_raw/results.csv

Colunas principais:

- date
- home_teamName
- away_teamName
- home_scoreHome
- away_scoreAway
- tournamentName
- cityCity
- countryCountry
- neutralTRUE

## Perguntas analiticas respondidas

A analise foi estruturada em 10 perguntas:

1. Quantos registros existem na base?
2. Quantas equipes unicas mandantes existem na base?
3. Quantas vezes as equipes mandantes sairam vitoriosas?
4. Quantas vezes as equipes visitantes sairam vitoriosas?
5. Quantas partidas resultaram em empate?
6. Quantas partidas foram realizadas em cada pais?
7. Qual pais teve mais partidas?
8. Qual a partida com maior numero de gols?
9. Qual a maior goleada?
10. Quantos jogos ocorreram no Brasil?

## Abordagem tecnica

Fluxo implementado no notebook:

1. Inicializacao de uma SparkSession.
2. Leitura do CSV com cabecalho para um DataFrame Spark.
3. Criacao da view temporaria tab para execucao de SQL.
4. Execucao das consultas via spark.sql(...).
5. Validacao dos totais com a regra:

   mandantes_vitoriosos + visitantes_vitoriosos + empates = total_de_partidas

## Principais resultados

Com base no dataset atual do repositorio, os resultados obtidos foram:

| Indicador | Resultado |
|---|---:|
| Total de partidas | 40.839 |
| Equipes mandantes unicas | 309 |
| Vitorias de mandantes | 19.864 |
| Vitorias de visitantes | 11.544 |
| Empates | 9.431 |
| Pais com mais partidas | United States (1.144) |
| Jogos realizados no Brasil | 529 |
| Partida com maior numero de gols | Australia 31 x 0 American Samoa (31 gols) |
| Maior goleada | Australia 31 x 0 American Samoa (diferenca de 31 gols) |

Top 10 paises por quantidade de partidas:

1. United States — 1.144
2. France — 801
3. England — 687
4. Malaysia — 644
5. Sweden — 637
6. Germany — 581
7. Brazil — 529
8. Spain — 517
9. Thailand — 483
10. Italy — 480

## Estrutura do repositorio

```text
.
├── data_raw/
│   └── results.csv
├── requirements.txt
└── trabalho.ipynb
```

## Tecnologias e bibliotecas

- Python
- Apache Spark (PySpark)
- Jupyter Notebook

Dependencias principais registradas em requirements.txt:

- pyspark==3.5.1
- py4j==0.10.9.7
- ipykernel==7.1.0
- ipython==8.37.0

## Como executar o projeto

### 1) Clonar o repositorio

```bash
git clone <url-do-repositorio>
cd distribuited_data_processing
```

### 2) Instalar dependencias

```bash
pip install -r requirements.txt
```

### 3) Executar o notebook

Abra o arquivo trabalho.ipynb no VS Code (ou Jupyter) e rode as celulas em sequencia.

## Aprendizados da entrega

- Uso de Spark para consultas analiticas em volume de dados historicos.
- Aplicacao de SQL em contexto distribuido para responder perguntas de negocio.
- Validacao de consistencia entre metricas agregadas.
- Estruturacao de uma entrega tecnica com foco em reprodutibilidade.
