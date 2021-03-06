---
title: MSdatatype_mappings (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/03/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-views
ms.reviewer: 
ms.suite: sql
ms.technology:
- replication
ms.tgt_pltfrm: 
ms.topic: language-reference
applies_to:
- SQL Server
f1_keywords:
- MSdatatype_mappings
- MSdatatype_mappings_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- MSdatatype_mappings view
ms.assetid: 13cdabb3-6e07-4e8d-ae80-4235022ccc7f
caps.latest.revision: 
author: stevestein
ms.author: sstein
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: f0acbcbf2c70b08b44e0147989fb1f9dcd3e2301
ms.sourcegitcommit: c556eaf60a49af7025db35b7aa14beb76a8158c5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2018
---
# <a name="msdatatypemappings-transact-sql"></a>MSdatatype_mappings (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  O **MSdatatype_mappings** exibição mapeia tipos de dados do SQL Server para tipos de dados usados pelos sistemas de gerenciamento de banco de dados do SQL Server (DBMS). Essa tabela é armazenada no **msdb** banco de dados.  
  
|Nome da coluna|Tipo de dados|Description|  
|-----------------|---------------|-----------------|  
|**dbms_name**|**nvarchar(128)**|É o nome do DBMS. Abaixo estão os valores possíveis e suas descrições.<br /><br /> **MSSQLSERVER**: O destino é um banco de dados do SQL Server.<br />**ORACLE**: O destino é um banco de dados Oracle.<br />**DB2**: O destino é um banco de dados IBM DB2.<br />**SYBASE**: O destino é um banco de dados Sybase.|  
|**sql_type**|**nvarchar(128)**|É o tipo de dados do SQL Server.|  
|**dest_type**|**nvarchar(128)**|É o nome do tipo de dados do SQL Server.|  
|**dest_prec**|**bigint**|É a precisão do tipo de dados do SQL Server.|  
|**dest_create_params**|**Int**|Somente para uso interno.|  
|**dest_nullable**|**bit**|É se o tipo de dados do SQL Server oferece suporte a um valor nulo.|  
  
## <a name="see-also"></a>Consulte também  
 [Replicação de banco de dados heterogênea](../../relational-databases/replication/non-sql/heterogeneous-database-replication.md)   
 [Especificar mapeamentos de tipo de dados para um publicador Oracle](../../relational-databases/replication/publish/specify-data-type-mappings-for-an-oracle-publisher.md)   
 [Tabelas de replicação &#40; Transact-SQL &#41;](../../relational-databases/system-tables/replication-tables-transact-sql.md)   
 [Exibições de replicação &#40;Transact-SQL&#41;](../../relational-databases/system-views/replication-views-transact-sql.md)  
  
  
