---
title: "Criando uma cadeia de Conexão válida usando o protocolo de memória compartilhada | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- connection strings [Database Engine], shared memory
- aliases [SQL Server], shared memory
ms.assetid: 5fff42e8-377f-4b40-b0c8-b02393f8a1af
caps.latest.revision: 25
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 36a885eba54a3710e5cb4c77a13a6382c5c9559a
ms.contentlocale: pt-br
ms.lasthandoff: 08/02/2017

---
# Criando uma cadeia de conexão válida usando o protocolo de memória compartilhada
  As conexões com o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a partir de um cliente executado no mesmo computador usam o protocolo de memória compartilhada. A memória compartilhada não tem propriedades configuráveis. Essa memória sempre é tentada primeiro e não pode ser movida da posição superior da lista **Protocolos Habilitados** na lista **Propriedades de Protocolos de Cliente** . O protocolo de Memória Compartilhada pode ser desabilitado, o que é útil ao solucionar problemas dos outros protocolos.  
  
 Não é possível criar um alias usando o protocolo de memória compartilhada, mas se a memória compartilhada estiver habilitada, a conexão com o [!INCLUDE[ssDE](../../includes/ssde-md.md)] pelo nome criará uma conexão de memória compartilhada. Uma cadeia de conexão de memória compartilhada usa o formato `lpc:<servername>[\instancename]`.  
  
## Conectando-se ao servidor local  
 Ao conectar-se ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] executado no mesmo computador que o cliente, você pode usar **(local)** como o nome do servidor. Esse procedimento não é incentivado, pois leva a ambiguidade. No entanto, ele pode ser útil quando se sabe que o cliente está sendo executado no computador pretendido. Por exemplo, ao criar um aplicativo para usuários móveis desconectados, como uma força de vendas, em que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] será executado em computadores laptop e armazenará dados de projeto, um cliente conectado a **(local)** sempre se conectaria ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] executado no laptop. A palavra **localhost** ou um ponto (**.**) pode ser usado em lugar de **(local)**.  
  
## Verificando o protocolo de conexão  
 A consulta a seguir retornará o protocolo usado para a conexão atual.  
  
```  
SELECT net_transport   
FROM sys.dm_exec_connections   
WHERE session_id = @@SPID;  
  
```  
  
## Exemplos:  
 Os seguintes nomes se conectarão ao computador local com o protocolo da memória compartilhada, se ele estiver habilitado:  
  
 `<servername>`  
  
 `<servername>\<instancename>`  
  
 `(local)`  
  
 `localhost`  
  
 Não é possível criar um alias para uma conexão de memória compartilhada.  
  
> [!NOTE]  
>  A especificação de um Endereço IP na caixa **Servidor** resultará em uma conexão TCP/IP.  
  
## Consulte também  
 [Criando uma cadeia de Conexão válida usando TCP/IP](../../tools/configuration-manager/creating-a-valid-connection-string-using-tcp-ip.md)   
 [Criando uma cadeia de Conexão válida usando Pipes nomeados](http://msdn.microsoft.com/library/90930ff2-143b-4651-8ae3-297103600e4f)   
 [Escolhendo um protocolo de rede](http://msdn.microsoft.com/library/6565fb7d-b076-4447-be90-e10d0dec359a)  
  
  