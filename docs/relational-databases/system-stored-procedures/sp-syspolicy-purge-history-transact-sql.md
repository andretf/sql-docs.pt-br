---
title: sp_syspolicy_purge_history (Transact-SQL) | Microsoft Docs
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
- sp_syspolicy_purge_history_TSQL
- sp_syspolicy_purge_history
dev_langs:
- TSQL
helpviewer_keywords:
- sp_syspolicy_purge_history
ms.assetid: 6db414e7-4946-4bd2-8264-6b490810b306
caps.latest.revision: 
author: stevestein
ms.author: sstein
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: 410cb6e1319adf5c1199a520ba54a236c6d01951
ms.sourcegitcommit: c556eaf60a49af7025db35b7aa14beb76a8158c5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2018
---
# <a name="spsyspolicypurgehistory-transact-sql"></a>sp_syspolicy_purge_history (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Remove o histórico de avaliação de política de acordo com a configuração do intervalo de retenção de histórico.  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Convenções da sintaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
sp_syspolicy_purge_history  
```  
  
## <a name="arguments"></a>Argumentos  
 Esse procedimento armazenado não possui parâmetros.  
  
## <a name="return-code-values"></a>Valores do código de retorno  
 **0** (êxito) ou **1** (falha)  
  
## <a name="remarks"></a>Remarks  
 Você deve executar sp_syspolicy_purge_history no contexto do banco de dados de sistema msdb.  
  
 Para exibir o intervalo de retenção de histórico, você pode usar a seguinte consulta:  
  
```  
SELECT current_value  
FROM msdb.dbo.syspolicy_configuration  
WHERE name = N'HistoryRetentionInDays';  
GO  
```  
  
> [!NOTE]  
>  Se o intervalo de retenção de histórico for definido com 0, o histórico de avaliação de política não será removido.  
  
## <a name="permissions"></a>Permissões  
 Requer a associação à função de banco de dados fixa PolicyAdministratorRole.  
  
> [!IMPORTANT]  
>  Possível elevação de credenciais: os usuários na função PolicyAdministratorRole podem criar gatilhos de servidor e agendar execuções de políticas que possam afetar a operação da instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)]. Por exemplo, os usuários da função PolicyAdministratorRole podem criar uma política que impeça a criação da maioria dos objetos no [!INCLUDE[ssDE](../../includes/ssde-md.md)]. Devido a essa possível elevação de credenciais, a função PolicyAdministratorRole deve ser concedida somente a usuários que sejam confiáveis com controle da configuração do [!INCLUDE[ssDE](../../includes/ssde-md.md)].  
  
## <a name="examples"></a>Exemplos  
 O exemplo a seguir remove o histórico de avaliação de política.  
  
```  
EXEC msdb.dbo.sp_syspolicy_purge_history;  
  
GO  
```  
  
## <a name="see-also"></a>Consulte também  
 [Gerenciamento baseado em políticas armazenados procedimentos &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/policy-based-management-stored-procedures-transact-sql.md)   
 [sp_syspolicy_set_config_history_retention &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-syspolicy-set-config-history-retention-transact-sql.md)   
 [sp_syspolicy_delete_policy_execution_history &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-syspolicy-delete-policy-execution-history-transact-sql.md)  
  
  
