---
title: Compreender o gerenciamento de janelas do SQL Server Management Studio | Microsoft Docs
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.prod_service: sql-tools
ms.service: 
ms.component: ssms
ms.reviewer: 
ms.suite: sql
ms.technology: tools-ssms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- autohide [SQL Server Management Studio]
- SQL Server Management Studio [SQL Server], tool windows
- push pin [SQL Server Management Studio]
- tool windows [SQL Server Management Studio]
ms.assetid: bebf8383-dcaf-466e-84f5-63b81c9cfe52
caps.latest.revision: "4"
author: stevestein
ms.author: sstein
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: f290bba3b9312d861e63d54b19a8ad7dee5299a7
ms.sourcegitcommit: b6116b434d737d661c09b78d0f798c652cf149f3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/17/2018
---
# <a name="understand-sql-server-management-studio-windows-management"></a>Compreender o gerenciamento de janelas do SQL Server Management Studio
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../includes/appliesto-ss-asdb-asdw-pdw-md.md)] As janelas de ferramenta do [!INCLUDE[msCoName](../includes/msconame_md.md)] [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull_md.md)] são um sistema altamente funcional, flexível e eficiente que permite que você:  
  
-   Maximize a área de trabalho de usuário para desenvolvimento e administração.  
  
-   Reduza o número de janelas não usadas exibidas simultaneamente.  
  
-   Personalize facilmente o ambiente de usuário.  
  
A manipulação de janelas é crucial no ambiente do [!INCLUDE[ssManStudio](../includes/ssmanstudio_md.md)] . Os usuários podem acessar as ferramentas e janelas usadas frequentemente com facilidade. Os usuários também podem controlar quanto espaço eles desejam alocar para diferentes informações e o ambiente se responsabiliza por maximizar o espaço disponível para edição de consultas. As janelas podem ser movidas para locais diferentes na tela. Muitas janelas podem ser desencaixadas e arrastadas para fora do quadro do [!INCLUDE[ssManStudio](../includes/ssmanstudio_md.md)] . Isso é particularmente útil quando se usa mais de um monitor.  
  
Para aumentar o espaço de edição e manter a funcionalidade, todas as janelas oferecem o recurso de ocultar automaticamente, que exibe a janela como uma guia dentro de uma barra na borda do ambiente principal do [!INCLUDE[ssManStudio](../includes/ssmanstudio_md.md)] . Quando o ponteiro é colocado sobre uma dessas guias, a janela subjacente é exibida. O recurso de ocultar automaticamente uma janela pode ser alternado clicando-se no botão **Ocultar Automaticamente** , representado por um alfinete no canto superior direito da janela. Há também uma opção **Ocultar Tudo Automaticamente** no menu **Janela** .  
  
Alguns componentes podem ser configurados no modo com guias, onde os componentes aparecem como guias no mesmo local de encaixe, ou no modo de interface de múltiplos documentos (MDI) onde cada documento tem sua própria janela. Para configurar esse recurso, no menu **Ferramentas** , clique em **Opções**, clique em **Ambiente**e clique em **Geral**.  
  
> [!IMPORTANT]  
> Quando um logon (ou um usuário de banco de dados independente) se conecta e é autenticado, a conexão armazena informações de identidade sobre o logon. Para um logon de Autenticação do Windows, isso inclui informações sobre a associação em grupos do Windows. A identidade do logon permanece autenticada desde que a conexão seja mantida. Para forçar alterações na identidade, como uma redefinição de senha ou alteração na associação de grupo do Windows, o logon deve fazer logoff da autoridade de autenticação (Windows ou [!INCLUDE[ssNoVersion](../includes/ssnoversion_md.md)]) e fazer logon novamente. Um membro da função de servidor fixa ou **sysadmin** ou qualquer logon com a permissão **ALTER ANY CONNECTION** pode usar o comando **KILL** para terminar uma conexão e forçar um logon para reconectar. [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull_md.md)] pode reutilizar informações de conexão ao abrir várias conexões para as janelas do Pesquisador de Objetos e do Editor de Consultas. Feche todas as conexões para forçar a reconexão.  
  
> [!IMPORTANT]  
> Quando um logon (ou um usuário de banco de dados independente) se conecta e é autenticado, a conexão armazena em cache as informações de identidade sobre o logon. Para um logon de Autenticação do Windows, isso inclui informações sobre a associação em grupos do Windows. A identidade do logon permanece autenticada desde que a conexão seja mantida. Para forçar alterações na identidade, como uma redefinição de senha ou alteração na associação de grupo do Windows, o logon deve fazer logoff da autoridade de autenticação (Windows ou [!INCLUDE[ssNoVersion](../includes/ssnoversion_md.md)]) e fazer logon novamente. Um membro da função de servidor fixa ou **sysadmin** ou qualquer logon com a permissão **ALTER ANY CONNECTION** pode usar o comando **KILL** para terminar uma conexão e forçar um logon para reconectar. [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull_md.md)] pode reutilizar informações de conexão ao abrir várias conexões para as janelas do Pesquisador de Objetos e do Editor de Consultas. Feche todas as conexões para forçar a reconexão.  
  
## <a name="see-also"></a>Consulte Também  
[Usar o SQL Server Management Studio](../ssms/use-sql-server-management-studio.md)  
[O ambiente do SQL Server Management Studio](../ssms/the-sql-server-management-studio-environment.md)  
  
