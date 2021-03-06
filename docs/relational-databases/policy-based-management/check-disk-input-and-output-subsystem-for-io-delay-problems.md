---
title: "Verificar subsistema de entrada e saída de disco quanto a problemas de atraso de E/S | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: performance-monitor
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 23863340-d8e0-48d6-928b-462745885d37
caps.latest.revision: 
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: aaf32c7bad950f857fcf5c9a66c89d4a916c7329
ms.sourcegitcommit: dcac30038f2223990cc21775c84cbd4e7bacdc73
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/18/2018
---
# <a name="check-disk-input-and-output-subsystem-for-io-delay-problems"></a>Verificar o subsistema de entrada e saída de disco para problemas de atraso de E/S
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)] Esta regra verifica o log de eventos quanto à mensagem de erro 833. Esta mensagem indica que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] emitiu uma solicitação de leitura ou gravação de disco, e que a solicitação demorou mais de 15 segundos para retornar. Esse erro é informado pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e indica um problema com o subsistema de E/S do disco. Atrasos longos podem danificar seriamente o desempenho do ambiente do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
## <a name="best-practices-recommendations"></a>Práticas Recomendadas  
 Solucione este erro procurando mensagens de erros relacionados a hardware no log de eventos de sistema. Examine também os logs específicos do hardware, se estiverem disponíveis.  
  
 Use o Monitor de Desempenho para examinar os seguintes contadores:  
  
-   Transferência média do disco por segundo  
  
-   Comprimento médio da fila de disco  
  
-   Comprimento da fila atual de disco  
  
 Por exemplo, o tempo médio de Disco seg/Transferência em um computador executando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] normalmente é inferior a 15 milissegundos. Se o valor médio de Disco seg/Transferência aumentar, isso indica que o subsistema de E/S do disco não está acompanhando da melhor maneira possível o ritmo da demanda de E/S.  
  
## <a name="for-more-information"></a>Para obter mais informações  
   
  
 [Artigo 897284 da Base de Dados de Conhecimento Microsoft](http://go.microsoft.com/fwlink/?linkid=117743)  
  
 [Fundamentos de E/S do SQL Server, Capítulo 2](http://go.microsoft.com/fwlink/?LinkId=69370)  
  
  
