---
title: PUBLISHINGSERVERNAME (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: sql-database
ms.service: 
ms.component: t-sql|functions
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- PUBLISHINGSERVERNAME_TSQL
- PUBLISHINGSERVERNAME
dev_langs:
- TSQL
helpviewer_keywords:
- PUBLISHINGSERVERNAME function
- Publishers [SQL Server replication], names
ms.assetid: e7c278e5-ab23-419e-ab3e-3bb20b0636df
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 256cdbcb82e257b1157c329a5e20e605d53d6f14
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="replication-functions---publishingservername"></a>Funções de replicação – PUBLISHINGSERVERNAME
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Retorna o nome do Publicador de origem de um banco de dados publicado que participa de uma sessão de espelhamento de banco de dados. Esta função é executada em uma instância de Publicador do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no banco de dados de publicação. Use-a para determinar o Publicador original do banco de dados publicado.  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Convenções da sintaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
PUBLISHINGSERVERNAME()  
```  
  
## <a name="return-types"></a>Tipos de retorno  
 **nvarchar**  
  
## <a name="remarks"></a>Remarks  
 PUBLISHINGSERVERNAME é usada em todos os tipos de replicação.  
  
 PUBLISHINGSERVERNAME é usada quando há uma sessão de espelhamento de banco de dados no banco de dados de publicação entre o Publicador e a instância parceira espelho.  
  
 Essa função deve ser executada dentro do contexto de um banco de dados de publicação. Quando PUBLISHINGSERVERNAME é executada em um banco de dados de publicação na instância de servidor espelho do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], o nome da instância do Publicador de origem do banco de dados publicado é retornado. Quando esta é executada em um banco de dados publicador na instância de servidor espelho não publicada ou que seja publicada pela instância de servidor espelho após um failover, o nome da instância de servidor de espelho é retornado. Quando esta função for executada na instância do Publicador original, o nome do Publicador será retornado.  
  
## <a name="see-also"></a>Consulte Também  
 [Espelhamento e replicação de banco de dados &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-and-replication-sql-server.md)   
 [Funções de Replicação &#40;Transact-SQL&#41;](http://msdn.microsoft.com/library/53702dee-de58-47d5-a552-7f32000f77d4)  
  
  
