---
title: MSSQL_ENG020598 | Microsoft Docs
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: replication
ms.reviewer: 
ms.suite: sql
ms.technology:
- replication
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSSQL_ENG020598 error
ms.assetid: 1c3032f2-23d1-4ead-94ee-16ac4d75cd0c
caps.latest.revision: 
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: cd821635130f3b631cfb08f29b66af13de82b3d3
ms.sourcegitcommit: ab25b08a312d35489a2c4a6a0d29a04bbd90f64d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/08/2018
---
# <a name="mssqleng020598"></a>MSSQL_ENG020598
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
    
## <a name="message-details"></a>Detalhes da mensagem  
  
|||  
|-|-|  
|Nome do produto|SQL Server|  
|ID do evento|20598|  
|Origem do evento|MSSQLSERVER|  
|Componente|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|Nome simbólico||  
|Texto da mensagem|A linha não foi encontrada no Assinante ao aplicar o comando replicado.|  
  
## <a name="explanation"></a>Explicação  
 Esse erro ocorre na replicação transacional quando o Distribution Agent tenta atualizar uma linha no Assinante, mas a linha foi excluída ou a chave primária da linha foi alterada. Por padrão, os Assinantes de publicações transacionais devem ser tratados como somente leitura, porque as alterações não são propagadas de volta para o Publicador. Para a replicação transacional, as alterações do usuário devem ser realizadas no Assinante somente se forem usadas assinaturas que podem ser atualizadas ou replicação ponto a ponto (P2P). Para obter mais informações sobre essas opções, consulte [Updatable Subscriptions for Transactional Replication](../../relational-databases/replication/transactional/updatable-subscriptions-for-transactional-replication.md) e [Peer-to-Peer Transactional Replication](../../relational-databases/replication/transactional/peer-to-peer-transactional-replication.md).  
  
## <a name="user-action"></a>Ação do usuário  
 **Para resolver esse problema:**  
  
1.  Se for necessário que a replicação continue enquanto você identifica a origem do erro, especifique o parâmetro **-SkipErrors 20598** para o Agente de Distribuição. Isso permite que o agente ignore alterações que resultem no erro 20598, enquanto permite que outras alterações sejam replicadas.  
  
2.  Identifique quais linhas no Assinante foram excluídas ou possuem uma chave primária diferente daquela das linhas correspondentes no Publicador. É possível usar o [tablediff Utility](../../tools/tablediff-utility.md) para determinar quais linhas são diferentes nos bancos de dados de publicação e de assinatura. Para obter informações sobre como usar esse utilitário com bancos de dados replicados, consulte [Comparar diferenças em tabelas replicadas &#40;programação de replicação&#41;](../../relational-databases/replication/administration/compare-replicated-tables-for-differences-replication-programming.md).  
  
3.  Corrija as linhas no Assinante usando o utilitário **tablediff** ou qualquer outro método.  
  
4.  (Opcional) Remova o parâmetro **-SkipErrors** .  
  
## <a name="see-also"></a>Consulte Também  
 [Referência de erros e eventos &#40;Replicação&#41;](../../relational-databases/replication/errors-and-events-reference-replication.md)  
  
  
