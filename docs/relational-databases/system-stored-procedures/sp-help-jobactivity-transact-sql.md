---
title: sp_help_jobactivity (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-stored-procedures
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- sp_help_jobactivity_TSQL
- sp_help_jobactivity
dev_langs: TSQL
helpviewer_keywords: sp_help_jobactivity
ms.assetid: d344864f-b4d3-46b1-8933-b81dec71f511
caps.latest.revision: "33"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 4cb0d3d344b97f0ce14e3bd156b5915a1721c8f4
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2017
---
# <a name="sphelpjobactivity-transact-sql"></a>sp_help_jobactivity (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Lista informações sobre o estado de tempo de execução dos trabalhos do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Convenções da sintaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
sp_help_jobactivity { [ @job_id = ] job_id | [ @job_name = ] 'job_name' }  
     [ , [ @session_id = ] session_id ]  
```  
  
## <a name="arguments"></a>Argumentos  
 [  **@job_id =**] *job_id*  
 O número de identificação do trabalho. *job_id*é **uniqueidentifier**, com um padrão NULL.  
  
 [  **@job_name =**] **'***job_name***'**  
 O nome do trabalho. *job_name*é **sysname**, com um padrão NULL.  
  
> [!NOTE]  
>  O *job_id* ou *job_name* devem ser especificados, mas não é possível especificar ambos.  
  
 [  **@session_id**  =] *session_id*  
 A id da sessão sobre a qual relatar informações. *session_id* é **int**, com um padrão NULL.  
  
## <a name="return-code-values"></a>Valores do código de retorno  
 **0** (êxito) ou **1** (falha)  
  
## <a name="result-sets"></a>Conjuntos de resultados  
 Retorna o seguinte conjunto de resultados:  
  
|Nome da coluna|Tipo de dados|Description|  
|-----------------|---------------|-----------------|  
|**session_id**|**int**|Número de identificação da sessão do agente.|  
|**job_id**|**uniqueidentifier**|Identificador do trabalho.|  
|**job_name**|**sysname**|Nome do trabalho.|  
|**run_requested_date**|**datetime**|Momento em que foi solicitada a execução do trabalho.|  
|**run_requested_source**|**sysname**|A origem da solicitação para executar o trabalho. Um dos seguintes:<br /><br /> **1** = executar em um agendamento<br /><br /> **2** = executar em resposta a um alerta<br /><br /> **3** = executar na inicialização<br /><br /> **4** = executar pelo usuário<br /><br /> **6** = executar em um agendamento ocioso de CPU|  
|**queued_date**|**datetime**|Data em que a solicitação foi colocada em fila. NULL se o trabalho foi executado diretamente.|  
|**start_execution_date**|**datetime**|Data em que o trabalho foi atribuído a um thread executável.|  
|**last_executed_step_id**|**int**|A ID de etapa da última etapa de trabalho executada.|  
|**last_exectued_step_date**|**datetime**|A data em que começou a execução da última etapa de trabalho.|  
|**stop_execution_date**|**datetime**|A data em que o trabalho parou de ser executado.|  
|**next_scheduled_run_date**|**datetime**|Quando o trabalho lado é agendado para execução.|  
|**job_history_id**|**int**|Identificador para o histórico de trabalho na tabela de histórico de trabalho.|  
|**Mensagem**|**nvarchar (1024)**|Mensagem produzida durante a última execução do trabalho.|  
|**run_status**|**int**|Status retornado da última execução do trabalho:<br /><br /> **0** = erro de falha<br /><br /> **1** = foi bem-sucedida<br /><br /> **3** = cancelada<br /><br /> **5** = status desconhecido|  
|**operator_id_emailed**|**int**|Número de ID do operador notificado por email na conclusão do trabalho.|  
|**operator_id_netsent**|**int**|Número de identificação do operador notificado **net send** na conclusão do trabalho.|  
|**operator_id_paged**|**int**|Número de ID do operador notificado por pager na conclusão do trabalho.|  
  
## <a name="remarks"></a>Comentários  
 Esse procedimento fornece um instantâneo do status atual dos trabalhos. Os resultados retornados representam as informações no momento em que a solicitação é processada.  
  
 O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent cria uma nova ID de sessão sempre que seu serviço é iniciado. A id de sessão é armazenada na tabela **syssessions**.  
  
 Quando nenhum *session_id* for fornecido, a lista informações sobre a sessão mais recente.  
  
 Quando nenhum *job_name* ou *job_id* for fornecido, a lista de informações para todos os trabalhos.  
  
## <a name="permissions"></a>Permissões  
 Por padrão, membros do **sysadmin** função fixa de servidor pode executar esse procedimento armazenado. Deve ser concedida a outros usuários uma das seguintes funções de banco de dados fixas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent no banco de dados **msdb** :  
  
-   **SQLAgentUserRole**  
  
-   **SQLAgentReaderRole**  
  
-   **SQLAgentOperatorRole**  
  
 Para obter detalhes sobre as permissões dessas funções, consulte [Funções de banco de dados fixas do SQL Server Agent](http://msdn.microsoft.com/library/719ce56b-d6b2-414a-88a8-f43b725ebc79).  
  
 Somente membros da **sysadmin** pode exibir a atividade de trabalhos pertencentes a outros usuários.  
  
## <a name="examples"></a>Exemplos  
 O exemplo a seguir lista a atividade de todos os trabalhos que o usuário atual tem permissão para exibir.  
  
```  
USE msdb ;  
GO  
  
EXEC dbo.sp_help_jobactivity ;  
GO  
```  
  
## <a name="see-also"></a>Consulte também  
 [Agente do SQL Server armazenados procedimentos &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sql-server-agent-stored-procedures-transact-sql.md)  
  
  