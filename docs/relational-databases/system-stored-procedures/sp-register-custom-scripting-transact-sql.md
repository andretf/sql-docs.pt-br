---
title: sp_register_custom_scripting (Transact-SQL) | Microsoft Docs
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
- sp_register_custom_scripting
- sp_register_custom_scripting_TSQL
helpviewer_keywords:
- sp_register_custom_scripting
ms.assetid: a8159282-de3b-4b9e-bdc9-3d3fce485c7f
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 16274b71d1ce14b2a143e5d6ce723bcb64cbaebd
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="spregistercustomscripting-transact-sql"></a>sp_register_custom_scripting (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  A replicação permite procedimentos armazenados personalizados definidos pelo usuário, para substituir um ou mais dos procedimentos padrão usados em replicação transacional. Quando uma alteração de esquema é feita em uma tabela replicada, esses procedimentos armazenados são recriados. **sp_register_custom_scripting** registra um procedimento armazenado ou [!INCLUDE[tsql](../../includes/tsql-md.md)] arquivo de script que é executado quando ocorre uma alteração de esquema para o script de definição para um novo definido pelo usuário procedimento armazenado personalizado. Esse novo procedimento armazenado personalizado deve refletir o novo esquema da tabela. **sp_register_custom_scripting** é executado no publicador do banco de dados de publicação, e o arquivo de script registrado ou o procedimento armazenado é executado no assinante quando ocorre uma alteração de esquema.  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Convenções da sintaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
sp_register_custom_scripting [ @type  = ] 'type'  
    [ @value = ] 'value'   
    [ , [ @publication = ] 'publication' ]  
    [ , [ @article = ] 'article' ]  
```  
  
## <a name="arguments"></a>Argumentos  
 [  **@type**  =] **'***tipo***'**  
 É o tipo de procedimento armazenado personalizado ou script que está sendo registrado. *tipo* é **varchar (16)**, sem padrão e pode ser um dos valores a seguir.  
  
|Valor|Description|  
|-----------|-----------------|  
|**Inserir**|Procedimento armazenado personalizado registrado é executado quando uma instrução INSERT é replicada.|  
|**Atualizar**|Procedimento armazenado personalizado registrado é executado quando uma instrução UPDATE é replicada.|  
|**Excluir**|Procedimento armazenado personalizado registrado é executado quando uma instrução DELETE é replicada.|  
|**CUSTOM_SCRIPT**|O script é executado ao término do gatilho DDL (Data Definition Language).|  
  
 [  **@value** =] **'***valor***'**  
 Nome de um procedimento armazenado ou nome e caminho completamente qualificado para o arquivo script [!INCLUDE[tsql](../../includes/tsql-md.md)] que está sendo registrado. *valor* é **nvarchar (1024)**, sem padrão.  
  
> [!NOTE]  
>  Especificando NULL para *valor*parâmetro irá cancelar o registro de um script registrado anteriormente, o que é o mesmo que executar [sp_unregister_custom_scripting](../../relational-databases/system-stored-procedures/sp-unregister-custom-scripting-transact-sql.md).  
  
 Quando o valor de *tipo* é **custom_script**, o nome e caminho completo de um [!INCLUDE[tsql](../../includes/tsql-md.md)] arquivo de script é esperado. Caso contrário, *valor* deve ser o nome de um procedimento armazenado registrado.  
  
 [  **@publication** =] **'***publicação***'**  
 Nome da publicação para a qual o procedimento armazenado personalizado ou script está sendo registrado. *publicação* é **sysname**, com um padrão de **nulo**.  
  
 [  **@article** =] **'***artigo***'**  
 Nome do artigo para o qual o procedimento armazenado personalizado ou script está sendo registrado. *artigo* é **sysname**, com um padrão de **nulo**.  
  
## <a name="return-code-values"></a>Valores do código de retorno  
 **0** (êxito) ou **1** (falha)  
  
## <a name="remarks"></a>Comentários  
 **sp_register_custom_scripting** é usado em replicação de instantâneo e transacional.  
  
 Esse procedimento armazenado deve ser executado antes de efetuar uma alteração de esquema em uma  tabela replicada. Para obter mais informações sobre como usar esse procedimento armazenado, consulte [regenerar os procedimentos transacionais personalizados para refletir as alterações de esquema](../../relational-databases/replication/transactional/transactional-articles-regenerate-to-reflect-schema-changes.md).  
  
## <a name="permissions"></a>Permissões  
 Somente membros do **sysadmin** função fixa de servidor a **db_owner** função de banco de dados fixa ou **db_ddladmin** pode executar a função de banco de dados fixa **SP _ register_custom_scripting**.  
  
## <a name="see-also"></a>Consulte também  
 [sp_unregister_custom_scripting &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sp-unregister-custom-scripting-transact-sql.md)  
  
  
