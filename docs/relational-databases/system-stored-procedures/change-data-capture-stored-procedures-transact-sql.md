---
title: Change Data Capture procedimentos armazenados (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/06/2017
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
dev_langs:
- TSQL
helpviewer_keywords:
- system stored procedures [SQL Server], change data capture
- change data capture [SQL Server], stored procedures
ms.assetid: 7da7068d-6388-465a-b708-a2f27ded1efe
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 1f9911d990ef6cad879ddfd2fc9abd47fee97bc0
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="change-data-capture-stored-procedures-transact-sql"></a>Procedimentos armazenados de captura de dados de alteração (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  O Change Data Capture disponibiliza em um formato relacional conveniente o registro histórico da atividade DML (Data Manipulation Language) que ocorreu em tabelas habilitadas. Os seguintes procedimentos armazenados são usados para configurar o Change Data Capture, gerenciar os trabalhos do Agente do Change Data Capture e fornecer metadados atuais para consumidores de dados de alteração.  
  
|||  
|-|-|  
|[sys.sp_cdc_add_job &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sys-sp-cdc-add-job-transact-sql.md)|[sys. sp_cdc_generate_wrapper_function &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sys-sp-cdc-generate-wrapper-function-transact-sql.md)|  
|[sp_cdc_change_job &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sys-sp-cdc-change-job-transact-sql.md)|[sp_cdc_get_captured_columns &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sys-sp-cdc-get-captured-columns-transact-sql.md)|  
|[sys. sp_cdc_cleanup_change_table &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sys-sp-cdc-cleanup-change-table-transact-sql.md)|[sp_cdc_get_ddl_history &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sys-sp-cdc-get-ddl-history-transact-sql.md)|  
|[sp_cdc_disable_db &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sys-sp-cdc-disable-db-transact-sql.md)|[sp_cdc_help_change_data_capture &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sys-sp-cdc-help-change-data-capture-transact-sql.md)|  
|[sp_cdc_disable_table &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sys-sp-cdc-disable-table-transact-sql.md)|[sp_cdc_help_jobs &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sys-sp-cdc-help-jobs-transact-sql.md)|  
|[sp_cdc_drop_job &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sys-sp-cdc-drop-job-transact-sql.md)|[sp_cdc_scan &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sys-sp-cdc-scan-transact-sql.md)|  
|[sp_cdc_enable_db &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sys-sp-cdc-enable-db-transact-sql.md)|[sp_cdc_start_job &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sys-sp-cdc-start-job-transact-sql.md)|  
|[sp_cdc_enable_table &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sys-sp-cdc-enable-table-transact-sql.md)|[sp_cdc_stop_job &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sys-sp-cdc-stop-job-transact-sql.md)|  
  
## <a name="see-also"></a>Consulte também  
 [Change Data Capture tabelas &#40; Transact-SQL &#41;](../../relational-databases/system-tables/change-data-capture-tables-transact-sql.md)  
  
  
