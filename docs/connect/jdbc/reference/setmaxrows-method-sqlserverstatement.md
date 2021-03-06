---
title: "Método setMaxRows (SQLServerStatement) | Microsoft Docs"
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
apiname: SQLServerStatement.setMaxRows
apilocation: sqljdbc.jar
apitype: Assembly
ms.assetid: cccc0667-589b-4655-8ea8-14ae8b2eb9dc
caps.latest.revision: "24"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 9b35a8295c8dda7c56ed20d38f47e5b5740ef0fe
ms.sourcegitcommit: 2713f8e7b504101f9298a0706bacd84bf2eaa174
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2017
---
# <a name="setmaxrows-method-sqlserverstatement"></a>Método setMaxRows (SQLServerStatement)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Define o limite para o número máximo de linhas que qualquer [SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md) objeto pode conter como o número fornecido.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
public final void setMaxRows(int max)  
```  
  
#### <a name="parameters"></a>Parâmetros  
 *Max*  
  
 Um **int** que indica o número máximo de linhas ou 0 se não houver nenhum limite.  
  
## <a name="exceptions"></a>Exceções  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Comentários  
 Esse método setMaxRows é especificado pelo método setMaxRows na interface Java.SQL. Statement.  
  
 Esse método setMaxRows não tem nenhum efeito para cursores roláveis dinâmicos. O aplicativo deve usar sintaxe de SQL SELECT TOP N para limitar o número de linhas retornado de conjuntos de resultados potencialmente grandes.  
  
 Quando o método setMaxRows é chamado, o [!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)] executa a instrução SQL SET ROWCOUNT quando executa a consulta do aplicativo. Isso faz com que o driver JDBC limitar o número máximo de linhas afetadas por todos os [!INCLUDE[tsql](../../../includes/tsql_md.md)] instruções executadas por essa consulta, não apenas o número de linhas retornadas pela consulta. Se o aplicativo deve definir um limite no nível superior [SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md) do objeto, ele deve usar sintaxe SQL SELECT TOP N na consulta em vez do método setMaxRows.  
  
 Para obter mais informações sobre a instrução SQL SET ROWCOUNT, consulte o "[SET ROWCOUNT (Transact-SQL)](http://go.microsoft.com/fwlink/?LinkId=139522)" tópico [!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)] Manuais Online.  
  
## <a name="see-also"></a>Consulte também  
 [Membros SQLServerStatement](../../../connect/jdbc/reference/sqlserverstatement-members.md)   
 [Classe SQLServerStatement](../../../connect/jdbc/reference/sqlserverstatement-class.md)  
  
  
