---
title: "Adicionar uma expressão (construtor de relatórios e SSRS) | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- reporting-services-sharepoint
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a60ee091-b4ed-41e1-9b6a-032c316cd03f
caps.latest.revision: 8
author: maggiesMSFT
ms.author: maggies
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 57cdb0a373d713741216b1cebc8d3d44ff7fceb3
ms.contentlocale: pt-br
ms.lasthandoff: 08/09/2017

---
# <a name="add-an-expression-report-builder-and-ssrs"></a>Adicionar uma expressão (Construtor de Relatórios e SSRS)
  As expressões são usadas em um relatório inteiro para definir as propriedades de itens de relatório, os filtros, os grupos, a ordem de classificação, as cadeias de conexão e os valores de parâmetro. As expressões começam com o sinal de igual (=) e são gravadas no [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]. Elas são avaliadas durante a execução pelo processador de relatório, que combina o resultado da avaliação com os elementos de layout do relatório.  
  
 As expressões podem ser simples ou complexas. Uma expressão simples faz referência a um único item de uma coleção interna. As expressões complexas podem conter constantes, operadores, itens de coleção global e chamadas de função. Para obter mais informações, consulte [Expressões &#40;Construtor de Relatórios e SSRS&#41;](../../reporting-services/report-design/expressions-report-builder-and-ssrs.md).  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-an-expression-to-a-text-box"></a>Para adicionar uma expressão a uma caixa de texto  
  
-   No modo **Design** , clique na caixa de texto na superfície de design à qual você deseja adicionar uma expressão.  
  
    -   No caso de uma expressão simples, digite na caixa de texto o texto para exibição da expressão. Por exemplo, para o campo de conjunto de dados Vendas, digite `[Sales]`.  
  
    -   No caso de uma expressão complexa, clique com o botão direito do mouse na caixa de texto e selecione **Expressão**. A caixa de diálogo **Expressão** é aberta. Digite ou crie a expressão interativamente após o sinal '=' no painel Expressão e clique em OK.  
  
         A expressão aparece na superfície de design como `<<Expr>>`.  
  
## <a name="see-also"></a>Consulte também  
 [Formatação de texto e espaços reservados &#40; Construtor de relatórios e SSRS &#41;](../../reporting-services/report-design/formatting-text-and-placeholders-report-builder-and-ssrs.md)   
 [Caixas de texto &#40; Construtor de relatórios e SSRS &#41;](../../reporting-services/report-design/text-boxes-report-builder-and-ssrs.md)   
 [Uso de expressões em relatórios &#40; Construtor de relatórios e SSRS &#41;](../../reporting-services/report-design/expression-uses-in-reports-report-builder-and-ssrs.md)   
 [Exemplos de equações de filtro &#40; Construtor de relatórios e SSRS &#41;](../../reporting-services/report-design/filter-equation-examples-report-builder-and-ssrs.md)   
 [Exemplos de expressões de grupo &#40; Construtor de relatórios e SSRS &#41;](../../reporting-services/report-design/group-expression-examples-report-builder-and-ssrs.md)   
 [Caixa de diálogo expressão &#40; Construtor de relatórios &#41;](http://msdn.microsoft.com/library/e89c4d97-5d41-4b55-8695-79329edac15d)   
 [Exemplos de expressões &#40; Construtor de relatórios e SSRS &#41;](../../reporting-services/report-design/expression-examples-report-builder-and-ssrs.md)   
 [Adicione código para um relatório &#40; SSRS &#41;](../../reporting-services/report-design/add-code-to-a-report-ssrs.md)  
  
  