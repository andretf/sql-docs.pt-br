---
title: "Método getNString (int) | Microsoft Docs"
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
ms.assetid: 2048bb9f-7d9b-4aaa-b135-c716910cc800
caps.latest.revision: "12"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 393c1b5b0d704d814d40559154a73da4525fc603
ms.sourcegitcommit: 2713f8e7b504101f9298a0706bacd84bf2eaa174
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2017
---
# <a name="getnstring-method-int"></a>Método getNString (int)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Recupera o valor de designado **NCHAR**, **NVARCHAR**, ou **LONGNVARCHAR** parâmetro como uma cadeia de caracteres no Java linguagem de programação.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
public final java.lang.String getNString(int parameterIndex)  
```  
  
#### <a name="parameters"></a>Parâmetros  
 *parameterIndex*  
  
 Um **int** que indica o índice do parâmetro.  
  
## <a name="return-value"></a>Valor de retorno  
 AStringobject.  
  
## <a name="exceptions"></a>Exceções  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Comentários  
 Esse método getNString é especificado pelo método getNString na interface do CallableStatement.  
  
## <a name="see-also"></a>Consulte também  
 [Método getNString &#40; SQLServerCallableStatement &#41;](../../../connect/jdbc/reference/getnstring-method-sqlservercallablestatement.md)   
 [Membros SQLServerCallableStatement](../../../connect/jdbc/reference/sqlservercallablestatement-members.md)  
  
  
