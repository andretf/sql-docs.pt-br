---
title: "Operadores lógicos (Transact-SQL) | Microsoft Docs"
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- TSQL
helpviewer_keywords:
- operators [Transact-SQL], logical
- testing truth
- truth testing
- TRUE
- FALSE
- logical operators [SQL Server], Transact-SQL
ms.assetid: edd92f08-76fb-4fd7-a4b6-8520d6a81df1
caps.latest.revision: 26
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: aa7f707ba758b6811f2fc8425bf4c2da96973e02
ms.contentlocale: pt-br
ms.lasthandoff: 09/01/2017

---
# <a name="logical-operators-transact-sql"></a>Operadores lógicos (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2012-xxxx-xxxx-xxx_md](../../includes/tsql-appliesto-ss2012-xxxx-xxxx-xxx-md.md)]

  Os operadores lógicos testam a legitimidade de algumas condições. Operadores lógicos, como operadores de comparação, retornam um **booliano** de tipo de dados com um valor de TRUE, FALSE ou UNKNOWN.  
  
|Operador|Significado|  
|--------------|-------------|  
|[ALL](../../t-sql/language-elements/all-transact-sql.md)|TRUE se tudo em um conjunto de comparações for TRUE.|  
|[AND](../../t-sql/language-elements/and-transact-sql.md)|TRUE se as duas expressões boolianas forem TRUE.|  
|[QUALQUER](../../t-sql/language-elements/any-transact-sql.md)|TRUE se qualquer conjunto de comparações for TRUE.|  
|[ENTRE](../../t-sql/language-elements/between-transact-sql.md)|TRUE se o operando estiver dentro de um intervalo.|  
|[EXISTE](../../t-sql/language-elements/exists-transact-sql.md)|TRUE se uma subconsulta tiver qualquer linha.|  
|[IN](../../t-sql/language-elements/in-transact-sql.md)|TRUE se o operando for igual a um de uma lista de expressões.|  
|[COMO](../../t-sql/language-elements/like-transact-sql.md)|TRUE se o operando corresponder a um padrão.|  
|[NOT](../../t-sql/language-elements/not-transact-sql.md)|Inverte o valor de qualquer outro operador booliano.|  
|[OR](../../t-sql/language-elements/or-transact-sql.md)|TRUE se qualquer expressão booliana for TRUE.|  
|[ALGUNS](../../t-sql/language-elements/some-any-transact-sql.md)|TRUE se algum conjunto de comparações for TRUE.|  
  
## <a name="see-also"></a>Consulte também  
 [Precedência do operador &#40; Transact-SQL &#41;](../../t-sql/language-elements/operator-precedence-transact-sql.md)  
  
  