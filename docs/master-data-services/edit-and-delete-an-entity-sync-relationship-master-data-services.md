---
title: "Editar e excluir um relacionamento de sincroniza&#231;&#227;o de entidade (Master Data Services) | Microsoft Docs"
ms.custom: 
  - "SQL2016_New_Updated"
ms.date: "03/01/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "master-data-services"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9a5e37f3-352e-45a6-b4a0-6f98f83b4bd8
caps.latest.revision: 6
author: "sabotta"
ms.author: "carlasab"
manager: "jhubbard"
caps.handback.revision: 6
---
# Editar e excluir um relacionamento de sincroniza&#231;&#227;o de entidade (Master Data Services)
  A sincronização de entidade é uma sincronização unidirecional e repetível entre versões da entidade. Ela fornece uma maneira de compartilhar dados de entidade entre diferentes modelos. Você pode editar e excluir um relacionamento de sincronização que você criou.  
  
## Pré-requisitos  
 Pré-requisitos para executar um relacionamento de sincronização de entidade.  
  
-   Você deve ter permissão para acessar a área funcional Administração do Sistema. Para obter mais informações, consulte [Permissões de área funcional &#40;Master Data Services&#41;](../master-data-services/functional-area-permissions-master-data-services.md).  
  
-   Você deve ser um administrador de modelo do modelo de destino. Para obter mais informações, veja [Administradores &#40;Master Data Services&#41;](../master-data-services/administrators-master-data-services.md).  
  
-   É necessário ter, pelo menos, acesso de leitura à entidade de origem e a todos os seus atributos e membros.  
  
 Pré-requisitos para excluir um relacionamento de sincronização de entidade.  
  
-   Você deve ter permissão para acessar a área funcional Administração do Sistema. Para obter mais informações, consulte [Permissões de área funcional &#40;Master Data Services&#41;](../master-data-services/functional-area-permissions-master-data-services.md).  
  
-   Você deve ser um administrador de modelo do modelo de destino. Para obter mais informações, veja [Administradores &#40;Master Data Services&#41;](../master-data-services/administrators-master-data-services.md).  
  
 Considere o seguinte ao editar um relacionamento de sincronização de entidade.  
  
-   As entidades de origem e de destino devem ser em modelos diferentes.  
  
-   Um status de versão da entidade de destino não deve ser confirmado.  
  
-   Depois que o relacionamento de sincronização é estabelecido, o destino é imediatamente sincronizado com a origem.  
  
-   A versão da entidade de destino não pode ser uma versão da entidade de origem de outro relacionamento de sincronização.  
  
 Considere o seguinte ao executar um relacionamento de sincronização de entidade.  
  
-   Somente membros folha serão copiados  
  
-   Atributos baseados em domínio não serão copiados.  
  
-   Membros flexíveis excluídos não serão copiados.  
  
-   Sincronização não gera transações/históricos da entidade de destino.  
  
 **Para editar um relacionamento de sincronização de entidade**  
  
1.  No Master Data Manager, clique em **Administração do Sistema**.  
  
2.  Na página **Exibição de Modelos** , na barra de menus, aponte para **Gerenciar** e clique em **Sincronização de Entidades**.  
  
3.  Na página **Manutenção de Sincronização da Entidade** selecione um relacionamento de sincronização na grade.  
  
4.  Clique em **Editar**. Um painel aparece no lado direito.  
  
5.  Alterar **Frequência**. Selecione **Sincronização Sob Demanda**, ou selecione **Sincronização Automática** e configure uma frequência.  
  
6.  Clique em **Salvar**.  
  
 **Para excluir um relacionamento de sincronização de entidade**  
  
1.  No Master Data Manager, clique em **Administração do Sistema**.  
  
2.  Na página **Exibição de Modelos** , na barra de menus, aponte para **Gerenciar** e clique em **Sincronização de Entidades**.  
  
3.  Na página **Manutenção de Sincronização da Entidade** selecione um relacionamento de sincronização na grade.  
  
4.  Clique em **Excluir**.  
  
5.  Na caixa de diálogo de confirmação, clique em **OK**.  
  
## Consulte também  
 [Criar e executar uma relação de sincronização de entidade &#40;Master Data Services&#41;](../master-data-services/create-and-execute-an-entity-sync-relationship-master-data-services.md)   
 [Relação de sincronização de entidade &#40;Master Data Services&#41;](../master-data-services/entity-sync-relationship-master-data-services.md)  
  
  