---
title: Executar o SQL Server com ou sem uma rede | Microsoft Docs
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: configure-windows
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- verifying Server service has been started
- net start [SQL Server]
- command prompt [SQL Server], connections
- SQL Server services, networks
- status information [SQL Server], Server service
- running SQL Server
- networking [SQL Server], SQL Server with or without
- services [SQL Server], networks
- starting Server service
- SQL Server, running
ms.assetid: 54eac961-5c7a-4481-982d-f93a64b5c2f4
caps.latest.revision: 
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: 53f11ae418f3fa321a886abef8e6af08efb66199
ms.sourcegitcommit: d8ab09ad99e9ec30875076acee2ed303d61049b7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/23/2018
---
# <a name="run-sql-server-with-or-without-a-network"></a>Executar o SQL Server com ou sem uma rede
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pode ser executado em uma rede, ou funcionar sem uma rede.  
  
## <a name="running-sql-server-on-a-network"></a>Executando o SQL Server em uma rede  
 Para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se comunicar por meio de uma rede, o serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] deve estar em execução. Por padrão, o [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows inicia o serviço interno do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] automaticamente. Para descobrir se o serviço do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] foi iniciado, no prompt de comando, digite o seguinte:  
  
 **net start**  
  
 Se os serviços associados ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tiverem sido iniciados, os seguintes serviços serão exibidos na saída de **net start** :  
  
-   Analysis Services (MSSQLSERVER)  
  
-   SQL Server (MSSQLSERVER)  
  
-   SQL Server Agent (MSSQLSERVER)  
  
## <a name="running-sql-server-without-a-network"></a>Executando o SQL Server sem uma rede  
 Ao executar uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sem uma rede, não é preciso iniciar o serviço interno do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . Como o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], o SQL Server Configuration Manager e os comandos **net start** e **net stop** são funcionais até mesmo sem rede, os procedimentos para iniciar e interromper uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] são idênticos em uma operação com rede ou autônoma.  
  
 Ao se conectar a uma instância de um [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] autônomo de um cliente local, como o **sqlcmd**, você ignora a rede e se conecta diretamente à instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando um pipe local. A diferença entre um pipe local e um pipe de rede é se você está ou não usando uma rede. Os pipes local e de rede estabelecem uma conexão com uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando o pipe padrão (\\\\.\pipe\sql\query), a menos que sejam dadas outras instruções.  
  
 Ao se conectar a uma instância de um [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] local sem especificar um nome de servidor, você estará usando um pipe local. Ao se conectar a uma instância de um [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] local e especificar um nome de servidor explicitamente, você estará usando um pipe de rede ou outro mecanismo de IPC (comunicação entre processos) de rede, como IPX/SPX (Internetwork Packet Exchange/Sequenced Packet Exchange) (assumindo que você tenha configurado o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para usar várias redes). Como um [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] autônomo não é compatível com pipes de rede, você deve omitir o argumento **/***<Server_name>* desnecessário ao se conectar à instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em um cliente. Por exemplo, para se conectar a uma instância autônoma do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no **osql**, digite:  
  
 **osql /Usa /P** *\<saPassword>*  
  
  
