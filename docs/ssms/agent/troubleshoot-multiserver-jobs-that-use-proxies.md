---
title: Solucionar problemas de trabalhos com multisservidor que usam proxies | Microsoft Docs
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- tools-ssms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- proxies [SQL Server Agent], multiserver jobs
- jobs [SQL Server Agent], multiserver jobs using proxies
ms.assetid: fc579bd3-010c-4f72-8b5c-d0cc18a1f280
caps.latest.revision: 4
author: stevestein
ms.author: sstein
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: 6a02ace1fe1ba285bc340b9dca87112325f97210
ms.contentlocale: pt-br
ms.lasthandoff: 06/22/2017

---
# <a name="troubleshoot-multiserver-jobs-that-use-proxies"></a>Solucionar problemas de trabalhos multisservidor que usam proxies
Trabalhos distribuídos cujas etapas estejam associadas a um proxy são executados no contexto da conta proxy no servidor de destino. Se as etapas de trabalho que usam contas proxy falharem ao serem baixadas do servidor mestre, verifique a coluna **error_message** da tabela **sysdownloadlist** no banco de dados **msdb** quanto às seguintes mensagens de erro:  
  
-   "A etapa do trabalho requer uma conta proxy. Entretanto, a verificação de proxy está desabilitada no servidor de destino."  
  
    Para resolver este erro, defina a subchave do Registro **\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\MSSQL.***\<n*>**\SQLServerAgent\AllowDownloadedJobsToMatchProxyName** como **1 (verdadeiro)**. Por padrão, essa subchave está definida como **0** (**falso**). O valor de **MSSQL.**\<*n*> é o nome de instância; por exemplo, **MSSQL.1** ou **MSSQL.3**.  
  
-   "Proxy não localizado."  
  
    Para resolver este erro, verifique se existe uma conta proxy no servidor de destino com o mesmo nome da conta proxy do servidor mestre sob a qual a etapa de trabalho é executada.  
  
> [!CAUTION]  
> [!INCLUDE[ssNoteRegistry](../../includes/ssnoteregistry_md.md)]  
  
## <a name="see-also"></a>Consulte também  
[Criar um ambiente multisservidor](../../ssms/agent/create-a-multiserver-environment.md)  
  
