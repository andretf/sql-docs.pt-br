---
title: Projetos (SQL Server Management Studio) | Microsoft Docs
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- tools-ssms
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c13af859-ca66-4e43-b76a-0650ac6566c0
caps.latest.revision: 4
author: stevestein
ms.author: sstein
manager: jhubbard
translationtype: Human Translation
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: e207a41546270197fa35cccd63348107db2d30f4
ms.lasthandoff: 04/11/2017

---
# <a name="projects-sql-server-management-studio"></a>Projetos (SQL Server Management Studio)
Um projeto do [!INCLUDE[ssManStudio](../../includes/ssmanstudio_md.md)] é uma coleção de scripts e arquivos logicamente relacionados que podem ser salvos em conjunto para administração e desenvolvimento de bancos de dados.  
  
## <a name="script-project-overview"></a>Visão geral de projeto de script  
[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] são exibidos no componente Gerenciador de Soluções do [!INCLUDE[ssManStudio](../../includes/ssmanstudio_md.md)]. Um projeto de script pode conter zero ou mais arquivos de projeto. Você pode adicionar um projeto a uma solução ou combinar mais de um projeto em uma solução.  
  
Projetos podem incluir o seguinte:  
  
-   **Conexões**. Uma conexão, persistente em um projeto, conterá informações de logon, nome de servidor, banco de dados padrão, protocolo preferencial, tipo de autenticação e propriedades de conexão. As informações de conexão podem ser armazenadas opcionalmente com um script (consulte abaixo).  
  
-   **SQLScripts**. Scripts SQL usados com frequência pelo usuário. Clicar duas vezes em um arquivo .sql dentro do projeto fará com que o Editor SQL abra o script selecionado.  
  
-   **Scripts MDX, DMX e XMLA**. Scripts MDX usados com frequência pelo usuário. Clicar duas vezes em um arquivo .mdx dentro do projeto fará com que o Editor SQL abra o script selecionado.  
  
-   **Diversos** Essa pasta pode ser usada para arquivos que não se ajustam a nenhum outro tipo de nó padrão, como um arquivo de texto que contenha os objetivos do projeto.  
  
Projetos também podem ser integrados em um sistema de controle do código-fonte.  
  
## <a name="connecting-to-an-instance-of-sql-server-from-a-script-project"></a>Conectando a uma instância do SQL Server de um projeto de script  
Um projeto de script pode conter conexões com uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]. Você pode se conectar a uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] em um projeto clicando na conexão. Isso abrirá uma janela do Script SQL conectada à instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] definida na conexão selecionada. Se você abrir um script MDX ou do [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] com uma conexão que use autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] , será solicitado a colocar a senha usando a caixa de diálogo **Conectar ao SQL Server** depois que o Editor tiver sido aberto e o script carregado.  
  
A conexão será fechada depois que a janela correspondente for fechada.  
  
Para modificar informações sobre uma conexão, use a janela de propriedades no [!INCLUDE[ssManStudio](../../includes/ssmanstudio_md.md)].  
  
## <a name="project-tasks"></a>Tarefas do projeto  
  
|Descrição da tarefa|Tópico|  
|--------------------|---------|  
|Descreve como criar um novo projeto em uma solução.|[Criar um projeto](../../ssms/solution/create-a-project.md)|  
|Descreve como adicionar um projeto existente a uma solução|[Adicionar um projeto existente a uma solução](../../ssms/solution/add-an-existing-project-to-a-solution.md)|  
|Descreve como alterar a localização padrão na qual arquivos de projeto são salvos.|[Alterar o local padrão dos projetos](../../ssms/solution/change-the-default-location-for-projects.md)|  
|Descreve como exibir as propriedades atuais de um projeto.|[Exibir propriedades do projeto](../../ssms/solution/view-project-properties.md)|  
|Descreve como adicionar novos itens, como conexões ou arquivos de script, a um projeto.|[Adicionar novos itens a um projeto](../../ssms/solution/add-new-items-to-a-project.md)|  
|Descreve como estabelecer as informações de conexão para uma consulta.|[Associar uma consulta a uma conexão em um projeto](../../ssms/solution/associate-a-query-with-a-connection-in-a-project.md)|  
|Descreve como alterar as informações de conexão para uma consulta.|[Alterar a conexão associada a uma consulta](../../ssms/solution/change-the-connection-associated-with-a-query.md)|  
|Descreve como alterar propriedades de conexão.|[Exibir ou alterar as propriedades de uma conexão em um projeto](../../ssms/solution/view-or-change-the-properties-of-a-connection-in-a-project.md)|  
  
## <a name="see-also"></a>Consulte também  
[Gerenciador de Soluções](../../ssms/solution/solution-explorer.md)  
[Soluções &amp;#40;SQL Server Management Studio&amp;#41;](../../ssms/solution/solutions-sql-server-management-studio.md)  
[Controle do código-fonte do Gerenciador de Soluções](https://msdn.microsoft.com/en-us/library/ms173879.aspx)  
  
