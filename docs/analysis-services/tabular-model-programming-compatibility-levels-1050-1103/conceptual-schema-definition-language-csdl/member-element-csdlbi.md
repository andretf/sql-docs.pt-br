---
title: Elemento Member (CSDLBI) | Microsoft Docs
ms.custom: 
ms.date: 03/07/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: 
ms.component: 
ms.reviewer: 
ms.suite: pro-bi
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
ms.assetid: 1ba225f5-3867-4aae-a519-e3c277688d1e
caps.latest.revision: 
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 5507e746f2f87abe2c4a08b5bda47a2eab5f61b5
ms.sourcegitcommit: 7519508d97f095afe3c1cd85cf09a13c9eed345f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2018
---
# <a name="member-element-csdlbi"></a>Elemento Member (CSDLBI)
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]
O elemento Member é um tipo complexo que serve como base para outros elementos.  
  
 Seu atributos podem aparecer em colunas, medidas, propriedades de navegação, hierarquias e níveis.  
  
## <a name="elements-and-attributes"></a>Elementos e atributos  
 A tabela a seguir lista os elementos e atributos que definem o elemento Member.  
  
|Nome|É obrigatório|Descrição|  
|----------|-----------------|-----------------|  
|Nome||O nome fornecido ao membro (coluna, medida, propriedade de navegação, hierarquia ou nível) que é definido pela implementação do tipo TMember|  
|Caption|Sim|O nome para exibição do membro.|  
|ContextualNameRule|Sim|O formato de nomenclatura que é usado para resolver a ambiguidade de membros. O conteúdo desse atributo é definido pelo tipo simples ContextualNameRule.|  
|Oculto||Um valor booliano que indica se o membro será ocultado do cliente.<br /><br /> O padrão é false, o que significa que as colunas ficam visíveis no cliente.|  
|ReferenceName||O identificador usado para fazer referência ao membro em uma consulta DAX. Se esse atributo for omitido, será usado o nome do campo|  
  
## <a name="contextualnamerule-element"></a>Elemento ContextualNameRule  
 Esse tipo simples define o formato de nomenclatura que é usado para resolver a ambiguidade de membros.  
  
|Valor|Description|  
|-----------|-----------------|  
|Nenhuma|Use o nome do atributo.|  
|Contexto|Use o nome da relação de entrada.|  
|Mesclagem|Concatene o nome da relação de entrada e o nome da propriedade.|  
  
## <a name="see-also"></a>Consulte também  
 [Noções básicas sobre o modelo de objeto de tabela em compatibilidade 1050 1103 por meio de níveis](../../../analysis-services/tabular-model-programming-compatibility-levels-1050-1103/representation/understanding-tabular-object-model-at-levels-1050-through-1103.md)  
  
  
