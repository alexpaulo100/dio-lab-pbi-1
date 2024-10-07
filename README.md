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




![modelo-transformacao-dados-dax](https://github.com/user-attachments/assets/d464b070-8ba8-49b3-85ec-692f9e059266)
