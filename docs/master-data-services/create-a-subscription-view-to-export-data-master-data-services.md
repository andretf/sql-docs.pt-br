---
title: "Criar uma exibição de assinatura para exportar dados (Master Data Services) | Microsoft Docs"
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-non-specified
ms.prod_service: mds
ms.service: 
ms.component: non-specific
ms.reviewer: 
ms.suite: sql
ms.technology:
- master-data-services
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- subscription views [Master Data Services], creating
- creating subscription views [Master Data Services]
ms.assetid: a5e28961-af16-414a-9845-d2e06aac5214
caps.latest.revision: 
author: leolimsft
ms.author: lle
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: eda098f740c6ffa5bf7bbb4025b6f7d181af608d
ms.sourcegitcommit: 6ac1956307d8255dc544e1063922493b30907b80
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/05/2018
---
# <a name="create-a-subscription-view-to-export-data-master-data-services"></a>Criar uma exibição de assinatura para exportar dados (Master Data Services)
  Crie uma exibição de assinatura para exportar dados do Master Data Services para sistemas de assinatura. Você está criando uma exibição para seus dados no banco de dados do [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .  
  
## <a name="prerequisites"></a>Prerequisites  
 Para executar esse procedimento:  
  
-   Você deve ter permissão para acessar a área funcional **Gerenciamento de Integração** . Para obter mais informações, consulte [Permissões de área funcional &#40;Master Data Services&#41;](../master-data-services/functional-area-permissions-master-data-services.md).  
  
-   Você deve ser um administrador de modelo. Para obter mais informações, veja [Administradores &#40;Master Data Services&#41;](../master-data-services/administrators-master-data-services.md).  
  
### <a name="to-create-and-edit-a-subscription-view"></a>Para criar e editar uma exibição de assinatura  
  
1.  No [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], clique em **Gerenciamento de Integração**.  
  
2.  Da barra de menus, clique em **Criar Exibições**.  
  
3.  Na página **Exibições de Assinatura** , clique em **Adicionar** para criar uma exibição ou clique em **Editar** para editar uma exibição. Um painel é exibido no lado direito.  
  
4.  No painel **Criar Exibição de Assinatura** , na caixa **Nome** , digite um nome para a exibição.  
  
     No painel **Editar Exibição de Assinatura** , na caixa **Nome** , digite o nome atualizado para a exibição.  
  
5.  Na lista **Modelo** , selecione um modelo.  
  
6.  Selecione **Incluir membros excluídos de modo reversível**para incluir membros excluídos de modo reversível à exibição.  
  
7.  Selecione a opção **Versão** ou **Sinalizador de Versão** em **Opções de Versão**e, em seguida, selecione da lista correspondente.  
  
    > [!TIP]  
    >  Crie uma exibição de assinatura com base em um sinalizador de versão. Quando você bloqueia uma versão, pode reatribuir o sinalizador a uma versão aberta sem atualizar a exibição de assinatura.  
  
8.  Selecione a opção **Entidade** ou **Hierarquia derivada** na opção **Fontes de Dados** e, em seguida, selecione da lista correspondente.  
  
9. Selecione um formato de exibição de assinatura na lista **Formato** .  
  
10. Se você escolheu **Níveis Explícitos** ou **Níveis Derivados** da lista **Formato** , digite o número de níveis na hierarquia para incluir na exibição.  
  
11. Clique em **Salvar**.  
  
## <a name="view-information"></a>Informações de Exibição  
 Para cada exibição criada, uma linha com dez colunas é adicionada à grade. A tabela a seguir descreve as colunas.  
  
|coluna|Description|  
|------------|-----------------|  
|Status|O status da exibição.<br /><br /> Quando você clica em **Salvar**, a imagem ![Ícone para o status de atualização](../master-data-services/media/mds-statusicon-updating.png "Ícone para o status de atualização") é exibida, indicando que a exibição está sendo atualizada.<br /><br /> Se houver erros ao criar ou editar uma exibição, a imagem ![Ícone para o status de erro](../master-data-services/media/mds-statusicon-error.png "Ícone para o status de erro") será exibida.<br /><br /> Caso contrário, o status será OK e a imagem ![Ícone para o status OK](../master-data-services/media/mds-statusicon-ok.png "Ícone para o status OK") será exibida.|  
|Nome|O nome da exibição de assinatura.|  
|Modelo|O nome do modelo.|  
|Versão|O nome da versão.|  
|Sinalizador de Versão|O nome do sinalizador de versão.|  
|Hierarquia derivada|O nome da hierarquia derivada.|  
|Entidade|O nome da entidade.|  
|Formato|Especifica o tipo dos dados na exibição.|  
|Nível|Especifica o número de níveis na exibição, que é usado apenas para os formatos de Nível explícito ou Nível derivado|  
|Incluir membros excluídos|Indica se membros excluídos de forma reversível são incluídos na exibição.|  
  
 Quando você clica em uma exibição, as informações a seguir são exibidas.  
  
-   **Criada Por**: o nome do usuário que criou a exibição.  
  
-   **Em**: obtém a data e a hora em que a exibição foi criada.  
  
-   **Atualizada Por**: o nome do usuário que atualizou a exibição pela última vez.  
  
-   **Em**: obtém a data e a hora em que a exibição foi atualizada pela última vez.  
  
## <a name="see-also"></a>Consulte Também  
 [Visão geral: Exportando dados &#40;Master Data Services&#41;](../master-data-services/overview-exporting-data-master-data-services.md)   
 [Excluir uma exibição de assinatura &#40;Master Data Services&#41;](../master-data-services/delete-a-subscription-view-master-data-services.md)   
 [Criar um sinalizador de versão &#40;Master Data Services&#41;](../master-data-services/create-a-version-flag-master-data-services.md)  
  
  
