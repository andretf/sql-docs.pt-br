---
title: MSmerge_identity_range (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/04/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-tables
ms.reviewer: 
ms.suite: sql
ms.technology:
- replication
ms.tgt_pltfrm: 
ms.topic: language-reference
applies_to:
- SQL Server
f1_keywords:
- MSmerge_identity_range_TSQL
- MSmerge_identity_range
dev_langs:
- TSQL
helpviewer_keywords:
- MSmerge_identity_range system table
ms.assetid: 493a2028-88a0-4e83-ad89-ae5661d9f477
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: ec799b6fcf16f4cb7f0146c6e01915d7e40d464a
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="msmergeidentityrange-transact-sql"></a>MSmerge_identity_range (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  O **MSmerge_identity_range** tabela é usada para controlar os intervalos numéricos atribuídos a colunas de identidade para assinatura em publicações em que a replicação gerencia automaticamente essas atribuições de intervalo. Essa tabela é armazenada nos bancos de dados de publicação e assinatura.  
  
|Nome da coluna|Tipo de dados|Description|  
|-----------------|---------------|-----------------|  
|**subid**|**uniqueidentifier**|O número de identificação exclusivo para uma determinada assinatura.|  
|**artid**|**uniqueidentifier**|O número de identificação exclusivo para o artigo determinado.|  
|**range_begin**|**numeric(38)**|O valor de identidade no início do intervalo atual.|  
|**range_end**|**numeric(38)**|O valor de identidade no fim do intervalo atual.|  
|**next_range_begin**|**numeric(38)**|O valor de identidade no início do próximo intervalo a ser atribuído.|  
|**next_range_end**|**numeric(38)**|O valor de identidade no fim do próximo intervalo a ser atribuído.|  
|**is_pub_range**|**bit**|Um valor de **1** se o intervalo de identidade é atribuído à publicação.|  
|**max_used**|**numeric(38)**|O valor de identidade máximo que pode ser atribuído.|  
  
## <a name="see-also"></a>Consulte também  
 [Tabelas de replicação &#40; Transact-SQL &#41;](../../relational-databases/system-tables/replication-tables-transact-sql.md)   
 [Exibições de replicação &#40;Transact-SQL&#41;](../../relational-databases/system-views/replication-views-transact-sql.md)  
  
  
