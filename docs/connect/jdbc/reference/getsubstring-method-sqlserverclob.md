---
title: "Método getSubString (SQLServerClob) | Microsoft Docs"
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
apiname: SQLServerClob.getSubString
apilocation: sqljdbc.jar
apitype: Assembly
ms.assetid: bf915590-a883-4403-befa-5b5bb42f34d8
caps.latest.revision: "10"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 7492c21386b833d335cc898d997afdb3e04f3b97
ms.sourcegitcommit: 2713f8e7b504101f9298a0706bacd84bf2eaa174
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2017
---
# <a name="getsubstring-method-sqlserverclob"></a>Método getSubString (SQLServerClob)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Retorna uma cópia da subcadeia de caracteres especificada no CLOB com base na posição inicial fornecida e no número de caracteres a serem copiados.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
public java.lang.String getSubString(long pos,  
                                     int length)  
```  
  
#### <a name="parameters"></a>Parâmetros  
 *POS*  
  
 O primeiro caractere da subcadeia a ser extraído. O primeiro caractere está na posição 1.  
  
 *length*  
  
 O número de caracteres consecutivos a serem copiados.  
  
## <a name="return-value"></a>Valor de retorno  
 Um **cadeia de caracteres** que é a subcadeia de caracteres especificada no CLOB.  
  
## <a name="exceptions"></a>Exceções  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Comentários  
 Esse método getSubString é especificado pelo método getSubString na interface do CLOB.  
  
 A tentativa de obter zero caracteres de um CLOB nulo ou de comprimento zero retorna uma cadeia de caracteres vazia. A tentativa de obter qualquer comprimento de caracteres em qualquer posição que não seja a posição 1 em um CLOB de comprimento zero fará com que uma exceção de posição seja lançada.  
  
## <a name="see-also"></a>Consulte também  
 [Métodos SQLServerClob](../../../connect/jdbc/reference/sqlserverclob-methods.md)   
 [Membros SQLServerClob](../../../connect/jdbc/reference/sqlserverclob-members.md)   
 [Classe SQLServerClob](../../../connect/jdbc/reference/sqlserverclob-class.md)  
  
  
