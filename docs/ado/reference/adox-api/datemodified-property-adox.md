---
title: Propriedade DateModified (ADOX) | Microsoft Docs
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
- _Table::get_DateModified
- _Table::DateModified
- _Table::GetDateModified
helpviewer_keywords:
- DateModified property [ADOX]
ms.assetid: fed09266-1547-4bda-9088-c254d81cc738
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 733de516ee160bb26cba4568cbe34b76277e511d
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2018
---
# <a name="datemodified-property-adox"></a>Propriedade DateModified (ADOX)
Indica a data em que o objeto foi modificado pela última vez.  
  
## <a name="return-values"></a>Valores de retorno  
 Retorna um **Variant** valor que especifica a data de modificação. O valor será nulo se **DateModified** não é suportado pelo provedor.  
  
## <a name="remarks"></a>Remarks  
 O **DateModified** propriedade é nula para objetos recentemente adicionados. Depois de anexar um novo [exibição](../../../ado/reference/adox-api/view-object-adox.md) ou [procedimento](../../../ado/reference/adox-api/procedure-object-adox.md), você deve chamar o [atualizar](../../../ado/reference/ado-api/refresh-method-ado.md) método o [exibições](../../../ado/reference/adox-api/views-collection-adox.md) ou [procedimentos ](../../../ado/reference/adox-api/procedures-collection-adox.md) coleção para obter valores para o **DateModified** propriedade.  
  
## <a name="applies-to"></a>Aplica-se a  
  
||||  
|-|-|-|  
|[Objeto Procedure (ADOX)](../../../ado/reference/adox-api/procedure-object-adox.md)|[Objeto Table (ADOX)](../../../ado/reference/adox-api/table-object-adox.md)|[Objeto View (ADOX)](../../../ado/reference/adox-api/view-object-adox.md)|  
  
## <a name="see-also"></a>Consulte também  
 [DateCreated e DateModified propriedades exemplo (VB)](../../../ado/reference/adox-api/datecreated-and-datemodified-properties-example-vb.md)   
 [Propriedade DateCreated (ADOX)](../../../ado/reference/adox-api/datecreated-property-adox.md)
