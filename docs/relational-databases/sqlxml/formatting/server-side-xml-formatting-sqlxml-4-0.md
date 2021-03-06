---
title: "Formatação de XML do lado do servidor (SQLXML 4.0) | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database
ms.service: 
ms.component: sqlxml
ms.reviewer: 
ms.suite: sql
ms.technology:
- dbe-xml
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- FOR XML clause, formatting
- server-side XML formatting
ms.assetid: ae9ea068-0857-4505-a3b2-f53d256b644c
caps.latest.revision: 
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: d10ab42eb2998dc0d39ef59dc77eb6fe24eccdae
ms.sourcegitcommit: 37f0b59e648251be673389fa486b0a984ce22c81
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2018
---
# <a name="server-side-xml-formatting-sqlxml-40"></a>Formatação XML do lado do servidor (SQLXML 4.0)
[!INCLUDE[appliesto-ss-asdb-xxxx-xxx-md](../../../includes/appliesto-ss-asdb-xxxx-xxx-md.md)]
Este tópico fornece informações sobre a formatação de documentos XML no lado do servidor a partir de conjuntos de linhas gerados por consultas executadas com relação a um banco de dados no Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].  
  
 No [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], você pode armazenar e recuperar documentos XML para e de tabelas de banco de dados. Para recuperar um documento XML, use a extensão de consulta FOR XML em uma consulta SELECT.  
  
 Por exemplo, suponha que um aplicativo cliente executa um comando em [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] que consiste no seguinte [!INCLUDE[tsql](../../../includes/tsql-md.md)] consulta:  
  
```  
SELECT FirstName, LastName  
FROM   Person.Contact  
FOR XML AUTO  
```  
  
 O servidor executa a consulta em duas etapas. Primeiro, o servidor executa esta instrução SELECT:  
  
```  
SELECT FirstName, LastName  
FROM   Person.Contact  
```  
  
 O servidor aplica a transformação FOR XML ao conjunto de linhas gerado. O XML resultante é enviado para o cliente como um conjunto de linhas de uma coluna. Nesta documentação, esse processo é chamado de formatação XML do lado do servidor.  
  
 No lado do servidor, você pode especificar os seguintes modos com uma cláusula FOR XML:  
  
-   RAW  
  
-   AUTO  
  
-   EXPLICIT  
  
 Para obter mais informações sobre a cláusula FOR XML, consulte [construindo XML usando FOR XML](../../../relational-databases/xml/for-xml-sql-server.md).  
  
## <a name="see-also"></a>Consulte também  
 [Arquitetura de formatação de XML do lado do cliente e do servidor &#40; SQLXML 4.0 &#41;](../../../relational-databases/sqlxml/formatting/architecture-of-client-side-and-server-side-xml-formatting-sqlxml-4-0.md)   
 [Formatação XML do lado do cliente &#40; SQLXML 4.0 &#41;](../../../relational-databases/sqlxml/formatting/client-side-xml-formatting-sqlxml-4-0.md)   
 [FOR XML &#40;SQL Server&#41;](../../../relational-databases/xml/for-xml-sql-server.md)  
  
  
