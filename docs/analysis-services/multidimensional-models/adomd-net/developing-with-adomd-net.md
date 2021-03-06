---
title: Desenvolvendo com ADOMD.NET | Microsoft Docs
ms.custom: 
ms.date: 02/14/2018
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
helpviewer_keywords:
- ADOMD.NET
ms.assetid: abaf33aa-db55-43bf-8f30-15547559be1d
caps.latest.revision: 
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 67251d077156d608e249ec44125002bc7cc3cda9
ms.sourcegitcommit: 7519508d97f095afe3c1cd85cf09a13c9eed345f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2018
---
# <a name="developing-with-adomdnet"></a>Desenvolvendo com ADOMD.NET
  O ADOMD.NET é um [!INCLUDE[msCoName](../../../includes/msconame-md.md)] provedor de dados .NET Framework que foi projetado para se comunicar com [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]. O ADOMD.NET usa o protocolo XML for Analysis para se comunicar com fontes de dados analíticos usando conexões TCP/IP ou HTTP para transmitir e receber solicitações e respostas SOAP compatíveis com a especificação do XML for Analysis. Os comandos podem ser enviados em MDX (Multidimensional Expressions), DMX (Data Mining Extensions), ASSL (Analysis Services Scripting Language) ou até em uma sintaxe limitada de SQL, e pode não retornar um resultado. Os dados analíticos, KPIs (indicadores chave de desempenho) e modelos de mineração podem ser consultados e ser manipulados por meio do modelo de objeto do ADOMD.NET. Ao usar o ADOMD.NET, você também pode exibir e trabalhar com metadados recuperando conjuntos de linhas do esquema compatíveis ou usando o modelo de objeto do ADOMD.NET.  
  
 O provedor de dados do ADOMD.NET é representado pelo **Microsoft.AnalysisServices.AdomdClient** namespace.  
  
## <a name="in-this-section"></a>Nesta seção  
  
|Tópico|Description|  
|-----------|-----------------|  
|[Programação do cliente no ADOMD.NET](../../../analysis-services/multidimensional-models-adomd-net-client/adomd-net-client-programming.md)|Descreve como usar objetos cliente do ADOMD.NET na recuperação de dados e de metadados de fontes de dados analíticos.|  
|[Programação do servidor no ADOMD.NET](../../../analysis-services/multidimensional-models-adomd-net-server/adomd-net-server-programming.md)|Descreve como usar objetos de servidor do ADOMD.NET na criação de procedimentos armazenados e de funções definidas pelo usuário.|  
|[Redistribuindo o ADOMD.NET](../../../analysis-services/multidimensional-models/adomd-net/redistributing-adomd-net.md)|Descreve o processo de redistribuição do ADOMD.NET.|  
|<xref:Microsoft.AnalysisServices.AdomdClient>|Fornece detalhes sobre os objetos que estão contidos no **Microsoft.AnalysisServices.AdomdClient** namespace.|  
  
## <a name="see-also"></a>Consulte também  
 [Expressões multidimensionais &#40; MDX &#41; Referência](../../../mdx/multidimensional-expressions-mdx-reference.md)   
 [Extensões de mineração de dados &#40; DMX &#41; Referência](../../../dmx/data-mining-extensions-dmx-reference.md)   
 [Conjuntos de linhas do esquema do Analysis Services](../../../analysis-services/schema-rowsets/analysis-services-schema-rowsets.md)   
 [Desenvolvendo com o Analysis Services Scripting Language &#40; ASSL &#41;](../../../analysis-services/multidimensional-models/scripting-language-assl/developing-with-analysis-services-scripting-language-assl.md)   
 [Acesso a dados modelo multidimensional &#40; Analysis Services - dados multidimensionais &#41;](../../../analysis-services/multidimensional-models/mdx/multidimensional-model-data-access-analysis-services-multidimensional-data.md)  
  
  
