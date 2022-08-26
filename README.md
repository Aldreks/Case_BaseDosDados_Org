# Project: CASE BASEDOSDADOS.ORG
## Objetivo: Avaliar conhecimentos em Python, ETL, SQL
## Autor: Aldreks Albuquerque
## Data: 25/08/2022

--------------------------------------------------------------------------------------------------------- 

### Aplicação do Projeto:
Normalizar base de dados em CSV, utilisando Python 3.10.6, e apresentar insights em dashboard (gráficos).

### Estrutura do código:
- Carrega-se as bibliotecas à serem usadas no processo.
- Carrega-se o dataset "municipio.csv" e cria-se o dataframe.
- Visualiza-se o dataframe em busca de anormalidades nos dados e para compreender os dados.
- Verifica-se a estrutura e dimensão do dataset.
- Faz-se a normalização (tratamento) dos dados como: exclusão de registros ou colunas que não agregam valor as análises desejadas, 
bem como registros vazios ou dados inconsistentes, registros duplicados.
- Após normalização, segue-se as análises dos dados buscando insights válidos e significativos para tomada de decisão.
- Em seguida gera-se os gráficos para demonstração por visualização de tais insights criados.
- Finalmente, faz-se algumas consultas SQL na base de dados do Postgres/SQL, obtendo alguns insights relevantes.
- Seria possível, também, termos utilizado Spark e SparkSQL, bem como arquivo Parquet, para uma maior flexibilidade 
e eficiência no manuseio do dataset transformado em dataframe.

### Atendimento aos requisitos
- Utilizar as bases do datalake da "basedosdados". Foi utilizada a base <b>"Censo Agropecuário"</b>;
- Utilizar o pacote basedosdados em Python;
- Subir a visualização e todo código em Python em um repositório público no seu Github;
- Incluir alguma query em SQL no código 

### Recursos utilizados:
- IDE - Microsoft Visual Studio Code (VS Code)  v. 1.70.2
- Arquivo jupyter notebook
- Pandas
- Matplotlib
- SQL

### Considerações Sobre a Base de Dados e o Processo de ETL:
1. O dataset continha 20.738 registros e 116 colunas;
2. Haviam 878.323 campos vazios (dados ausentes);
3. Não haviam linhas com dados duplicados;
4. As colunas "proporcao_despesa_fertilizante", "proporcao_despesa_defensivos", "proporcao_despesa_sementes", "proporcao_despesa_salarios", foram
excluídas do dataset por possuírem mais de 90% de dados ausentes, se tornando irrelevantes para o processo de análise e insights, restando 112 colunas válidas;
5. Mesmo com a dropagem das colunas, supra-citadas, o volume de dados vazios (ausentes) ainda foi elevadíssimo. Foi tomada a decisão de trabalharmos apenas
com as colunas que apresentassem, no máximo, 3,6% de dados ausentes. Assim, criamos novo dataset com tais dados, diminuindo o impacto dos dados ausentes;
6. As colunas: <b>"ano, sigla_uf, valor_total_producao_cafe e producao_leite"</b> apresentavam 100% de integridade dos dados. E a coluna "producao_cafe" 
apresentava 98% de integridade. Por tais considerações e por serem dados relevantes, escolhemos as mesmas como amostragem para nossa análise nessa apresentação;
7. O dataset é composto por dados dos anos: 1985, 1996, 2006, 2017.

### Análise dos Dados (Insights)

- Gráfico_1 - ANÁLISE DO VALOR TOTAL DE PRODUÇÃO DO CAFÉ: Verificamos que o ano 2006 teve maior valor negociado. O valor mais baixo ficou com o ano 2017. Existe
a possibilidade de, talvez, o impute de dados do ano 2017 estar incompleto, o que explicaria a expressiva baixa, quase insignificante, do valor negociado
quando, inclusive, comparamos com os anos de 1996 e 1985;

- Gráfico_2 - ANÁLISE DA PRODUÇÃO DE CAFÉ: Verifica-se que o ano 1985 foi recorde de safra. O ano mais baixo foi 1996, menos de 1/5 do ano 1985. O segundo lugar
ficou com o ano 2017, e o terceiro lugar com o ano 2006.

- Gráfico 3 - ANÁLISE DA PRODUÇÃO DE LEITE: Verifica-se que o ano 1985 teve recorde de safra. O ano de 1996 não apresentou dados imputados. O ano de 2006 teve pouco mais de 5 milhões de Litros ficando em segundo lugar. Já o ano de 2017 teve o menor valor não chegando a 500 mil litros. Mais uma vez sugere que o ano de 2017 pode não estar com o ano completo;

- Gráfico 4 - ANÁLISE DO VALOR DA PRODUÇÃO DE CAFÉ ACUMULADA POR ESTADO: Vefica-se que o primeiro lugar ficou com MG com pouco mais de $ 70 Mi. Já MS ficou em segundo lugar com pouco mais de $ 54 Mi. O terceiro lugar coube a GO com cerca de $ 50 Mi;

- Gráfico 5 - ANÁLISE PRODUÇÃO DE CAFÉ ACUMULADA POR ESTADO: Verifica-se que o primeiro lugar ficou com MG com pouco mais de 3 Mi de toneladas. Já SP ficou em segundo lugar com pouco menos de 1,5 Mi de toneladas. O terceiro lugar coube a ES com pouco menos de 1 Mi de toneladas;
 
- Gráfico 6 - ANÁLISE PRODUÇÃO DE LEITE POR ESTADO: Verifica-se que o primeiro lugar ficou com a BA com pouco menos de 1,6 Mi de toneladas. Já MG ficou em segundo lugar com pouco menos de 1,2 Mi de toneladas. O terceiro lugar coube a RS com cerca de 1 Mi de toneladas;

