# Introdução ao SQL SERVER :floppy_disk:

### Aulas do Curso SQL Completo 2019 [Iniciantes] + Desafios + Muita Prática

### + DEV APRENDER CANAL YOUTUBE +

https://www.youtube.com/watch?v=rX2I7OjLqWE&t=4810s


###	Distinct: Para listar valores diferentes.


SELECT distinct FirstName FROM person.Person

select distinct LastName from Person.Person

	And : E
	Or  : Ou
	In  : Dentro
	>   : Maior
	<   : Menor
	=<  : Menor Igual
	>=  : Maior Igual
	Where: Onde faz condicional.

select * from Person.Person where LastName = 'miller' and FirstName = 'anna'


### cont: Faz contas da coluna passada. 

select count(Title) from Person.Person

select count(distinct Title) from Person.Person


select count(size) from Production.Product



### TOP: lista campos e sua contidades.



select top 100 * from Production.Product


select FirstName, MiddleName, LastName from Person.Person  order by FirstName asc, MiddleName asc ,LastName asc


select top 10 ProductID from Production.Product order by ListPrice desc

select top 4 Name, ProductNumber from Production.Product order by ProductID asc 


### Between: Pega valores entre. Como os exemplos à baixo:


select ListPrice from Production.Product where ListPrice NOT between 1000 and 1500;

SELECT * FROM HumanResources.Employee WHERE HireDate between '2009/01/01' and '2010/01/01' order by HireDate;


### IN: Para verificar se um valor correspondem com qualquer valor passado na lista de valores. 


select * from Person.Person where BusinessEntityID not in(2, 7, 13)


### LIKE: Procurar no campo, string que foram colocadas.


select * 
from Person.Person
where FirstName like '%ro_%'

### Desafio:

	1 -	Quantos produtos temos cadastrados no sistema que custa mais que 1500 dolares ?
	
	SELECT COUNT(ListPrice) FROM Production.Product WHERE ListPrice > 1500;

	2 - Quantas pessoas temos com o sobrenome que inicia com a letra P ?
	
	SELECT COUNT(LastName) FROM Person.Person WHERE LastName LIKE 'P%';

	3 - Em quantas cidades únicas estão cadastradas nossos clientes ? 
	
	SELECT COUNT(distinct city) FROM Person.Address; 

	4 - Quais são as cidades únicas que temos cadastradas em nosso sistema ? 

	SELECT distinct(City) FROM Person.Address

	5 - Quantos produtos vermelhos tem preço entre 500 a 1000 dolares ?

	SELECT COUNT(*) FROM Production.Product WHERE  ListPrice Between 500 and 1000 AND COLOR = 'RED' ;

	6 - Quantos produtos cadastrados tem a palavra 'road' no nome deles ?

	SELECT COUNT(ProductID) FROM Production.Product WHERE Name LIKE '%road%'




	MIN: Minimo
	MAX: Maxima
	SUM: Soma 
	AVG: Média

###	Função de Agregação Basicamente agregam ou combinam dados de uma tabela em 1 resultado só 



SELECT TOP 10 SUM(LineTotal) AS SOMA FROM Sales.SalesOrderDetail;

SELECT TOP 10 MIN(LineTotal) AS MINIMO FROM Sales.SalesOrderDetail;

SELECT TOP 10 AVG(LineTotal) FROM Sales.SalesOrderDetail;



### GROUP BY 
	O GROUP BY basicamente divide o resultado da sua pesquisa em grupos.

	Para cada grupo você pode aplicar uma função de agregação, por exemplo:
	- Calcular a soma de itens 
	- Contar o número de itens naquele grupo



SELECT * FROM Sales.SalesOrderDetail


SELECT SpecialOfferID, SUM(LineTotal) AS "SOMA" 
	  FROM Sales.SalesOrderDetail 
GROUP BY SpecialOfferID


#### VAMOS DIZER QUE EU QUERO SABER QUANTOS CADA PRODUTO FOI VENDIDO ATÉ HOJE

SELECT 
	 ProductID, COUNT(ProductID) AS QUANTIDADE_VENDIDA
FROM Sales.SalesOrderDetail
GROUP BY ProductID

#### VAM0S DIZER QUE EU QUERO SABER QUANTOS NOMES DE CADA NOME TEMOS CADASTRADOS EM NOSSO BANCO DE DADOS 


SELECT 
	FirstName, count(FirstName) AS QUANTIDADE_NOME
FROM  Person.Person
GROUP BY FirstName

#### NA TABELA PRODUCTION.PRODUCT EU QUERO SABER A MÉDIA DE PREÇO PARA OS PRODUTOS QUE SÃO PRATAS(SILVER)

SELECT COLOR, AVG(ListPrice) AS MEDIA
	FROM Production.Product 
WHERE COLOR = 'SILVER'
GROUP BY COLOR, ListPrice 



	