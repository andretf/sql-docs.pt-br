---
title: "Método (SQLServerStatement) setPoolable | Microsoft Docs"
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
ms.assetid: f0f798c8-cafb-4acc-b85d-2e0059c91d92
caps.latest.revision: "5"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 3cb4fd96733a36f6f9f0743fede135327c7d8b5e
ms.sourcegitcommit: 2713f8e7b504101f9298a0706bacd84bf2eaa174
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2017
---
# <a name="setpoolable-method-sqlserverstatement"></a>setPoolable método (SQLServerStatement)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Solicita que uma instrução seja colocada ou não em pool.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
public void setPoolable(boolean poolable) throws SQLException  
```  
  
#### <a name="parameters"></a>Parâmetros  
 *em um pool*  
  
 Se **true**, solicita que a instrução seja colocada em pool. Se **false**, solicita que a instrução não seja agrupado.  
  
## <a name="exceptions"></a>Exceções  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Comentários  
 O valor especificado no *em um pool* parâmetro é uma dica à implementação de pool de instrução que indica se o aplicativo deseja que a instrução seja colocada em pool. O gerenciador de pools de instrução decidirá se usará a dica.  
  
 O valor do pool de uma instrução aplica-se aos caches de instrução internos implementados pelo driver e aos caches de instrução externos implementados por servidores de aplicativos e outros aplicativos.  
  
 Por padrão, um objeto SQLServerStatement não está em um pool quando criado. Objetos SQLServerPreparedStatement e SQLServerCallableStatement estão em um pool quando criado.  
  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md) é gerada se esse método for chamado em uma instrução fechada.  
  
 [isPoolable](../../../connect/jdbc/reference/ispoolable-method-sqlserverstatement.md) retorna um valor que indica se o objeto está em um pool.  
  
## <a name="see-also"></a>Consulte também  
 [Membros SQLServerStatement](../../../connect/jdbc/reference/sqlserverstatement-members.md)   
 [Classe SQLServerStatement](../../../connect/jdbc/reference/sqlserverstatement-class.md)  
  
  
