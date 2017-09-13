---
title: "Criar os arquivos de Conexão de servidor (AccessToSQL) | Microsoft Docs"
ms.prod: sql-non-specified
ms.custom: 
ms.date: 08/17/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- sql-ssma
ms.tgt_pltfrm: 
ms.topic: article
applies_to:
- Azure SQL Database
- SQL Server
ms.assetid: 829153be-aa8e-4162-87e8-69882feecf19
caps.latest.revision: 10
author: Shamikg
ms.author: Shamikg
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 7d5bc198ae3082c1b79a3a64637662968b0748b2
ms.openlocfilehash: 7812e5ad1b6566a3ef477800d8098b23abacdd6a
ms.contentlocale: pt-br
ms.lasthandoff: 08/17/2017

---
# <a name="creating-the-server-connection-files-accesstosql"></a>Criando o servidor de arquivos de conexão (AccessToSQL)
Informações do servidor podem ser especificado na seção de servidores do arquivo de script. Informações do servidor também podem ser especificadas em um arquivo de conexão de servidor separado. O parâmetro de linha de comando para o arquivo de conexão de servidor é `-c <serverconnectionfile>`. Se a mesma id de servidor estiver presente em arquivos de conexão do servidor e o script, a definição de servidor no arquivo de script é considerada.  
  
```xml  
<!--Sample of server connection file commands -->  
<!--Connection to SQL Server-->  
  
<sql-server name="target_3">  
  
  <sql-server-authentication>  
  
    <server value="$TargetServerName$"/>  
  
    <database value="$TargetDB$"/>  
  
    <user-id value="$TargetUserName$"/>  
  
    <password value="$TargetPassword$"/>  
  
    <encrypt value="true"/>  
  
    <trust-server-certificate value="true"/>  
  
  </sql-server-authentication>  
  
</sql-server>  
```  
  
```xml  
<!--Connection to SQL Azure-->  
  
<sql-azure name="target_azure">  
  
  <server value="$TargetAzureServerName$"/>  
  
  <database value="$TargetAzureDB$"/>  
  
  <user-id value="$TargetAzureUserName$"/>  
  
  <password value="$TargetAzurePassword$"/>  
  
</sql-azure>  
```  
  
## <a name="server-connection-file-validation"></a>Validação do arquivo de conexão de servidor  
O usuário facilmente possa validar o arquivo de conexão de servidor no arquivo de definição de esquema **'A2SSConsoleScriptServersSchema.xsd'** disponíveis na pasta 'Esquemas'.  
  
## <a name="next-step"></a>Próxima etapa  
A próxima etapa no operando o console é [executando o Console SSMA &#40; AccessToSQL &#41;](../../ssma/access/executing-the-ssma-console-accesstosql.md)  
  
## <a name="see-also"></a>Consulte também  
[Executar o Console do SSMA (acesso)](http://msdn.microsoft.com/aa1bf665-8dc0-4259-b36f-46ae67197a43)  
  
