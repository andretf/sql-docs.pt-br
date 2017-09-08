---
title: COMO (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/15/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- ESCAPE
- LIKE
- ESCAPE_TSQL
- LIKE_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- ESCAPE keyword
- '% (wildcard - character(s) to match)'
- ASCII pattern matching
- pattern searching [SQL Server]
- wildcard characters [SQL Server]
- literals [SQL Server], using wildcards
- character strings [SQL Server], LIKE
- exact matches [SQL Server]
- Boolean functions
- LIKE comparisons
- matching patterns [SQL Server]
- NOT LIKE keyword
ms.assetid: 581fb289-29f9-412b-869c-18d33a9e93d5
caps.latest.revision: 50
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 643966017caf06959fef24177dd93d7254f30915
ms.contentlocale: pt-br
ms.lasthandoff: 09/01/2017

---
# <a name="like-transact-sql"></a>LIKE (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all_md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  Determina se uma cadeia de caracteres específica corresponde a um padrão especificado. Um padrão pode incluir caracteres normais e curingas. Durante a correspondência de padrões, os caracteres normais devem corresponder exatamente aos caracteres especificados na cadeia de caracteres. No entanto, os caracteres curinga podem ser correspondidos a fragmentos arbitrários da cadeia de caracteres. O uso de caracteres curinga torna o operador LIKE mais flexível que o uso dos operadores de comparação de cadeias de caracteres = e !=. Se qualquer um dos argumentos não for do tipo de dados de cadeia de caracteres, o [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] o converterá no tipo de dados de cadeia de caracteres, se possível.  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Convenções da sintaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
-- Syntax for SQL Server and Azure SQL Database  
  
match_expression [ NOT ] LIKE pattern [ ESCAPE escape_character ]  
```  
  
```  
-- Syntax for Azure SQL Data Warehouse and Parallel Data Warehouse  
  
match_expression [ NOT ] LIKE pattern  
```  
  
## <a name="arguments"></a>Argumentos  
 *match_expression*  
 É qualquer [expressão](../../t-sql/language-elements/expressions-transact-sql.md) do tipo de dados de caractere.  
  
 *padrão*  
 É a cadeia de caracteres específica de caracteres a ser pesquisado em *match_expression*e pode incluir os seguintes caracteres curinga válidos. *padrão de* pode ter um máximo de 8.000 bytes.  
  
|Caractere curinga|Description|Exemplo|  
|------------------------|-----------------|-------------|  
|%|Qualquer cadeia de zero ou mais caracteres.|WHERE title LIKE '%computer%' localiza todos os títulos de livro com a palavra 'computer' em qualquer lugar no título do livro.|  
|_ (sublinhado)|Qualquer caractere único.|WHERE au_fname LIKE '_ean' localiza todos os nomes de quatro letras que terminam com ean (Dean, Sean e assim por diante).|  
|[ ]|Qualquer caractere único no intervalo ([a-f]) ou conjunto ([abcdef]) especificado.|WHERE au_lname LIKE '[C-P]arsen' localiza os sobrenomes de autores que terminem com arsen e que comecem com qualquer caractere único entre C e P, por exemplo, Carsen, Larsen, Karsen e assim por diante. Em pesquisas de intervalo, os caracteres incluídos no intervalo podem variar de acordo com as regras de classificação do agrupamento.|  
|[^]|Qualquer caractere único que não esteja no intervalo (^[a-f]) ou conjunto ([^abcdef]) especificado.|WHERE au_lname LIKE 'de[^l]%' localiza todos os sobrenomes de autor que comecem com de e a letra seguinte não seja l.|  
  
 *escape_character*  
 É um caractere colocado na frente de um caractere curinga para indicar que o curinga deve ser interpretado como um caractere comum, e não como um curinga. *escape_character* é uma expressão de caractere que não tem padrão e deve ser avaliada somente como um caractere.  
  
## <a name="result-types"></a>Tipos de resultado  
 **Booliano**  
  
## <a name="result-value"></a>Valor do resultado  
 LIKE retornará TRUE se o *match_expression* corresponde especificado *padrão*.  
  
## <a name="remarks"></a>Comentários  
 Ao executar comparações de cadeias de caracteres usando LIKE, todos os caracteres na cadeia padrão são significativos. Isso inclui espaços à esquerda ou à direita. Se uma comparação em uma consulta deve retornar todas as linhas com uma cadeia de caracteres LIKE 'abc ' (abc seguido de um único espaço), não será retornada nenhuma linha na qual o valor daquela coluna seja abc (abc sem espaço). Entretanto, os espaços em branco à direita da expressão cujo padrão é correspondido são ignorados. Se uma comparação em uma consulta deve retornar todas as linhas com a cadeia de caracteres LIKE 'abc' (abc sem espaço), serão retornadas todas as linhas que comecem com abc e que tenham zero ou mais espaços em branco à direita.  
  
 Uma comparação de cadeia de caracteres usando um padrão que contém **char** e **varchar** dados não podem passar uma comparação LIKE devido a como os dados são armazenados. Você deve entender o armazenamento de cada tipo de dados e onde uma comparação LIKE pode falhar. O exemplo a seguir passa um local **char** variável para um procedimento armazenado e, em seguida, usa correspondência de padrões para localizar todos os funcionários cujos sobrenomes comecem com um conjunto especificado de caracteres.  
  
```tsql
-- Uses AdventureWorks  
  
CREATE PROCEDURE FindEmployee @EmpLName char(20)  
AS  
SELECT @EmpLName = RTRIM(@EmpLName) + '%';  
SELECT p.FirstName, p.LastName, a.City  
FROM Person.Person p JOIN Person.Address a ON p.BusinessEntityID = a.AddressID  
WHERE p.LastName LIKE @EmpLName;  
GO  
EXEC FindEmployee @EmpLName = 'Barb';  
GO  
```  
  
 No `FindEmployee` procedimento, nenhuma linha será retornada porque o **char** variável (`@EmpLName`) contém espaços em branco à direita sempre que o nome contém menos de 20 caracteres. Porque o `LastName` coluna é **varchar**, não há nenhum espaço em branco à direita. Este procedimento falha porque os espaços em branco à direita são significativos.  
  
 No entanto, o exemplo a seguir terá êxito porque os espaços em branco não são adicionados a um **varchar** variável.  
  
```tsql
-- Uses AdventureWorks  
  
CREATE PROCEDURE FindEmployee @EmpLName varchar(20)  
AS  
SELECT @EmpLName = RTRIM(@EmpLName) + '%';  
SELECT p.FirstName, p.LastName, a.City  
FROM Person.Person p JOIN Person.Address a ON p.BusinessEntityID = a.AddressID  
WHERE p.LastName LIKE @EmpLName;  
GO  
EXEC FindEmployee @EmpLName = 'Barb';  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 ```
 FirstName      LastName            City
 ----------     -------------------- --------------- 
 Angela         Barbariol            Snohomish
 David          Barber               Snohomish
 (2 row(s) affected)  
 ``` 
 
## <a name="pattern-matching-by-using-like"></a>Correspondência de padrão com o uso de LIKE  
 LIKE oferece suporte à correspondência de padrão ASCII e à correspondência de padrão Unicode. Quando todos os argumentos (*match_expression*, *padrão*, e *escape_character*, se presente) são tipos de dados de caractere ASCII, correspondência de padrão ASCII é executada. Se algum dos argumentos for do tipo de dados Unicode, todos os argumentos serão convertidos em Unicode e será executada a correspondência de padrão Unicode. Quando você usa dados Unicode (**nchar** ou **nvarchar** tipos de dados) com LIKE, espaços em branco à direita são significativos; no entanto, para dados não Unicode, os espaços em branco não são significativos. LIKE Unicode é compatível com o padrão ISO. LIKE ASCII é compatível com versões anteriores do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
 A seguir é apresentada uma série de exemplos que mostram as diferenças em linhas retornadas entre a correspondência de padrão LIKE ASCII e Unicode.  
  
```tsql  
-- ASCII pattern matching with char column  
CREATE TABLE t (col1 char(30));  
INSERT INTO t VALUES ('Robert King');  
SELECT *   
FROM t   
WHERE col1 LIKE '% King';   -- returns 1 row  
  
-- Unicode pattern matching with nchar column  
CREATE TABLE t (col1 nchar(30));  
INSERT INTO t VALUES ('Robert King');  
SELECT *   
FROM t   
WHERE col1 LIKE '% King';   -- no rows returned  
  
-- Unicode pattern matching with nchar column and RTRIM  
CREATE TABLE t (col1 nchar (30));  
INSERT INTO t VALUES ('Robert King');  
SELECT *   
FROM t   
WHERE RTRIM(col1) LIKE '% King';   -- returns 1 row  
```  
  
> [!NOTE]  
>  As comparações de LIKE são afetadas por agrupamento. Para obter mais informações, veja [COLLATE &#40;Transact-SQL&#41;](~/t-sql/statements/collations.md).  
  
## <a name="using-the--wildcard-character"></a>Usando o caractere curinga %  
 Se o símbolo LIKE '5%' for especificado, o [!INCLUDE[ssDE](../../includes/ssde-md.md)] procurará o número 5 seguido por qualquer cadeia de zero ou mais caracteres.  
  
 Por exemplo, a consulta a seguir mostra todas as exibições de gerenciamento dinâmico do banco de dados [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)], porque todas começam com as letras `dm`.  
  
```tsql  
-- Uses AdventureWorks  
  
SELECT Name  
FROM sys.system_views  
WHERE Name LIKE 'dm%';  
GO  
```  
  
 Para consultar todos os objetos que não sejam exibições de gerenciamento dinâmico, use `NOT LIKE 'dm%'`. Se tiver um total de 32 objetos e LIKE localizar 13 nomes que correspondam ao padrão, NOT LIKE localizará os 19 objetos que não correspondem ao padrão LIKE.  
  
 Talvez você nem sempre localize os mesmos nomes com um padrão do tipo `LIKE '[^d][^m]%'`. Em vez de 19 nomes, poderá localizar somente 14, com todos os nomes que começam com `d` ou têm `m` como a segunda letra eliminada dos resultados, e os nomes de exibição de gerenciamento dinâmico. Isto ocorre porque as cadeias de correspondência com caracteres curinga negativos são avaliadas em etapas, um curinga de cada vez. Se a correspondência falhar em qualquer ponto da avaliação, ela será eliminada.  
  
## <a name="using-wildcard-characters-as-literals"></a>Usando caracteres curinga como literais  
 Você pode usar os caracteres curinga de correspondência de padrão como caracteres literais. Para usar um caractere curinga como um caractere literal, inclua o caractere curinga entre colchetes. A tabela a seguir mostra vários exemplos de uso da palavra-chave LIKE e dos caracteres curinga [ ].  
  
|Símbolo|Significado|  
|------------|-------------|  
|LIKE '5[%]'|5%|  
|LIKE '[_]n'|_n|  
|LIKE '[a-cdf]'|a, b, c, d ou f|  
|LIKE '[-acdf]'|-, a, c, d ou f|  
|LIKE '[ [ ]'|[|  
|LIKE ']'|]|  
|LIKE 'abc[_]d%'|abc_d e abc_de|  
|LIKE 'abc[def]'|abcd, abce e abcf|  
  
## <a name="pattern-matching-with-the-escape-clause"></a>Correspondência de padrão com a cláusula ESCAPE  
 Você pode procurar cadeias de caracteres que incluam um ou mais dos caracteres curinga especiais. Por exemplo, a tabela discounts em um banco de dados customers pode armazenar valores de desconto que incluem um sinal de por cento (%). Para procurar o sinal de por cento como um caractere em vez de como um caractere curinga, a palavra-chave ESCAPE e o caractere de escape devem ser fornecidos. Por exemplo, um banco de dados de exemplo contém uma coluna denominada comment que contém o texto 30%. Para procurar quaisquer linhas que contenham a cadeia de caracteres 30% em qualquer lugar da coluna comment, especifique uma cláusula WHERE, como `WHERE comment LIKE '%30!%%' ESCAPE '!'`. Se ESCAPE e o caractere de escape não forem especificados, o [!INCLUDE[ssDE](../../includes/ssde-md.md)] retornará quaisquer linhas com a cadeia 30.  
  
 Se não houver caractere depois de um caractere de escape no padrão de LIKE, o padrão não será válido e LIKE retornará FALSE. Se o caractere após um caractere de escape não for um caractere curinga, o caractere de escape será descartado e o caractere após ele será tratado como um caractere normal no padrão. Isso inclui os caracteres curinga de sinal de por cento (%), sublinhado (_) e colchete esquerdo ([) quando eles estiverem incluídos entre colchetes duplos ([ ]). Além disso, dentro dos caracteres de colchete duplo ([ ]), os caracteres de escape podem ser usados e o acento circunflexo (^), o hífen (-) e o colchete direito (]) podem seguir o caractere de escape.  
  
 0x0000 (**char(0)**) é um caractere indefinido em agrupamentos do Windows e não pode ser incluído em LIKE.  
  
## <a name="examples"></a>Exemplos  
  
### <a name="a-using-like-with-the--wildcard-character"></a>A. Usando LIKE com o caractere curinga %  
 O exemplo a seguir localiza todos os números de telefone com o código de área `415` na tabela `PersonPhone`.  
  
```tsql  
-- Uses AdventureWorks  
  
SELECT p.FirstName, p.LastName, ph.PhoneNumber  
FROM Person.PersonPhone AS ph  
INNER JOIN Person.Person AS p  
ON ph.BusinessEntityID = p.BusinessEntityID  
WHERE ph.PhoneNumber LIKE '415%'  
ORDER by p.LastName;  
GO  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
 
 ```
 FirstName             LastName             Phone
 -----------------     -------------------  ------------
 Ruben                 Alonso               415-555-124  
 Shelby                Cook                 415-555-0121  
 Karen                 Hu                   415-555-0114  
 John                  Long                 415-555-0147  
 David                 Long                 415-555-0123  
 Gilbert               Ma                   415-555-0138  
 Meredith              Moreno               415-555-0131  
 Alexandra             Nelson               415-555-0174  
 Taylor                Patterson            415-555-0170  
 Gabrielle              Russell             415-555-0197  
 Dalton                 Simmons             415-555-0115  
 (11 row(s) affected)  
 ``` 
 
### <a name="b-using-not-like-with-the--wildcard-character"></a>B. Usando NOT LIKE com o caractere curinga %  
 O exemplo a seguir localiza todos os números de telefone na tabela `PersonPhone` que têm códigos de área diferentes de `415`.  
  
```tsql  
-- Uses AdventureWorks  
  
SELECT p.FirstName, p.LastName, ph.PhoneNumber  
FROM Person.PersonPhone AS ph  
INNER JOIN Person.Person AS p  
ON ph.BusinessEntityID = p.BusinessEntityID  
WHERE ph.PhoneNumber NOT LIKE '415%' AND p.FirstName = 'Gail'  
ORDER BY p.LastName;  
GO  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
 
 ```
FirstName              LastName            Phone
---------------------- -------------------- -------------------
Gail                  Alexander            1 (11) 500 555-0120  
Gail                  Butler               1 (11) 500 555-0191  
Gail                  Erickson             834-555-0132  
Gail                  Erickson             849-555-0139  
Gail                  Griffin              450-555-0171  
Gail                  Moore                155-555-0169  
Gail                  Russell              334-555-0170  
Gail                  Westover             305-555-0100  
(8 row(s) affected)  
```  

### <a name="c-using-the-escape-clause"></a>C. Usando a cláusula ESCAPE  
 O exemplo a seguir usa a cláusula `ESCAPE` e o caractere de escape para localizar a cadeia de caracteres exata `10-15%` na coluna `c1` da tabela `mytbl2`.  
  
```tsql
USE tempdb;  
GO  
IF EXISTS(SELECT TABLE_NAME FROM INFORMATION_SCHEMA.TABLES  
      WHERE TABLE_NAME = 'mytbl2')  
   DROP TABLE mytbl2;  
GO  
USE tempdb;  
GO  
CREATE TABLE mytbl2  
(  
 c1 sysname  
);  
GO  
INSERT mytbl2 VALUES ('Discount is 10-15% off'), ('Discount is .10-.15 off');  
GO  
SELECT c1   
FROM mytbl2  
WHERE c1 LIKE '%10-15!% off%' ESCAPE '!';  
GO  
```  
  
### <a name="d-using-the---wildcard-characters"></a>D. Usando os caracteres curinga [ ]  
 O exemplo a seguir localiza funcionários no `Person` tabela com o nome de `Cheryl` ou `Sheryl`.  
  
```tsql  
-- Uses AdventureWorks  
  
SELECT BusinessEntityID, FirstName, LastName   
FROM Person.Person   
WHERE FirstName LIKE '[CS]heryl';  
GO  
```  
  
 O exemplo a seguir localiza as linhas de funcionários na tabela `Person` com os sobrenomes `Zheng` ou `Zhang`.  
  
```tsql  
-- Uses AdventureWorks  
  
SELECT LastName, FirstName  
FROM Person.Person  
WHERE LastName LIKE 'Zh[ae]ng'  
ORDER BY LastName ASC, FirstName ASC;  
GO  
```  
  
## <a name="examples-includesssdwfullincludessssdwfull-mdmd-and-includesspdwincludessspdw-mdmd"></a>Exemplos: [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] e[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
  
### <a name="e-using-like-with-the--wildcard-character"></a>E. Usando LIKE com o caractere curinga %  
 O exemplo a seguir localiza todos os funcionários a `DimEmployee` tabela com números de telefone que começam com `612`.  
  
```tsql  
-- Uses AdventureWorks  
  
SELECT FirstName, LastName, Phone  
FROM DimEmployee  
WHERE phone LIKE '612%'  
ORDER by LastName;  
```  
  
### <a name="f-using-not-like-with-the--wildcard-character"></a>F. Usando NOT LIKE com o caractere curinga %  
 O exemplo a seguir localiza todos os números de telefone no `DimEmployee` tabela que não começam com `612`.  .  
  
```tsql  
-- Uses AdventureWorks  
  
SELECT FirstName, LastName, Phone  
FROM DimEmployee  
WHERE phone NOT LIKE '612%'  
ORDER by LastName;  
```  
  
### <a name="g-using-like-with-the--wildcard-character"></a>G. Usando LIKE com o caractere curinga de _  
 O exemplo a seguir localiza todos os números de telefone que tem um código de área, começando com `6` e terminando em `2` no `DimEmployee` tabela. Observe que o caractere curinga % também é incluído no final do padrão de pesquisa, já que o código de área é a primeira parte do número de telefone e caracteres adicionais existirem depois do valor de coluna.  
  
```tsql  
-- Uses AdventureWorks  
  
SELECT FirstName, LastName, Phone  
FROM DimEmployee  
WHERE phone LIKE '6_2%'  
ORDER by LastName;   
```  
  
### <a name="h-using-the---wildcard-characters"></a>H. Usando os caracteres curinga [ ]  
 O exemplo a seguir localiza `DimEmployee` linhas com o nome de `Rob` ou `Bob`.  
  
```tsql  
-- Uses AdventureWorks  
  
SELECT FirstName, LastName, Phone  
FROM DimEmployee  
WHERE FirstName LIKE '[RB]ob'  
ORDER by LastName;  
```  
  
## <a name="see-also"></a>Consulte também  
 [Expressões &#40; Transact-SQL &#41;](../../t-sql/language-elements/expressions-transact-sql.md)   
 [Funções internas &#40;Transact-SQL&#41;](~/t-sql/functions/functions.md)   
 [SELECT &#40;Transact-SQL&#41;](../../t-sql/queries/select-transact-sql.md)   
 [ONDE &#40; Transact-SQL &#41;](../../t-sql/queries/where-transact-sql.md)  
 
