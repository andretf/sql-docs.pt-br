---
title: Propriedade CommandType (ADO) | Microsoft Docs
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: ado
ms.technology:
- drivers
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: sql
ms.tgt_pltfrm: 
ms.topic: article
apitype: COM
f1_keywords:
- Command15::CommandType
helpviewer_keywords:
- CommandType property [ADO]
ms.assetid: ca44809c-8647-48b6-a7fb-0be70a02f53e
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 607c78b7026d482660c4866be58ffa30d0b86196
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2018
---
# <a name="commandtype-property-ado"></a>Propriedade CommandType (ADO)
Indica o tipo de um [comando](../../../ado/reference/ado-api/command-object-ado.md) objeto.  
  
## <a name="settings-and-return-values"></a>Configurações e valores de retorno  
 Define ou retorna uma ou mais [CommandTypeEnum](../../../ado/reference/ado-api/commandtypeenum.md) valores.  
  
> [!NOTE]
>  Não use o **CommandTypeEnum** valores de **adCmdFile** ou **adCmdTableDirect** com **CommandType**. Esses valores podem ser usados apenas como opções com a [abrir](../../../ado/reference/ado-api/open-method-ado-recordset.md) e [Requery](../../../ado/reference/ado-api/requery-method.md) métodos de um [registros](../../../ado/reference/ado-api/recordset-object-ado.md).  
  
## <a name="remarks"></a>Remarks  
 Use o **CommandType** propriedade para otimizar a avaliação do [CommandText](../../../ado/reference/ado-api/commandtext-property-ado.md) propriedade.  
  
 Se o **CommandType** o valor da propriedade é definido como o valor padrão, **adCmdUnknown**, você pode enfrentar desempenho reduzido porque ADO deve fazer chamadas para o provedor para determinar se o  **CommandText** propriedade é um nome de tabela, um procedimento armazenado ou uma instrução SQL. Se você souber o tipo de comando que você está usando, configurando o **CommandType** propriedade instrui o ADO para ir diretamente para o código relevante. Se o **CommandType** propriedade não corresponde ao tipo de comando no **CommandText** propriedade, um erro ocorre quando você chama o [Execute](../../../ado/reference/ado-api/execute-method-ado-command.md) método.  
  
## <a name="applies-to"></a>Aplica-se a  
 [Objeto Command (ADO)](../../../ado/reference/ado-api/command-object-ado.md)  
  
## <a name="see-also"></a>Consulte também  
 [ActiveConnection CommandText, CommandTimeout, CommandType, tamanho e exemplo de propriedades de direção (VB)](../../../ado/reference/ado-api/activeconnection-commandtext-commandtimeout-commandtype-size-example-vb.md)   
 [ActiveConnection CommandText, CommandTimeout, CommandType, tamanho e exemplo de propriedades de direção (VC + +)](../../../ado/reference/ado-api/activeconnection-commandtext-commandtimeout-commandtype-size-example-vc.md)   
 [ActiveConnection CommandText, CommandTimeout, CommandType, tamanho e exemplo de propriedades de direção (JScript)](../../../ado/reference/ado-api/activeconnection-commandtext-timeout-type-size-example-jscript.md)
