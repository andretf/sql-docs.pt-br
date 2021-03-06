---
title: core.sp_create_snapshot (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/03/2017
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
- sp_create_snapshot
- sp_create_snapshot_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- management data warehouse, data collector stored procedures
- data collector [SQL Server], stored procedures
- core.sp_create_snapshot stored procedure
- sp_create_snapshot
ms.assetid: ff297bda-0ee2-4fda-91c8-7000377775e3
caps.latest.revision: 
author: stevestein
ms.author: sstein
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 559eed3c2ae0a5bada1453e21347fee791625eb5
ms.sourcegitcommit: c556eaf60a49af7025db35b7aa14beb76a8158c5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2018
---
# <a name="corespcreatesnapshot-transact-sql"></a>core.sp_create_snapshot (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Insere uma linha na exibição core.snapshots do data warehouse de gerenciamento. Esse procedimento é chamado sempre que um pacote de carregamento começa a carregar dados no data warehouse de gerenciamento.  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Convenções da sintaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
core.sp_create_snapshot [ @collection_set_uid = ] 'collection_set_uid'  
    , [ @collector_type_uid = ] 'collector_type_uid'  
    ,[ @machine_name = ] 'machine_name'  
    , [ @named_instance = ] 'named_instance'  
    , [ @log_id = ] log_id  
    , [ @snapshot_id = ] snapshot_id OUTPUT  
```  
  
## <a name="arguments"></a>Argumentos  
 [ @collection_set_uid = ] '*collection_set_uid*'  
 O GUID do conjunto de coleta. *collection_set_uid* é **uniqueidentifier** sem nenhum valor padrão. Para obter o GUID, consulte a exibição dbo.syscollector_collection_sets no banco de dados msdb.  
  
 [ @collector_type_uid =] '*collector_type_uid*'  
 O GUID de um tipo de coletor. *collector_type_uid* é **uniqueidentifier** sem nenhum valor padrão. Para obter o GUID, consulte a exibição dbo.syscollector_collector_types no banco de dados msdb.  
  
 [ @machine_name=] '*nome_da_máquina*'  
 O nome do servidor no qual o conjunto de coleta reside. *nome_da_máquina* é **sysname**, sem nenhum valor padrão.  
  
 [ @named_instance= ] '*named_instance*'  
 O nome da instância do conjunto de coleta. *instância_nomeada* é **sysname**, sem nenhum valor padrão.  
  
 [ @log_id = ] *log_id*  
 O identificador exclusivo que é mapeado para o log de eventos do conjunto de coleta que coletou os dados. *log_id* é **bigint** sem nenhum valor padrão. Para obter o valor de *log_id*, consulte a exibição syscollector_execution_log no banco de dados msdb.  
  
 [ @snapshot_id =] *snapshot_id*  
 O identificador exclusivo de uma linha que é inserido no modo de exibição snapshots. *snapshot_id* é **int** e é retornada como OUTPUT.  
  
## <a name="return-code-values"></a>Valores do código de retorno  
 **0** (êxito) ou **1** (falha)  
  
## <a name="remarks"></a>Remarks  
 Sempre que um pacote de carregamento começa a carregar dados no data warehouse de gerenciamento, o componente de tempo de execução do coletor de dados chama core.sp_create_snapshot.  
  
 Esse procedimento verifica se:  
  
-   O collection_set_uid corresponde a uma entrada existente na tabela core.source_info_internal.  
  
-   O collector_type_uid corresponde a uma entrada existente na exibição core.supported_collector_types.  
  
 Se alguma das verificações acima falhar, o procedimento falhará e retornará um erro.  
  
## <a name="permissions"></a>Permissões  
 Requer a participação no **mdw_writer** (com permissão EXECUTE) função fixa de banco de dados.  
  
## <a name="examples"></a>Exemplos  
 O exemplo a seguir cria um instantâneo do conjunto de coleta Uso do Disco, adiciona-o ao data warehouse de gerenciamento e retorna o identificador do instantâneo. No exemplo, a instância padrão é usada.  
  
```  
USE <management_data_warehouse>;  
DECLARE @snapshot_id int;  
EXEC core.sp_create_snapshot   
    @collection_set_uid = '7B191952-8ECF-4E12-AEB2-EF646EF79FEF',   
    @collector_type_uid = '302E93D1-3424-4BE7-AA8E-84813ECF2419',  
    @machine_name = '<computername>',  
    @named_instance = 'MSSQLSERVER',  
    @log_id = 11, -- ID of the log for the collection set  
    @snapshot_id = @snapshot_id OUTPUT;  
```  
  
## <a name="see-also"></a>Consulte também  
 [Procedimentos armazenados do sistema &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)   
 [Procedimentos armazenados de coletor de dados &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/data-collector-stored-procedures-transact-sql.md)   
 [Data warehouse de gerenciamento](../../relational-databases/data-collection/management-data-warehouse.md)  
  
  
