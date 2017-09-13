---
title: Exibir o log de erros do SQL Server (SQL Server Management Studio) | Microsoft Docs
ms.custom: 
ms.date: 07/29/2016
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- viewing logs
- displaying logs
- errors [SQL Server], logs
- logs [SQL Server], SQL Server error logs
- logs [SQL Server], viewing
ms.assetid: 55f468ba-146c-4ab3-95cd-d35d051afd12
caps.latest.revision: 14
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 4acdc87a3317c38b5b19235dae681bce426244e3
ms.contentlocale: pt-br
ms.lasthandoff: 06/22/2017

---
# <a name="view-the-sql-server-error-log-sql-server-management-studio"></a>Exibir o log de erros do SQL Server (SQL Server Management Studio)
  O log de erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] contém eventos definidos pelo usuário e alguns eventos do sistema que serão úteis para a solução de problemas. 
  

  ## <a name="how-to-view-the-logs"></a>Como exibir os logs
1.  No SSMS, selecione **Pesquisador de Objetos**

>Para **abrir** o Pesquisador de Objetos: atalho de teclado **F8**. Se preferir, no menu superior, clique em Exibir/Pesquisador de Objetos ![Object_explorer](../../relational-databases/performance/media/object-explorer.png) 


2.  No **Pesquisador de Objetos**, conecte-se a uma instância do SQL Server e expanda-a.
  
3.  Encontre e expanda a seção **Gerenciamento** (supondo que você tenha permissões para vê-la).

4.  Clique com o botão direito do mouse em **Logs do SQL Server**, selecione Exibir e escolha **Exibir Log do SQL Server**.
 ![View_SQLServer_Log_SSMS](../../relational-databases/performance/media/view-sqlserver-log-ssms.png) 
 
5.  O Visualizador do Arquivo de Log será exibido (pode levar um minuto) com uma lista de logs a serem exibidos.
  
6. Várias pessoas recomendaram a postagem útil [Identify location of the SQL Server Error Log file](https://www.mssqltips.com/) de [MSSQLTips.com](https://www.mssqltips.com/sqlservertip/2506/identify-location-of-the-sql-server-error-log-file/). Nela, você encontra informações muito interessantes – não deixe de conferir!
  
  
