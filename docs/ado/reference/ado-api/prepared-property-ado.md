---
title: Preparado propriedade (ADO) | Microsoft Docs
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
- Command15::Prepared
helpviewer_keywords:
- Prepared property [ADO]
ms.assetid: 11ca8825-765e-4bb4-a6ce-3f6564ad8755
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: c5b45f14d0513dfda61688dc664affbf760c8598
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2018
---
# <a name="prepared-property-ado"></a>Propriedade preparado (ADO)
Indica se é necessário salvar uma versão compilada de uma [comando](../../../ado/reference/ado-api/command-object-ado.md) antes da execução.  
  
## <a name="settings-and-return-values"></a>Configurações e valores de retorno  
 Define ou retorna um **booliano** valor que, se definido como **True**, indica que o comando deve ser preparado.  
  
## <a name="remarks"></a>Remarks  
 Use o **preparado** propriedade para que o provedor de salvar uma versão preparada (ou compilada) da consulta especificada no [CommandText](../../../ado/reference/ado-api/commandtext-property-ado.md) propriedade antes de um [comando](../../../ado/reference/ado-api/command-object-ado.md) do objeto primeira execução. Isso pode reduzir a primeira execução de um comando, mas depois que o provedor compila um comando, o provedor usará a versão compilada do comando para todas as execuções subsequentes, que resultarão em desempenho aprimorado.  
  
 Se a propriedade for **False**, o provedor será executado o **comando** objeto diretamente, sem criar uma versão compilada.  
  
 Se o provedor não oferece suporte a preparação de comando, pode retornar um erro quando essa propriedade é definida como **True**. Se o provedor não retornar um erro, ele simplesmente ignora a solicitação para preparar o comando e conjuntos de **preparado** propriedade **False**.  
  
## <a name="applies-to"></a>Aplica-se a  
 [Objeto Command (ADO)](../../../ado/reference/ado-api/command-object-ado.md)  
  
## <a name="see-also"></a>Consulte também  
 [Exemplo da propriedade preparada (VB)](../../../ado/reference/ado-api/prepared-property-example-vb.md)   
 [Exemplo da propriedade Prepared (VC++)](../../../ado/reference/ado-api/prepared-property-example-vc.md)   
