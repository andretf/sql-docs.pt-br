---
title: "Método (Java) getBytes | Microsoft Docs"
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
apiname: SQLServerCallableStatement.getBytes (java.lang.String)
apilocation: sqljdbc.jar
apitype: Assembly
ms.assetid: 4d0dac7f-7f39-47a2-953e-80ab03688d82
caps.latest.revision: "12"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: aa5647c000c2d3370f6e98d845044eb5ee067fcf
ms.sourcegitcommit: 2713f8e7b504101f9298a0706bacd84bf2eaa174
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2017
---
# <a name="getbytes-method-javalangstring"></a>Método getBytes (java.lang.String)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Recupera o valor do parâmetro designado como uma matriz de valores bytes, considerando o nome do parâmetro.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
public byte[] getBytes(java.lang.String sCol)  
```  
  
#### <a name="parameters"></a>Parâmetros  
 *sCol*  
  
 Um **cadeia de caracteres** que contém o nome do parâmetro.  
  
## <a name="return-value"></a>Valor de retorno  
 Uma matriz de **bytes** valores.  
  
## <a name="exceptions"></a>Exceções  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Comentários  
 Em uma versão anterior do [!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)], você pode usar Sqlservercallablestatement para converter valores entre matrizes de bytes e [!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)] tipo de dados **data**, **tempo**,  **datetime2**, ou **datetimeoffset**. Agora, ao usar esse método com esses tipos de dados, ocorrerá uma exceção indicando que não há suporte para a conversão.  
  
 Esse método getBytes é especificado pelo método getBytes na interface do CallableStatement.  
  
## <a name="see-also"></a>Consulte também  
 [Método getBytes &#40; SQLServerCallableStatement &#41;](../../../connect/jdbc/reference/getbytes-method-sqlservercallablestatement.md)   
 [Membros SQLServerCallableStatement](../../../connect/jdbc/reference/sqlservercallablestatement-members.md)   
 [Classe SQLServerCallableStatement](../../../connect/jdbc/reference/sqlservercallablestatement-class.md)  
  
  
