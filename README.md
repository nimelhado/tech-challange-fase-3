# Tech Challenge — State of Data Brasil

## Sobre o projeto

Este projeto foi desenvolvido como parte do Tech Challenge da pós-graduação em Data Analytics da FIAP.

O objetivo é analisar o mercado brasileiro de Dados e Tecnologia a partir das três edições mais recentes da pesquisa **State of Data Brasil**, realizada pela Data Hackers, referentes aos anos de **2024, 2025 e 2026**.

A análise busca identificar características do mercado, perfis profissionais, remuneração, diversidade, tecnologias utilizadas, evolução da Inteligência Artificial e modelos de trabalho.

---

## Objetivos

- Analisar a estrutura do mercado brasileiro de Dados;
- Identificar os principais perfis e cargos profissionais;
- Avaliar diferenças de senioridade e remuneração;
- Analisar indicadores de diversidade;
- Identificar as principais tecnologias e ferramentas utilizadas;
- Avaliar a evolução da adoção de Inteligência Artificial;
- Analisar mudanças nos modelos de trabalho e possíveis impactos na retenção de profissionais.

---

## Arquitetura da solução

A solução foi desenvolvida utilizando serviços da **AWS**, seguindo uma organização em camadas:

**Bronze → Silver → Gold**

### Fluxo

Data Hackers  
↓  
Amazon S3 — Bronze  
↓  
AWS Glue + Apache Spark/PySpark  
↓  
Amazon S3 — Silver  
↓  
AWS Glue + Spark  
↓  
Amazon S3 — Gold  
↓  
Glue Notebook — Análise e DataViz

A arquitetura completa está disponível em:

`/diagrama/arquitetura_aws.png`

---

## Tecnologias utilizadas

- Amazon S3
- AWS Glue
- AWS Glue Data Catalog
- Apache Spark
- PySpark
- Python
- Pandas
- Matplotlib
- SQL/Athena
- Draw.io

---

## Processamento dos dados

Os dados foram inicialmente armazenados na camada **Bronze**, mantendo sua estrutura original.

Na camada **Silver**, foram realizadas etapas de:

- padronização dos nomes das colunas;
- tratamento de valores nulos;
- ajuste e organização dos dados;
- identificação e remoção de registros duplicados;
- padronização dos tipos e estruturas.

Na camada **Gold**, os dados foram organizados para as análises do projeto, sendo divididos nas principais dimensões:

- Perfil;
- Tecnologias;
- Inteligência Artificial;
- Mercado.

Os dados tratados e transformados foram armazenados em formato **Parquet** no Amazon S3.

---

## Análises realizadas

O projeto aborda cinco principais dimensões:

### Mercado de Dados
- Senioridade;
- Cargos profissionais;
- Distribuição regional;
- Remuneração.

### Diversidade
- Gênero;
- Raça;
- Pessoas com deficiência;
- Experiências profissionais prejudicadas.

### Tecnologias
- Tipos de dados utilizados;
- Ferramentas de Business Intelligence;
- Tecnologias utilizadas pelos profissionais.

### Inteligência Artificial
- Índice de maturidade de IA;
- Formas de utilização de IA nas empresas;
- Evolução da adoção de IA.

### Modelos de trabalho
- Trabalho remoto;
- Trabalho híbrido;
- Trabalho presencial;
- Intenção de mudança diante de um retorno ao presencial.

---

## Principais resultados

Entre os principais resultados encontrados, destacam-se:

- forte presença de profissionais **Plenos e Sêniores** no mercado;
- crescimento da importância de perfis especializados em **Engenharia e Ciência de Dados**;
- concentração dos profissionais na região **Sudeste**;
- relação entre senioridade e faixas de remuneração mais elevadas;
- permanência do **Power BI** como principal ferramenta de BI entre os respondentes;
- crescimento da utilização de **Inteligência Artificial** em aplicações mais estruturadas;
- redução da participação do trabalho **100% remoto** em 2026;
- forte intenção de mudança entre profissionais remotos diante de uma possível exigência de trabalho 100% presencial.

---

## Estrutura do repositório

```text
projeto-state-of-data/
│
├── notebooks/
│   ├── Tech_Challenge_State_of_Data.ipynb
│   └── Funcoes_Fase3.py
│
├── diagrama/
│   └── arquitetura_aws.png
│
├── README.md
