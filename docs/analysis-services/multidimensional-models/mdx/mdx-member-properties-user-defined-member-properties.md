---
title: "Propriedades do membro (MDX) definido pelo usuário | Microsoft Docs"
ms.custom: 
ms.date: 03/03/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: 
ms.component: data-mining
ms.reviewer: 
ms.suite: pro-bi
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: custom member properties [MDX]
ms.assetid: b64cc581-e784-42c4-bec8-932abd687423
caps.latest.revision: "33"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 08576f10739533850f04a9e64fa052bf7c6bfeec
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2018
---
# <a name="mdx-member-properties---user-defined-member-properties"></a>Propriedades de membro MDX - propriedades do membro definidas pelo usuário
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]Propriedades do membro definidas pelo usuário podem ser adicionadas a um nível nomeado específico de uma dimensão como relações de atributo. Não é possível adicionar propriedades do membro definidas pelo usuário ao nível **(Tudo)** de uma hierarquia ou à própria hierarquia.  
  
## <a name="creating-user-defined-member-properties"></a>Criando propriedades do membro definidas pelo usuário  
 Propriedades do membro definidas pelo usuário podem ser adicionadas a dimensões ou cubos com base em servidor pela interface de usuário ou programaticamente:  
  
-   Para adicionar propriedades do membro definidas pelo usuário através da interface do usuário, use o Designer de Dimensão no [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)]. Para obter mais informações, consulte [Definir Relações de Atributos](../../../analysis-services/multidimensional-models/attribute-relationships-define.md).  
  
-   Para adicionar propriedades do membro definidas pelo usuário de forma programática, o aplicativo pode usar o Objetos de Gerenciamento de Análise (AMO) ou uma combinação de XML for Analysis (XMLA) e Analysis Services Scripting Language (ASSL). Para obter mais informações, consulte [Relações de atributos](../../../analysis-services/multidimensional-models-olap-logical-dimension-objects/attribute-relationships.md).  
  
## <a name="retrieving-user-defined-member-properties"></a>Recuperando propriedades do membro definidas pelo usuário  
 Você pode recuperar propriedades do membro definidas pelo usuário usando a palavra-chave **PROPERTIES** ou a função [Properties](../../../mdx/properties-mdx.md) .  
  
### <a name="using-the-properties-keyword-to-retrieve-user-defined-member-properties"></a>Usando a palavra-chave PROPERTIES para recuperar propriedades do membro definidas pelo usuário  
 A sintaxe que recupera as propriedades do membro definidas pelo usuário é similar àquela usada para recuperar propriedades do membro do nível intrínsecas, como mostrada na sintaxe a seguir:  
  
 `DIMENSION PROPERTIES [Dimension.]Level.<Custom_Member_Property>`  
  
 A palavra-chave **PROPERTIES** aparece depois da expressão de conjunto da especificação de eixo. Por exemplo, na consulta MDX a seguir, a palavra-chave **PROPERTIES** recupera as propriedades do membro definidas pelo usuário `List Price` e `Dealer Price` , e aparece depois da expressão de conjunto que identifica os produtos vendidos em janeiro:  
  
```  
SELECT   
   CROSSJOIN([Ship Date].[Calendar].[Calendar Year].Members,   
             [Measures].[Sales Amount]) ON COLUMNS,  
   NON EMPTY Product.Product.MEMBERS  
   DIMENSION PROPERTIES   
              Product.Product.[List Price],  
              Product.Product.[Dealer Price]  ON ROWS  
FROM [Adventure Works]  
WHERE ([Date].[Month of Year].[January])   
```  
  
### <a name="using-the-properties-function-to-retrieve-user-defined-member-properties"></a>Usando a função Properties para recuperar propriedades do membro definidas pelo usuário  
 Como alternativa, você pode acessar as propriedades do membro personalizadas com a função **Properties** . Por exemplo, a consulta MDX a seguir usa a palavra-chave **WITH** para criar um membro calculado formado pela propriedade do membro `List Price`:  
  
```  
WITH   
   MEMBER [Measures].[Product List Price] AS  
   [Product].[Product].CurrentMember.Properties("List Price")  
SELECT   
   [Measures].[Product List Price] on COLUMNS,  
   [Product].[Product].MEMBERS  ON Rows  
FROM [Adventure Works]  
```  
  
 Para obter mais informações sobre como criar membros calculados, consulte [Criando membros calculados em MDX &#40;MDX&#41;](../../../analysis-services/multidimensional-models/mdx/mdx-calculated-members-building-calculated-members.md).  
  
## <a name="see-also"></a>Consulte Também  
 [Usando propriedades do membro &#40;MDX&#41;](../../../analysis-services/multidimensional-models/mdx/mdx-member-properties.md)   
 [Propriedades &#40; MDX &#41;](../../../mdx/properties-mdx.md)  
  
  
