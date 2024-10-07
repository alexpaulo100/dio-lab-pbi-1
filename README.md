# dio-lab-pbi-1
### Desafio 1 - Analisando dados de um Dashboard de Vendas no Power BI
 
### Desafio 2 - Criando Relatório Gerencial de Vendas e Publicando no Power BI Service

### Desafio 3 - Criando um Relatório de Caracterização da base de dados Company

#### Consulta SQL para Mesclar Colaboradores e Nomes dos Gerentes

#### Este script SQL cria uma tabela que combina informações de colaboradores e seus respectivos gerentes.

### Tabelas Usadas:
- employee (contém informações dos colaboradores)
- departament (contém informações dos departamentos e gerentes)

### Query para Criar a Tabela:
``sql
CREATE TABLE employee_with_managers AS
SELECT 
    CONCAT(e.Fname, ' ', e.Lname) AS Employee_Name,
    d.Mgr_ssn AS Manager_SSN,
    CONCAT(m.Fname, ' ', m.Lname) AS Manager_Name
FROM 
    employee e
JOIN 
    departament d ON e.Dno = d.Dnumber
LEFT JOIN 
    employee m ON e.Super_ssn = m.Ssn OR (e.Super_ssn IS NULL AND m.Ssn = d.Mgr_ssn);``

### Explicação porque não é utilizado o atribuir e sim o mesclar para nomes e departamentos.

##### A mesclagem é essencial para criar um novo conjunto de dados que representa uma relação única entre departamento e localização, permitindo análises mais detalhadas.
##### A atribuição não se aplica aqui, pois não estamos apenas dando um valor, mas sim criando algo novo e significativo a partir da combinação de informações distintas.

### Desafio 4 - Criar o Diagrama Dimensional – Star Schema
<<<<<<< HEAD
### Desafio 5 - Projeto Transformação de Dados com Dax no Power BI


### Descrição do Projeto
Este projeto consiste na construção de um modelo de dados no Power BI utilizando a tabela "Financial Sample" como base.
O modelo foi desenvolvido seguindo a metodologia de star schema, 
permitindo uma análise eficiente e intuitiva dos dados financeiros.

Estrutura do Repositório:
Arquivo do projeto Power BI: Transformacao-de-dados-Dax.pbix

Imagem do Esquema em Estrela: 
Diagrama que ilustra a estrutura do modelo de dados.
#### Processo de Construção do Diagrama
##### Importação de Dados:
##### Iniciei importando a tabela "Financial Sample" para o Power BI.

#### Criação de Tabelas Dimensão:

###### Criei tabelas de dimensão, como D_Produtos, D_Descontos, D_Calendário, D_ Produtos_Detalhes e D_Detalhes, a partir da tabela original.
###### Usei o Power Query para duplicar e transformar os dados, selecionando colunas relevantes e criando medidas necessárias.
##### Criação da Tabela Fato:

###### A tabela F_Vendas foi criada, incluindo as métricas essenciais para análise, como unidades vendidas e preço de vendas.

##### Criação da Tabela de Calendário:
###### Criei a tabela D_Calendário utilizando a função DAX CALENDAR:
``D_Calendário = CALENDAR(MIN(financials_origem[Date]), MAX(financials_origem[Date]))``
###### Isso permitiu gerar uma tabela de datas abrangendo todo o período das vendas registradas.
##### Relacionamento entre Tabelas:

###### Relacionei as tabelas de dimensão com a tabela fato, assegurando que o modelo seguisse a estrutura de star schema.
##### Documentação do Esquema:

###### Salvei uma imagem do esquema em estrela para facilitar a visualização e entendimento do modelo.
#### Etapas e Funcionalidades
#### Tabelas Criadas
###### D_Produtos: Contém informações sobre produtos, incluindo medidas como média, mediana e valores máximos e mínimos de vendas.
###### D_Descontos: Inclui dados sobre descontos aplicados aos produtos.
###### D_Calendario: Criada com a função DAX CALENDAR, abrange todo o período das vendas registradas.
###### F_Vendas: Tabela fato que consolida as métricas de vendas, como unidades vendidas, preço de vendas e lucro.
###### D_Produtos_Detalhes: Contém os detalhes sobre os produtos
###### D_Detalhes: Contem mais detalhes nao contempladas nas demais tabelas dimensão referntes ao detalhes sobre vendas.
=======




![modelo-transformacao-dados-dax](https://github.com/user-attachments/assets/d464b070-8ba8-49b3-85ec-692f9e059266)
>>>>>>> e2f07fe02af3cf873a7a69ce9b93fed3abdf126a
