---
title: Cubos em modelos multidimensionais | Microsoft Docs
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- analysis-services/multidimensional-tabular
- analysis-services/data-mining
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- OLAP objects [Analysis Services], cubes
- cubes [Analysis Services], about cubes
- cubes [Analysis Services]
- OLAP [Analysis Services], cubes
ms.assetid: e0f7acf3-4b07-41fc-a5fc-ac30b4a56c54
caps.latest.revision: 33
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 1a555a25c41b4860aa16d5a2cfd43749a0ccd65d
ms.contentlocale: pt-br
ms.lasthandoff: 09/01/2017

---
# <a name="cubes-in-multidimensional-models"></a>Cubos em modelos multidimensionais
  Um cubo é uma estrutura multidimensional que contém informações para fins analíticos; os principais elementos constituintes de um cubo são dimensões e medidas. As dimensões definem a estrutura do cubo que você usa para fazer divisões, e as medidas fornecem valores numéricos agregados de interesse do usuário final. Como é uma estrutura lógica, um cubo permite a um aplicativo cliente recuperar valores, de medidas, como se estivessem contidos em células no cubo; as células são definidas para cada valor resumido possível. Uma célula, no cubo, é definida pela interseção de membros de dimensão e contém os valores agregados das medidas nessa interseção específica.  
  
## <a name="benefits-of-using-cubes"></a>Benefícios do uso de cubos  
 Um cubo oferece um único local onde todos os dados relacionados são armazenados para análise.  
  
## <a name="components-of-cubes"></a>Componentes de cubos  
 Um cubo é constituído de:  
  
|Elemento|Description|  
|-------------|-----------------|  
|Dimensões|[Dimensões em modelos multidimensionais](../../analysis-services/multidimensional-models/dimensions-in-multidimensional-models.md)|  
|Medidas e Grupos de Medidas|[Criar medidas e grupos de medidas em modelos multidimensionais](../../analysis-services/multidimensional-models/create-measures-and-measure-groups-in-multidimensional-models.md)|  
|Partições|[Partições em modelos multidimensionais](../../analysis-services/multidimensional-models/partitions-in-multidimensional-models.md)|  
|Perspectivas|[Perspectivas em modelos multidimensionais](../../analysis-services/multidimensional-models/perspectives-in-multidimensional-models.md)|  
|Hierarquias|[Criar hierarquias definidas pelo usuário](../../analysis-services/multidimensional-models/user-defined-hierarchies-create.md)|  
|Ações|[Ações em modelos multidimensionais](../../analysis-services/multidimensional-models/actions-in-multidimensional-models.md)|  
|KPI (indicadores de desempenho chave)|[Indicadores Chave de Desempenho &#40;KPIs&#41; em Modelos Multidimensionais](../../analysis-services/multidimensional-models/key-performance-indicators-kpis-in-multidimensional-models.md)|  
|Cálculos|[Cálculos em modelos multidimensionais](../../analysis-services/multidimensional-models/calculations-in-multidimensional-models.md)|  
|Traduções|[Traduções em modelos multidimensionais &#40;Analysis Services&#41;](../../analysis-services/multidimensional-models/translations-in-multidimensional-models-analysis-services.md)|  
  
## <a name="related-tasks"></a>Tarefas relacionadas  
  
|Tópico|Description|  
|-----------|-----------------|  
|[Criar um cubo usando o Assistente para Cubos](../../analysis-services/multidimensional-models/create-a-cube-using-the-cube-wizard.md)|Descreve como usar o Assistente para Cubos para definir um cubo, as dimensões, os atributos de dimensão e as hierarquias definidas pelo usuário.|  
|[Criar medidas e grupos de medidas em modelos multidimensionais](../../analysis-services/multidimensional-models/create-measures-and-measure-groups-in-multidimensional-models.md)|Descreve como definir os grupos de medidas.|  
|[Cálculos em modelos multidimensionais](../../analysis-services/multidimensional-models/calculations-in-multidimensional-models.md)|Descreve como definir e configurar um cálculo em um script MDX.|  
|[Ações em modelos multidimensionais](../../analysis-services/multidimensional-models/actions-in-multidimensional-models.md)|Descreve como definir e configurar uma ação.|  
|[Perspectivas em modelos multidimensionais](../../analysis-services/multidimensional-models/perspectives-in-multidimensional-models.md)|Descreve como definir e configurar uma perspectiva.|  
|[Definindo procedimentos armazenados](../../analysis-services/multidimensional-models-extending-olap-stored-procedures/defining-stored-procedures.md)|Descreve como trabalhar com procedimentos armazenados.|  
  
  