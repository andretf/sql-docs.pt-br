---
title: Elemento Tuples (XMLA) | Microsoft Docs
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
- Tuples Element
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
f1_keywords:
- http://schemas.microsoft.com/analysisservices/2003/engine#Tuples
- microsoft.xml.analysis.tuples
- urn:schemas-microsoft-com:xml-analysis#Tuples
helpviewer_keywords:
- Tuples element
ms.assetid: 5494bbaa-c1aa-43fa-b3e0-83befb2bccdd
caps.latest.revision: 11
author: jeannt
ms.author: jeannt
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: a3542b734b03a31de03cac5269bf98ac70663b0c
ms.contentlocale: pt-br
ms.lasthandoff: 09/01/2017

---
# <a name="tuples-element-xmla"></a>Elemento Tuples (XMLA)
  Contém um conjunto de [tupla](../../../analysis-services/xmla/xml-elements-properties/tuple-element-xmla.md) objetos para um [eixo](../../../analysis-services/xmla/xml-elements-properties/axis-element-xmla.md) elemento que usa o [MDDataSet](../../../analysis-services/xmla/xml-data-types/mddataset-data-type-xmla.md) retornado pelo tipo de dados, o [Execute](../../../analysis-services/xmla/xml-elements-methods-execute.md) método.  
  
## <a name="syntax"></a>Sintaxe  
  
```xml  
  
<Axis>  
   ...  
   <Tuples>  
      <Tuple>...</Tuple>  
   </Tuples>  
   ...  
</Axis>  
```  
  
## <a name="element-characteristics"></a>Características do elemento  
  
|Característica|Descrição|  
|--------------------|-----------------|  
|Comprimento e tipo de dados|Nenhuma|  
|Valor padrão|Nenhuma|  
|Cardinalidade|0-1: elemento obrigatório que pode ocorrer apenas uma vez.|  
  
## <a name="element-relationships"></a>Relações do elemento  
  
|Relação|Elemento|  
|------------------|-------------|  
|Elementos pai|[Axis](../../../analysis-services/xmla/xml-elements-properties/axis-element-xmla.md)|  
|Elementos filho|[Coleção de itens](../../../analysis-services/xmla/xml-elements-properties/tuple-element-xmla.md)|  
  
## <a name="remarks"></a>Comentários  
 Quando um aplicativo cliente definir a propriedade **AxisFormat** como *TupleFormat*, um eixo é representado como um conjunto de tuplas. Cada elemento **Axis** contém um elemento **Tuples** que representa o conjunto de tuplas naquele eixo. Cada tupla é representada usando um elemento **Tuple** que contém elementos [Member](../../../analysis-services/xmla/xml-elements-properties/member-element-xmla.md) de toda hierarquia no eixo.  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir ilustra a estrutura do **tuplas** elemento quando um cliente especifica *TupleFormat* ou *CustomFormat* para o **AxisFormat**  XML para a propriedade Analysis (XMLA), fornecida aos seguintes membros do eixo:  
  
|||||  
|-|-|-|-|  
|Hierarquia de **tempo**|1999|1999|2000|  
|Hierarquia de **categoria**|Real|Orçamento|Orçamento|  
  
```  
<Axes>  
   <Axis name="Axis0">  
      <Tuples>  
         <Tuple>  
            <Member Hierarchy="Time">  
               <UName>[Time].[1999]</UName>  
               ...  
            </Member>  
            <Member Hierarchy="Category">  
               <UName>[Scenario].[Actual]</UName>  
               ...  
            </Member>  
         </Tuple>  
         <Tuple>  
            <Member Hierarchy="Time">  
               <UName>[Time].[1999]</UName>  
               ...  
            </Member>  
            <Member Hierarchy="Category">  
               <UName>[Scenario].[Budget]</UName>  
               ...  
            </Member>  
         </Tuple>  
         <Tuple>  
            <Member Hierarchy="Time">  
               <UName>[Time].[2000]</UName>  
               ...  
            </Member>  
            <Member Hierarchy="Category">  
               <UName>[Scenario].[Budget]</UName>  
               ...  
            </Member>  
         </Tuple>  
      </Tuples>  
   </Axis>  
   ...  
</Axes>  
```  
  
## <a name="see-also"></a>Consulte também  
 [Propriedades &#40; XMLA &#41;](../../../analysis-services/xmla/xml-elements-properties/xml-elements-properties.md)  
  
  