---
title: "Expressões de comparação (XQuery) | Microsoft Docs"
ms.custom: 
ms.date: 08/09/2016
ms.prod: sql-non-specified
ms.prod_service: sql-non-specified
ms.service: 
ms.component: xquery
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- XML
helpviewer_keywords:
- node comparison operators [XQuery]
- comparison expressions [XQuery]
- node order comparison operators [XQuery]
- expressions [XQuery], comparison
- comparison operators [XQuery]
- value comparison operators
ms.assetid: dc671348-306f-48ef-9e6e-81fc3c7260a6
caps.latest.revision: 
author: rothja
ms.author: jroth
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: dfaf22d056759c6dc9350bec0bd265d1909d46b5
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2018
---
# <a name="comparison-expressions-xquery"></a>Expressões de comparação (XQuery)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  O XQuery fornece os seguintes tipos de operadores de comparação:  
  
-   Operadores de comparação gerais  
  
-   Operadores de comparação de valor  
  
-   Operadores de comparação de nó  
  
-   Operadores de comparação de ordem do nó  
  
## <a name="general-comparison-operators"></a>Operadores de comparação gerais  
 Os operadores de comparação gerais podem ser usados para comparar valores atômicos, sequências ou qualquer combinação dos dois.  
  
 Os operadores gerais estão definidos na tabela a seguir.  
  
|Operador|Description|  
|--------------|-----------------|  
|=|Equal|  
|!=|Não igual|  
|\<|Menor que|  
|>|Maior que|  
|\<=|Menor que ou igual a|  
|>=|Maior que ou igual a|  
  
 Quando você estiver comparando duas sequências usando operadores de comparação gerais e houver um valor na segunda sequência que compara True a um valor na primeira sequência, o resultado geral é True. Caso contrário, será False. Por exemplo, (1, 2, 3) = (3, 4) é True, pois o valor 3 aparece em ambas as sequências.  
  
```  
declare @x xml  
set @x=''  
select @x.query('(1,2,3) = (3,4)')    
```  
  
 A comparação espera que os valores sejam de tipos comparáveis. De forma específica, eles são verificados estaticamente. Para comparações numéricas, pode ocorrer a promoção de tipo numérico. Por exemplo, se um valor decimal de 10 for comparado a um valor 1e1 duplo, o valor decimal será alterado para duplo. Observe que isso pode criar resultados inexatos, pois comparações duplas não podem ser exatas.  
  
 Se um dos valores for não digitado, ele será convertido no tipo de outro valor. No exemplo a seguir, o valor 7 é tratado como um inteiro. Antes de ser comparado, o valor não digitado de /a [1] é convertido em um inteiro. A comparação de inteiro retorna True.  
  
```  
declare @x xml  
set @x='<a>6</a>'  
select @x.query('/a[1] < 7')  
```  
  
 Inversamente, se o valor não digitado for comparado a uma cadeia de caracteres ou outro valor não digitado, ele será convertido em xs:string. Na consulta a seguir, a cadeia de caracteres 6 é comparada à cadeia de caracteres "17". A consulta a seguir retorna False devido à comparação da cadeia de caracteres.  
  
```  
declare @x xml  
set @x='<a>6</a>'  
select @x.query('/a[1] < "17"')  
```  
  
 A consulta a seguir retorna imagens de tamanho pequeno de um modelo de produto do catálogo de produtos fornecido no banco de dados de exemplo AdventureWorks. A consulta compara uma sequência de valores atômicos retornada por `PD:ProductDescription/PD:Picture/PD:Size` com uma “pequena” sequência de singleton. Se a comparação for True, ele retorna o < imagem\> elemento.  
  
```  
WITH XMLNAMESPACES ('http://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription' AS PD)  
SELECT CatalogDescription.query('         
    for $P in /PD:ProductDescription/PD:Picture[PD:Size = "small"]         
    return $P') as Result         
FROM   Production.ProductModel         
WHERE  ProductModelID=19         
```  
  
 A consulta a seguir compara uma sequência de números de telefone em < número\> elementos para a cadeia de caracteres literal "112-111-1111". A consulta comparará a sequência de elementos de número de telefone na coluna AdditionalContactInfo para determinar se há um número de telefone específico para um cliente específico no documento.  
  
```  
WITH XMLNAMESPACES (  
  'http://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ContactTypes' AS act,  
  'http://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ContactInfo' AS aci)  
  
SELECT AdditionalContactInfo.value('         
   /aci:AdditionalContactInfo//act:telephoneNumber/act:number = "112-111-1111"', 'nvarchar(10)') as Result         
FROM Person.Contact         
WHERE ContactID=1         
```  
  
 A consulta retorna True. Isso indica que o número existe no documento. A consulta a seguir é uma versão levemente modificada da consulta anterior. Nesta consulta, são comparados os valores de número de telefone recuperados do documento a uma sequência de dois valores de número de telefone. Se a comparação for True, o < número\> elemento será retornado.  
  
```  
WITH XMLNAMESPACES (  
  'http://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ContactTypes' AS act,  
  'http://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ContactInfo' AS aci)  
  
SELECT AdditionalContactInfo.query('         
  if (/aci:AdditionalContactInfo//act:telephoneNumber/act:number = ("222-222-2222","112-111-1111"))         
  then          
     /aci:AdditionalContactInfo//act:telephoneNumber/act:number         
  else         
    ()') as Result         
FROM Person.Contact         
WHERE ContactID=1  
  
```  
  
 Este é o resultado:  
  
