---
title: Elemento InstanceSelection (ASSL) | Microsoft Docs
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
- InstanceSelection Element
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- InstanceSelection element
ms.assetid: 908a2da9-274c-40d2-87dc-4641cb8d77e6
caps.latest.revision: 14
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 4587536131aa3484846bc241a08be866a30d1da6
ms.contentlocale: pt-br
ms.lasthandoff: 09/01/2017

---
# <a name="instanceselection-element-assl"></a>Elemento InstanceSelection (ASSL)
  Fornece uma dica para aplicativos cliente para sugerir como uma lista de itens deve ser exibida, com base no número esperado de itens na lista.  
  
## <a name="syntax"></a>Sintaxe  
  
```xml  
  
<DimensionAttribute>  
   ...  
   <InstanceSelection>...</InstanceSelection>  
   ...  
</DimensionAttribute>  
```  
  
## <a name="element-characteristics"></a>Características do elemento  
  
|Característica|Descrição|  
|--------------------|-----------------|  
|Comprimento e tipo de dados|Cadeia de caracteres (enumeração)|  
|Valor padrão|*Nenhuma*|  
|Cardinalidade|0-1: elemento obrigatório que pode ocorrer apenas uma vez.|  
  
## <a name="element-relationships"></a>Relações do elemento  
  
|Relação|Elemento|  
|------------------|-------------|  
|Elemento pai|[DimensionAttribute](../../../analysis-services/scripting/data-type/dimensionattribute-data-type-assl.md)|  
|Elementos filho|Nenhuma|  
  
## <a name="remarks"></a>Comentários  
 O valor desse elemento é limitado a uma das cadeias de caracteres a seguir:  
  
|Valor|Description|  
|-----------|-----------------|  
|*Nenhuma*|Não exiba uma lista de seleções. Permita os usuários insiram valores diretamente.|  
|*Lista suspensa*|O número de itens é muito pequeno para ser exibido em uma lista suspensa.|  
|*Listaa*|O número de itens é muito grande para uma lista suspensa, mas não requer filtragem.|  
|*FilteredList*|O número de itens é grande o suficiente para exigir que os usuários filtrem os itens a serem exibidos.|  
|*MandatoryFilter*|O número de itens é tão grande que a exibição deve sempre ser filtrada.|  
  
 A enumeração que corresponde aos valores permitidos para **InstanceSelection** no objeto Analysis Management Objects (AMO) o modelo é <xref:Microsoft.AnalysisServices.InstanceSelection>.  
  
## <a name="see-also"></a>Consulte também  
 [Propriedades &#40; ASSL &#41;](../../../analysis-services/scripting/properties/properties-assl.md)  
  
  