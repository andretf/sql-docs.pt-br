---
title: XML (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 07/26/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- xml_TSQL
- xml
dev_langs:
- TSQL
helpviewer_keywords:
- xml data type [SQL Server], about xml data type
ms.assetid: 9198f671-8e61-4ca4-9c3a-859f84020e62
caps.latest.revision: 35
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 9e85eb245cf9d53f7d38579928a5145828797002
ms.contentlocale: pt-br
ms.lasthandoff: 09/01/2017

---
# <a name="xml-transact-sql"></a>xml (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  É o tipo de dados que armazena dados XML. Você pode armazenar **xml** instâncias em uma coluna ou uma variável de **xml** tipo.  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Convenções da sintaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
xml ( [ CONTENT | DOCUMENT ] xml_schema_collection )  
```  
  
## <a name="arguments"></a>Argumentos  
 CONTENT  
 Restringe o **xml** instância seja um fragmento XML bem-formado. Os dados XML podem conter vários zeros ou mais elementos no nível superior. Também são permitidos nós de texto no nível superior.  
  
 Esse é o comportamento padrão.  
  
 DOCUMENT  
 Restringe o **xml** instância seja um documento XML bem formado. Os dados XML devem ter um, e somente um, elemento raiz. Nós de texto não são permitidos no nível superior.  
  
 *xml_schema_collection*  
 É o nome de uma coleção de esquema XML. Para criar um tipo **xml** coluna ou variável, você pode opcionalmente especificar o nome de coleção de esquema XML. Para obter mais informações sobre digitados e não tipados XML, consulte [comparar XML digitado com XML não digitado](../../relational-databases/xml/compare-typed-xml-to-untyped-xml.md).  
  
## <a name="remarks"></a>Comentários  
 A representação armazenada de **xml** instâncias de tipo de dados não podem exceder 2 gigabytes (GB) de tamanho.  
  
 As facetas CONTENT e DOCUMENT se aplicam apenas a XML com tipo. Para obter mais informações, consulte [comparar XML digitado com XML não digitado](../../relational-databases/xml/compare-typed-xml-to-untyped-xml.md).  
  
## <a name="examples"></a>Exemplos  
  
```  
USE AdventureWorks2012;  
GO  
DECLARE @y xml (Sales.IndividualSurveySchemaCollection);  
SET @y =  (SELECT TOP 1 Demographics FROM Sales.Individual);  
SELECT @y;  
GO  
```  
  
## <a name="see-also"></a>Consulte também  
 [Conversão de tipo de dados &#40; mecanismo de banco de dados &#41;](../../t-sql/data-types/data-type-conversion-database-engine.md)   
 [Tipos de dados &#40;Transact-SQL&#41;](../../t-sql/data-types/data-types-transact-sql.md)   
 [Métodos de tipos de dados xml](../../t-sql/xml/xml-data-type-methods.md)   
 [Referência de linguagem XQuery &#40;SQL Server&#41;](../../xquery/xquery-language-reference-sql-server.md)  
  
  
