---
title: Criar uma etapa de trabalho Transact-SQL | Microsoft Docs
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- tools-ssms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Transact-SQL job step
- job steps [Transact-SQL]
- SQL Server Agent jobs, Transact-SQL step
ms.assetid: 69c571a7-debe-4063-9d38-e4b6a1e8e84c
caps.latest.revision: 5
author: stevestein
ms.author: sstein
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: 30d692969db247383010a268c9dd58ee5d2bd3ea
ms.contentlocale: pt-br
ms.lasthandoff: 06/22/2017

---
# <a name="create-a-transact-sql-job-step"></a>Create a Transact-SQL Job Step
Este tópico descreve como criar uma etapa de trabalho do [!INCLUDE[msCoName](../../includes/msconame_md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Agent que execute scripts [!INCLUDE[tsql](../../includes/tsql_md.md)] no [!INCLUDE[ssCurrent](../../includes/sscurrent_md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull_md.md)], [!INCLUDE[tsql](../../includes/tsql_md.md)]ou o SQL Server Management Objects.  
  
Esses scripts de etapa de trabalho podem chamar procedimentos armazenados e procedimentos armazenados estendidos. Uma mesma etapa de trabalho [!INCLUDE[tsql](../../includes/tsql_md.md)] pode conter vários lotes e comandos GO inseridos. Para obter mais informações sobre como criar um trabalho, consulte [Criando trabalhos](../../ssms/agent/create-jobs.md).  
  
**Neste tópico**  
  
-   **Antes de começar:**  
  
    [Segurança](#Security)  
  
-   **Para criar uma etapa de trabalho Transact-SQL usando:**  
  
    [SQL Server Management Studio](#SSMS)  
  
    [Transact-SQL](#TSQL)  
  
    [SQL Server Management Objects](#SMO)  
  
## <a name="BeforeYouBegin"></a>Antes de começar  
  
### <a name="Security"></a>Segurança  
Para obter informações detalhadas, consulte [Implement SQL Server Agent Security](../../ssms/agent/implement-sql-server-agent-security.md).  
  
## <a name="SSMS"></a>Usando o SQL Server Management Studio  
  
#### <a name="to-create-a-transact-sql-job-step"></a>Para criar uma etapa de trabalho Transact-SQL  
  
1.  No **Pesquisador de Objetos** , conecte-se a uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion_md.md)]e a expanda.  
  
2.  Expanda **SQL Server Agent**, crie um novo trabalho ou clique com o botão direito do mouse em um trabalho existente e clique em **Propriedades**.  
  
3.  Na caixa de diálogo **Propriedades do Trabalho** , clique na página **Etapas** e, em seguida, em **Nova**.  
  
4.  Na caixa de diálogo **Nova Etapa de Trabalho** , digite o **Nome da etapa**de trabalho.  
  
5.  Na lista **Tipo** , clique em **Script Transact-SQL (TSQL)**.  
  
6.  Na caixa **Comando** , digite os lotes de comandos [!INCLUDE[tsql](../../includes/tsql_md.md)] ou clique em **Abrir** para selecionar um arquivo [!INCLUDE[tsql](../../includes/tsql_md.md)] a ser usado como comando.  
  
7.  Clique em **Analisar** para verificar a sintaxe.  
  
8.  A mensagem "Êxito da análise" será exibida se a sintaxe estiver correta. Se um erro for encontrado, corrija a sintaxe antes de continuar.  
  
9. Clique na página **Avançado** para definir opções para a etapa de trabalho, tais como: que ação deve ser adotada em caso de êxito ou falha da etapa, quantas vezes o [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Agent deve tentar executar a etapa e em que arquivo ou tabela o [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Agent deve gravar a saída da etapa de trabalho. Só membros da função de servidor fixa **sysadmin** podem gravar a saída de etapas de trabalho em um arquivo do sistema operacional. Todos os usuários do SQL Server Agent podem registrar a saída em uma tabela.  
  
10. Se você for membro da função de servidor fixa **sysadmin** e desejar executar a etapa de trabalho como um logon SQL diferente, selecione esse logon na lista **Executar como usuário** .  
  
## <a name="TSQL"></a>Usando Transact-SQL  
  
#### <a name="to-create-a-transact-sql-job-step"></a>Para criar uma etapa de trabalho Transact-SQL  
  
1.  No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde_md.md)].  
  
2.  Na barra Padrão, clique em **Nova Consulta**.  
  
3.  Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.  
  
    ```  
    -- creates a job step that that uses Transact-SQL  
    USE msdb;  
    GO  
    EXEC sp_add_jobstep  
        @job_name = N'Weekly Sales Data Backup',  
        @step_name = N'Set database to read only',  
        @subsystem = N'TSQL',  
        @command = N'ALTER DATABASE SALES SET READ_ONLY',   
        @retry_attempts = 5,  
        @retry_interval = 5 ;  
    GO  
    ```  
  
Para obter mais informações, consulte [sp_add_jobstep (Transact-SQL)](http://msdn.microsoft.com/en-us/97900032-523d-49d6-9865-2734fba1c755).  
  
## <a name="SMO"></a>Usando o SQL Server Management Objects  
**Para criar uma etapa de trabalho Transact-SQL**  
  
Use a classe **JobStep** com uma linguagem de programação à sua escolha, como Visual Basic, Visual C# ou PowerShell.  
  
