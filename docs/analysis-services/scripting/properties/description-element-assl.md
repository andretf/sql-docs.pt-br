---
title: Elemento Description (ASSL) | Microsoft Docs
ms.custom: 
ms.date: 03/14/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: 
ms.component: 
ms.reviewer: 
ms.suite: pro-bi
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: Description Element
apilocation: http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to: SQL Server 2016 Preview
f1_keywords: Description
helpviewer_keywords: Description element
ms.assetid: 34d67e7c-e79a-429b-8cc3-6ca13b9cf9c3
caps.latest.revision: "35"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 49be4d5ed0f50a6ec97c3ac8c7391d5c0dac0bb2
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2018
---
# <a name="description-element-assl"></a>Elemento Description (ASSL)
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]Contém a descrição do elemento pai.  
  
## <a name="syntax"></a>Sintaxe  
  
```xml  
  
<Action> <!-- or one of the elements listed below in the Element Relationships table -->  
   ...  
   <Description>...</Description>  
   ...  
</Action>  
```  
  
## <a name="element-characteristics"></a>Características do elemento  
  
|Característica|Description|  
|--------------------|-----------------|  
|Comprimento e tipo de dados|Cadeia de caracteres|  
|Valor padrão|Nenhum|  
|Cardinalidade|0-1: elemento opcional que ocorre apenas uma única vez.|  
  
## <a name="element-relationships"></a>Relações do elemento  
  
|Relação|Elemento|  
|------------------|-------------|  
|Elementos pai|[Ação](../../../analysis-services/scripting/objects/action-element-assl.md), [agregação](../../../analysis-services/scripting/objects/aggregation-element-assl.md), [AggregationDesign](../../../analysis-services/scripting/objects/aggregationdesign-element-assl.md), [Assembly](../../../analysis-services/scripting/objects/assembly-element-assl.md), [AttributePermission](../../../analysis-services/scripting/objects/attributepermission-element-assl.md), [ CalculationProperty](../../../analysis-services/scripting/objects/calculationproperty-element-assl.md), [CellPermission](../../../analysis-services/scripting/objects/cellpermission-element-assl.md), [cubo](../../../analysis-services/scripting/objects/cube-element-assl.md), [CubeDimensionPermission](../../../analysis-services/scripting/data-type/cubedimensionpermission-data-type-assl.md), [banco de dados](../../../analysis-services/scripting/objects/database-element-assl.md) , [DataSource](../../../analysis-services/scripting/objects/datasource-element-assl.md), [DataSourceView](../../../analysis-services/scripting/objects/datasourceview-element-assl.md), [dimensão](../../../analysis-services/scripting/objects/dimension-element-assl.md), [DimensionAttribute](../../../analysis-services/scripting/data-type/dimensionattribute-data-type-assl.md), [hierarquia](../../../analysis-services/scripting/objects/hierarchy-element-assl.md), [Kpi](../../../analysis-services/scripting/objects/kpi-element-assl.md), [nível](../../../analysis-services/scripting/objects/level-element-assl.md), [MdxScript](../../../analysis-services/scripting/objects/mdxscript-element-assl.md), [medidas](../../../analysis-services/scripting/objects/measure-element-assl.md), [MeasureGroup](../../../analysis-services/scripting/objects/measuregroup-element-assl.md), [MiningModel](../../../analysis-services/scripting/objects/miningmodel-element-assl.md), [MiningModelColumn](../../../analysis-services/scripting/data-type/miningmodelcolumn-data-type-assl.md), [MiningStructure](../../../analysis-services/scripting/objects/miningstructure-element-assl.md), [MiningStructureColumn](../../../analysis-services/scripting/data-type/miningstructurecolumn-data-type-assl.md), [ Partição](../../../analysis-services/scripting/objects/partition-element-assl.md), [permissão](../../../analysis-services/scripting/data-type/permission-data-type-assl.md), [perspectiva](../../../analysis-services/scripting/objects/perspective-element-assl.md), [função](../../../analysis-services/scripting/objects/role-element-assl.md), [Server](../../../analysis-services/scripting/objects/server-element-assl.md), [Rastreamento](../../../analysis-services/scripting/objects/trace-element-assl.md), [tradução](../../../analysis-services/scripting/objects/translation-element-assl.md)|  
|Elementos filho|Nenhum|  
  
## <a name="remarks"></a>Remarks  
 O valor de um **descrição** elemento tem as seguintes restrições:  
  
-   O valor não pode conter espaços à esquerda ou direita. Se os espaços à esquerda ou à direita serão incluídos no valor de um **descrição** elemento, os espaços serão implicitamente removidos pelo [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].  
  
-   O valor não pode conter caracteres de controle. Se os caracteres de controle são incluídos no valor de um **descrição** elemento, esses caracteres serão implicitamente removidos pelo [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].  
  
## <a name="see-also"></a>Consulte Também  
 [Elemento Name &#40; ASSL &#41;](../../../analysis-services/scripting/properties/name-element-assl.md)   
 [Propriedades &#40; ASSL &#41;](../../../analysis-services/scripting/properties/properties-assl.md)  
  
  
