---
title: "Método refreshRow (SQLServerResultSet) | Microsoft Docs"
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
apiname: SQLServerResultSet.refreshRow
apilocation: sqljdbc.jar
apitype: Assembly
ms.assetid: 048fe245-157f-4fd8-be75-ce54b83e02b3
caps.latest.revision: "11"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 5f1a7c8a4a5381291d21f35adba178f05bc83f3f
ms.sourcegitcommit: 2713f8e7b504101f9298a0706bacd84bf2eaa174
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2017
---
# <a name="refreshrow-method-sqlserverresultset"></a>Método refreshRow (SQLServerResultSet)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Atualiza a linha atual com seu valor mais recente no banco de dados.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
public void refreshRow()  
```  
  
## <a name="exceptions"></a>Exceções  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Comentários  
 Esse método refreshRow é especificado pelo método refreshRow na interface Java.SQL. resultset.  
  
 Esse método não pode ser chamado quando o cursor estiver na linha de inserção.  
  
 Esse método fornece uma maneira de um aplicativo informar explicitamente ao driver JDBC que as linhas do banco de dados devem ser buscadas novamente. Um aplicativo pode precisar chamar este método quando o [!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)] está armazenando em cache ou pré-busca o valor mais recente de uma linha do banco de dados. O driver JDBC poderá realmente atualizar várias linhas ao mesmo tempo se o tamanho da busca for maior que um.  
  
 É feita pré-busca de todos os valores dependendo do nível de isolamento da transação e da sensibilidade do cursor. Se esse método é chamado depois de chamar um método updater, mas antes de chamar o [updateRow](../../../connect/jdbc/reference/updaterow-method-sqlserverresultset.md) método, as atualizações feitas na linha são perdidas. Chamar este método com frequência provavelmente reduzirá o desempenho.  
  
## <a name="see-also"></a>Consulte também  
 [Membros de SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-members.md)   
 [Classe SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md)  
  
  
