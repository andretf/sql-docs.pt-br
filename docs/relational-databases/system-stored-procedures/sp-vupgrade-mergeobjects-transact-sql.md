---
title: sp_vupgrade_mergeobjects (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-stored-procedures
ms.reviewer: 
ms.suite: sql
ms.technology:
- replication
ms.tgt_pltfrm: 
ms.topic: language-reference
applies_to:
- SQL Server
f1_keywords:
- sp_vupgrade_mergeobjects
- sp_vupgrade_mergeobjects_TSQL
helpviewer_keywords:
- sp_vupgrade_mergeobjects
ms.assetid: 73257c2e-cc4c-48e7-9d66-7ef045bdd4f5
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 83c761ec8e22321e1d46a3b9aacaf5c619c45599
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="spvupgrademergeobjects-transact-sql"></a>sp_vupgrade_mergeobjects (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Regenera gatilhos específicos de artigo, procedimentos armazenados e exibições usadas para controlar e aplicar alterações de dados em replicação de mesclagem. Execute esse procedimento nas seguintes situações:  
  
-   Se um objeto exigido pela replicação for descartado acidentalmente.  
  
-   Se você aplicar uma atualização, como um hotfix, que requer modificação de um ou mais objetos de replicação. Execute o procedimento em cada nó depois de aplicar a atualização.  
  
 A execução desse procedimento armazenado não requer reinicialização da assinatura. Esse procedimento não será necessário se você instalar um pacote de serviço ou atualizar para uma nova  versão do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Convenções da sintaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
sp_vupgrade_mergeobjects [ [@login = ] 'login' ]  
    [ , [ @password = ] 'password' ]  
    [ , [ @security_mode = ] security_mode ]  
```  
  
## <a name="arguments"></a>Argumentos  
 [  **@login=**] **'***login***'**  
 É o logon do administrador do sistema a ser usado ao criar novos objetos do sistema no banco de dados de distribuição. *logon* é **sysname**, com um padrão NULL. Esse parâmetro não será necessário se *security_mode* é definido como **1**, que é a autenticação do Windows.  
  
 [  **@password=**] **'***senha***'**  
 É a senha do administrador do sistema a ser usada ao criar novos objetos do sistema no banco de dados de distribuição. *senha* é **sysname**, com um padrão de **'** (cadeia de caracteres vazia). Esse parâmetro não será necessário se *security_mode* é definido como **1**, que é a autenticação do Windows.  
  
 [  **@security_mode=**] **'***security_mode***'**  
 É o modo de segurança do logon a ser usado ao criar novos objetos do sistema no banco de dados de distribuição. *security_mode* é **bit** com um valor padrão de **1**. Se **0**, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] autenticação será usada. Se **1**, a autenticação do Windows será usada. [!INCLUDE[ssNoteWinAuthentication](../../includes/ssnotewinauthentication-md.md)]  
  
## <a name="return-code-values"></a>Valores do código de retorno  
 **0** (êxito) ou **1** (falha)  
  
## <a name="remarks"></a>Comentários  
 **sp_vupgrade_mergeobjects** é usado apenas para replicação de mesclagem.  
  
## <a name="permissions"></a>Permissões  
 Exige associação à função de servidor fixa **sysadmin** .  
  
## <a name="see-also"></a>Consulte também  
 [Procedimentos armazenados de replicação &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/replication-stored-procedures-transact-sql.md)   
 [Atualizar bancos de dados replicados](../../database-engine/install-windows/upgrade-replicated-databases.md)  
  
  
