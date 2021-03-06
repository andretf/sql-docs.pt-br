---
title: Gerenciando o Service Broker | Microsoft Docs
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: smo
ms.reviewer: 
ms.suite: sql
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- Service Broker [SMO]
ms.assetid: b29d7432-d1e5-4bb6-b544-57b3a9430f95
caps.latest.revision: 
author: stevestein
ms.author: sstein
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 80784d2a5df6d8bd6a2514da6451da6496688ed4
ms.sourcegitcommit: cb2f9d4db45bef37c04064a9493ac2c1d60f2c22
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2018
---
# <a name="managing-service-broker"></a>Gerenciando o Service Broker
[!INCLUDE[appliesto-ss-asdb-asdw-xxx-md](../../../includes/appliesto-ss-asdb-asdw-xxx-md.md)]

  No SMO, o [!INCLUDE[ssSB](../../../includes/sssb-md.md)] objetos são encontrados no **Microsoft.SqlServer.Management.Smo.Broker** namespace, o que requer uma referência ao Microsoft.SqlServer.Smo.dll. Uma referência ao Microsoft.SqlServer.ServiceBrokerEnum.dll também é necessária para suportar informações de classe.  
  
 O SMO fornece um conjunto de objetos do [!INCLUDE[ssSB](../../../includes/sssb-md.md)] que permitem gerenciamento programático (DDL) da implementação do [!INCLUDE[ssSB](../../../includes/sssb-md.md)]. Isso inclui a definição de tipos de mensagem, contratos, filas e serviços. Como o SMO é uma ferramenta de gerenciamento não voltada à manipulação de dados, o envio e recebimento de mensagens do [!INCLUDE[ssSB](../../../includes/sssb-md.md)] não são suportados pelo SMO.  
  
 No SMO, o objeto <xref:Microsoft.SqlServer.Management.Smo.Database.ServiceBroker%2A> é a classe de nível superior na qual reside toda a funcionalidade do [!INCLUDE[ssSB](../../../includes/sssb-md.md)]. É necessária uma implementação do [!INCLUDE[ssSB](../../../includes/sssb-md.md)] para cada banco de dados que está participando do aplicativo de mensagens distribuído. Portanto, o objeto <xref:Microsoft.SqlServer.Management.Smo.Broker.ServiceBroker> é filho do objeto <xref:Microsoft.SqlServer.Management.Smo.Database>.  
  
 O objeto <xref:Microsoft.SqlServer.Management.Smo.Broker.ServiceBroker> contém coleções dos seguintes objetos usados para definir a implementação do [!INCLUDE[ssSB](../../../includes/sssb-md.md)]:  
  
-   Os objetos <xref:Microsoft.SqlServer.Management.Smo.Broker.MessageType> representam tipos de mensagens que definem o conteúdo das mensagens.  
  
-   Os objetos <xref:Microsoft.SqlServer.Management.Smo.Broker.MessageTypeMapping> representam contratos que especificam a direção e o tipo de mensagens em uma determinada conversa.  
  
-   Os objetos <xref:Microsoft.SqlServer.Management.Smo.Broker.ServiceQueue> armazenam as mensagens antes do envio e depois que são recebidas. Eles proporcionam comunicação assíncrona entre serviços, bem como outros benefícios, como o bloqueio automático de mensagens no mesmo grupo de conversa.  
  
-   Os objetos <xref:Microsoft.SqlServer.Management.Smo.Broker.BrokerService> representam serviços [!INCLUDE[ssSB](../../../includes/sssb-md.md)], que são os pontos de extremidade endereçáveis para conversas. As mensagens do [!INCLUDE[ssSB](../../../includes/sssb-md.md)] são enviadas de um serviço para outro. Um serviço especifica uma fila para conter as mensagens e determina os contratos para os quais o serviço pode ser o destino.  
  
-   Os objetos <xref:Microsoft.SqlServer.Management.Smo.Broker.RemoteServiceBinding> representam as configurações que o [!INCLUDE[ssSB](../../../includes/sssb-md.md)] usa para segurança e autenticação ao se comunicar com um serviço remoto.  
  
-   Os objetos <xref:Microsoft.SqlServer.Management.Smo.Broker.ServiceRoute> representam uma rota do [!INCLUDE[ssSB](../../../includes/sssb-md.md)], que contém as informações de local para o serviço e o banco de dados no qual ele é definido. Uma rota é necessária para a entrega de mensagens. Por padrão, cada banco de dados contém uma rota que especifica o local como a instância atual do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].  
  
## <a name="see-also"></a>Consulte também  
 <xref:Microsoft.SqlServer.Management.Smo.Broker>   
 [SQL Server Service Broker](../../../database-engine/configure-windows/sql-server-service-broker.md)  
  
  
