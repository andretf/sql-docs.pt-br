---
title: "Método executeUpdate (Java, Java) | Microsoft Docs"
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
apiname: SQLServerStatement.executeUpdate (java.lang.String[])
apilocation: sqljdbc.jar
apitype: Assembly
ms.assetid: 2f44a689-65c8-4c94-9574-e9c08ea7918e
caps.latest.revision: "13"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: b81258e1175ae7aa752556145dbaa2573bb15d8d
ms.sourcegitcommit: 2713f8e7b504101f9298a0706bacd84bf2eaa174
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2017
---
# <a name="executeupdate-method-javalangstring-javalangstring"></a>Método executeUpdate (Java, Java)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Executa a instrução SQL fornecida e sinaliza [!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)] que as chaves geradas automaticamente indicadas na matriz fornecida devem ser disponibilizadas para recuperação.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
public final int executeUpdate(java.lang.String sql,  
                               java.lang.String[] columnNames)  
```  
  
#### <a name="parameters"></a>Parâmetros  
 *SQL*  
  
 Um **cadeia de caracteres** que contém uma instrução SQL.  
  
 *columnNames*  
  
 Uma matriz do tipo **cadeia de caracteres** que indica quais nomes de coluna das chaves geradas automaticamente devem ser disponibilizados.  
  
## <a name="return-value"></a>Valor de retorno  
 Um **int** que indica o número de linhas afetadas, 0 se usando uma instrução DDL.  
  
## <a name="exceptions"></a>Exceções  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Comentários  
 Esse método executeUpdate é especificado pelo método executeUpdate na interface Java.SQL. Statement.  
  
 Se executar um procedimento armazenado resulta em uma contagem de atualização que é maior do que um, ou que gera mais de um conjunto de resultados, use o [executar](../../../connect/jdbc/reference/execute-method-sqlserverstatement.md) método para executar o procedimento armazenado.  
  
## <a name="see-also"></a>Consulte também  
 [Método executeUpdate &#40; SQLServerStatement &#41;](../../../connect/jdbc/reference/executeupdate-method-sqlserverstatement.md)   
 [Membros SQLServerStatement](../../../connect/jdbc/reference/sqlserverstatement-members.md)   
 [Classe SQLServerStatement](../../../connect/jdbc/reference/sqlserverstatement-class.md)  
  
  
