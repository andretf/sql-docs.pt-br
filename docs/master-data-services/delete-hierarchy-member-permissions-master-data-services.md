---
title: "Excluir permiss&#245;es de membro de hierarquia (Master Data Services) | Microsoft Docs"
ms.custom: ""
ms.date: "03/01/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "master-data-services"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "excluindo permissões de membro [Master Data Services]"
  - "membros [Master Data Services], excluindo permissões"
  - "permissões [Master Data Services], excluindo permissões de membro"
ms.assetid: 7f22d5e2-70c1-422c-99c2-e995a47d812a
caps.latest.revision: 6
author: "sabotta"
ms.author: "carlasab"
manager: "jhubbard"
caps.handback.revision: 6
---
# Excluir permiss&#245;es de membro de hierarquia (Master Data Services)
  No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], exclua as permissões do objeto de modelo para remover as atribuições feitas.  
  
## Pré-requisitos  
 Para executar esse procedimento:  
  
-   Você deve ter permissão para acessar a área funcional **Permissões de Usuário e Grupo** .  
  
-   Você deve ser um administrador de modelo. Para obter mais informações, veja [Administradores &#40;Master Data Services&#41;](../master-data-services/administrators-master-data-services.md).  
  
### Para excluir permissões de membro de hierarquia  
  
1.  No [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], clique em **Permissões de Usuário e Grupo**.  
  
2.  Na página **Usuários** ou **Grupos** , selecione a linha do usuário ou grupo que deseja editar.  
  
3.  Clique em **Editar usuário selecionado**.  
  
4.  Clique na guia **Membros da Hierarquia**.  
  
5.  Na lista **Modelo**, selecione um modelo.  
  
6.  Na lista **Versão** , selecione uma versão.  
  
7.  Clique em **Editar**.  
  
8.  Localize o nó de árvore com a permissão, no painel **Permissões de Membro de Hierarquia**.  
  
9. Clique no nó de árvore e em **Nenhum** no menu de contexto.  
  
    > [!NOTE]  
    >  Você não poderá remover uma permissão de um usuário se a permissão for herdada de um grupo. Em vez disso, você deve remover a permissão do grupo.  
  
10. Clique em **Salvar**.  
  
## Consulte também  
 [Permissões de membro de hierarquia &#40;Master Data Services&#41;](../master-data-services/hierarchy-member-permissions-master-data-services.md)   
 [Atribuir permissões de membro de hierarquia &#40;Master Data Services&#41;](../master-data-services/assign-hierarchy-member-permissions-master-data-services.md)  
  
  