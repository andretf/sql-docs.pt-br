---
title: Linguagem de script (TMSL) de comandos na tabela modelo | Microsoft Docs
ms.date: 05/30/2017
ms.prod: analysis-services
ms.prod_service: analysis-services, azure-analysis-services
ms.service: 
ms.component: 
ms.reviewer: 
ms.suite: pro-bi
ms.custom: 
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 4eb07192-6f53-4426-830a-d63a945dbcab
caps.latest.revision: "12"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 39959a86e064da782097ddc75d9d3651b4d436fa
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2018
---
# <a name="tmsl-reference---commands"></a>Referência TMSL - comandos
[!INCLUDE[ssas-appliesto-sqlas-aas](../../includes/ssas-appliesto-sqlas-aas.md)]Você pode executar comandos em um ponto de extremidade do XMLA, formular definições de objeto em JSON usando o modelo de script TMSL (linguagem tabela), nos bancos de dados de modelo de tabela.   Consulte [definições de objeto na tabela de linguagem de scripts &#40; modelo TMSL &#41; ](../../analysis-services/tabular-models-scripting-language-objects/tmsl-reference-tabular-objects.md) para obter uma lista de objetos usados com os comandos a seguir.  
  
## <a name="object-operations"></a>Operações de objeto  
  
|||  
|-|-|  
|[Alterar o comando &#40; TMSL &#41;](../../analysis-services/tabular-models-scripting-language-commands/alter-command-tmsl.md)|Faça as modificações de embutido para um objeto sem a necessidade de especificar a definição completa.|  
|[Criar comando &#40; TMSL &#41;](../../analysis-services/tabular-models-scripting-language-commands/create-command-tmsl.md)|Cria um novo objeto, incluindo seus descendentes.|  
|[Comando CreateOrReplace &#40; TMSL &#41;](../../analysis-services/tabular-models-scripting-language-commands/createorreplace-command-tmsl.md)|Criar ou substituir partes de uma definição de objeto. A definição completa deve ser fornecida.|  
|[Excluir comando &#40; TMSL &#41;](../../analysis-services/tabular-models-scripting-language-commands/delete-command-tmsl.md)|Exclua um objeto, incluindo seus descendentes.|  
  
## <a name="data-refresh-operations"></a>Operações de atualização de dados  
  
|||  
|-|-|  
|[Comando MergePartitions &#40; TMSL &#41;](../../analysis-services/tabular-models-scripting-language-commands/mergepartitions-command-tmsl.md)|Mesclar uma partição de destino em uma fonte e, em seguida, exclua o destino.|  
|[Atualização de comando &#40; TMSL &#41;](../../analysis-services/tabular-models-scripting-language-commands/refresh-command-tmsl.md)|Processe um banco de dados, tabela ou partição.|  
  
## <a name="scripting"></a>Script  
  
|||  
|-|-|  
|[Sequência de comando &#40; TMSL &#41;](../../analysis-services/tabular-models-scripting-language-commands/sequence-command-tmsl.md)|Operações em lotes em sequência ou em paralelo|  
  
## <a name="database-management-operations"></a>Operações de gerenciamento de banco de dados  
  
|||  
|-|-|  
|[Anexar comando &#40; TMSL &#41;](../../analysis-services/tabular-models-scripting-language-commands/attach-command-tmsl.md)|Adiciona um arquivo para o servidor.|  
|[Desanexar comando &#40; TMSL &#41;](../../analysis-services/tabular-models-scripting-language-commands/detach-command-tmsl.md)|Remove um arquivo de servidores.|  
|[Comando de backup &#40; TMSL &#41;](../../analysis-services/tabular-models-scripting-language-commands/backup-command-tmsl.md)|Cria um arquivo de backup de um banco de dados.|  
|[Restaurar comando &#40; TMSL &#41;](../../analysis-services/tabular-models-scripting-language-commands/restore-command-tmsl.md)|Restaura o banco de dados para o servidor.|  
|[Sincronizar comando &#40; TMSL &#41;](../../analysis-services/tabular-models-scripting-language-commands/synchronize-command-tmsl.md)|Sincroniza um banco de dados do Analysis Services com outro banco de dados existente.|  
  
## <a name="see-also"></a>Consulte Também  
 [Referência de TMSL &#40;Linguagem de Scripts de Modelo de Tabela&#41;](../../analysis-services/tabular-model-scripting-language-tmsl-reference.md)   
 [Instalar provedores de dados do Analysis Services &#40; O AMO, ADOMD.NET, MSOLAP &#41;](../../analysis-services/instances/install-windows/install-analysis-services-data-providers-amo-adomd-net-msolap.md)   
 [Nível de compatibilidade para modelos de tabela no Analysis Services](../../analysis-services/tabular-models/compatibility-level-for-tabular-models-in-analysis-services.md)  
  
  
