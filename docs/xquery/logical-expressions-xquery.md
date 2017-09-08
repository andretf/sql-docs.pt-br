---
title: "Expressões lógicas (XQuery) | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
applies_to:
- SQL Server
dev_langs:
- XML
helpviewer_keywords:
- logical operators [SQL Server], XQuery
- effective Boolean value [XQuery]
- logical expressions [XQuery]
- EBV
- expressions [XQuery], logical
ms.assetid: de94cd2e-2d48-49fb-9ebd-a2d90c79bf62
caps.latest.revision: 26
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: e6a7c65f0c5758bdc8f50582d6d2288f9918677b
ms.contentlocale: pt-br
ms.lasthandoff: 09/01/2017

---
# <a name="logical-expressions-xquery"></a>Expressões lógicas (XQuery)
[!INCLUDE[tsql-appliesto-ss2012-xxxx-xxxx-xxx_md](../includes/tsql-appliesto-ss2012-xxxx-xxxx-xxx-md.md)]

  XQuery oferece suporte à lógica **e** e **ou** operadores.  
  
```  
expression1 and expression2  
expression1 or expression2  
```  
  
 As expressões de teste, `expression1,``expression2`, na [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] pode resultar em uma sequência vazia, uma sequência de um ou mais nós ou um único valor booliano. Com base no resultado, o valor Booliano efetivo da sequência é determinado da maneira seguinte:  
  
-   Se a expressão de teste resultar em uma sequência vazia, o resultado da expressão será False.  
  
-   Se a expressão de teste resultar em um único valor Booliano, esse valor será o resultado da expressão.  
  
-   Se a expressão de teste resultar em uma sequência de um ou mais nós, o resultado da expressão será True.  
  
-   Caso contrário, um erro estático surgirá.  
  
 A lógica **e** e **ou** operador, em seguida, é aplicado aos valores booliano resultantes das expressões com as semânticas lógicas padrão.  
  
 A consulta a seguir recupera do catálogo de produtos as pequenas imagens de ângulo frontal, o elemento <`Picture`>, para um modelo de produto específico. Observe que para cada documento de descrição de produto, o catálogo pode armazenar uma ou mais imagens de produto com atributos diferentes, como tamanho e ângulo.  
  
```  
SELECT CatalogDescription.query('  
     declare namespace PD="http://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription";  
     for $F in /PD:ProductDescription/PD:Picture[PD:Size="small"   
                                                 and PD:Angle="front"]  
     return   
         $F   
    ') as Result  
FROM  Production.ProductModel  
where ProductModelID=19  
```  
  
 Este é o resultado:  
  
```  
<PD:Picture   
  xmlns:PD="http://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription">  
  <PD:Angle>front</PD:Angle>  
  <PD:Size>small</PD:Size>  
  <PD:ProductPhotoID>31</PD:ProductPhotoID>  
</PD:Picture>  
  
```  
  
## <a name="see-also"></a>Consulte também  
 [Expressões XQuery](../xquery/xquery-expressions.md)  
  
  