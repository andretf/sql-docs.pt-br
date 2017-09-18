---
title: "Método (SQLServerPreparedStatement) setUnicodeStream | Microsoft Docs"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- SQLServerPreparedStatement.setUnicodeStream
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 0a413e83-e0a4-41f8-9fe0-33ce4d368ee4
caps.latest.revision: 11
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 342eeefd5fa5fc1dddb2687474e83b4beec6ca45
ms.contentlocale: pt-br
ms.lasthandoff: 09/09/2017

---
# <a name="setunicodestream-method-sqlserverpreparedstatement"></a>Método (SQLServerPreparedStatement) setUnicodeStream
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Define o número do parâmetro designado como o fluxo de entrada fornecido, que terá o número de bytes especificado.  
  
> [!NOTE]  
>  Esse método foi substituído na especificação do JDBC e chamá-lo lançará uma exceção "não implementada".  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
public final void setUnicodeStream(int n,  
                                   java.io.InputStream x,  
                                   int length)  
```  
  
#### <a name="parameters"></a>Parâmetros  
 *n*  
  
 Um **int** que indica o número do parâmetro.  
  
 *x*  
  
 Um objeto InputStream.  
  
 *length*  
  
 O número de bytes.  
  
## <a name="exceptions"></a>Exceções  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Comentários  
 Esse método setUnicodeStream é especificado pelo método setUnicodeStream na interface PreparedStatement.  
  
## <a name="see-also"></a>Consulte também  
 [Membros de SQLServerPreparedStatement](../../../connect/jdbc/reference/sqlserverpreparedstatement-members.md)   
 [Classe SQLServerPreparedStatement](../../../connect/jdbc/reference/sqlserverpreparedstatement-class.md)  
  
  