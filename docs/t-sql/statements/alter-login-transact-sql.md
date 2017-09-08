---
title: ALTER LOGIN (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 05/01/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- ALTER_LOGIN_TSQL
- ALTER LOGIN
dev_langs:
- TSQL
helpviewer_keywords:
- ALTER LOGIN statement
- change password
- mapping logins [SQL Server]
- logins [SQL Server], modifying
- passwords [SQL Server], modifying
- names [SQL Server], logins
- modifying login accounts
ms.assetid: e247b84e-c99e-4af8-8b50-57586e1cb1c5
caps.latest.revision: 68
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 9dd47cb63c56dbbfb5f31ea3f7b2c8d4f45e9d73
ms.contentlocale: pt-br
ms.lasthandoff: 09/01/2017

---
# <a name="alter-login-transact-sql"></a>ALTER LOGIN (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all_md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  Altera as propriedades de uma conta de logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Convenções da sintaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
-- Syntax for SQL Server  
  
ALTER LOGIN login_name   
    {   
    <status_option>   
    | WITH <set_option> [ ,... ]  
    | <cryptographic_credential_option>  
    }   
[;]  
  
<status_option> ::=  
        ENABLE | DISABLE  
  
<set_option> ::=              
    PASSWORD = 'password' | hashed_password HASHED  
    [   
      OLD_PASSWORD = 'oldpassword'  
      | <password_option> [<password_option> ]   
    ]  
    | DEFAULT_DATABASE = database  
    | DEFAULT_LANGUAGE = language  
    | NAME = login_name  
    | CHECK_POLICY = { ON | OFF }  
    | CHECK_EXPIRATION = { ON | OFF }  
    | CREDENTIAL = credential_name  
    | NO CREDENTIAL  
  
<password_option> ::=   
    MUST_CHANGE | UNLOCK  
  
<cryptographic_credentials_option> ::=   
    ADD CREDENTIAL credential_name  
  | DROP CREDENTIAL credential_name  
```  
  
```  
-- Syntax for Azure SQL Database  
  
ALTER LOGIN login_name   
  {   
      <status_option>   
    | WITH <set_option> [ ,.. .n ]   
  }   
[;]  
  
<status_option> ::=  
    ENABLE | DISABLE  
  
<set_option> ::=   
    PASSWORD ='password'   
    [  
      OLD_PASSWORD ='oldpassword'  
    ]   
    | NAME = login_name  
```  
  
```  
-- Syntax for Azure SQL Data Warehouse and Parallel Data Warehouse  
  
ALTER LOGIN login_name   
    {   
    <status_option>   
    | WITH <set_option> [ ,... ]  
    }   
  
<status_option> ::=ENABLE | DISABLE  
  
<set_option> ::=              
    PASSWORD ='password'   
    [   
      OLD_PASSWORD ='oldpassword'  
      | <password_option> [<password_option> ]   
    ]  
    | NAME = login_name  
    | CHECK_POLICY = { ON | OFF }  
    | CHECK_EXPIRATION = { ON | OFF }   
      
<password_option> ::=   
    MUST_CHANGE | UNLOCK  
```  
  
## <a name="arguments"></a>Argumentos  
 *login_name*  
 Especifica o nome do logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que está sendo alterado. Logons no domínio devem ser colocados entre colchetes no formato [domínio\usuário].  
  
 ENABLE | DISABLE  
 Habilita ou desabilita este logon. Desabilitar um logon não afeta o comportamento de logons que já estão conectados. (Use o `KILL` instrução encerrar as conexões existentes.) Logons desabilitados retêm suas permissões e ainda podem ser representados.  
  
 SENHA **='***senha***'**  
 Aplica-se somente a logons do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Especifica a senha do logon que está sendo alterado. As senhas diferenciam maiúsculas de minúsculas.  
  
 Continuamente as conexões ativas para banco de dados SQL exigem autorização (executada pelo mecanismo de banco de dados) pelo menos a cada 10 horas. O mecanismo de banco de dados de tentativas de autorização usando a senha originalmente enviada e nenhuma entrada do usuário é necessária. Por motivos de desempenho, quando uma senha é redefinida no banco de dados SQL, a conexão não será autenticado novamente, mesmo se a conexão for redefinida devido ao pooling de conexão. Isso é diferente do comportamento do SQL Server no local. Se a senha foi alterada desde que a conexão foi autorizado inicialmente, a conexão deve ser terminada e uma nova conexão feita usando a nova senha. Um usuário com a permissão KILL DATABASE CONNECTION explicitamente pode encerrar uma conexão ao banco de dados SQL usando o comando KILL. Para obter mais informações, consulte [KILL &#40; Transact-SQL &#41; ](../../t-sql/language-elements/kill-transact-sql.md).  
  
 SENHA  **=**  *hashed_password*  
 **Aplica-se a**: do [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] ao [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].  
  
 Só se aplica à palavra-chave HASHED. Especifica o valor com hash da senha para o logon que está sendo criado.  
  
> [!IMPORTANT]  
>  Quando um logon (ou um usuário de banco de dados independente) se conecta e é autenticado, a conexão armazena em cache as informações de identidade sobre o logon. Para um logon de Autenticação do Windows, isso inclui informações sobre a associação em grupos do Windows. A identidade do logon permanece autenticada desde que a conexão seja mantida. Para forçar alterações na identidade, como uma redefinição de senha ou alteração na associação de grupo do Windows, o logon deve fazer logoff da autoridade de autenticação (Windows ou [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]) e fazer logon novamente. Um membro da função de servidor fixa ou **sysadmin** ou qualquer logon com a permissão **ALTER ANY CONNECTION** pode usar o comando **KILL** para terminar uma conexão e forçar um logon para reconectar. [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] pode reutilizar informações de conexão ao abrir várias conexões para as janelas do Pesquisador de Objetos e do Editor de Consultas. Feche todas as conexões para forçar a reconexão.  
  
 HASHED  
   
**Aplica-se a**: do [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] ao [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].  
  
 Aplica-se a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] somente de logons. Especifica que a senha digitada depois do argumento PASSWORD já esteja com hash. Se esta opção não for selecionada, a senha terá hash antes de ser armazenada no banco de dados. Essa opção deve ser usada somente para sincronização de logon entre dois servidores. Não use a opção HASHED para alterar senhas rotineiramente.  
  
 OLD_PASSWORD **='***senha_atual***'**  
 Aplica-se somente a logons do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. A senha atual do logon a que uma senha nova será atribuída. As senhas diferenciam maiúsculas de minúsculas.  
  
 MUST_CHANGE  
 **Aplica-se a**: do [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] ao [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].  
  
 Aplica-se somente a logons do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Se esta opção estiver incluída, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] solicitará uma senha atualizada quando o logon alterado for usado pela primeira vez.  
  
 DEFAULT_DATABASE  **=**  *banco de dados*  
**Aplica-se a**: do [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] ao [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].  
  
 Especifica um banco de dados padrão a ser atribuído ao logon.  
  
 DEFAULT_LANGUAGE  **=**  *idioma*  
 
 **Aplica-se a**: do [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] ao [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].  
  
 Especifica um idioma padrão a ser atribuído ao logon. O idioma padrão para todos os logons de banco de dados SQL está em inglês e não pode ser alterado. O idioma padrão do `sa` logon [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no Linux, é o inglês, mas pode ser alterada.  
  
 NOME = *login_name*  
 O nome novo do logon que está sendo renomeado. Se este for um logon do Windows, o SID do administrador do Windows correspondente ao novo nome deverá corresponder ao SID associado ao logon no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. O novo nome de um [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] logon não pode conter um caractere de barra invertida (\\).  
  
 CHECK_EXPIRATION = {ON | **OFF** }  
 **Aplica-se a**: do [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] ao [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].  
  
 Aplica-se somente a logons do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Especifica se a política de expiração de senha deve ser aplicada neste logon. O valor padrão é OFF.  
  
 CHECK_POLICY  **=**  { **ON** | OFF}  
 **Aplica-se a**: do [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] ao [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].  
  
 Aplica-se somente a logons do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Especifica se as políticas de senha do Windows do computador em que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] está em execução devem ser aplicadas neste logon. O valor padrão é ON.  
  
 CREDENCIAL = *credential_name*  
 **Aplica-se a**: do [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] ao [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].  
  
 O nome de uma credencial a ser mapeada para um logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. A credencial já deve existir no servidor. Para obter mais informações, consulte [credenciais &#40; mecanismo de banco de dados &#41;](../../relational-databases/security/authentication-access/credentials-database-engine.md). Uma credencial não pode ser mapeada para o logon de sa.  
  
 NO CREDENTIAL  
 **Aplica-se a**: do [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] ao [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].  
  
 Remove qualquer mapeamento existente do logon para uma credencial de servidor. Para obter mais informações, consulte [credenciais &#40; mecanismo de banco de dados &#41;](../../relational-databases/security/authentication-access/credentials-database-engine.md).  
  
 UNLOCK  
 **Aplica-se a**: do [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] ao [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].  
  
 Aplica-se somente a logons do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Especifica que um logon bloqueado deve ser desbloqueado.  
  
 ADD CREDENTIAL  
 **Aplica-se a**: do [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] ao [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].  
  
 Adiciona uma credencial de provedor EKM (gerenciamento de chave extensível) ao logon. Para obter mais informações, consulte [gerenciamento extensível de chaves &#40; EKM &#41; ](../../relational-databases/security/encryption/extensible-key-management-ekm.md).  
  
 DROP CREDENTIAL  
 **Aplica-se a**: do [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] ao [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].  
  
Remove uma credencial do provedor de gerenciamento de chave extensível (EKM) do logon. Para obter mais informações, consulte [gerenciamento extensível de chaves &#40; EKM &#41; ](../../relational-databases/security/encryption/extensible-key-management-ekm.md).  
  
## <a name="remarks"></a>Comentários  
 Quando CHECK_POLICY estiver definido como ON, o argumento HASHED não poderá ser usado.  
  
 Quando CHECK_POLICY for alterado para ON, o seguinte comportamento ocorrerá:  
  
-   O histórico de senhas é inicializado com o valor do hash da senha atual.  
  
 Quando CHECK_POLICY for alterado para OFF, o seguinte comportamento ocorrerá:  
  
-   CHECK_EXPIRATION também será definido como OFF.  
  
-   O histórico de senhas será apagado.  
  
-   O valor de *lockout_time* é redefinido.  
  
Se MUST_CHANGE for especificado, CHECK_EXPIRATION e CHECK_POLICY deverão ser definidos como ON. Caso contrário, a instrução falhará.  
  
Se CHECK_POLICY for definido como OFF, CHECK_EXPIRATION não poderá ser definido como ON. Uma instrução ALTER LOGON com essa combinação de opções falhará.  
  
Você não pode usar ALTER_LOGIN com o argumento DISABLE para negar acesso a um grupo do Windows. Por exemplo, ALTER_LOGIN [*domain\group*] DISABLE retornará a seguinte mensagem de erro:  
  
 “Msg 15151, Nível 16, Estado 1, Linha 1  
  
 "Não é possível alterar o logon '*Domain\Group*', porque ele não existe ou você não tem permissão."  
  
 Isso ocorre por design.  
  
Em [!INCLUDE[ssSDS](../../includes/sssds-md.md)], dados de logon necessárias para autenticar uma conexão e as regras de firewall de nível de servidor são armazenados em cache temporariamente em cada banco de dados. Esse cache é atualizado periodicamente. Para forçar uma atualização do cache de autenticação e certifique-se de que um banco de dados tem a versão mais recente da tabela de logons, execute [DBCC FLUSHAUTHCACHE &#40; Transact-SQL &#41; ](../../t-sql/database-console-commands/dbcc-flushauthcache-transact-sql.md).  
  
## <a name="permissions"></a>Permissões  
 Requer a permissão ALTER ANY LOGIN.  
  
 Se a opção CREDENTIAL for usada, também será necessária a permissão ALTER ANY CREDENTIAL.  
  
 Se o logon que está sendo alterado for um membro do **sysadmin** função fixa de servidor ou um usuário autorizado da permissão CONTROL SERVER, também exige permissão CONTROL SERVER ao fazer as seguintes alterações:  
  
-   Redefinição de senha sem fornecimento da senha antiga.  
  
-   Ativação de MUST_CHANGE, CHECK_POLICY ou CHECK_EXPIRATION.  
  
-   Alteração do nome de logon.  
  
-   Habilitação ou desabilitação do logon.  
  
-   Mapeamento do logon para uma credencial diferente.  
  
 Um administrador pode alterar a senha, o idioma padrão e o banco de dados padrão do seu próprio logon.  
  
## <a name="examples"></a>Exemplos  
  
### <a name="a-enabling-a-disabled-login"></a>A. Habilitando um logon desabilitado  
 O exemplo seguinte ativa o logon `Mary5`.  
  
```tsql  
ALTER LOGIN Mary5 ENABLE;  
```  
  
### <a name="b-changing-the-password-of-a-login"></a>B. Alterando a senha de um logon  
 O exemplo seguinte altera a senha de logon `Mary5` para uma senha forte.  
  
```tsql  
ALTER LOGIN Mary5 WITH PASSWORD = '<enterStrongPasswordHere>';  
```  
  
### <a name="c-changing-the-name-of-a-login"></a>C. Alterando o nome de um logon  
 O exemplo seguinte altera o nome de logon `Mary5` para `John2`.  
  
```tsql  
ALTER LOGIN Mary5 WITH NAME = John2;  
```  
  
### <a name="d-mapping-a-login-to-a-credential"></a>D. Mapeando um logon para uma credencial  
 O exemplo seguinte mapeia o logon `John2` para a credencial `Custodian04`.  
  
```tsql  
ALTER LOGIN John2 WITH CREDENTIAL = Custodian04;  
```  
  
### <a name="e-mapping-a-login-to-an-extensible-key-management-credential"></a>E. Mapeando um logon para uma credencial de Gerenciamento Extensível de Chaves  
 O exemplo seguinte mapeia o logon `Mary5` para a credencial de EKM `EKMProvider1`.  
  
 
**Aplica-se a**: do [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] ao [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].  
  
```tsql  
ALTER LOGIN Mary5  
ADD CREDENTIAL EKMProvider1;  
GO  
```  
  
### <a name="f-unlocking-a-login"></a>F. Desbloqueando um logon  
 Para desbloquear um logon no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], execute a seguinte instrução, substituindo **** pela senha da conta desejada.  
  
  
```tsql  
ALTER LOGIN [Mary5] WITH PASSWORD = '****' UNLOCK ;  

GO  
```  
  
 Para desbloquear um logon sem alterar a senha, desative a política de verificação e ative-a novamente.  
  
```tsql  
ALTER LOGIN [Mary5] WITH CHECK_POLICY = OFF;  
ALTER LOGIN [Mary5] WITH CHECK_POLICY = ON;  
GO  
```  
  
### <a name="g-changing-the-password-of-a-login-using-hashed"></a>G. Alterando a senha de um logon usando HASHED  
 O exemplo seguinte altera a senha do logon `TestUser` para um valor em que o hash já foi aplicado.  
  
**Aplica-se a**: do [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] ao [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].  
  
```tsql  
ALTER LOGIN TestUser WITH   
PASSWORD = 0x01000CF35567C60BFB41EBDE4CF700A985A13D773D6B45B90900 HASHED ;  
GO  
```  
  
 
  
## <a name="see-also"></a>Consulte também  
 [Credenciais &#40; mecanismo de banco de dados &#41;](../../relational-databases/security/authentication-access/credentials-database-engine.md)   
 [CREATE LOGIN &#40;Transact-SQL&#41;](../../t-sql/statements/create-login-transact-sql.md)   
 [Remover logon &#40; Transact-SQL &#41;](../../t-sql/statements/drop-login-transact-sql.md)   
 [CREATE CREDENTIAL &#40;Transact-SQL&#41;](../../t-sql/statements/create-credential-transact-sql.md)   
 [EVENTDATA &#40;Transact-SQL&#41;](../../t-sql/functions/eventdata-transact-sql.md)   
 [Gerenciamento Extensível de Chaves &#40;EKM&#41;](../../relational-databases/security/encryption/extensible-key-management-ekm.md)  
  
  


