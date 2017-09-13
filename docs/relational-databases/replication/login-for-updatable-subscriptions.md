---
title: "Logon para assinaturas atualizáveis | Microsoft Docs"
ms.custom: 
ms.date: 08/25/2016
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- replication
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sql13.rep.newsubwizard.updatablesubscriptionslogin.f1
ms.assetid: 301ea227-0455-40ba-9009-d38f8676b325
caps.latest.revision: 18
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 8a8e5888afba843d601f6dc85395c52b08b9b597
ms.contentlocale: pt-br
ms.lasthandoff: 06/22/2017

---
# <a name="login-for-updatable-subscriptions"></a>Logon para Assinaturas Atualizáveis
  Para a atualização imediata, se você selecionou **Replicar** na página **Assinaturas Atualizáveis** desse assistente, terá de especificar uma conta no Assinante na qual as conexões com o Publicador são feitas. 
  
 Conexões são usadas pelos gatilhos acionados no Assinante e propagam as alterações no Publicador. Essa conta é necessária mesmo que você selecionou **Colocar alterações na fila e confirmar quando possível** na página **Assinaturas Atualizáveis**. Por padrão, o Assistente para Nova Assinatura configura a atualização na fila com a capacidade de alternar para a atualização imediata, se necessário.  
  
> **IMPORTANTE:** A conta especificada para a conexão só deve receber permissão para inserir, atualizar e excluir dados nas exibições criadas pela replicação no banco de dados de publicação. Ela não deve receber nenhuma permissão adicional. Conceda permissões para Exibições no banco de dados de publicação nomeadas no formato **syncobj_***\<HexadecimalNumber>* para a conta configurada em cada Assinante.  
  
 Há três opções disponíveis para o tipo de conexão:  
  
-   Um servidor vinculado ou remoto que você já definiu.  
  
-   Um servidor vinculado que a replicação cria; a conexão é feita com as credenciais que você especifica nesse assistente.  
  
-   Um servidor vinculado que a replicação cria; a conexão é feita com as credenciais do usuário que faz a alteração no Assinante.  
  
 As duas primeiras opções podem ser especificadas nesse assistente. A última opção só pode ser especificada com o uso de [sp_link_publication &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-link-publication-transact-sql.md); especifique um valor igual a **1** para o parâmetro **@security_mode**.  
  
## <a name="options"></a>Opções  
 **Criar um servidor vinculado que conecta usando o seguinte logon de Autenticação do SQL Server:**  
 A replicação cria um servidor vinculado usando as credenciais especificadas nos campos **Logon** e **Senha** .  
  
 **Logon**  
 Insira um logon [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que tenha somente as permissões descritas neste tópico.  
  
 **Senha**  
 Insira uma senha forte para o logon especificado em **Logon**.  
    
 **Usar servidor vinculado ou remoto já definido.**  
 Essa opção requer um servidor vinculado ou remoto já definido. Para obter mais informações, consulte [Servidores vinculados &#40;Mecanismo de Banco de Dados&#41;](../../relational-databases/linked-servers/linked-servers-database-engine.md) e [Servidores remotos](../../database-engine/configure-windows/remote-servers.md). Verifique se o logon usado para o servidor vinculado ou servidor remoto tem uma senha forte e somente as permissões descritas nesse tópico.  
  
## <a name="see-also"></a>Consulte também  
 [Criar uma assinatura atualizável em uma publicação transacional](https://msdn.microsoft.com/library/ms152769.aspx)   
 [Exibir e modificar configurações de segurança de replicação](../../relational-databases/replication/security/view-and-modify-replication-security-settings.md)   
 [Assinaturas atualizáveis para replicação transacional](../../relational-databases/replication/transactional/updatable-subscriptions-for-transactional-replication.md)   
 [Assinar Publicações](../../relational-databases/replication/subscribe-to-publications.md)  
  
  
