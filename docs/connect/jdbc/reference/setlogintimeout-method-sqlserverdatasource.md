---
title: "Método setLoginTimeout (SQLServerDataSource) | Microsoft Docs"
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
apiname: SQLServerDataSource.setLoginTimeout
apilocation: sqljdbc.jar
apitype: Assembly
ms.assetid: b63d1cf4-dc1b-4e35-9a56-50436642eaaf
caps.latest.revision: "11"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 4a65f835792fc342cbbcc3803c9a3be6d0bb9214
ms.sourcegitcommit: 2713f8e7b504101f9298a0706bacd84bf2eaa174
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2017
---
# <a name="setlogintimeout-method-sqlserverdatasource"></a>Método setLoginTimeout (SQLServerDataSource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Define o número de segundos que isso [SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-class.md) objeto aguardará ao tentar estabelecer uma conexão.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
public void setLoginTimeout(int loginTimeout)  
```  
  
#### <a name="parameters"></a>Parâmetros  
 *loginTimeout*  
  
 Um **int** valor que representa o número de segundos de espera. Zero indica que o tempo limite é o padrão do sistema, especificado como 15 segundos por padrão.  
  
## <a name="remarks"></a>Comentários  
 Esse método setLoginTimeout é especificado pelo método setLoginTimeout na interface javax.SQL.  
  
## <a name="see-also"></a>Consulte também  
 [Membros de SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-members.md)   
 [Classe SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
  
