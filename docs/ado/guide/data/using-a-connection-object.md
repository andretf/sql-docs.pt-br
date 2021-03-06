---
title: "Usando um objeto de Conexão | Microsoft Docs"
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: ado
ms.technology:
- drivers
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: sql
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- connections [ADO]
ms.assetid: 4b34f971-5699-43e7-9b15-137d334fa66e
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: e27a3da94c2699e2281d331e6aa1fff4b9a62001
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2018
---
# <a name="using-a-connection-object"></a>Usando um objeto de Conexão
Antes de abrir um **Conexão** do objeto, você deve definir certas informações sobre a fonte de dados e o tipo de conexão. A maioria dessas informações é mantido pelo *ConnectionString* parâmetro do [método Open](../../../ado/reference/ado-api/open-method-ado-connection.md) no **Conexão** objeto, ou o [ConnectionString propriedade](../../../ado/reference/ado-api/connectionstring-property-ado.md) no **Conexão** objeto. Uma cadeia de caracteres de conexão consiste em uma lista de pares de valor do argumento separados por ponto e vírgula, com os valores entre aspas simples. Por exemplo:  
  
```  
Dim sConn As String  
sConn = "Provider='SQLOLEDB';Data Source='MySqlServer';" & _  
             "Initial Catalog='Northwind';Integrated Security='SSPI';"  
```  
  
> [!NOTE]
>  Você também pode especificar um nome de fonte de dados ODBC (DSN) ou um arquivo UDL (Data Link) em uma cadeia de caracteres de conexão. Para obter mais informações sobre DSNs, consulte [gerenciar fontes de dados](../../../odbc/admin/managing-data-sources.md) na referência do programador de ODBC. Para obter mais informações sobre UDLs, consulte [visão geral de API de Link de dados](http://msdn.microsoft.com/en-us/95c180ea-bd4f-4dca-b95a-576afd135bbc) de referência OLE DB do programador.  
  
 Normalmente, você estabelece uma conexão chamando o **Connection.Open** método com um número apropriado um *cadeia de caracteres de conexão* como seu parâmetro. Um exemplo é mostrado no seguinte trecho de código do Visual Basic:  
  
```  
Dim oConn As ADODB.Connection  
Dim oRs As ADODB.Recordset  
Dim sConn As String  
Dim sSQL as String  
  
' Open a connection.  
Set oConn = New ADODB.Connection  
.Open   
  
' Make a query over the connection.  
sSQL = "SELECT ProductID, ProductName, CategoryID, UnitPrice " & _  
             "FROM Products"  
Set oRs = New ADODB.Recordset  
oRs.Open sSQL, , adOpenStatic, adLockBatchOptimistic, adCmdText  
  
MsgBox oRs.RecordCount  
  
' Close the connection.  
oConn.Close  
Set oConn = Nothing  
  
```  
  
 Aqui **oRs.Open** leva um **Conexão** objeto (*oConn*) variável como o valor do seu *ActiveConnection* parâmetro. Além disso, o **Connection.CursorLocation** propriedade assume o valor padrão de **adUseServer**. Compare isso para o [HelloData](../../../ado/guide/data/hellodata-a-simple-ado-application.md) exemplo na seção anterior. A instrução a seguir pode resultar em erros de tempo de execução.  
  
```  
oRs.MarshalOptions = adMarshalModifiedOnly  
' Disconnect the Recordset.  
Set oRs.ActiveConnection = Nothing  
```