```  
\<act:number   
  xmlns:act="http://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ContactTypes">  
    111-111-1111  
\</act:number>  
\<act:number   
  xmlns:act="http://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ContactTypes">  
    112-111-1111  
\</act:number>   
```  
  
## <a name="value-comparison-operators"></a>Operadores de comparação de valores  
 São usados operadores de comparação de valor para comparar valores atômicos. Observe que você pode usar operadores de comparação gerais em vez de operadores de comparação de valor em suas consultas.  
  
 Os operadores de comparação de valor são definidos na tabela a seguir.  
  
|Operador|Description|  
|--------------|-----------------|  
|eq|Equal|  
|ne|Não igual|  
|lt|Menor que|  
|gt|Maior que|  
|le|Menor que ou igual a|  
|ge|Maior que ou igual a|  
  
 Se os dois valores compararem o mesmo de acordo com o operador escolhido, a expressão retornará True. Caso contrário, ele retornará False. Se qualquer valor for uma sequência vazia, o resultado da expressão será False.  
  
 Esses operadores só funcionam em valores atômicos singleton. Ou seja, você não pode especificar uma sequência como um dos operandos.  
  
 Por exemplo, a seguinte consulta recupera \<imagem > elementos de um modelo de produto em que o tamanho da imagem é "pequeno:  
  
```  
SELECT CatalogDescription.query('         
              declare namespace PD="http://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription";         
              for $P in /PD:ProductDescription/PD:Picture[PD:Size eq "small"]         
              return         
                    $P         
             ') as Result         
FROM Production.ProductModel         
WHERE ProductModelID=19         
```  
  
 Observe o seguinte na consulta anterior:  
  
-   O `declare namespace` define o prefixo de namespace que é subsequentemente utilizado na consulta.  
  
-   O \<tamanho > o valor do elemento é comparado com o valor atômico especificado, "pequeno".  
  
-   Observe que, como os operadores de valor só funcionam em valores atômicos, o **Data ()** função implicitamente é usada para recuperar o valor do nó. Ou seja, o `data($P/PD:Size) eq "small"` produz o mesmo resultado.  
  
 Este é o resultado:  
  
```  
\<PD:Picture   
  xmlns:PD="http://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription">  
  \<PD:Angle>front\</PD:Angle>  
  \<PD:Size>small\</PD:Size>  
  \<PD:ProductPhotoID>31\</PD:ProductPhotoID>  
\</PD:Picture>  
```  
  
 Observe que as regras da promoção de tipo para comparações de valor são as mesmas das comparações gerais. Além disso, o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] usa as mesmas regras de conversão para valores não digitados durante as comparações de valor que as usadas durante as comparações gerais. Em contraste, as regras na especificação XQuery sempre convertem o valor não digitado em xs:string durante as comparações de valor.  
  
## <a name="node-comparison-operator"></a>Operador de comparação de nó  
 O operador de comparação de nó, **é**, aplica-se somente aos tipos de nó. O resultado que ele retorna indica se dois nós passados como operandos representam o mesmo nó no documento original. Esse operador retornará True se os dois operandos forem o mesmo nó. Caso contrário, retornará False.  
  
 A consulta a seguir verifica se o local do centro de trabalho 10 é o primeiro no processo de fabricação de um modelo de produto específico.  
  
```  
WITH XMLNAMESPACES ('http://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions' AS AWMI)  
  
SELECT ProductModelID, Instructions.query('         
    if (  (//AWMI:root/AWMI:Location[@LocationID=10])[1]         
          is          
          (//AWMI:root/AWMI:Location[1])[1] )          
    then         
          <Result>equal</Result>         
    else         
          <Result>Not-equal</Result>         
         ') as Result         
FROM Production.ProductModel         
WHERE ProductModelID=7           
```  
  
 Este é o resultado:  
  
```  
ProductModelID       Result          
-------------- --------------------------  
7              <Result>equal</Result>      
```  
  
## <a name="node-order-comparison-operators"></a>Operadores de comparação da ordem do nó  
 Os operadores de comparação da ordem do nó comparam pares de nós, com base em suas posições em um documento.  
  
 Estas são as comparações feitas, com base na ordem do documento:  
  
-   `<<`: **Operando 1** preceder **operando 2** na ordem do documento.  
  
-   `>>`: **Operando 1** siga **operando 2** na ordem do documento.  
  
 A consulta a seguir retorna True se a descrição do catálogo de produto tem a \<garantia > elemento que aparecem antes do \<manutenção > elemento na ordem do documento de um produto específico.  
  
```  
WITH XMLNAMESPACES (  
  'http://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription' AS PD,  
  'http://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelWarrAndMain' AS WM)  
  
SELECT CatalogDescription.value('  
     (/PD:ProductDescription/PD:Features/WM:Warranty)[1] <<   
           (/PD:ProductDescription/PD:Features/WM:Maintenance)[1]', 'nvarchar(10)') as Result  
FROM  Production.ProductModel  
where ProductModelID=19  
```  
  
 Observe o seguinte na consulta anterior:  
  
-   O **Value ()** método o **xml**tipo de dados é usado na consulta.  
  
-   O resultado booliano da consulta é convertido em **nvarchar (10)** e retornado.  
  
-   A consulta retorna True.  
  
## <a name="see-also"></a>Consulte também  
 [Digite sistema &#40; XQuery &#41;](../xquery/type-system-xquery.md)   
 [Expressões XQuery](../xquery/xquery-expressions.md)  
  
  
