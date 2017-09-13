---
title: "Aplicar imediatamente as permissões de membro (Master Data Services) | Microsoft Docs"
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- master-data-services
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- members [Master Data Services], applying permissions immediately
- permissions [Master Data Services], applying member permissions immediately
ms.assetid: 5b16de66-5c39-49f5-992f-402a9eb319aa
caps.latest.revision: 6
author: sabotta
ms.author: carlasab
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 1549958a5c84045eccbb52c5fac2f2f2b09d316e
ms.contentlocale: pt-br
ms.lasthandoff: 08/02/2017

---
# <a name="immediately-apply-member-permissions-master-data-services"></a>Aplicar permissões de membros imediatamente (Master Data Services)
  No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], em vez de esperar que a segurança de membro seja aplicada a intervalos regulares, você pode aplicar permissões de membro imediatamente.  
  
## <a name="prerequisites"></a>Pré-requisitos  
 Para executar esse procedimento:  
  
-   Você deverá ter permissão para executar o procedimento armazenado mdm.udpSecurityMemberProcessRebuildModel no banco de dados do [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]. Para obter mais informações, consulte [Segurança do objeto de banco de dados &#40;Master Data Services&#41;](../master-data-services/database-object-security-master-data-services.md).  
  
### <a name="to-immediately-apply-hierarchy-member-permissions"></a>Para aplicar permissões de membro da hierarquia imediatamente  
  
1.  Abra o [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] e conecte-se à instância do [!INCLUDE[ssDE](../includes/ssde-md.md)] de seu banco de dados do [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .  
  
2.  Crie uma nova consulta.  
  
3.  Digite o seguinte texto, substituindo *database* pelo nome do banco de dados e *Model_Name* pelo nome do modelo.  
  
    ```  
    USE [database];  
    GO  
  
    DECLARE @Model_ID INT;  
    SELECT @Model_ID = ID FROM mdm.tblModel WHERE [Name] = N'Model_Name';  
    EXEC [mdm].[udpSecurityMemberProcessRebuildModel] @Model_ID=@Model_ID, @ProcessNow=1;  
    GO  
    ```  
  
4.  Executa a consulta.  
  
## <a name="see-also"></a>Consulte também  
 [Atribuir permissões de membro de hierarquia &#40; Master Data Services &#41;](../master-data-services/assign-hierarchy-member-permissions-master-data-services.md)   
 [Permissões de membro de hierarquia &#40; Master Data Services &#41;](../master-data-services/hierarchy-member-permissions-master-data-services.md)  
  
  