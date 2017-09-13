---
title: Elemento HideMemberIf (ASSL) | Microsoft Docs
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- HideMemberIf Element
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
f1_keywords:
- HideMemberIf
helpviewer_keywords:
- HideMemberIf element
ms.assetid: ff0e6b19-6216-43ac-ba76-1628da8c333b
caps.latest.revision: 34
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 63e9386cbeb679bef13c87857df9b95a10863099
ms.contentlocale: pt-br
ms.lasthandoff: 09/01/2017

---
# <a name="hidememberif-element-assl"></a>Elemento HideMemberIf (ASSL)
  Indica se, e quando, um membro em um nível ficará oculto pelos aplicativos cliente.  
  
## <a name="syntax"></a>Sintaxe  
  
```xml  
  
<Level>  
   ...  
   <HideMemberIf>...</HideMemberIf>  
   ...  
</Level>  
```  
  
## <a name="element-characteristics"></a>Características do elemento  
  
|Característica|Descrição|  
|--------------------|-----------------|  
|Comprimento e tipo de dados|Cadeia de caracteres (enumeração)|  
|Valor padrão|*Nunca*|  
|Cardinalidade|0-1: elemento obrigatório que pode ocorrer apenas uma vez.|  
  
## <a name="element-relationships"></a>Relações do elemento  
  
|Relação|Elemento|  
|------------------|-------------|  
|Elemento pai|[Level](../../../analysis-services/scripting/objects/level-element-assl.md)|  
|Elementos filho|Nenhuma|  
  
## <a name="remarks"></a>Comentários  
 O valor desse elemento é limitado a uma das cadeias de caracteres listadas na tabela a seguir.  
  
|Valor|Description|  
|-----------|-----------------|  
|*Nunca*|Membros nunca são ocultados.|  
|*OnlyChildWithNoName*|Um membro é ocultado quando ele for o único filho de seu pai e seu nome estiver vazio.|  
|*OnlyChildWithParentName*|Um membro é ocultado quando ele for o único filho de seu pai e seu nome for idêntico ao de seu pai.|  
|*Sem nome*|Um membro é ocultado quando seu nome estiver vazio.|  
|*ParentName*|Um membro é ocultado quando seu nome for idêntico ao de seu pai.|  
  
## <a name="remarks"></a>Comentários  
 A enumeração que corresponde aos valores permitidos para **HideMemberIf** no objeto Analysis Management Objects (AMO) o modelo é <xref:Microsoft.AnalysisServices.HideIfValue>.  
  
## <a name="see-also"></a>Consulte também  
 [Propriedades &#40; ASSL &#41;](../../../analysis-services/scripting/properties/properties-assl.md)  
  
  