---
title: Cargas de monitor para Parallel Data Warehouse
author: barbkess
ms.author: barbkess
manager: jhubbard
ms.prod: analytics-platform-system
ms.prod_service: mpp-data-warehouse
ms.service: 
ms.component: 
ms.suite: sql
ms.custom: 
ms.technology: mpp-data-warehouse
description: "Você pode monitorar ativas e recente [dwloader](dwloader.md) carrega usando o Console de administração Analytics Platform System (APS) ou as exibições do sistema Parallel Data Warehouse (PDW)."
ms.date: 10/20/2016
ms.topic: article
ms.assetid: c0c55c16-00bc-4676-8970-a8e10b3e9408
caps.latest.revision: "6"
ms.openlocfilehash: 988c34b248b0058941f53575a79e4f3b6acb4de0
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/21/2017
---
# <a name="monitor-loads"></a>Monitorar cargas
Você pode monitorar ativas e recente [dwloader](dwloader.md) carrega usando o Console de administração Analytics Platform System (APS) ou o Parallel Data Warehouse (PDW) [exibições do sistema](https://azure.microsoft.com/documentation/articles/sql-data-warehouse-reference-tsql-system-views/). 
  
> [!TIP]  
> Algumas cargas são iniciadas usando instruções INSERT ou ferramentas de business intelligence que usam instruções SQL para executar a carga. 

<!-- MISSING LINKS
To monitor this type of load, see [Monitoring Active Queries](monitor-active-queries.md).  
-->
  
## <a name="prerequisites"></a>Prerequisites  
Independentemente do método usado para monitorar uma carga, o logon deve ter permissão para acessar fontes de dados subjacentes. 

<!-- MISSING LINKS
For the permissions to grant, see “Use All of the Admin Console” in [Grant Permissions to Use the Admin Console](grant-permissions-admin-console.md). 

--> 
  
## <a name="monitoring-loads"></a>Cargas de monitoramentos  
As seções a seguir descrevem como monitorar cargas.  
  
### <a name="to-monitor-loads-by-using-the-admin-console"></a>Para monitorar cargas usando o Console de administração  
  
1.  Faça logon no Console do administrador. <!-- MISSING LINKS See [Monitor the Appliance by Using the Admin Console;](monitor-admin-console.md) for instructions. --> 
  
2.  No menu superior, clique em **cargas**. Você verá uma tabela classificável, mostrando todos os recentes e de cargas ativas além de informações adicionais, como se o carregamento foi concluído ou ainda está ativo. Clique nos cabeçalhos de coluna para classificar as linhas.  
  
3.  Para exibir detalhes adicionais para uma carga específica, clique a carga **ID** na coluna esquerda. Na exibição detalhada, você pode ver o progresso de cada etapa da carga.  
  
Consulte esses modos de exibição do sistema para obter informações sobre os metadados sobre a carga que é mostrado no Console do administrador:  
  
-   [sys.dm_pdw_exec_requests](../relational-databases/system-dynamic-management-views/sys-dm-pdw-exec-requests-transact-sql.md)  
  
-   [sys.pdw_loader_run_stages](https://msdn.microsoft.com/library/mt203879.aspx.md)  
  
-   [sys.pdw_loader_backup_runs](../relational-databases/system-catalog-views/sys-pdw-loader-backup-runs-transact-sql.md)  
  
-   [sys.pdw_loader_backup_run_details](../relational-databases/system-catalog-views/sys-pdw-loader-backup-run-details-transact-sql.md)  
  
### <a name="to-monitor-loads-by-using-system-views"></a>Para monitorar cargas usando exibições do sistema  
Para monitorar cargas ativas e recentes usando exibições do SQL Server PDW, siga as etapas abaixo. Para cada modo de exibição de sistema usado, consulte a documentação para essa exibição para obter informações sobre as colunas e os possíveis valores retornados pela exibição.  
  
1.  Localizar o `request_id` para a carga no [sys.dm_pdw_exec_requests](../relational-databases/system-dynamic-management-views/sys-dm-pdw-exec-requests-transact-sql.md) exibição, localizando a linha de comando do carregador no `command` coluna para esta exibição.  
  
    Por exemplo, o comando a seguir retorna o texto do comando e o status atual, mais o `request_id`.  
  
    ```sql  
    SELECT request_id, status, command FROM sys.dm_pdw_exec_requests;  
    ```  
  
2.  Use o `request_id` para recuperar informações adicionais para a carga por meio de [sys.pdw_loader_run_stages](../relational-databases/system-catalog-views/sys-pdw-loader-run-stages-transact-sql.md) , e [sys.pdw_loader_backup_run_details](../relational-databases/system-catalog-views/sys-pdw-loader-backup-run-details-transact-sql.md) modos de exibição. Por exemplo, a consulta a seguir retorna o `run_id` e obter informações sobre o início, fim e tempos de duração da carga, além de quaisquer erros e informações sobre o número de linhas processadas:  
  
    ```sql  
    SELECT lbr.run_id,   
    er.submit_time, er.end_time, er.total_elapsed_time, er.error_id, lbr.rows_processed, lbr.rows_rejected, lbr.rows_inserted   
    FROM sys.dm_pdw_exec_requests er   
    LEFT OUTER JOIN   
    sys.pdw_loader_backup_runs lbr   
    ON (er.request_id=lbr.requst_id)   
    WHERE er.request_id=’12738’;  
    ```  
  
<!-- MISSING LINKS

## See Also  
[Common metadata query examples](metadata-query-examples.md)
-->  
  
