---
title: Evento FetchProgress (ADO) | Microsoft Docs
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
- FetchProgress
- Recordset::FetchProgress
helpviewer_keywords:
- FetchProgress event [ADO]
ms.assetid: 301716fd-81fc-40eb-8a04-221ef7ab410e
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 3bd5284c35e51a8cc711fe7612d1176241c00ac7
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2018
---
# <a name="fetchprogress-event-ado"></a>Evento FetchProgress (ADO)
O **FetchProgress**evento é chamado periodicamente durante uma operação demorada assíncrona para informar quantas linhas mais atualmente foram recuperadas no [registros](../../../ado/reference/ado-api/recordset-object-ado.md).  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
FetchProgress Progress, MaxProgress, adStatus, pRecordset  
```  
  
#### <a name="parameters"></a>Parâmetros  
 *Andamento*  
 Um **longo** valor que indica o número de registros que foram recuperados pela operação de busca no momento.  
  
 *MaxProgress*  
 Um **longo** esperado de valor que indica o número máximo de registros a serem recuperados.  
  
 *adStatus*  
 Um [EventStatusEnum](../../../ado/reference/ado-api/eventstatusenum.md) valor de status.  
  
 *pRecordset*  
 Um **registros** objeto que é o objeto para o qual os registros estão sendo recuperados.  
  
## <a name="remarks"></a>Remarks  
 Ao usar **FetchProgress** com um filho **registros**, lembre-se que o *andamento* e *MaxProgress* valores de parâmetro são derivados de subjacente [serviço Cursor](../../../ado/guide/appendixes/microsoft-cursor-service-for-ole-db-ado-service-component.md) conjunto de linhas. Os valores retornados representam o número total de registros no conjunto de linhas subjacente, não apenas o número de registros no capítulo atual.  
  
> [!NOTE]
>  Para usar **FetchProgress** com o Microsoft Visual Basic, Visual Basic 6.0 ou posterior é necessário.  
  
## <a name="see-also"></a>Consulte também  
 [Exemplo de modelo de eventos do ADO (VC + +)](../../../ado/reference/ado-api/ado-events-model-example-vc.md)   
 [Resumo do manipulador de eventos ADO](../../../ado/guide/data/ado-event-handler-summary.md)
