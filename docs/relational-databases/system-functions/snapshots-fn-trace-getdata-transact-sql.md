---
title: snapshots.fn_trace_getdata (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/03/2017
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
f1_keywords:
- snapshots.fn_trace_getdata
dev_langs:
- TSQL
helpviewer_keywords:
- snapshots.fn_trace_getdata function
ms.assetid: ac28ef48-f4f4-4bf2-ba22-d44e1be88172
caps.latest.revision: 
author: rothja
ms.author: jroth
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 0911f35d9573394492376457a47b369a04a8fbf7
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2018
---
# <a name="snapshotsfntracegetdata-transact-sql"></a>snapshots.fn_trace_getdata (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Essa função retorna todos os eventos capturados para o rastreamento especificado.  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Convenções da sintaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
snapshots.fn_trace_gettable ( trace_info_id, start_time, end_time )  
```  
  
## <a name="arguments"></a>Argumentos  
 *trace_info_id*  
 O identificador exclusivo para a chave primária na tabela trace_info os dados de gerenciamento de banco de dados do data warehouse. *trace_info_id* é **int**.  
  
 *start_time*  
 A hora em que o rastreamento foi iniciado. *start_time* é **datetime**.  
  
 *end_time*  
 A hora em que o rastreamento foi terminado. *end_time* é **datetime**.  
  
## <a name="table-returned"></a>Tabela retornada  
  
|Nome da coluna|Tipo de dados|Description|  
|-----------------|---------------|-----------------|  
|\<Todas as colunas de rastreamento >|\<Varia >|Os dados de rastreamento da tabela snapshots.trace_data no banco de dados de data warehouse de gerenciamento.<br /><br /> Uma lista de colunas para o rastreamento especificado pode ser obtida usando a consulta a seguir:<br /><br /> `SELECT * FROM sys.trace_columns`<br /><br /> **Observação:** as colunas que são retornadas pela função fn_trace_gettable correspondem aos valores na coluna Nome trace_columns do sistema. A única diferença é que a coluna GroupID não é retornada pela função.|  
  
## <a name="permissions"></a>Permissões  
 Requer permissão SELECT para mdw_reader.  
  
## <a name="see-also"></a>Consulte também  
 [Coleta de Dados](../../relational-databases/data-collection/data-collection.md)  
  
  
