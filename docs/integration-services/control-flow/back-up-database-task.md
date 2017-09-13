---
title: Tarefa de banco de dados de backup | Microsoft Docs
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- integration-services
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sql13.dts.designer.backupdatabasetask.f1
helpviewer_keywords:
- database backups [Integration Services]
- Back Up Database task [Integration Services]
- backing up databases [Integration Services]
- transaction log backups [Integration Services]
- backing up transaction logs [Integration Services]
ms.assetid: b8839d71-13b7-41f2-a434-cb95020e79d7
caps.latest.revision: 46
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: a71821c8fc7710d86d819d65ef35878a2594f997
ms.contentlocale: pt-br
ms.lasthandoff: 08/03/2017

---
# <a name="back-up-database-task"></a>Tarefa de Backup de Banco de Dados
  A tarefa Backup de Banco de Dados executa vários tipos de backups de bancos de dados [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . Para obter mais informações, consulte [Back Up and Restore of SQL Server Databases](../../relational-databases/backup-restore/back-up-and-restore-of-sql-server-databases.md).  
  
 Usando a tarefa de Backup de Banco de Dados, um pacote poderá fazer backup de um único ou de vários bancos de dados. Se a tarefa fizer backup de um único banco de dados, você poderá escolher o componente de backup: o banco de dados ou seus arquivos e grupos de arquivos.  
  
## <a name="supported-recover-models-and-backup-types"></a>Modelos de recuperação e tipos de backup com suporte  
 A tabela a seguir relaciona os modelos de recuperação e tipos de backup que a tarefa de Backup de Banco de Dados oferece suporte.  
  
|Modelo de recuperação|Banco de dados|Diferenciais de bancos de dados|Log de transações|Arquivo ou diferencial de arquivo|  
|--------------------|--------------|---------------------------|---------------------|-------------------------------|  
|Simple (simples)|Required|Opcional|Sem suporte|Sem suporte|  
|Full (cheio)|Required|Opcional|Required|Opcional|  
|Bulk-logged|Required|Opcional|Required|Opcional|  
  
 A tarefa de Backup de Banco de Dados encapsula uma instrução BACKUP Transact-SQL. Para obter mais informações, consulte [BACKUP &#40;Transact-SQL&#41;](../../t-sql/statements/backup-transact-sql.md).  
  
## <a name="configuration-of-the-back-up-database-task"></a>Configuração da tarefa de Backup de Banco de Dados  
 Você pode definir propriedades por meio do [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer. Esta tarefa está na seção **Tarefas do Plano de Manutenção** da **Caixa de Ferramentas** , no Designer [!INCLUDE[ssIS](../../includes/ssis-md.md)] .  
  
 Para obter mais informações sobre as propriedades que podem ser definidas no [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, clique no tópico a seguir:  
  
-   [Tarefa Backup de Banco de Dados &#40;Plano de Manutenção&#41;](../../relational-databases/maintenance-plans/options-in-the-back-up-database-task-for-maintenance-plan.md)  
  
 Para obter mais informações sobre como definir essas propriedades no [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, clique no tópico a seguir:  
  
-   [Definir as propriedades de uma tarefa ou contêiner](http://msdn.microsoft.com/library/52d47ca4-fb8c-493d-8b2b-48bb269f859b)  
  
  