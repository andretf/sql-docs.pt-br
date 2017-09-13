---
title: "Permissões de ponto de extremidade GRANT (Transact-SQL) | Microsoft Docs"
ms.custom: 
ms.date: 06/17/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- TSQL
helpviewer_keywords:
- endpoints [SQL Server], permissions
- granting permissions [SQL Server], endpoints
- GRANT statement, endpoints
- permissions [SQL Server], endpoints
ms.assetid: 9eda885c-fc3a-4c9d-8de6-ce07fb35a934
caps.latest.revision: 16
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 6f89febc7d63bcf36c947aacd90337e7f9478c96
ms.contentlocale: pt-br
ms.lasthandoff: 09/01/2017

---
# <a name="grant-endpoint-permissions-transact-sql"></a>Permissões de ponto de extremidade GRANT (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Concede permissões em um ponto de extremidade.  

  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Convenções da sintaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
GRANT permission  [ ,...n ] ON ENDPOINT :: endpoint_name  
        TO < server_principal >  [ ,...n ]  
    [ WITH GRANT OPTION ]  
    [ AS SQL_Server_login ]   
  
<server_principal> ::=   
        SQL_Server_login  
    | SQL_Server_login_from_Windows_login   
    | SQL_Server_login_from_certificate   
    | SQL_Server_login_from_AsymKey  
```  
  
## <a name="arguments"></a>Argumentos  
 *permissão*  
 Especifica uma permissão que pode ser concedida em um ponto de extremidade. Para obter uma lista de permissões, consulte a seção Comentários mais adiante neste tópico.  
  
 NO ponto de EXTREMIDADE **::***endpoint_name*  
 Especifica o ponto de extremidade no qual a permissão está sendo concedida. O qualificador de escopo (**::**) é necessária.  
  
 PARA \<server_principal >  
 Especifica o logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ao qual a permissão está sendo concedida.  
  
 *SQL_Server_login*  
 Especifica o nome de um logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
 *SQL_Server_login_from_Windows_login*  
 Especifica o nome de um logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] criado a partir de um logon do Windows.  
  
 *SQL_Server_login_from_certificate*  
 Especifica o nome de um logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mapeado para um certificado.  
  
 *SQL_Server_login_from_AsymKey*  
 Especifica o nome de um logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mapeado para uma chave assimétrica.  
  
 WITH GRANT OPTION  
 Indica que o principal também terá a capacidade de conceder a permissão especificada a outros principais.  
  
 AS *SQL_Server_login*  
 Especifica o logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] do qual o principal que executa esta consulta deriva seu direito de conceder a permissão.  
  
## <a name="remarks"></a>Comentários  
 Permissões no escopo do servidor podem ser concedidas somente quando o banco de dados atual é **mestre**.  
  
 Informações sobre pontos de extremidade são visíveis no [Endpoints](../../relational-databases/system-catalog-views/sys-endpoints-transact-sql.md) exibição do catálogo. Informações sobre permissões de servidor são visíveis no [server_permissions](../../relational-databases/system-catalog-views/sys-server-permissions-transact-sql.md) exibição de catálogo e obter informações sobre as entidades de servidor é visível no [sys. server_principals](../../relational-databases/system-catalog-views/sys-server-principals-transact-sql.md) exibição do catálogo.  
  
 Um ponto de extremidade é um protegível em nível de servidor. As permissões mais específicas e limitadas que podem ser concedias em um ponto de extremidade são listadas na tabela a seguir, junto com as permissões mais gerais que as incluem implicitamente.  
  
|Permissão de ponto de extremidade|Indicado pela permissão de ponto de extremidade|Implícito na permissão de servidor|  
|-------------------------|------------------------------------|----------------------------------|  
|ALTER|CONTROL|ALTER ANY ENDPOINT|  
|CONNECT|CONTROL|CONTROL SERVER|  
|CONTROL|CONTROL|CONTROL SERVER|  
|TAKE OWNERSHIP|CONTROL|CONTROL SERVER|  
|VIEW DEFINITION|CONTROL|VIEW ANY DEFINITION|  
  
## <a name="permissions"></a>Permissões  
 Requer permissão CONTROL no ponto de extremidade ou a permissão ALTER ANY ENDPOINT no servidor.  
  
## <a name="examples"></a>Exemplos  
  
### <a name="a-granting-view-definition-permission-on-an-endpoint"></a>A. Concedendo a permissão VIEW DEFINITION em um ponto de extremidade  
 O exemplo a seguir concede a permissão `VIEW DEFINITION` no ponto de extremidade `Mirror7` para o logon no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de `ZArifin`.  
  
```  
USE master;  
GRANT VIEW DEFINITION ON ENDPOINT::Mirror7 TO ZArifin;  
GO  
```  
  
### <a name="b-granting-take-ownership-permission-with-the-grant-option"></a>B. Concedendo a permissão TAKE OWNERSHIP com GRANT OPTION  
 O exemplo a seguir concede a permissão `TAKE OWNERSHIP` no ponto de extremidade `Shipping83` para o usuário do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `PKomosinski` com `GRANT OPTION`.  
  
```  
USE master;  
GRANT TAKE OWNERSHIP ON ENDPOINT::Shipping83 TO PKomosinski   
    WITH GRANT OPTION;  
GO  
```  
  
## <a name="see-also"></a>Consulte também  
 [Negar permissões de ponto de extremidade &#40; Transact-SQL &#41;](../../t-sql/statements/deny-endpoint-permissions-transact-sql.md)   
 [REVOGAR permissões de ponto de extremidade &#40; Transact-SQL &#41;](../../t-sql/statements/revoke-endpoint-permissions-transact-sql.md)   
 [CREATE ENDPOINT &#40;Transact-SQL&#41;](../../t-sql/statements/create-endpoint-transact-sql.md)   
 [Exibições do catálogo de pontos de extremidade &#40; Transact-SQL &#41;](../../relational-databases/system-catalog-views/endpoints-catalog-views-transact-sql.md)   
 [sys. Endpoints &#40; Transact-SQL &#41;](../../relational-databases/system-catalog-views/sys-endpoints-transact-sql.md)   
 [Permissões &#40;Mecanismo de Banco de Dados&#41;](../../relational-databases/security/permissions-database-engine.md)   
 [Entidades &#40;Mecanismo de Banco de Dados&#41;](../../relational-databases/security/authentication-access/principals-database-engine.md)  
  
  
