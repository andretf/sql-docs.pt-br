---
title: "Método getMaxBinaryLiteralLength (SQLServerDatabaseMetaData) | Microsoft Docs"
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
apiname: SQLServerDatabaseMetaData.getMaxBinaryLiteralLength
apilocation: sqljdbc.jar
apitype: Assembly
ms.assetid: 42e49ff9-8072-44e4-ad75-c864c3a4ad8c
caps.latest.revision: "7"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 330ac853619806c160f433d6212bc59495ae6e6e
ms.sourcegitcommit: 2713f8e7b504101f9298a0706bacd84bf2eaa174
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2017
---
# <a name="getmaxbinaryliterallength-method-sqlserverdatabasemetadata"></a>Método getMaxBinaryLiteralLength (SQLServerDatabaseMetaData)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Recupera o número máximo de caracteres hexadecimais que esse banco de dados permite em um literal binário embutido.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
public int getMaxBinaryLiteralLength()  
```  
  
## <a name="return-value"></a>Valor de retorno  
 Um **int** que indica o número máximo de caracteres hexadecimais.  
  
## <a name="exceptions"></a>Exceções  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Comentários  
 Esse método getMaxBinaryLiteralLength é especificado pelo método getMaxBinaryLiteralLength na interface DatabaseMetadata.  
  
## <a name="see-also"></a>Consulte também  
 [Métodos SQLServerDatabaseMetaData](../../../connect/jdbc/reference/sqlserverdatabasemetadata-methods.md)   
 [Membros de SQLServerDatabaseMetaData](../../../connect/jdbc/reference/sqlserverdatabasemetadata-members.md)   
 [Classe SQLServerDatabaseMetaData](../../../connect/jdbc/reference/sqlserverdatabasemetadata-class.md)  
  
  
