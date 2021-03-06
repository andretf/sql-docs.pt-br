---
title: sp_syscollector_upload_collection_set (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-stored-procedures
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- sp_syscollector_upload_collection_set
- sp_syscollector_upload_collection_set_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sp_syscollector_upload_collection_set
- data collector [SQL Server], stored procedures
ms.assetid: eed9232c-2b0a-4b6a-8ba0-76b7c99f48dc
caps.latest.revision: 
author: stevestein
ms.author: sstein
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 6b99daf03610520275823aa97f1f2917d72bff99
ms.sourcegitcommit: c556eaf60a49af7025db35b7aa14beb76a8158c5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2018
---
# <a name="spsyscollectoruploadcollectionset-transact-sql"></a>sp_syscollector_upload_collection_set (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Inicia um carregamento de dados do conjunto de coleta se o conjunto de dados estiver habilitado.  
  
> [!IMPORTANT]  
>  Esse procedimento armazenado só pode ser usado para conjuntos de coleta que são configurados para a coleta e o carregamento dos dados em cache.  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Convenções da sintaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
sp_syscollector_upload_collection_set [[ @collection_set_id = ] collection_set_id ]  
          , [[ @name = ] 'name' ]   
```  
  
## <a name="arguments"></a>Argumentos  
 [ **@collection_set_id =** ] *collection_set_id*  
 É o identificador local exclusivo do conjunto de coleta. *collection_set_id* é **int** e deve ter um valor se *nome* é NULL.  
  
 [ **@name =** ] **'***name***'**  
 É o nome do conjunto de coleta. *nome* é **sysname** e deve ter um valor se *collection_set_id* é NULL.  
  
## <a name="return-code-values"></a>Valores do código de retorno  
 **0** (êxito) ou **1** (falha)  
  
## <a name="remarks"></a>Remarks  
 O *collection_set_id* ou *nome* deve ter um valor; não pode ser NULL.  
  
 Este procedimento pode ser usado para iniciar uma carga sob demanda de um conjunto de coleta em execução. Só pode ser usado para conjuntos de coleta configurados para a coleta e o carregamento dos dados em cache. Isto permite que o usuário obtenha dados para analisar sem precisar aguardar um carregamento programado.  
  
## <a name="permissions"></a>Permissões  
 Requer a participação no **dc_operator** (com permissão EXECUTE) função de banco de dados fixa para executar esse procedimento.  
  
## <a name="example"></a>Exemplo  
 Efetua o carregamento sob demanda de um conjunto de coleta chamado `Simple Collection Set`.  
  
```  
USE msdb;  
GO  
EXEC sp_syscollector_upload_collection_set @name = 'Simple Collection Set' ;  
```  
  
## <a name="see-also"></a>Consulte também  
 [Procedimentos armazenados do sistema &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)   
 [Coleta de Dados](../../relational-databases/data-collection/data-collection.md)  
  
  
