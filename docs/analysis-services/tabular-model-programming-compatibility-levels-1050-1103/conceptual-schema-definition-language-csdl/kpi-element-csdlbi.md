---
title: Elemento KPI (CSDLBI) | Microsoft Docs
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
applies_to:
- SQL Server 2016 Preview
ms.assetid: 203ee6e8-eef2-4476-b09f-bd95e492ddaa
caps.latest.revision: 13
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: bc60e58643df0a47c0f31b93278e95bd1b64a804
ms.contentlocale: pt-br
ms.lasthandoff: 09/01/2017

---
# <a name="kpi-element-csdlbi"></a>Elemento KPI (CSDLBI)
  O elemento Kpi define um cálculo que pode ser usado como um KPI (Indicador Chave de Desempenho). Em um modelo de dados de Business Intelligence, os KPIs se baseiam em medidas e, como tal a definição de KPI contém todos os metadados associados a medidas, bem como as informações necessárias para apresentação dos valores de KPI, incluindo um gráfico padrão.  
  
 O elemento Kpi não especifica a fórmula, contida na definição de medida, mas especifica os metadados adicionais associados às medidas que são usadas como KPIs. Depois que você designar uma medida como um KPI, não poderá usá-la em outros contextos.  
  
## <a name="elements-and-attributes"></a>Elementos e atributos  
 A tabela a seguir lista os elementos e atributos que definem o elemento Kpi.  
  
|Nome|É obrigatório|Descrição|  
|----------|-----------------|-----------------|  
|Documentação|Não|Uma descrição do KPI.|  
|KpiGoal|Sim|Uma referência a uma coluna que contém valores que podem ser usados como meta.<br /><br /> Consulte [PropertyRef Element &#40;CSDLBI&#41;](../../../analysis-services/tabular-model-programming-compatibility-levels-1050-1103/conceptual-schema-definition-language-csdl/propertyref-element-csdlbi.md)a.|  
|KpiStatus|Sim|Uma referência a uma coluna que contém valores que representam o status atual do KPI.|  
|StatusGraphic|Sim|Uma referência a uma imagem que indica progresso negativo, neutro ou positivo em relação aos destinos definidos no KPI.|  
  
## <a name="remarks"></a>Comentários  
 Quando você projeta um modelo, pode criar um KPI criando uma medida e atribuindo-a para uso como um KPI. Em seguida, você adiciona informações que são específicas para KPIs, como um gráfico a ser usado para mostrar tendências.  
  
## <a name="example"></a>Exemplo  
 **Tabular**  
  
 O exemplo a seguir, na versão 1.0 da CSDLBI, mostra um KPI que mede as vendas, com base no exemplo de modelo de tabela da AdventureWorks.  
  
```  
  
<Property Name="InternetCurrSalesPerf" Type="Double">  
  <bi:Measure>  
    <bi:Kpi StatusGraphic="Three Stars Colored">  
      <bi:KpiGoal>  
        <bi:PropertyRef Name="v_InternetCurrSalesPerf_Goal" />  
      </bi:KpiGoal>  
      <bi:KpiStatus>  
        <bi:PropertyRef Name="v_InternetCurrSalesPerf_Status" />  
      </bi:KpiStatus>  
    </bi:Kpi>  
  </bi:Measure>  
</Property>  
  
```  
  
## <a name="example"></a>Exemplo  
 **Multidimensional**  
  
 O exemplo a seguir, na versão 1.1 da CSDLBI, mostra um KPI do cubo Operações da Contoso.  
  
```  
<Property Name="Sum_of_SalesAmount" Type="Decimal" Precision="19" Scale="4">  
   <Documentation>  
     <Summary>KPI Description</Summary>  
   </Documentation>  
     <bi:Measure   
         Caption="Sum of SalesAmount"   
         ReferenceName="Sum of SalesAmount"   
         FormatString="\$#,0.00;(\$#,0.00);\$#,0.00">  
     <bi:Kpi   
           StatusGraphic="Three Circles Colored">  
         <bi:KpiGoal>  
            <bi:PropertyRef Name="v_Sum_of_SalesAmount_Goal" />  
          </bi:KpiGoal>  
          <bi:KpiStatus>  
              <bi:PropertyRef Name="v_Sum_of_SalesAmount_Status" />  
          </bi:KpiStatus>  
     </bi:Kpi>  
     </bi:Measure>  
</Property>  
```  
  
## <a name="see-also"></a>Consulte também  
 [Referência técnica para anotações de BI para CSDL](../../../analysis-services/tabular-model-programming-compatibility-levels-1050-1103/conceptual-schema-definition-language-csdl/technical-reference-for-bi-annotations-to-csdl.md)  
  
  