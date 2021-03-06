---
title: sp_helparticlecolumns (Transact-SQL) | Microsoft Docs
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
- sp_helparticlecolumns
- sp_helparticlecolumns_TSQL
helpviewer_keywords:
- sp_helparticlecolumns
ms.assetid: 9ea55df3-2e99-4683-88ad-bde718288bc7
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: f4a234740c8d6f9eabd8f34f93a246db9e6502f7
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="sphelparticlecolumns-transact-sql"></a>sp_helparticlecolumns (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Retorna todas as colunas na tabela subjacente. Esse procedimento armazenado é executado no Publicador, no banco de dados publicador. Para Editores Oracle, esse procedimento armazenado é executado no Distribuidor, em qualquer banco de dados.  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Convenções da sintaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
sp_helparticlecolumns [ @publication = ] 'publication'   
        , [ @article = ] 'article'  
    [ , [ @publisher = ] 'publisher' ]  
```  
  
## <a name="arguments"></a>Argumentos  
 [  **@publication =**] **'***publicação***'**  
 É o nome da publicação que contém o artigo. *publicação* é **sysname**, sem padrão.  
  
 [  **@article=**] **'***artigo***'**  
 É o nome do artigo que tem suas colunas retornadas. *artigo* é **sysname**, sem padrão.  
  
 [  **@publisher** =] **'***publicador***'**  
 Especifica um não[!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] publicador. *publicador* é **sysname**, com um padrão NULL.  
  
> [!NOTE]  
>  *publicador* não deve ser especificado quando o artigo solicitado é publicado por um [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] publicador.  
  
## <a name="return-code-values"></a>Valores do código de retorno  
 **0** (colunas que não são publicadas) ou **1** (colunas que são publicadas)  
  
## <a name="result-sets"></a>Conjuntos de resultados  
  
|Nome da coluna|Tipo de dados|Description|  
|-----------------|---------------|-----------------|  
|**id da coluna**|**int**|Identificador para a coluna.|  
|**coluna**|**sysname**|Nome da coluna.|  
|**publicado**|**bit**|Se a coluna for publicada:<br /><br /> **0** = não<br /><br /> **1** = Sim|  
|**tipo de publicador**|**sysname**|Tipo de dados da coluna no Publicador.|  
|**tipo de assinante**|**sysname**|Tipo de dados da coluna no Assinante.|  
  
## <a name="remarks"></a>Comentários  
 **sp_helparticlecolumns** é usado em replicação de instantâneo e transacional.  
  
 **sp_helparticlecolumns** é útil para verificar uma partição vertical.  
  
## <a name="permissions"></a>Permissões  
 Somente membros do **sysadmin** função de servidor fixa, o **db_owner** função fixa de banco de dados ou a lista de acesso da publicação para a publicação atual pode executar **sp_helparticlecolumns**.  
  
## <a name="see-also"></a>Consulte também  
 [Definir e modificar um filtro de coluna](../../relational-databases/replication/publish/define-and-modify-a-column-filter.md)   
 [sp_addarticle &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sp-addarticle-transact-sql.md)   
 [sp_articlecolumn &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-articlecolumn-transact-sql.md)   
 [sp_changearticle &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-changearticle-transact-sql.md)   
 [sp_droparticle &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-droparticle-transact-sql.md)   
 [sp_droppublication &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sp-droppublication-transact-sql.md)   
 [Procedimentos armazenados do sistema &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
