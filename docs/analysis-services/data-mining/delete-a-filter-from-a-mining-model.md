---
title: "Excluir um filtro de um modelo de mineração | Microsoft Docs"
ms.custom: 
ms.date: 03/01/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: 
ms.component: data-mining
ms.reviewer: 
ms.suite: pro-bi
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: filters [Analysis Services]
ms.assetid: 91220b21-adbc-49a9-b200-8bf0a724eff1
caps.latest.revision: "13"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 6352491a172ce751ed2cec28038a085a22c96654
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2018
---
# <a name="delete-a-filter-from-a-mining-model"></a>Excluir um filtro de um modelo de mineração
[!INCLUDE[ssas-appliesto-sqlas](../../includes/ssas-appliesto-sqlas.md)]Quando você cria um filtro em um modelo de mineração, você pode criar modelos em um subconjunto dos dados na exibição da fonte de dados. Os filtros também são úteis para testar a precisão do modelo em um subconjunto dos dados originais.  
  
 Porém, você deve excluir o filtro se quiser exibir novamente o conjunto completo de casos. Este procedimento descreve como remover as condições em um filtro ou excluir completamente o filtro.  
  
### <a name="to-delete-a-condition-from-a-filter-on-a-mining-model"></a>Para excluir uma condição de um filtro em um modelo de mineração  
  
1.  Em [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], no Gerenciador de Soluções, clique na estrutura de mineração que contém o modelo de mineração a filtrar.  
  
2.  Clique na guia **Modelos de Mineração** .  
  
3.  Selecione o modelo, e clique com o botão direito do mouse para abrir o menu de atalho.  
  
     –ou–  
  
     Selecione o modelo. No menu **Modelo de Mineração** , selecione **Definir Filtro de Modelos**.  
  
4.  Na caixa de diálogo **Filtro de Modelos** , clique com o botão direito do mouse na linha da grade que contém a condição a excluir.  
  
5.  Selecione **Excluir**.  
  
### <a name="to-clear-the-filter-on-a-mining-model-in-the-filter-editor-dialog-box"></a>Para desmarcar o filtro em um modelo de mineração na caixa de diálogo Editor de Filtro  
  
-   Na caixa de diálogo **Editor de Filtro** , clique com o botão direito do mouse em uma linha na grade e selecione **Excluir Tudo**.  
  
## <a name="working-with-model-filters-using-the-properties-window"></a>Trabalhando com os filtros de modelos usando a janela Propriedades  
 Para excluir o filtro inteiro, você não precisa abrir as caixas de diálogo do editor de filtro. As condições de filtro que você criou estão disponíveis na propriedade **Filter** do modelo de mineração.  
  
> [!NOTE]  
>  Você pode exibir as propriedades de um modelo de mineração no [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], mas não no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].  
  
#### <a name="to-clear-the-filter-on-a-mining-model-in-solution-explorer"></a>Para desmarcar o filtro em um modelo de mineração no Gerenciador de Soluções  
  
1.  No Gerenciador de Soluções, clique no modelo de mineração que contém o filtro.  
  
2.  Na janela **Propriedades** , clique com o botão direito do mouse no texto do filtro na propriedade **Filtro** e marque **Selecionar Tudo**.  
  
3.  Pressione a tecla Backspace ou Delete.  
  
## <a name="see-also"></a>Consulte Também  
 [Detalhar dados do caso a partir do modelo de mineração](../../analysis-services/data-mining/drill-through-to-case-data-from-a-mining-model.md)   
 [Tarefas e instruções do modelo de mineração](../../analysis-services/data-mining/mining-model-tasks-and-how-tos.md)   
 [Filtros para modelos de mineração &#40;Analysis Services – Mineração de dados&#41;](../../analysis-services/data-mining/filters-for-mining-models-analysis-services-data-mining.md)  
  
  
