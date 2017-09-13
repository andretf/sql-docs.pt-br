---
title: "Segurança do agente de distribuição (replicação ponto a ponto) | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- replication
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sql13.rep.p2pwizard.DA.f1
ms.assetid: def6bf26-c640-4caf-ad30-05d1e649541d
caps.latest.revision: 15
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: cca409052d10cc153417c1bd984273e1cad4bb9a
ms.contentlocale: pt-br
ms.lasthandoff: 06/22/2017

---
# <a name="distribution-agent-security-peer-to-peer-replication"></a>Segurança do Agente de Distribuição (replicação ponto a ponto)
  A página **Segurança do Agente de Distribuição** permite especificar as contas nas quais o Agente de Distribuição é executado e faz conexões com computadores em uma topologia ponto a ponto. Para obter informações sobre as permissões necessárias para os agentes e as melhores práticas de segurança da replicação, consulte [Modelo de segurança do agente de replicação](../../relational-databases/replication/security/replication-agent-security-model.md) e [Melhores práticas de segurança da replicação](../../relational-databases/replication/security/replication-security-best-practices.md).  
  
> [!NOTE]  
>  Se o Agente de Distribuição de uma assinatura já foi configurado em uma execução anterior deste assistente, você não poderá alterar as credenciais que ele usa neste assistente. Se você especificar credenciais novas, elas serão ignoradas. Para alterar as credenciais, use a caixa de diálogo **Propriedades de Assinatura** . Para obter mais informações, consulte [View and Modify Replication Security Settings](../../relational-databases/replication/security/view-and-modify-replication-security-settings.md).  
  
## <a name="options"></a>Opções  
 Clique no botão de propriedades (**...**) na linha de cada Assinante para acessar a caixa de diálogo **Segurança do Agente de Distribuição** . Clique em **Ajuda** na caixa de diálogo **Segurança do Agente de Distribuição** que é iniciada para obter mais informações sobre as permissões requeridas para contas usadas pelos agentes.  
  
 Depois que as configurações forem inseridas em uma das caixas de diálogo, as informações de conexão para o Assinante serão exibidas na grade.  
  
 **Agente para Assinante**  
 O nome de cada computador par.  
  
 **Banco de dados par**  
 O banco de dados no mesmo nível que funciona como um banco de dados de publicação e um banco de dados de assinatura.  
  
 **Conexão com o Distribuidor**  
 O contexto no qual a conexão com o Distribuidor é feita. Conexões locais sempre são feitas usando o contexto da conta do Windows na qual o agente é executado. Esse assistente cria assinaturas push (a conexão local é a conexão com o Distribuidor), portanto, esse campo sempre exibirá: **Representar '\<Domain>\\<Login\>'** ou **Representar '\<Computador>\\<Login\>'**.  
  
 **Conexão com o Assinante**  
 O contexto no qual a conexão com o Assinante é feita. A conexão pode ser feita usando o contexto da conta do Windows na qual o agente é executado ou no contexto de um logon no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . O campo exibe uma das seguintes opções: **Usar logon '\<Login>'**, **Representar '\<Domain>\\<Login\>'** ou **Representar '\<Computer>\\<Login\>'**. A[!INCLUDE[msCoName](../../includes/msconame-md.md)] recomenda que todas as conexões sejam feitas com o uso do contexto da conta do Windows.  
  
## <a name="see-also"></a>Consulte também  
 [Administrar uma topologia ponto a ponto &#40;programação Transact-SQL de replicação&#41;](../../relational-databases/replication/administration/administer-a-peer-to-peer-topology-replication-transact-sql-programming.md)   
 [Replicação transacional ponto a ponto](../../relational-databases/replication/transactional/peer-to-peer-transactional-replication.md)  
  
  