---
title: Tipo de dados TableBinding (ASSL) | Microsoft Docs
ms.custom: 
ms.date: 03/06/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: 
ms.component: 
ms.reviewer: 
ms.suite: pro-bi
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: TableBinding Data Type
apilocation: http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to: SQL Server 2016 Preview
f1_keywords: TableBinding
helpviewer_keywords: TableBinding data type
ms.assetid: 3195dca4-82bf-46b7-a31f-5383586e3573
caps.latest.revision: "39"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 22c9b057ef8ae5623732fadf3daf41ed1734a6c0
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2018
---
# <a name="tablebinding-data-type-assl"></a>Tipo de dados TableBinding (ASSL)
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]Define um tipo de dados derivado que representa uma associação a uma tabela.  
  
## <a name="syntax"></a>Sintaxe  
  
```xml  
  
<TableBinding>  
   <!-- The following elements extend TabularBinding -->  
   <DataSourceID>...</DataSourceID>  
   <DbTableName>...</DbTableName>  
   <DbSchemaName>...</DbSchemaName>  
</TableBinding>  
```  
  
## <a name="data-type-characteristics"></a>Características do tipo de dados  
  
|Característica|Description|  
|--------------------|-----------------|  
|Tipos de dados base|[TabularBinding](../../../analysis-services/scripting/data-type/tabularbinding-data-type-assl.md)|  
|Tipos de dados derivados|Nenhum|  
  
## <a name="data-type-relationships"></a>Relação do tipo de dados  
  
|Relação|Elemento|  
|------------------|-------------|  
|Elementos pai|Nenhum|  
|Elementos filho|[DataSourceID](../../../analysis-services/scripting/properties/datasourceid-element-assl.md), [DbSchemaName](../../../analysis-services/scripting/properties/dbschemaname-element-assl.md), [DbTableName](../../../analysis-services/scripting/properties/dbtablename-element-assl.md)|  
|Elementos derivados|Consulte [de associação](../../../analysis-services/scripting/data-type/binding-data-type-assl.md)|  
  
## <a name="remarks"></a>Remarks  
 Observe que fazer referência a outras tabelas na expressão do filtro pelo uso de uma subseleção pode causar implicações de desempenho em algumas fontes de dados. No entanto, o designer pode controlar totalmente a expressão SQL, definindo uma consulta nomeada na exibição da fonte de dados e, em seguida, fazendo referência a ela.  
  
 O método de definição das associações de uma partição independem do uso de tabelas particionadas na exibição da fonte de dados.  
  
 Como exemplo, considere um grupo de medidas cuja tabela padrão seja "Vendas", como as colunas Data, ID do produto, Qtd., Preço e Total (calculado na exibição da fonte de dados). Então a partição "Sales97" poderia usar o tabela "Sales97" com o filtro "Year (Sales.Date) = 97."  
  
 A consulta efetiva é:  
  
```  
SELECT Date, Product ID, Qty, Price, Qty * Price AS Amount   
   FROM Sales97 As Sales  
   WHERE Year(Sales.Date) = 97  
```  
  
 A expressão calculada ainda se aplica, até mesmo se a expressão tenha utilizado nomes de tabelas qualificados (por exemplo, Sales.Qty). O mesmo se aplica se, em vez disso, a tabela foram substituída por alguma consulta "SELECT..." A cláusula FROM acima iria se tornar "de SELECT... As Sales."  
  
 Para obter mais informações sobre o **associação** tipo, incluindo as tabelas de objetos do Analysis Services Scripting Language (ASSL) do tipo **associação** e a hierarquia de herança de **deassociação** tipos, consulte [associação de tipo de dados &#40; ASSL &#41; ](../../../analysis-services/scripting/data-type/binding-data-type-assl.md).  
  
 Para obter uma visão geral de associações de dados em ASSL, consulte [fontes de dados e associações &#40; SSAS Multidimensional &#41; ](../../../analysis-services/multidimensional-models/data-sources-and-bindings-ssas-multidimensional.md).  
  
 O elemento correspondente no modelo de objeto Analysis Management Objects (AMO) é <xref:Microsoft.AnalysisServices.TableBinding>.  
  
## <a name="see-also"></a>Consulte Também  
 [Associação de tipo de dados &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/binding-data-type-assl.md)   
 [Fontes de dados e associações &#40; SSAS Multidimensional &#41;](../../../analysis-services/multidimensional-models/data-sources-and-bindings-ssas-multidimensional.md)   
 [Tipos de dados XML de linguagem de script &#40; do Analysis Services ASSL &#41;](../../../analysis-services/scripting/data-type/analysis-services-scripting-language-xml-data-types-assl.md)  
  
  
