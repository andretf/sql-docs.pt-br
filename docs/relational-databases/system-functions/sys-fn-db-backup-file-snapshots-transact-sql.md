---
title: sys.fn_db_backup_file_snapshots (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 06/03/2015
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-functions
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- TSQL
ms.assetid: 45010ff2-219f-4086-9ea4-016a6c17cddd
caps.latest.revision: 
author: rothja
ms.author: jroth
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 0d72c64ec88ce9252698bb869e12b54340f685cf
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2018
---
# <a name="sysfndbbackupfilesnapshots-transact-sql"></a>sys.fn_db_backup_file_snapshots (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2016-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2016-xxxx-xxxx-xxx-md.md)]

  Retorna os instantâneos do Azure associados aos arquivos de banco de dados. Se o banco de dados especificado não foi encontrado ou se os arquivos de banco de dados não são armazenados no serviço de armazenamento de BLOBs do Microsoft Azure, nenhuma linha será retornada. Use essa função de sistema em conjunto com o **sys. sp_delete_backup_file_snapshot** sistema de procedimento armazenado para identificar e excluir órfãos os instantâneos de backup. Para obter mais informações, consulte [Backups de instantâneo de arquivo para arquivos de banco de dados no Azure](../../relational-databases/backup-restore/file-snapshot-backups-for-database-files-in-azure.md).  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Convenções da sintaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
sys.fn_db_backup_file_snapshots   
   [ ( database_name ) ]  
```  
  
## <a name="arguments"></a>Argumentos  
 *Database_name*  
 O nome do banco de dados que está sendo consultado. Se for NULL, essa função é executada no escopo do banco de dados atual.  
  
## <a name="table-returned"></a>Tabela retornada  
  
|Nome da coluna|Tipo de dados|Description|  
|-----------------|---------------|-----------------|  
|file_id|**Int**|A ID de arquivo para o banco de dados. Não permite valor nulo.|  
|snapshot_time|**nvarchar(260)**|O carimbo de hora do instantâneo como ele é retornado pela API REST. Retorna NULL se nenhum instantâneo existe.|  
|snapshot_url|**nvarchar(360)**|A URL completa para o instantâneo de arquivo. Retorna nulo se nenhum instantâneo existe.|  
  
## <a name="permissions"></a>Permissões  
 Requer a permissão VIEW DATABASE STATE no banco de dados.  
  
## <a name="see-also"></a>Consulte também  
 [sp_delete_backup_file_snapshot &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/snapshot-backup-sp-delete-backup-file-snapshot.md)   
 [sp_delete_backup &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/snapshot-backup-sp-delete-backup.md)  
  
  
