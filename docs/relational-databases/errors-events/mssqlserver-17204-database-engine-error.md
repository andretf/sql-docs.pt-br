---
title: MSSQLSERVER_17204 | Microsoft Docs
ms.custom: 
ms.date: 04/04/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: errors-events
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
helpviewer_keywords:
- 17204 (Database Engine error)
ms.assetid: 40db66f9-dd5e-478c-891e-a06d363a2552
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: befada4a3c2b5ea56fbe8c6ec6b14f6d5a558886
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="mssqlserver17204"></a>MSSQLSERVER_17204
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  
## <a name="details"></a>Detalhes  
  
|||  
|-|-|  
|Nome do produto|SQL Server|  
|ID do evento|17204|  
|Origem do evento|MSSQLSERVER|  
|Componente|SQLEngine|  
|Nome simbólico|DBLKIO_DEVOPENFAILED|  
|Texto da mensagem|%ls: Não foi possível abrir arquivo %ls para o número de arquivo %d.  Erro de SO: %ls.|  
  
## <a name="explanation"></a>Explicação  
O SQL Server não pôde abrir o arquivo indicado devido ao erro especificado.  
  
## <a name="user-action"></a>Ação do usuário  
Analise e corrija o sistema operacional; em seguida, tente executar a operação novamente.  
  
