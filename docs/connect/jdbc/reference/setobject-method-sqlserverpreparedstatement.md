---
title: "Método (SQLServerPreparedStatement) setObject | Microsoft Docs"
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
apiname: SQLServerPreparedStatement.setObject
apilocation: sqljdbc.jar
apitype: Assembly
ms.assetid: 93a2b22c-82b4-48c7-a428-369ebe98a372
caps.latest.revision: "15"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: c7085bc90a76c1b4098cd6a0afa3156669985248
ms.sourcegitcommit: 2713f8e7b504101f9298a0706bacd84bf2eaa174
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2017
---
# <a name="setobject-method-sqlserverpreparedstatement"></a>setObject método (SQLServerPreparedStatement)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Define o valor do parâmetro designado usando o objeto fornecido.  
  
 Começando com [!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)] JDBC Driver 3.0, o comportamento desse método é modificado pelo **sendTimeAsDatetime** propriedade de conexão ([definindo as propriedades de Conexão](../../../connect/jdbc/setting-the-connection-properties.md)) e [ Setsendtimeasdatetime](../../../connect/jdbc/reference/setsendtimeasdatetime-method-sqlserverdatasource.md).  
  
 Para obter mais informações, consulte [Java.SQL. time configurando como os valores são enviados para o servidor](../../../connect/jdbc/configuring-how-java-sql-time-values-are-sent-to-the-server.md).  
  
## <a name="overload-list"></a>Lista de sobrecargas  
  
|Nome|Description|  
|----------|-----------------|  
|[setObject (int, java.lang.Object)](../../../connect/jdbc/reference/setobject-method-int-java-lang-object.md)|Define o valor do parâmetro designado usando o objeto fornecido.|  
|[setObject (int, java.lang.Object, int)](../../../connect/jdbc/reference/setobject-method-int-java-lang-object-int.md)|Define o valor do parâmetro designado usando o tipo de objeto e de destino fornecido.|  
|[setObject (int, java.lang.Object, int, int)](../../../connect/jdbc/reference/setobject-method-int-java-lang-object-int-int.md)|Define o valor do parâmetro designado usando o objeto fornecido, o tipo de destino e a escala.|  
  
## <a name="see-also"></a>Consulte também  
 [Membros de SQLServerPreparedStatement](../../../connect/jdbc/reference/sqlserverpreparedstatement-members.md)   
 [Classe SQLServerPreparedStatement](../../../connect/jdbc/reference/sqlserverpreparedstatement-class.md)  
  
  
