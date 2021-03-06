---
title: "Abra o método (ADO MD) | Microsoft Docs"
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
- Open
- Cellset::Open
helpviewer_keywords:
- Open method [ADO MD]
ms.assetid: a87d8080-a238-45e5-bc80-9a8625b3810f
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: c23630224808a70c20583759b6d62c8475ede66a
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2018
---
# <a name="open-method-ado-md"></a>Método Open (ADO MD)
Recupera os resultados de uma consulta multidimensional e retorna os resultados para um [conjunto de células](../../../ado/reference/ado-md-api/cellset-object-ado-md.md).  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
Cellset.Open Source, ActiveConnection  
```  
  
#### <a name="parameters"></a>Parâmetros  
 *Origem*  
 Opcional. Um **Variant** que é avaliada como uma consulta multidimensional válida, como uma consulta MDX (Multidimensional Expression). O *fonte* argumento corresponde do [fonte](../../../ado/reference/ado-md-api/source-property-ado-md.md) propriedade. Para obter mais informações sobre o MDX, consulte o [OLE DB para OLAP processamento analítico Online ()](http://msdn.microsoft.com/en-us/8a7673c6-3ca1-4411-9f1e-adf1e47df4f3) documentação na Microsoft Data Access Components SDK.  
  
 *ActiveConnection*  
 Opcional. Um **Variant** que é avaliada como uma cadeia de caracteres especificando o um ADO válido [Conexão](../../../ado/reference/ado-api/connection-object-ado.md) nome de variável ou uma definição para uma conexão do objeto. O *ActiveConnection* argumento especifica a conexão para abrir o [conjunto de células](../../../ado/reference/ado-md-api/cellset-object-ado-md.md) objeto. Se você passar uma definição de conexão para esse argumento, o ADO abre uma nova conexão usando os parâmetros especificados. O *ActiveConnection* argumento corresponde do [ActiveConnection](../../../ado/reference/ado-md-api/activeconnection-property-ado-md.md) propriedade.  
  
## <a name="remarks"></a>Remarks  
 O **abrir** método gera um erro se qualquer um dos seus parâmetros for omitido e o valor da propriedade correspondente não foi definida antes de tentar abrir o **conjunto de células**.  
  
## <a name="applies-to"></a>Aplica-se a  
 [Objeto Cellset (ADO MD)](../../../ado/reference/ado-md-api/cellset-object-ado-md.md)  
  
## <a name="see-also"></a>Consulte também  
 [Exemplo de conjunto de células (VB)](../../../ado/reference/ado-md-api/cellset-example-vb.md)   
 [Propriedade ActiveConnection (ADO MD)](../../../ado/reference/ado-md-api/activeconnection-property-ado-md.md)   
 [Feche o método (ADO MD)](../../../ado/reference/ado-md-api/close-method-ado-md.md)   
 [Objeto de Conexão (ADO)](../../../ado/reference/ado-api/connection-object-ado.md)   
 [Propriedade Source (ADO MD)](../../../ado/reference/ado-md-api/source-property-ado-md.md)   
 [Propriedade State (ADO MD)](../../../ado/reference/ado-md-api/state-property-ado-md.md)
