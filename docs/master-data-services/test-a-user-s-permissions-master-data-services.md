---
title: "Testar permissões de um usuário (Master Data Services) | Microsoft Docs"
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
ms.assetid: 83a03b85-ea7f-4b4a-b19b-f7eca534ffae
caps.latest.revision: 
author: leolimsft
ms.author: lle
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: c5c84a7d6c678f7bf98d62ed63e78b6922243c7e
ms.sourcegitcommit: 6ac1956307d8255dc544e1063922493b30907b80
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/05/2018
---
# <a name="test-a-user39s-permissions-master-data-services"></a>Testar permissões de um usuário (Master Data Services)
  No [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], você pode criar um usuário de teste e registrar em log no aplicativo Web para testar permissions. Quando um usuário tenta acessar a URL [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , as credenciais do usuário são autenticadas. No Internet Explorer, as configurações de segurança controlam se isso ocorre automaticamente ou se o usuário deve inserir nome de usuário e senha. Para alterar essas configurações, conclua as seguintes etapas:  
  
### <a name="to-test-a-users-security"></a>Para testar a segurança de um usuário  
  
1.  No Internet Explorer 7 e posterior, clique em **Ferramentas**, em **Opções de Internet**e na guia **Segurança** .  
  
2.  Clique em **Intranet Local** e no botão **Nível Personalizado** .  
  
3.  Na seção **Autenticação de Usuário** , escolha **Aviso para nome de usuário e senha**.  
  
4.  Da próxima vez que você abrir a janela do navegador, será solicitado a fornecer um nome de usuário e senha.  
  
## <a name="see-also"></a>Consulte Também  
 [Segurança &#40;Master Data Services&#41;](../master-data-services/security-master-data-services.md)  
  
  
