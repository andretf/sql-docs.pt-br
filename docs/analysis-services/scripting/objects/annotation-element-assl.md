---
title: Elemento Annotation (ASSL) | Microsoft Docs
ms.custom: 
ms.date: 03/03/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: 
ms.component: 
ms.reviewer: 
ms.suite: pro-bi
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: Annotation Element
apilocation: http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to: SQL Server 2016 Preview
f1_keywords: Annotation
helpviewer_keywords: Annotation element
ms.assetid: 7d75291a-47b4-498a-8ba4-3d093b8513b2
caps.latest.revision: "43"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 09cafc5c5dcbafd48047995b03082a4d15e84288
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2018
---
# <a name="annotation-element-assl"></a>Elemento Annotation (ASSL)
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]Contém elementos que são usados para estender o esquema do Analysis Services Scripting Language (ASSL).  
  
## <a name="syntax"></a>Sintaxe  
  
```xml  
  
<Annotations>  
   <Annotation>  
      <Name>...</Name>  
      <Visibility>...</Visibility>  
      <Value>...</Value>  
   </Annotation>  
</Annotations >  
```  
  
## <a name="element-characteristics"></a>Características do elemento  
  
|Característica|Description|  
|--------------------|-----------------|  
|Comprimento e tipo de dados|Nenhum|  
|Valor padrão|Nenhum|  
|Cardinalidade|0-n: Elemento opcional que pode ocorrer mais de uma vez.|  
  
## <a name="element-relationships"></a>Relações do elemento  
  
|Relação|Elemento|  
|------------------|-------------|  
|Elementos pai|[Anotações](../../../analysis-services/scripting/collections/annotations-element-assl.md)|  
|Elementos filho|[Nome](../../../analysis-services/scripting/properties/name-element-assl.md), [valor](../../../analysis-services/scripting/properties/value-element-assl.md), [visibilidade](../../../analysis-services/scripting/properties/visibility-element-assl.md)|  
  
## <a name="remarks"></a>Remarks  
 O **anotação** elemento fornece a extensibilidade do esquema ASSL para todos os objetos diferentes dos usados unicamente para definir um tipo de dados complexos. O **valor** elemento o **anotação** elemento pode conter um XML válido de qualquer namespace XML diferente de ASSL, sujeito às seguintes regras:  
  
-   O XML pode conter somente elementos.  
  
-   Cada elemento deve ter um nome exclusivo. É recomendável que o valor da **nome** elemento o **anotação** elemento referência ao namespace de destino.  
  
 Essas regras são impostas para permitir que o conteúdo do **anotação** pares de elemento deve ser exposta como um conjunto de nome/valor por meio de outras interfaces, como Decision Support Objects (DSO).  
  
 Comentários e espaços em branco dentro do **anotação** elemento que não são incluídos em um elemento filho não pode ser preservado. Além disso, todos os elementos devem ter permissão de leitura/gravação; os elementos somente leitura serão ignorados.  
  
 O elemento correspondente no modelo de objeto Analysis Management Objects (AMO) é <xref:Microsoft.AnalysisServices.Annotation>.  
  
## <a name="see-also"></a>Consulte Também  
 [Objetos de &#40; ASSL &#41;](../../../analysis-services/scripting/objects/objects-assl.md)  
  
  
