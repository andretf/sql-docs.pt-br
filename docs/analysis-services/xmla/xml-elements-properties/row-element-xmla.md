---
title: Elemento Row (XMLA) | Microsoft Docs
ms.custom: 
ms.date: 03/03/2017
ms.prod: analysis-services
ms.prod_service: analysis-services, azure-analysis-services
ms.service: 
ms.component: 
ms.reviewer: 
ms.suite: pro-bi
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: row Element
apilocation: http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to: SQL Server 2016 Preview
f1_keywords:
- urn:schemas-microsoft-com:xml-analysis#row
- microsoft.xml.analysis.row
- http://schemas.microsoft.com/analysisservices/2003/engine#row
helpviewer_keywords: row element
ms.assetid: 4d9977a0-c396-44c7-9fd4-97f4c3d643aa
caps.latest.revision: "13"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: e28026dda3ddb43e1ed43ac427851b8fa4ff773c
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2018
---
# <a name="row-element-xmla"></a>Elemento row (XMLA)
[!INCLUDE[ssas-appliesto-sqlas-aas](../../../includes/ssas-appliesto-sqlas-aas.md)]Contém uma única linha de dados para um [raiz](../../../analysis-services/xmla/xml-elements-properties/root-element-xmla.md) elemento que contém dados tabulares retornados por uma [Discover](../../../analysis-services/xmla/xml-elements-methods-discover.md) ou [Execute](../../../analysis-services/xmla/xml-elements-methods-execute.md) chamada de método.  
  
## <a name="syntax"></a>Sintaxe  
  
```xml  
  
<root xmlns="urn:schemas-microsoft-com:xml-analysis:rowset">  
   <row>  
      <!-- One or more column elements -->  
   </row>  
</root>  
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
|Elementos pai|[raiz](../../../analysis-services/xmla/xml-elements-properties/root-element-xmla.md) (usando o [linhas](../../../analysis-services/xmla/xml-data-types/rowset-data-type-xmla.md) tipo de dados)|  
|Elementos filho|Um ou mais elementos de coluna.|  
  
## <a name="remarks"></a>Remarks  
 Cada linha retornada por um elemento **root** que contém dados tabulares tem um elemento **row** correspondente. Cada coluna no elemento **root** é representada por um elemento XML separado. O valor da coluna para o elemento **row** equivale aos dados contidos pelo elemento XML e o nome da coluna corresponde ao nome do elemento XML.  
  
 Há dois modos para expressar um valor nulo para uma coluna em uma linha:  
  
-   Um elemento de coluna ausente indica que a coluna é nula.  
  
-   O elemento de coluna pode usar o atributo `xsi:nil='true'` para indicar que tem um valor nulo.  
  
 Por exemplo, se uma linha tiver uma única coluna chamada Store_Name e seu valor for NULL, ela poderá ser representada como:  
  
```  
<row>  
</row>  
```  
  
 Ou:  
  
```  
<row>  
   <Store_name xsi:nil='true'/>  
</row>  
```  
  
 Se um elemento de coluna contiver um erro, um elemento **Error** fornecerá informações sobre o erro, conforme descrito no exemplo a seguir:  
  
```  
<row>   <Store_name>  
      <Error xmlns="urn:schemas-microsoft-com:xml-analysis:exception">  
         <ErrorCode>3238658054</ErrorCode>  
         <Description>The object [X] was not found in the cube when [X] was parsed.</Description>  
      </Error>  
   </Store_name>  
</row>  
```  
  
 Para obter mais informações sobre nomes de coluna e informações de esquema para dados de tabela, consulte [tipo de dados do conjunto de linhas &#40; XMLA &#41; ](../../../analysis-services/xmla/xml-data-types/rowset-data-type-xmla.md).  
  
## <a name="see-also"></a>Consulte Também  
 [Propriedades &#40; XMLA &#41;](../../../analysis-services/xmla/xml-elements-properties/xml-elements-properties.md)  
  
  
