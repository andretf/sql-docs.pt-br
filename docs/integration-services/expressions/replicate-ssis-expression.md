---
title: "REPLICATE (expressão SSIS) | Microsoft Docs"
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- integration-services
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- REPLICATE function
ms.assetid: e7a37b93-6d1d-42d5-9a65-de1790abf6a5
caps.latest.revision: 34
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: c94e5f4221251b3b931ebabc5076620ba6ab0e7e
ms.contentlocale: pt-br
ms.lasthandoff: 08/03/2017

---
# <a name="replicate-ssis-expression"></a>REPLICATE (Expressão SSIS)
  Retorna uma expressão de caractere que é replicada várias vezes. O argumento *times* deve ser avaliado como um inteiro.  
  
> [!NOTE]  
>  A função REPLICATE usa com frequência cadeias longas e, portanto, é mais provável de incorrer o limite de 4.000 caracteres no tamanho da expressão. Se o resultado da avaliação de uma expressão tiver o tipo de dados DT_WSTR ou DT_STR do Integration Services, a expressão truncará em 4.000 caracteres. Se o tipo de resultado de uma subexpressão for DT_STR ou DT_WSTR, essa subexpressão será truncada em 4.000 caracteres, independentemente do tipo de resultado da expressão geral. As consequências do truncamento podem ser controladas muito bem ou causam um aviso ou um erro. Para obter mais informações, consulte [Sintaxe &#40;SSIS&#41;](../../integration-services/expressions/syntax-ssis.md).  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
REPLICATE(character_expression,times)  
```  
  
## <a name="arguments"></a>Argumentos  
 *character_expression*  
 É uma expressão de caractere a ser replicada.  
  
 *times*  
 É uma expressão de inteiro que especifica o número de vezes que *character_expression* é replicado.  
  
## <a name="result-types"></a>Tipos de resultado  
 DT_WSTR  
  
## <a name="remarks"></a>Comentários  
 Se *times* for zero, a função retornará uma cadeia de comprimento zero.  
  
 Se *times* for um número negativo, a função retornará um erro.  
  
 O argumento *times* também pode usar variáveis e colunas.  
  
 REPLICATE só funciona com o tipo de dados DT_WSTR. Um argumento *character_expression* que é um literal de cadeia de caracteres ou uma coluna de dados com o tipo de dados DT_STR é implicitamente convertido para o tipo de dados DT_WSTR antes que REPLICATE execute sua operação. Outros tipos de dados devem ser explicitamente convertidos para o tipo de dados DT_WSTR. Para obter mais informações, consulte [Tipos de dados do Integration Services](../../integration-services/data-flow/integration-services-data-types.md) e [Cast &#40;Expressão SSIS&#41;](../../integration-services/expressions/cast-ssis-expression.md).  
  
 REPLICATE retornará um resultado nulo se o argumento for nulo.  
  
## <a name="expression-examples"></a>Exemplos de expressões  
 Esse exemplo replica um literal de cadeia três vezes. O resultado de retorno é "Mountain BikeMountain BikeMountain Bike".  
  
```  
REPLICATE("Mountain Bike", 3)  
```  
  
 Esse exemplo replica os valores na coluna **Nome** pelo valor na variável **Vezes** . Se **Vezes** for 3 e **Nome** for Roda Dianteira de Passeio, o resultado de retorno será Roda Dianteira de PasseioRoda Dianteira de PasseioRoda Dianteira de Passeio.  
  
```  
REPLICATE(Name, @Times)  
```  
  
 Esse exemplo replica o valor na variável **Nome** pelo valor na coluna **Vezes** . **Times** tem um tipo de dados não Integer e a expressão inclui uma conversão explícita para um tipo de dados Integer. Se **Nome** contiver Capacete e **Vezes** for 2, o resultado de retorno será "CapaceteCapacete".  
  
```  
REPLICATE(@Name, (DT_I4(Times))  
```  
  
## <a name="see-also"></a>Consulte também  
 [Funções &#40; Expressão do SSIS &#41;](../../integration-services/expressions/functions-ssis-expression.md)  
  
  