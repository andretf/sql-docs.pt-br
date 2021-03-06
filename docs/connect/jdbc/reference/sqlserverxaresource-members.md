---
title: Membros SQLServerXAResource | Microsoft Docs
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: jdbc
ms.reviewer: 
ms.suite: sql
ms.technology: drivers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a069bf2c-1b70-4817-b084-a508445de799
caps.latest.revision: "12"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 7e61b22a719ea74b1097a50f811a4e1bde85db54
ms.sourcegitcommit: 2713f8e7b504101f9298a0706bacd84bf2eaa174
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2017
---
# <a name="sqlserverxaresource-members"></a>Membros SQLServerXAResource
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  As tabelas a seguir listam os membros expostos pelo [SQLServerXAResource](../../../connect/jdbc/reference/sqlserverxaresource-class.md) classe.  
  
## <a name="constructors"></a>Construtores  
 Nenhum.  
  
## <a name="fields"></a>Campos  
  
|Nome|Description|  
|----------|-----------------|  
|[SSTRANSTIGHTLYCPLD](../../../connect/jdbc/reference/sstranstightlycpld-field-sqlserverxaresource.md)|Usado para permitir transações XA estritamente acopladas, que possuem diferentes IDs de transação de ramificação XA (XIDs), mas que têm a mesma ID de transação global (GTRID).|  
  
## <a name="inherited-fields"></a>Campos herdados  
  
|Classe herdada de:|Métodos|  
|---------------------------|-------------|  
|javax.transaction.xa.XAResource|TMENDRSCAN, TMFAIL, TMJOIN, TMNOFLAGS, TMONEPHASE, TMRESUME, TMSTARTRSCAN, TMSUCCESS, TMSUSPEND, XA_OK, XA_RDONLY|  
  
## <a name="methods"></a>Métodos  
  
|Nome|Description|  
|----------|-----------------|  
|[confirmação](../../../connect/jdbc/reference/commit-method-sqlserverxaresource.md)|Confirma a transação global especificada pelo objeto Xid fornecido.|  
|[final](../../../connect/jdbc/reference/end-method-sqlserverxaresource.md)|Termina o trabalho executado em nome de uma ramificação de transação.|  
|[esquecer](../../../connect/jdbc/reference/forget-method-sqlserverxaresource.md)|Informa ao gerenciador de recursos para esquecer uma ramificação de transação concluída de modo heurístico.|  
|[getTransactionTimeout](../../../connect/jdbc/reference/gettransactiontimeout-method-sqlserverxaresource.md)|Obtém o valor de tempo limite de transação atual definida para este [SQLServerXAResource](../../../connect/jdbc/reference/sqlserverxaresource-class.md) objeto.|  
|[isSameRM](../../../connect/jdbc/reference/issamerm-method-sqlserverxaresource.md)|Determina se a instância do Gerenciador de recursos representada pelo objeto de destino é o mesmo que a instância do Gerenciador de recursos representada pelo objeto XAResource fornecido.|  
|[preparar](../../../connect/jdbc/reference/prepare-method-sqlserverxaresource.md)|Solicita que o Gerenciador de recursos se preparar para uma confirmação de transação da transação especificada pelo objeto Xid fornecido.|  
|[recuperação](../../../connect/jdbc/reference/recover-method-sqlserverxaresource.md)|Obtém uma lista de ramificações de transação preparadas de um gerenciador de recursos.|  
|[reversão](../../../connect/jdbc/reference/rollback-method-sqlserverxaresource.md)|Solicita que o gerenciador de recursos reverta o trabalho feito em nome de uma ramificação de transação.|  
|[setTransactionTimeout](../../../connect/jdbc/reference/settransactiontimeout-method-sqlserverxaresource.md)|Define o valor de tempo limite de transação atual para este [SQLServerXAResource](../../../connect/jdbc/reference/sqlserverxaresource-class.md) objeto.|  
|[Iniciar](../../../connect/jdbc/reference/start-method-sqlserverxaresource.md)|Inicia o trabalho em nome de uma ramificação de transação especificada no objeto Xid.|  
  
## <a name="inherited-methods"></a>Métodos herdados  
  
|Classe herdada de:|Métodos|  
|---------------------------|-------------|  
|java.lang.Object|clone, equals, finalize, getClass, hashCode, notify, notifyAll, toString, wait|  
  
## <a name="see-also"></a>Consulte também  
 [Classe SQLServerXAResource](../../../connect/jdbc/reference/sqlserverxaresource-class.md)  
  
  
