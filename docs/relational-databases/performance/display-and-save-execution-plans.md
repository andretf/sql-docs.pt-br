---
title: "Exibir e salvar planos de execução | Microsoft Docs"
ms.custom: 
ms.date: 08/21/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Showplan results
- execution plans [SQL Server]
- queries [SQL Server], tuning
- execution plans [SQL Server], how-to topics
- SQL Server Management Studio [SQL Server], execution plans
- tuning queries [SQL Server]
ms.assetid: bcd6f094-c613-4835-ae19-4caaadb4bb17
caps.latest.revision: 24
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.translationtype: HT
ms.sourcegitcommit: 014b531a94b555b8d12f049da1bd9eb749b4b0db
ms.openlocfilehash: 3eb1056b561e2fea455c29c2d5f72736564c1ffd
ms.contentlocale: pt-br
ms.lasthandoff: 08/22/2017

---
# <a name="display-and-save-execution-plans"></a>Exibir e salvar planos de execução
  Esta seção explica como exibir planos de execução e como salvá-los em um arquivo no formato XML usando o Microsoft [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].  
  
 Os planos de execução exibem graficamente os métodos de recuperação de dados escolhidos pelo Otimizador de Consulta do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Os planos de execução representam o custo de execução de instruções e consultas específicas no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando ícones em vez da representação tabular produzida pelas instruções [SET SHOWPLAN_ALL](../../t-sql/statements/set-showplan-all-transact-sql.md) ou [SET SHOWPLAN_TEXT](../../t-sql/statements/set-showplan-text-transact-sql.md). Essa abordagem gráfica é muito útil para entender as características de desempenho de uma consulta.  

 Enquanto o Otimizador de Consulta [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] produz apenas um plano de execução, há o conceito de plano de execução **estimado** e de plano de execução **real**.
 -  Um [plano de execução estimado](../../relational-databases/performance/display-the-estimated-execution-plan.md) retorna o plano de execução como produzido pelo Otimizador de Consulta no tempo de compilação. A produção do plano de execução estimado não executa a consulta ou o lote de fato e, portanto, não contém nenhuma informação de tempo de execução, como avisos de métrica ou tempo de execução de uso real do recurso. 
 -  Um [plano de execução real](../../relational-databases/performance/display-an-actual-execution-plan.md) retorna o plano de execução produzido pelo Otimizador de Consulta e, depois disso, as consultas ou os lotes concluem a execução. Isso inclui informações de tempo de execução sobre as métricas de uso de recursos e os avisos de tempo de execução.  

 Para obter mais informações, consulte [Guia da Arquitetura de Processamento de Consultas](../../relational-databases/query-processing-architecture-guide.md).
  
## <a name="in-this-section"></a>Nesta seção  
  
-   [Exibir o plano de execução estimado](../../relational-databases/performance/display-the-estimated-execution-plan.md)  
  
-   [Exibir um plano de execução real](../../relational-databases/performance/display-an-actual-execution-plan.md)  
  
-   [Salvar um plano de execução em formato XML](../../relational-databases/performance/save-an-execution-plan-in-xml-format.md)  
  
  
