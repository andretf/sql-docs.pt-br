---
title: ALTER CREDENTIAL (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 08/19/2015
ms.prod: sql-non-specified
ms.prod_service: sql-database
ms.service: 
ms.component: t-sql|statements
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- ALTER CREDENTIAL
- ALTER_CREDENTIAL_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- passwords [SQL Server], credentials
- credentials [SQL Server], ALTER CREDENTIAL statement
- modifying credentials
- authentication [SQL Server], credentials
- ALTER CREDENTIAL statement
ms.assetid: b08899a6-c09e-4af4-91aa-a978ada79264
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: f939a257a427007e4b0a101a933aafbff9e50546
ms.sourcegitcommit: 3ed9be04cc7fb9ab1a9ec230c298ad2932acc71b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/17/2018
---
# <a name="alter-credential-transact-sql"></a>ALTER CREDENTIAL (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdbmi-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdbmi-xxxx-xxx-md.md)]

  Altera as propriedades de uma credencial.  

[!INCLUDE[ssMIlimitation](../../includes/sql-db-mi-limitation.md)]

 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Convenções da sintaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
ALTER CREDENTIAL credential_name WITH IDENTITY = 'identity_name'  
    [ , SECRET = 'secret' ]  
```  
  
## <a name="arguments"></a>Argumentos  
 *credential_name*  
 Especifica o nome da credencial que está sendo alterada.  
  
 IDENTITY **='***identity_name***'**  
 Especifica o nome da conta a ser usada ao conectar o servidor externamente.  
  
 SECRET **='***secret***'**  
 Especifica o segredo necessário para a autenticação de saída. *secret* é opcional.  
  
## <a name="remarks"></a>Remarks  
 Quando uma credencial é alterada, os valores de *identity_name* e *secret* são redefinidos. Se o argumento SECRET opcional não for especificado, o valor do segredo armazenado será definido como NULL.  
  
 O segredo é criptografado com a chave mestra de serviço. Se a chave mestra de serviço for gerada novamente, o segredo será criptografado usando a nova chave mestra de serviço.  
  
 As informações sobre as credenciais são visíveis na exibição do catálogo **sys.credentials**.  
  
## <a name="permissions"></a>Permissões  
 Requer a permissão ALTER ANY CREDENTIAL. Se a credencial for uma credencial do sistema, será necessária a permissão CONTROL SERVER.  
  
## <a name="examples"></a>Exemplos  
  
### <a name="a-changing-the-password-of-a-credential"></a>A. Alterando a senha de uma credencial  
 O exemplo a seguir altera o segredo armazenado em uma credencial chamada `Saddles`. A credencial contém o logon do Windows `RettigB` e sua senha. A nova senha é adicionada à credencial que usa a cláusula SECRET.  
  
```  
ALTER CREDENTIAL Saddles WITH IDENTITY = 'RettigB',   
    SECRET = 'sdrlk8$40-dksli87nNN8';  
GO  
```  
  
### <a name="b-removing-the-password-from-a-credential"></a>B. Removendo a senha de uma credencial  
 O exemplo a seguir remove a senha de uma credencial chamada `Frames`. A credencial contém o logon do Windows `Aboulrus8` e uma senha. Depois que a instrução for executada, a credencial terá uma senha NULL porque a opção SECRET não é especificada.  
  
```  
ALTER CREDENTIAL Frames WITH IDENTITY = 'Aboulrus8';  
GO  
```  
  
## <a name="see-also"></a>Consulte Também  
 [Credenciais &#40;Mecanismo de Banco de Dados&#41;](../../relational-databases/security/authentication-access/credentials-database-engine.md)   
 [CREATE CREDENTIAL &#40;Transact-SQL&#41;](../../t-sql/statements/create-credential-transact-sql.md)   
 [DROP CREDENTIAL &#40;Transact-SQL&#41;](../../t-sql/statements/drop-credential-transact-sql.md)   
 [ALTER DATABASE SCOPED CREDENTIAL &#40;Transact-SQL&#41;](../../t-sql/statements/alter-database-scoped-credential-transact-sql.md)   
 [CREATE LOGIN &#40;Transact-SQL&#41;](../../t-sql/statements/create-login-transact-sql.md)   
 [sys.credentials &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-credentials-transact-sql.md)  
  
  
