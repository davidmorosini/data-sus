# data-sus

Repositório dedicado para versionar os Notebooks com os scripts responsáveis por realizar a consolidação dos bancos de dados SIM/SIH


## SIH

Consiste em um banco de dados disponibilizado pela plataforma data-sus, está instanciado como uma coleção de arquivos `.xlsx`. Cada um deste contém informações de um determinado ano. Neste processamento estamos utilizando arquivos entre os anos de 2000 e 2020. Cada arquivo individual está organizado em planilhas representando cada uma um mês do ano corrente ao qual o arquivo representa.

### Objetivo

O objetivo deste item é consolidar o banco de dados, originalmente este conta com aproximadamente 40 milhões de registros, dos quais apenas uma pequena parte de fato é de interesse para o desenvolvimento de uma pesquisa relacionada a doenças respiratórias. Para isso, devemos unir todas as informações em um único ponto de verdade (Base de dados consolidada) apenas com as informações de interesse para a pesquisa.

### Metodologia

Dado o grande volume de informações nos arquivos originais, devemos dividir a consolidação em etapas menores, as quais estão dispostas abaixo

- **Seleção da base de dados original:** Nesta etapa devemos buscar junto ao data-sus os arquivos originais que serão utilizados para a consolidação.

- **Processamento por ano**: Conforme descrito acima, cada arquivo do SIH representa um ano e internamente conta com divisões (Planilhas) que representam os meses do ano corrente. Desta forma, devemos nesta etapa unir todas as informações dentro de um mesmo arquivo, ou seja, ter como produto um único arquivo sem divisões internas com todas as informações dispostas de forma sequencial. Além disso são selecionadas apenas as colunas específicas de interesse da pesquisa, desta forma otimizamos as estruturas de dados envolvidas e despoluímos a base final.

- **Filtragem dos dados:** Nesta etapa, utilizamos o produto anterior para selecionar apenas as linhas de cada ano que são de interesse para os pesquisadores. A filtragem é executada de uma forma simples atuando sobre três das N colunas selecionadas. Foi alinhado que se um uma determinada linha ocorrer um dos valores especificados em qualquer uma das colunas descritas esta linha deve ser selecionada, caso contrário será descartada.
  
