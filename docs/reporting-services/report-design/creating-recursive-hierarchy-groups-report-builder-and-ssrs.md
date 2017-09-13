---
title: "Criando grupos de hierarquia recursiva (construtor de relatórios e SSRS) | Microsoft Docs"
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- reporting-services-sharepoint
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 06eccab6-4089-46e8-a84f-5bf3bbe0c23b
caps.latest.revision: 8
author: maggiesMSFT
ms.author: maggies
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: b6f587b40c53ff64b484b86a324b92ca5de21b77
ms.contentlocale: pt-br
ms.lasthandoff: 08/09/2017

---
# <a name="creating-recursive-hierarchy-groups-report-builder-and-ssrs"></a>Criando grupos de hierarquias recursivas (Construtor de Relatórios e SSRS)
Para exibir dados recursivos em relatórios paginados do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] (em que o relacionamento entre pai e filho é representado por campos no conjunto de dados), defina a expressão de grupo de região de dados com base no campo filho e defina a propriedade Parent com base no campo pai.  
  
 Exibir dados hierárquicos é um uso comum dos grupos de hierarquias recursivas (por exemplo, funcionários em um organograma). O conjunto de dados inclui uma lista de funcionários e gerentes, em que os nomes de gerentes também aparecem na lista de funcionários.  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="creating-recursive-hierarchies"></a>Criando hierarquias recursivas  
 Para criar uma hierarquia recursiva em uma região de dados tablix, você deve definir a expressão de grupo como o campo que especifica os dados filho e a propriedade Parent do grupo como o campo que especifica os dados pai. Por exemplo, no caso de um conjunto de dados que inclui campos ID de funcionário e ID de gerente em que os funcionários estão subordinados aos gerentes, defina a expressão de grupo como ID de funcionário e a propriedade Parent como ID de gerente.  
  
 Um grupo definido como hierarquia recursiva (isto é, um grupo que usa a propriedade Parent) só pode ter uma expressão de grupo. É possível usar a função **Level** no preenchimento da caixa de texto para recuar os nomes de funcionários conforme seu nível na hierarquia.  
  
 Para obter mais informações, consulte [adicionar ou excluir um grupo em uma região de dados &#40; Construtor de relatórios e SSRS &#41; ](../../reporting-services/report-design/add-or-delete-a-group-in-a-data-region-report-builder-and-ssrs.md) e [criar um grupo de hierarquia recursiva &#40; Construtor de relatórios e SSRS &#41; ](../../reporting-services/report-design/create-a-recursive-hierarchy-group-report-builder-and-ssrs.md).  
  
### <a name="aggregate-functions-that-support-recursion"></a>Funções de agregação compatíveis com recursão  
 Você pode usar as funções de agregação do Reporting Services que aceitam o parâmetro *Recursive* para calcular dados resumidos de uma hierarquia recursiva. Estas funções aceitam **Recursive** como parâmetro: [Sum](../../reporting-services/report-design/report-builder-functions-sum-function.md), [Avg](../../reporting-services/report-design/report-builder-functions-avg-function.md), [Count](../../reporting-services/report-design/report-builder-functions-count-function.md), [CountDistinct](../../reporting-services/report-design/report-builder-functions-countdistinct-function.md), [CountRows](../../reporting-services/report-design/report-builder-functions-countrows-function.md), [Max](../../reporting-services/report-design/report-builder-functions-max-function.md), [Min](../../reporting-services/report-design/report-builder-functions-min-function.md), [StDev](../../reporting-services/report-design/report-builder-functions-stdev-function.md), [StDevP](../../reporting-services/report-design/report-builder-functions-stdevp-function.md), [Sum](../../reporting-services/report-design/report-builder-functions-sum-function.md), [Var](../../reporting-services/report-design/report-builder-functions-var-function.md)e [VarP](../../reporting-services/report-design/report-builder-functions-varp-function.md). Para obter mais informações, consulte [Referência de funções de agregação &#40;Construtor de Relatórios e SSRS&#41;](../../reporting-services/report-design/report-builder-functions-aggregate-functions-reference.md).  
  
## <a name="see-also"></a>Consulte também  
 [Tabelas, matrizes e listas &#40;Construtor de Relatórios e SSRS&#41;](../../reporting-services/report-design/tables-matrices-and-lists-report-builder-and-ssrs.md)   
 [Região de dados Tablix &#40; Construtor de relatórios e SSRS &#41;](../../reporting-services/report-design/tablix-data-region-report-builder-and-ssrs.md)   
 [Referência de funções de agregação &#40; Construtor de relatórios e SSRS &#41;](../../reporting-services/report-design/report-builder-functions-aggregate-functions-reference.md)   
 [Tabelas &#40; Construtor de relatórios e SSRS &#41;](../../reporting-services/report-design/tables-report-builder-and-ssrs.md)   
 [Matrizes &#40; Construtor de relatórios e SSRS &#41;](../../reporting-services/report-design/create-a-matrix-report-builder-and-ssrs.md)   
 [Listas de &#40; Construtor de relatórios e SSRS &#41;](../../reporting-services/report-design/create-invoices-and-forms-with-lists-report-builder-and-ssrs.md)    
 [Tabelas, matrizes e listas de &#40; Construtor de relatórios e SSRS &#41;](../../reporting-services/report-design/tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  