---
title: Executar o Windows PowerShell no SQL Server Management Studio | Microsoft Docs
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: powershell
ms.service: 
ms.component: powershell
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1f841825-da1f-4062-9a81-3cdbab03845b
caps.latest.revision: "11"
author: stevestein
ms.author: sstein
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: 762d038aba38b2cbcb8906b729179aca6a6f7835
ms.sourcegitcommit: 779f3398e4e3f4c626d81ae8cedad153bee69540
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2018
---
# <a name="run-windows-powershell-from-sql-server-management-studio"></a>Executar o Windows PowerShell no SQL Server Management Studio
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../includes/appliesto-ss-asdb-asdw-pdw-md.md)]

Você pode iniciar sessões do Windows PowerShell no **Pesquisador de Objetos** no [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]. [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] inicia o Windows PowerShell, carrega o módulo do **SqlServer** e define o contexto de caminho ao nó associado na árvore do **Pesquisador de Objetos**.  
  

> [!NOTE]
> Há dois módulos do SQL Server PowerShell; **SqlServer** e **SQLPS**. O módulo **SQLPS** está incluído na instalação do SQL Server (para compatibilidade com versões anteriores), mas não está sendo atualizado. O módulo do PowerShell mais atualizado é o módulo do **SqlServer**. O módulo do **SqlServer** contém versões atualizadas dos cmdlets no **SQLPS** e também inclui novos cmdlets para dar suporte aos recursos mais recentes do SQL.  
> As versões anteriores do módulo do **SqlServer** *foram* incluídas no SQL Server Management Studio (SSMS), mas apenas nas versões 16.x do SSMS. Para usar o PowerShell com o SSMS 17.0 e versões posteriores, o módulo do **SqlServer** deve ser instalado da Galeria do PowerShell.
> Para instalar o módulo do **SqlServer**, consulte [Instalar o SQL Server PowerShell](download-sql-server-ps-module.md).



Quando você especificar a execução do PowerShell para um objeto no **Pesquisador de Objetos**, o [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] iniciará uma sessão do Windows PowerShell na qual os snap-ins do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell foram carregados e registrados. O caminho da sessão é predefinido no local do objeto no qual você clicou com o botão direito no Pesquisador de Objetos. Por exemplo, se você clicar com o botão direito do mouse no objeto de banco de dados [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] no Pesquisador de Objetos e selecionar **Iniciar PowerShell**, o caminho do Windows PowerShell será definido da seguinte forma:  
  
```  
SQLSERVER:\SQL\MyComputer\MyInstance\Databases\AdventureWorks2012>  
```  
  
## <a name="run-powershell"></a>Executar o PowerShell  
 **Para executar o PowerShell no SQL Server Management Studio**  
  
1.  Abra o **Pesquisador de Objetos**.  
  
2.  Navegue até o nó do objeto que será utilizado.  
  
3.  Clique com o botão direito do mouse no objeto e selecione **Iniciar PowerShell**.  
  
## <a name="permissions"></a>Permissões  
 Quando aberto no [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], o PowerShell não é executado com privilégios de Administrador, que podem impedir algumas atividades como chamadas ao WMI.  
  
## <a name="see-also"></a>Consulte Também  
 [SQL Server PowerShell](sql-server-powershell.md)  
  
  
