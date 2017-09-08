---
title: Nome de elemento (XMLA) | Microsoft Docs
ms.custom: 
ms.date: 03/03/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- Name Element
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
f1_keywords:
- http://schemas.microsoft.com/analysisservices/2003/engine#Name
- urn:schemas-microsoft-com:xml-analysis#Name
- microsoft.xml.analysis.name
helpviewer_keywords:
- Name element
ms.assetid: cc1a93df-0b1b-4c38-9183-4f11c26fea6a
caps.latest.revision: 12
author: jeannt
ms.author: jeannt
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 5251f22e39932f49fa4c512b8c5b76a2bf0e7af9
ms.contentlocale: pt-br
ms.lasthandoff: 09/01/2017

---
# <a name="name-element-xmla"></a>Elemento Name (XMLA)
  Contém o nome de um membro de atributo para o pai [atributo](../../../analysis-services/xmla/xml-elements-properties/attribute-element-xmla.md) ou [tradução](../../../analysis-services/xmla/xml-elements-properties/translation-element-xmla.md) elemento.  
  
## <a name="syntax"></a>Sintaxe  
  
```xml  
  
<Attribute> <!-- or Translation -->  
   ...  
   <Name>...</Name>  
   ...  
</Attribute>  
```  
  
## <a name="element-characteristics"></a>Características do elemento  
  
|Característica|Descrição|  
|--------------------|-----------------|  
|Comprimento e tipo de dados|String|  
|Valor padrão|Nenhuma|  
|Cardinalidade|Consulte a tabela a seguir.|  
  
|Ancestral ou pai|Cardinalidade|  
|------------------------|-----------------|  
|[Atributo](../../../analysis-services/xmla/xml-elements-properties/attribute-element-xmla.md)|1-1: elemento obrigatório que ocorre apenas uma única vez.|  
|[Tradução](../../../analysis-services/xmla/xml-elements-properties/translation-element-xmla.md)|0-1: elemento obrigatório que pode ocorrer apenas uma vez.|  
  
## <a name="element-relationships"></a>Relações do elemento  
  
|Relação|Elemento|  
|------------------|-------------|  
|Elementos pai|[Atributo](../../../analysis-services/xmla/xml-elements-properties/attribute-element-xmla.md), [tradução](../../../analysis-services/xmla/xml-elements-properties/translation-element-xmla.md)|  
|Elementos filho|Nenhuma|  
  
## <a name="remarks"></a>Comentários  
 Para **atributo** elementos, o **nome** elemento contém o nome do membro do atributo a ser inserido ou atualizado durante, respectivamente, o **inserir** ou **Atualização** comando.  
  
 Para **tradução** elementos, o **nome** elemento contém a legenda do membro do atributo, no idioma especificado pelo **idioma** elemento do pai  **Tradução** objeto. Se o **nome** elemento não for especificado ou contiver uma cadeia de caracteres vazia, o valor da **nome** elemento para o **atributo** elemento que contém o  **Tradução** elemento é usado.  
  
## <a name="see-also"></a>Consulte também  
 [Inserir o elemento &#40; XMLA &#41;](../../../analysis-services/xmla/xml-elements-commands/insert-element-xmla.md)   
 [Elemento de linguagem &#40; XMLA &#41;](../../../analysis-services/xmla/xml-elements-properties/language-element-xmla.md)   
 [Atualizar o elemento &#40; XMLA &#41;](../../../analysis-services/xmla/xml-elements-commands/update-element-xmla.md)   
 [Propriedades &#40; XMLA &#41;](../../../analysis-services/xmla/xml-elements-properties/xml-elements-properties.md)  
  
  