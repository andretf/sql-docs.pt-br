---
title: "Referência da classe de evento do SQL Server | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- events [SQL Server], event classes
- event classes [SQL Server], listed
- event classes [SQL Server]
- SQL Server event classes, listed
- SQL Server event classes
ms.assetid: 0f0fe567-e115-4ace-b63c-73dc3428c0f6
caps.latest.revision: 34
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: d88dcea1aee43bc8603bfe25b73a8c5b09cb31ad
ms.contentlocale: pt-br
ms.lasthandoff: 06/22/2017

---
# <a name="sql-server-event-class-reference"></a>Referência de classe de evento do SQL Server
  [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] lets you record events as they occur in an instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]. Os eventos registrados são instâncias das classes de evento na definição de rastreamento. No [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], as classes de evento e suas categorias estão disponíveis na guia **Seleção de Eventos** da caixa de diálogo **Propriedades do Arquivo de Rastreamento** .  
  
 A tabela a seguir descreve as categorias de evento e lista suas classes de evento associadas.  
  
|Categoria de evento|Classes de evento|  
|--------------------|-------------------|  
|A [Categoria de Evento de Agente](../../relational-databases/event-classes/broker-event-category.md) contém as classes de evento que são produzidas pelo [!INCLUDE[ssSB](../../includes/sssb-md.md)].|[Classe de evento Broker:Activation](../../relational-databases/event-classes/broker-activation-event-class.md)<br /><br /> [Classe de evento Broker:Connection](../../relational-databases/event-classes/broker-connection-event-class.md)<br /><br /> [Classe de evento Broker:Conversation](../../relational-databases/event-classes/broker-conversation-event-class.md)<br /><br /> [Classe de evento Broker:Conversation Group](../../relational-databases/event-classes/broker-conversation-group-event-class.md)<br /><br /> [Classe de evento Broker:Corrupted Message](../../relational-databases/event-classes/broker-corrupted-message-event-class.md)<br /><br /> [Classe de evento Broker:Forwarded Message Dropped](../../relational-databases/event-classes/broker-forwarded-message-dropped-event-class.md)<br /><br /> [Classe de evento Broker:Forwarded Message Sent](../../relational-databases/event-classes/broker-forwarded-message-sent-event-class.md)<br /><br /> [Classe de evento Broker:Message Classify](../../relational-databases/event-classes/broker-message-classify-event-class.md)<br /><br /> [Classe de evento Broker:Message Drop](../../relational-databases/event-classes/broker-message-drop-event-class.md)<br /><br /> [Agente: Classe de evento Remote Message Ack](../../relational-databases/event-classes/broker-remote-message-ack-event-class.md)|  
|A [Categoria de Evento de Cursores](../../relational-databases/event-classes/cursors-event-category.md) contém as classes de evento que são produzidas por operações de cursor.|[Classe de evento CursorClose](../../relational-databases/event-classes/cursorclose-event-class.md)<br /><br /> [Classe de evento CursorExecute](../../relational-databases/event-classes/cursorexecute-event-class.md)<br /><br /> [Classe de evento CursorImplicitConversion](../../relational-databases/event-classes/cursorimplicitconversion-event-class.md)<br /><br /> [Classe de evento CursorOpen](../../relational-databases/event-classes/cursoropen-event-class.md)<br /><br /> [Classe de evento CursorPrepare](../../relational-databases/event-classes/cursorprepare-event-class.md)<br /><br /> [Classe de evento CursorRecompile](../../relational-databases/event-classes/cursorrecompile-event-class.md)<br /><br /> [Classe de evento CursorUnprepare](../../relational-databases/event-classes/cursorunprepare-event-class.md)|  
|A [Categoria de evento CLR](../../relational-databases/event-classes/clr-event-category.md) inclui classes de evento que são produzidas pela execução de objetos CLR (Common Language Runtime) do .NET.|[Classe de evento Assembly Load](http://msdn.microsoft.com/library/cfb0b69d-4ce0-4067-a3df-d82775e57886)|  
|A [Categoria de Evento de Banco de Dados](../../relational-databases/event-classes/database-event-category.md) contém as classes de evento que são produzidas quando os arquivos de dados ou de log aumentam ou diminuem automaticamente.|[Classe de evento Data File Auto Grow](../../relational-databases/event-classes/data-file-auto-grow-event-class.md)<br /><br /> [Classe de evento Data File Auto Shrink](../../relational-databases/event-classes/data-file-auto-shrink-event-class.md)<br /><br /> [Classe de evento Database Mirroring State Change](../../relational-databases/event-classes/database-mirroring-state-change-event-class.md)<br /><br /> [Classe de evento Log File Auto Grow](../../relational-databases/event-classes/log-file-auto-grow-event-class.md)<br /><br /> [Classe de evento Log File Auto Shrink](../../relational-databases/event-classes/log-file-auto-shrink-event-class.md)|  
|A [Categoria de Evento de Reprovação](../../relational-databases/event-classes/deprecation-event-category.md) inclui eventos relacionados à reprovação.|[Classe de evento Deprecation Announcement](../../relational-databases/event-classes/deprecation-announcement-event-class.md)<br /><br /> [Classe de evento Deprecation Final Support](../../relational-databases/event-classes/deprecation-final-support-event-class.md)|  
|A [Categoria de Evento de Erros e Avisos &#40;Mecanismo de Banco de Dados&#41;](../../relational-databases/event-classes/errors-and-warnings-event-category-database-engine.md) contém as classes de evento que são produzidas quando um erro ou aviso do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é retornado. Por exemplo, se ocorrer um erro durante a compilação de um procedimento armazenado ou se ocorrer uma exceção no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].|[Classe de evento Attention](../../relational-databases/event-classes/attention-event-class.md)<br /><br /> [Classe de evento Background Job Error](../../relational-databases/event-classes/background-job-error-event-class.md)<br /><br /> [Classe de evento Blocked Process Report](../../relational-databases/event-classes/blocked-process-report-event-class.md)<br /><br /> [Classe de evento CPU Threshold Exceeded](../../relational-databases/event-classes/cpu-threshold-exceeded-event-class.md)<br /><br /> [Classe de evento ErrorLog](../../relational-databases/event-classes/errorlog-event-class.md)<br /><br /> [Classe de evento EventLog](../../relational-databases/event-classes/eventlog-event-class.md)<br /><br /> [Classe de evento Exception](../../relational-databases/event-classes/exception-event-class.md)<br /><br /> [Classe de evento Exchange Spill](../../relational-databases/event-classes/exchange-spill-event-class.md)<br /><br /> [Classe de evento Execution Warnings](../../relational-databases/event-classes/execution-warnings-event-class.md)<br /><br /> [Classe de evento Hash Warning](../../relational-databases/event-classes/hash-warning-event-class.md)<br /><br /> [Classe de evento Missing Column Statistics](../../relational-databases/event-classes/missing-column-statistics-event-class.md)<br /><br /> [Classe de evento Missing Join Predicate](../../relational-databases/event-classes/missing-join-predicate-event-class.md)<br /><br /> [Classe de evento Sort Warnings](../../relational-databases/event-classes/sort-warnings-event-class.md)<br /><br /> [Classe de evento User Error Message](../../relational-databases/event-classes/user-error-message-event-class.md)|  
|A [Categoria de Evento de Texto Completo](../../relational-databases/event-classes/full-text-event-category.md) contém as classes de evento que são produzidas quando as pesquisas de texto completo são iniciadas, interrompidas ou paradas.|[Classe de evento FT:Crawl Aborted](../../relational-databases/event-classes/ft-crawl-aborted-event-class.md)<br /><br /> [Classe de evento FT:Crawl Started](../../relational-databases/event-classes/ft-crawl-started-event-class.md)<br /><br /> [Classe de evento FT:Crawl Stopped](../../relational-databases/event-classes/ft-crawl-stopped-event-class.md)|  
|A [Categoria de Evento de Bloqueios](../../relational-databases/event-classes/locks-event-category.md) contém as classes de evento que são produzidas quando um bloqueio é adquirido, cancelado, liberado, ou quando qualquer outra ação é executada nele.|[Classe de evento Deadlock Graph](../../relational-databases/event-classes/deadlock-graph-event-class.md)<br /><br /> [Classe de evento Lock:Acquired](../../relational-databases/event-classes/lock-acquired-event-class.md)<br /><br /> [Classe de evento Lock:Cancel](../../relational-databases/event-classes/lock-cancel-event-class.md)<br /><br /> [Classe de evento Lock:Deadlock Chain](../../relational-databases/event-classes/lock-deadlock-chain-event-class.md)<br /><br /> [Classe de evento Lock:Deadlock](../../relational-databases/event-classes/lock-deadlock-event-class.md)<br /><br /> [Classe de evento Lock:Escalation](../../relational-databases/event-classes/lock-escalation-event-class.md)<br /><br /> [Classe de evento Lock:Released](../../relational-databases/event-classes/lock-released-event-class.md)<br /><br /> [Classe de evento Lock:Timeout &#40;timeout &#62; 0&#41;](../../relational-databases/event-classes/lock-timeout-timeout-0-event-class.md)<br /><br /> [Classe de evento Lock:Timeout](../../relational-databases/event-classes/lock-timeout-event-class.md)|  
|A [Categoria de Evento de Objetos](../../relational-databases/event-classes/objects-event-category.md) contém as classes de evento que são produzidas quando os objetos de banco de dados são criados, abertos, fechados, descartados ou excluídos.|[Classe de evento Auto Stats](../../relational-databases/event-classes/auto-stats-event-class.md)<br /><br /> [Classe de evento Object:Altered](../../relational-databases/event-classes/object-altered-event-class.md)<br /><br /> [Classe de evento Object:Created](../../relational-databases/event-classes/object-created-event-class.md)<br /><br /> [Classe de evento Object:Deleted](../../relational-databases/event-classes/object-deleted-event-class.md)|  
|A [Categoria de Evento OLEDB](../../relational-databases/event-classes/oledb-event-category.md) contém as classes de evento que são produzidas pelo OLE DB.|[Classe de evento OLEDB Call](../../relational-databases/event-classes/oledb-call-event-class.md)<br /><br /> [Classe de evento OLEDB DataRead](../../relational-databases/event-classes/oledb-dataread-event-class.md)<br /><br /> [Classe de evento OLEDB Errors](../../relational-databases/event-classes/oledb-errors-event-class.md)<br /><br /> [Classe de evento OLEDB Provider Information](../../relational-databases/event-classes/oledb-provider-information-event-class.md)<br /><br /> [Classe de evento OLEDB QueryInterface](../../relational-databases/event-classes/oledb-queryinterface-event-class.md)|  
|A [Categoria de Evento de Desempenho](../../relational-databases/event-classes/performance-event-category.md) contém as classes de evento que são produzidas quando os operadores DML (linguagem de manipulação de dados) do SQL são executados.|[Classe de evento Grau de Paralelismo &#40;7.0 Insert&#41;](../../relational-databases/event-classes/degree-of-parallelism-7-0-insert-event-class.md)<br /><br /> [Classe de evento Performance Statistics](../../relational-databases/event-classes/performance-statistics-event-class.md)<br /><br /> [Classe de evento Showplan All](../../relational-databases/event-classes/showplan-all-event-class.md)<br /><br /> [Classe de evento Showplan All for Query Compile](../../relational-databases/event-classes/showplan-all-for-query-compile-event-class.md)<br /><br /> [Classe de Evento Showplan Statistics Profile](../../relational-databases/event-classes/showplan-statistics-profile-event-class.md)<br /><br /> [Classe de evento Showplan Text](../../relational-databases/event-classes/showplan-text-event-class.md)<br /><br /> [Texto do plano de execução &#40;Não codificado&#41; Classe de Evento](../../relational-databases/event-classes/showplan-text-unencoded-event-class.md)<br /><br /> [Classe de evento Showplan XML](../../relational-databases/event-classes/showplan-xml-event-class.md)<br /><br /> [Classe de evento Showplan XML for Query Compile](../../relational-databases/event-classes/showplan-xml-for-query-compile-event-class.md)<br /><br /> [Classe de evento Showplan XML Statistics Profile](../../relational-databases/event-classes/showplan-xml-statistics-profile-event-class.md)<br /><br /> [Classe de evento SQL:FullTextQuery](../../relational-databases/event-classes/sql-fulltextquery-event-class.md)|  
|A [Categoria de Evento Relatório de Progresso](../../relational-databases/event-classes/progress-report-event-category.md) inclui a classe de evento **Relatório de Progresso: Operação de Índice Online** .|[Classe de evento Progress Report: Online Index Operation](../../relational-databases/event-classes/progress-report-online-index-operation-event-class.md)|  
|A [Categoria de Evento de Varreduras](../../relational-databases/event-classes/scans-event-category.md) contém as classes de evento que são produzidas quando tabelas e índices são verificados.|[Classe de evento Scan:Started](../../relational-databases/event-classes/scan-started-event-class.md)<br /><br /> [Classe de evento Scan:Stopped](../../relational-databases/event-classes/scan-stopped-event-class.md)|  
|A [Categoria de evento de Auditoria de Segurança](../../relational-databases/event-classes/security-audit-event-category-sql-server-profiler.md) contém as classes de evento que são usadas para auditoria da atividade do servidor.|[Classe de evento Audit Add DB User](../../relational-databases/event-classes/audit-add-db-user-event-class.md)<br /><br /> [Classe de evento Audit Add Login to Server Role](../../relational-databases/event-classes/audit-add-login-to-server-role-event-class.md)<br /><br /> [Classe de evento Audit Add Member to DB Role](../../relational-databases/event-classes/audit-add-member-to-db-role-event-class.md)<br /><br /> [Classe de evento Audit Add Role](../../relational-databases/event-classes/audit-add-role-event-class.md)<br /><br /> [Classe de evento Audit Addlogin](../../relational-databases/event-classes/audit-addlogin-event-class.md)<br /><br /> [Classe de evento Audit App Role Change Password](../../relational-databases/event-classes/audit-app-role-change-password-event-class.md)<br /><br /> [Classe de evento Audit Backup e Restore](../../relational-databases/event-classes/audit-backup-and-restore-event-class.md)<br /><br /> [Classe de evento Audit Broker Conversation](../../relational-databases/event-classes/audit-broker-conversation-event-class.md)<br /><br /> [Classe de evento Audit Broker Login](../../relational-databases/event-classes/audit-broker-login-event-class.md)<br /><br /> [Classe de evento Audit Change Audit](../../relational-databases/event-classes/audit-change-audit-event-class.md)<br /><br /> [Classe de evento Audit Change Database Owner](../../relational-databases/event-classes/audit-change-database-owner-event-class.md)<br /><br /> [Classe de evento Audit Database Management](../../relational-databases/event-classes/audit-database-management-event-class.md)<br /><br /> [Classe de evento Audit Database Object Access](../../relational-databases/event-classes/audit-database-object-access-event-class.md)<br /><br /> [Classe de evento Audit Database Object GDR](../../relational-databases/event-classes/audit-database-object-gdr-event-class.md)<br /><br /> [Classe de evento Audit Database Object Management](../../relational-databases/event-classes/audit-database-object-management-event-class.md)<br /><br /> [Classe de evento Audit Database Object Take Ownership](../../relational-databases/event-classes/audit-database-object-take-ownership-event-class.md)<br /><br /> [Classe de evento Audit Database Operation](../../relational-databases/event-classes/audit-database-operation-event-class.md)<br /><br /> [Classe de evento Audit Database Principal Impersonation](../../relational-databases/event-classes/audit-database-principal-impersonation-event-class.md)<br /><br /> [Classe de evento Audit Database Principal Management](../../relational-databases/event-classes/audit-database-principal-management-event-class.md)<br /><br /> [Classe de evento Audit Database Scope GDR](../../relational-databases/event-classes/audit-database-scope-gdr-event-class.md)<br /><br /> [Classe de evento Audit DBCC](../../relational-databases/event-classes/audit-dbcc-event-class.md)<br /><br /> [Classe de evento Audit Login Change Password](../../relational-databases/event-classes/audit-login-change-password-event-class.md)<br /><br /> [Classe de evento Audit Login Change Property](../../relational-databases/event-classes/audit-login-change-property-event-class.md)<br /><br /> [Classe de evento Audit Login](../../relational-databases/event-classes/audit-login-event-class.md)<br /><br /> [Classe de evento Audit Login Failed](../../relational-databases/event-classes/audit-login-failed-event-class.md)<br /><br /> [Classe de evento Audit Login GDR](../../relational-databases/event-classes/audit-login-gdr-event-class.md)<br /><br /> [Classe de evento Audit Logout](../../relational-databases/event-classes/audit-logout-event-class.md)<br /><br /> [Classe de evento Audit Object Derived Permission](../../relational-databases/event-classes/audit-object-derived-permission-event-class.md)<br /><br /> [Classe de evento Audit Schema Object Access](../../relational-databases/event-classes/audit-schema-object-access-event-class.md)<br /><br /> [Classe de evento Audit Schema Object GDR](../../relational-databases/event-classes/audit-schema-object-gdr-event-class.md)<br /><br /> [Classe de evento Audit Schema Object Management](../../relational-databases/event-classes/audit-schema-object-management-event-class.md)<br /><br /> [Classe de evento Audit Schema Object Take Ownership](../../relational-databases/event-classes/audit-schema-object-take-ownership-event-class.md)<br /><br /> [Classe de evento Audit Server Alter Trace](../../relational-databases/event-classes/audit-server-alter-trace-event-class.md)<br /><br /> [Classe de evento Audit Server Object GDR](../../relational-databases/event-classes/audit-server-object-gdr-event-class.md)<br /><br /> [Classe de evento Audit Server Object Management](../../relational-databases/event-classes/audit-server-object-management-event-class.md)<br /><br /> [Classe de evento Audit Server Object Take Ownership](../../relational-databases/event-classes/audit-server-object-take-ownership-event-class.md)<br /><br /> [Classe de evento Audit Server Operation](../../relational-databases/event-classes/audit-server-operation-event-class.md)<br /><br /> [Classe de evento Audit Server Principal Impersonation](../../relational-databases/event-classes/audit-server-principal-impersonation-event-class.md)<br /><br /> [Classe de evento Audit Server Principal Management](../../relational-databases/event-classes/audit-server-principal-management-event-class.md)<br /><br /> [Classe de evento Audit Server Scope GDR](../../relational-databases/event-classes/audit-server-scope-gdr-event-class.md)<br /><br /> [Classe de evento Audit Server Starts and Stops](../../relational-databases/event-classes/audit-server-starts-and-stops-event-class.md)<br /><br /> [Classe de evento Audit Statement Permission](../../relational-databases/event-classes/audit-statement-permission-event-class.md)|  
|A [Categoria de Evento de Servidor](../../relational-databases/event-classes/server-event-category.md) contém eventos gerais de servidor.|[Classe de evento Mount Tape](../../relational-databases/event-classes/mount-tape-event-class.md)<br /><br /> [Classe de evento Server Memory Change](../../relational-databases/event-classes/server-memory-change-event-class.md)<br /><br /> [Classe de evento Trace File Close](../../relational-databases/event-classes/trace-file-close-event-class.md)|  
|A [Categoria de Evento de Sessões](../../relational-databases/event-classes/sessions-event-category.md) contém as classes de evento produzidas por clientes que se conectam e desconectam de uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].|[Classe de evento ExistingConnection](../../relational-databases/event-classes/existingconnection-event-class.md)|  
|A [Categoria de Evento de Procedimentos Armazenados](../../relational-databases/event-classes/stored-procedures-event-category.md) inclui as classes de evento produzidas pela execução de procedimentos armazenados.|[Classe de evento PreConnect:Completed](../../relational-databases/event-classes/preconnect-completed-event-class.md)<br /><br /> [Classe de evento PreConnect:Starting](../../relational-databases/event-classes/preconnect-starting-event-class.md)<br /><br /> [Classe de evento RPC:Completed](../../relational-databases/event-classes/rpc-completed-event-class.md)<br /><br /> [Classe de evento RPC Output Parameter](../../relational-databases/event-classes/rpc-output-parameter-event-class.md)<br /><br /> [Classe de evento RPC:Starting](../../relational-databases/event-classes/rpc-starting-event-class.md)<br /><br /> [Classe de evento SP:CacheHit](../../relational-databases/event-classes/sp-cachehit-event-class.md)<br /><br /> [Classe de evento SP:CacheInsert](../../relational-databases/event-classes/sp-cacheinsert-event-class.md)<br /><br /> [Classe de evento SP:CacheMiss](../../relational-databases/event-classes/sp-cachemiss-event-class.md)<br /><br /> [Classe de evento SP:CacheRemove](../../relational-databases/event-classes/sp-cacheremove-event-class.md)<br /><br /> [Classe de evento SP:Completed](../../relational-databases/event-classes/sp-completed-event-class.md)<br /><br /> [Classe de evento SP:Recompile](../../relational-databases/event-classes/sp-recompile-event-class.md)<br /><br /> [Classe de evento SP:Starting](../../relational-databases/event-classes/sp-starting-event-class.md)<br /><br /> [Classe de evento SP:StmtCompleted](../../relational-databases/event-classes/sp-stmtcompleted-event-class.md)<br /><br /> [Classe de evento SP:StmtStarting](../../relational-databases/event-classes/sp-stmtstarting-event-class.md)|  
|A [Categoria de Evento de Transações](../../relational-databases/event-classes/transactions-event-category.md) contém as classes de evento produzidas pela execução de transações do Coordenador de transações distribuídas da [!INCLUDE[msCoName](../../includes/msconame-md.md)] ou pela gravação no log de transações.|[Classe de evento DTCTransaction](../../relational-databases/event-classes/dtctransaction-event-class.md)<br /><br /> [Classe de evento SQLTransaction](../../relational-databases/event-classes/sqltransaction-event-class.md)<br /><br /> [Classe de evento TM: Begin Tran Completed](../../relational-databases/event-classes/tm-begin-tran-completed-event-class.md)<br /><br /> [Classe de evento TM: Begin Tran Starting](../../relational-databases/event-classes/tm-begin-tran-starting-event-class.md)<br /><br /> [Classe de evento TM: Commit Tran Completed](../../relational-databases/event-classes/tm-commit-tran-completed-event-class.md)<br /><br /> [Classe de evento TM: Commit Tran Starting](../../relational-databases/event-classes/tm-commit-tran-starting-event-class.md)<br /><br /> [Classe de evento TM: Promote Tran Completed](../../relational-databases/event-classes/tm-promote-tran-completed-event-class.md)<br /><br /> [Classe de evento TM: Promote Tran Starting](../../relational-databases/event-classes/tm-promote-tran-starting-event-class.md)<br /><br /> [Classe de evento TM: Rollback Tran Completed](../../relational-databases/event-classes/tm-rollback-tran-completed-event-class.md)<br /><br /> [Classe de evento TM: Rollback Tran Starting](../../relational-databases/event-classes/tm-rollback-tran-starting-event-class.md)<br /><br /> [Classe de evento TM: Save Tran Completed](../../relational-databases/event-classes/tm-save-tran-completed-event-class.md)<br /><br /> [Classe de evento TM: Save Tran Starting](../../relational-databases/event-classes/tm-save-tran-starting-event-class.md)<br /><br /> [Classe de evento TransactionLog](../../relational-databases/event-classes/transactionlog-event-class.md)|  
|A [Categoria de Evento TSQL](../../relational-databases/event-classes/tsql-event-category.md) contém as classes de evento produzidas pela execução de instruções Transact-SQL passadas do cliente para uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .|[Classe de evento Exec Prepared SQL](../../relational-databases/event-classes/exec-prepared-sql-event-class.md)<br /><br /> [Classe de evento Prepare SQL](../../relational-databases/event-classes/prepare-sql-event-class.md)<br /><br /> [Classe de evento SQL:BatchCompleted](../../relational-databases/event-classes/sql-batchcompleted-event-class.md)<br /><br /> [Classe de evento SQL:BatchStarting](../../relational-databases/event-classes/sql-batchstarting-event-class.md)<br /><br /> [Classe de evento SQL:StmtCompleted](../../relational-databases/event-classes/sql-stmtcompleted-event-class.md)<br /><br /> [Classe de evento SQL:StmtRecompile](../../relational-databases/event-classes/sql-stmtrecompile-event-class.md)<br /><br /> [Classe de evento SQL:StmtStarting](../../relational-databases/event-classes/sql-stmtstarting-event-class.md)<br /><br /> [Classe de evento Unprepare SQL](../../relational-databases/event-classes/unprepare-sql-event-class.md)<br /><br /> [Classe de evento XQuery Static Type](../../relational-databases/event-classes/xquery-static-type-event-class.md)|  
|A [Categoria de Evento Configurável pelo Usuário](../../relational-databases/event-classes/user-configurable-event-category.md) inclui classes de evento que você pode definir.|[Classe de evento User-Configurable](../../relational-databases/event-classes/user-configurable-event-class.md)|  
  
## <a name="see-also"></a>Consulte também  
 [SQL Server Profiler](../../tools/sql-server-profiler/sql-server-profiler.md)  
  
  