---
title: "Filtrar os exemplos de equações (construtor de relatórios e SSRS) | Microsoft Docs"
ms.custom: 
ms.date: 03/07/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- reporting-services-sharepoint
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- filtering data [Reporting Services], filter equation examples
ms.assetid: 66bec93d-7c3b-4d4a-8cb6-7a7bb2f34ec6
caps.latest.revision: 18
author: maggiesMSFT
ms.author: maggies
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: e6bbd95ac20afbeb00b331efa13492a0036fff20
ms.contentlocale: pt-br
ms.lasthandoff: 08/09/2017

---
# <a name="filter-equation-examples-report-builder-and-ssrs"></a>Exemplos de equações de filtro (Construtor de Relatórios e SSRS)
  Para criar um filtro, é necessário especificar uma ou mais equações de filtro. As equações de filtro incluem uma expressão, um tipo de dados, um operador e um valor. Este tópico traz exemplos de filtros que são utilizados com frequência.  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="filter-examples"></a>Exemplos de filtro  
 A tabela a seguir mostra exemplo de equações de filtro que usam diferentes tipos de dados e operadores. O escopo da comparação é determinado pelo item de relatório para o qual é definido um filtro. Por exemplo, no caso de um filtro definido em um conjunto de dados, **TOP % 10** representa os principais 10% de valores do conjunto de dados; no caso de um filtro definido em um grupo, **TOP % 10** são os principais 10% de valores do grupo.  
  
|Expressão simples|Tipo de Dados|Operador|Value|Description|  
|-----------------------|---------------|--------------|-----------|-----------------|  
|`[SUM(Quantity)]`|**Integer**|**>**|`7`|Inclui valores de dados maiores que 7.|  
|`[SUM(Quantity)]`|**Integer**|**TOP N**|`10`|Inclui os 10 principais valores de dados.|  
|`[SUM(Quantity)]`|**Integer**|**TOP %**|`20`|Inclui os principais 20% de valores de dados.|  
|`[Sales]`|**Texto**|**>**|`=CDec(100)`|Inclui todos os valores do tipo System.Decimal (tipos de dados “money” do SQL) maiores que $100.|  
|`[OrderDate]`|**DateTime**|**>**|`2008-01-01`|Inclui todas as datas, desde 1º de janeiro de 2008 até a presente data.|  
|`[OrderDate]`|**DateTime**|**BETWEEN**|`2008-01-01`<br /><br /> `2008-02-01`|Inclui as datas de 1o. de janeiro de 2008 até, e incluindo, 1º de fevereiro de 2008.|  
|`[Territory]`|**Texto**|**LIKE**|`*east`|Todos os nomes de território que terminam com "leste".|  
|`[Territory]`|**Texto**|**LIKE**|`%o%th*`|Todos os nomes de território que incluem Norte e Sul no início do nome.|  
|`=LEFT(Fields!Subcat.Value,1)`|**Texto**|**IN**|`B, C, T`|Todos os valores de subcategorias que começam com as letras B, C ou T.|  
  
## <a name="see-also"></a>Consulte também  
 [Parâmetros de relatório e &#40; Construtor de relatórios, Report Designer e &#41;](../../reporting-services/report-design/report-parameters-report-builder-and-report-designer.md)   
 [Adicionar filtros de conjunto de dados, filtros de região de dados e filtros de grupo &#40; Construtor de relatórios e SSRS &#41;](../../reporting-services/report-design/add-dataset-filters-data-region-filters-and-group-filters.md)   
 [Tipos de dados em expressões &#40; Construtor de relatórios e SSRS &#41;](../../reporting-services/report-design/data-types-in-expressions-report-builder-and-ssrs.md)   
 [Uso de expressões em relatórios &#40; Construtor de relatórios e SSRS &#41;](../../reporting-services/report-design/expression-uses-in-reports-report-builder-and-ssrs.md)   
 [Exemplos de expressões &#40; Construtor de relatórios e SSRS &#41;](../../reporting-services/report-design/expression-examples-report-builder-and-ssrs.md)  
  
  