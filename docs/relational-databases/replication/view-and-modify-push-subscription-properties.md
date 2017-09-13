---
title: Exibir e modificar propriedades de assinatura push | Microsoft Docs
ms.custom: 
ms.date: 03/16/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- replication
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- viewing replication properties
- push subscriptions [SQL Server replication], properties
- subscriptions [SQL Server replication], push
- push subscriptions [SQL Server replication], modifying
- modifying replication properties, push subscriptions
- modifying subscriptions, SQL Server Management Studio
ms.assetid: 801d2995-7aa5-4626-906e-c8190758ec71
caps.latest.revision: 37
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 3fc246be116d9468733d8b66f501717a4310bba2
ms.contentlocale: pt-br
ms.lasthandoff: 06/22/2017

---
# <a name="view-and-modify-push-subscription-properties"></a>Exibir e modificar propriedades de assinatura push
  Este tópico descreve como exibir e modificar propriedades de assinatura push no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], o [!INCLUDE[tsql](../../includes/tsql-md.md)]ou o RMO (Replication Management Objects).  
  
 **Neste tópico**  
  
-   **Para exibir e modificar propriedades de assinatura push, usando:**  
  
     [SQL Server Management Studio](#SSMSProcedure)  
  
     [Transact-SQL](#TsqlProcedure)  
  
     [RMO (Replication Management Objects)](#RMOProcedure)  
  
##  <a name="SSMSProcedure"></a> Usando o SQL Server Management Studio  
 Exibir e modificar as propriedades de assinatura push do Publicador em:  
  
-   A caixa de diálogo **Propriedades da Assinatura – \<Publisher>: \<PublicationDatabase>**, que está disponível no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].  
  
-   A guia **Todas as Assinaturas** que está disponível no Replication Monitor. Para obter informações sobre como iniciar o Replication Monitor, consulte [Start the Replication Monitor](../../relational-databases/replication/monitor/start-the-replication-monitor.md) (Iniciar o Replication Monitor).  
  
#### <a name="to-view-and-modify-push-subscription-properties-in-management-studio"></a>Para exibir e modificar propriedades de assinatura push no Management Studio  
  
1.  Conecte-se ao Publicador no [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]e expanda o nó do servidor.  
  
2.  Expanda a pasta **Replicação** e, em seguida, a pasta **Publicações Locais** .  
  
3.  Expanda a publicação apropriada, clique com o botão direito do mouse em uma assinatura e, então, clique em **Propriedades**.  
  
4.  Modifique propriedades, se necessário, depois clique em **OK**.  
  
#### <a name="to-view-and-modify-push-subscription-properties-in-replication-monitor"></a>Para exibir e modificar propriedades de assinatura push no Replication Monitor  
  
1.  Expanda um Grupo do publicador no painel esquerdo do Replication Monitor, expanda um Publicador e, em seguida, clique em uma publicação.  
  
2.  Clique na guia **Todas as Assinaturas** .  
  
3.  Clique com o botão direito do mouse em uma assinatura e clique em **Propriedades**.  
  
4.  Modifique propriedades, se necessário, depois clique em **OK**.  
  
##  <a name="TsqlProcedure"></a> Usando Transact-SQL  
 As assinaturas push podem ser modificadas e suas propriedades acessadas programaticamente usando procedimentos armazenados de replicação. Os procedimentos armazenados usados dependem do tipo de publicação ao qual a assinatura pertence.  
  
#### <a name="to-view-the-properties-of-a-push-subscription-to-a-snapshot-or-transactional-publication"></a>Para exibir as propriedades de uma assinatura push de um instantâneo ou publicação transacional  
  
1.  No Publicador do banco de dados da publicação, execute [sp_helpsubscription](../../relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql.md). Especifique **@publication**, o **@subscriber**, e o valor **all** para **@article**.  
  
2.  No Publicador do banco de dados da publicação, execute [sp_helpsubscriberinfo](../../relational-databases/system-stored-procedures/sp-helpsubscriberinfo-transact-sql.md), especificando **@subscriber**.  
  
#### <a name="to-change-the-properties-of-a-push-subscription-to-a-snapshot-or-transactional-publication"></a>Para alterar as propriedades de uma assinatura push de um instantâneo ou publicação transacional  
  
1.  No Publicador do banco de dados da publicação, execute [sp_changesubscriber](../../relational-databases/system-stored-procedures/sp-changesubscriber-transact-sql.md), especificando **@subscriber** e quaisquer parâmetros para as propriedades do Assinante que está sendo alterado.  
  
2.  No Publicador do banco de dados de publicação, execute [sp_changesubscription](../../relational-databases/system-stored-procedures/sp-changesubscription-transact-sql.md). Especifique **@publication**, o **@subscriber**, o **@destination_db**, o valor **all** para **@article**, a propriedade da assinatura sendo alterada para **@property**, e o novo valor para **@value**. Isto altera as configurações de segurança para a assinatura push.  
  
3.  (Opcional) Para alterar as propriedades do pacote DTS (Data Transformation Services) de uma assinatura, execute [sp_changesubscriptiondtsinfo](../../relational-databases/system-stored-procedures/sp-changesubscriptiondtsinfo-transact-sql.md) , do Assinante no banco de dados de assinatura. Especifique o ID do trabalho do Distribution Agent para **@jobid** e as seguintes propriedades de pacote DTS:  
  
    -   **@dts_package_name**  
  
    -   **@dts_package_password**  
  
    -   **@dts_package_location**  
  
     Isso altera as propriedades de pacote DTS de uma assinatura.  
  
    > [!NOTE]  
    >  O ID de trabalho pode ser obtido executando [sp_helpsubscription](../../relational-databases/system-stored-procedures/sp-helpsubscription-transact-sql.md).  
  
#### <a name="to-view-the-properties-of-a-push-subscription-to-a-merge-publication"></a>Para exibir as propriedades de uma assinatura push de uma publicação de mesclagem  
  
1.  No Publicador do banco de dados de publicação, execute [sp_helpmergesubscription](../../relational-databases/system-stored-procedures/sp-helpmergesubscription-transact-sql.md). Especifique **@publication** e **@subscriber**.  
  
2.  No Publicador, execute [sp_helpsubscriberinfo](../../relational-databases/system-stored-procedures/sp-helpsubscriberinfo-transact-sql.md), especificando **@subscriber**.  
  
#### <a name="to-change-the-properties-of-a-push-subscription-to-a-merge-publication"></a>Para alterar as propriedades de uma assinatura push de uma publicação de mesclagem  
  
1.  No Publicador do banco de dados de publicação, execute [sp_changemergesubscription](../../relational-databases/system-stored-procedures/sp-changemergesubscription-transact-sql.md). Especifique **@publication**, o **@subscriber**, o **@subscriber_db**, a propriedade da assinatura sendo alterada para **@property**, e o novo valor para **@value**.  
  
###  <a name="TsqlExample"></a> Exemplo (Transact-SQL)  
  
##  <a name="RMOProcedure"></a> Usando o RMO (Replication Management Objects)  
 As classes RMO a serem usadas para exibir ou modificar as propriedades da assinatura push dependem do tipo de publicação em que a assinatura push está inscrita.  
  
#### <a name="to-view-or-modify-properties-of-a-push-subscription-to-a-snapshot-or-transactional-publication"></a>Para exibir ou modificar as propriedades de uma assinatura push para um instantâneo ou publicação transacional  
  
1.  Crie uma conexão com o Publicador usando a classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection>.  
  
2.  Crie uma instância da classe <xref:Microsoft.SqlServer.Replication.TransSubscription>.  
  
3.  Defina as propriedades <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A> e <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A>.  
  
4.  Defina <xref:Microsoft.SqlServer.Management.Common.ServerConnection> da etapa 1 para definir a propriedade <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>.  
  
5.  Chame o método <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> para obter as propriedades do objeto. Se esse método retornar **false**, as propriedades de assinatura na etapa 3 foram definidas incorretamente ou a assinatura não existe.  
  
6.  (Opcional) Para alterar propriedades, defina um novo valor para uma das propriedades <xref:Microsoft.SqlServer.Replication.TransSubscription> que podem ser definidas e depois chame o método <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A>.  
  
7.  (Opcional) Para exibir as novas configurações, chame o método <xref:Microsoft.SqlServer.Replication.ReplicationObject.Refresh%2A> para recarregar as propriedades da assinatura.  
  
#### <a name="to-view-or-modify-properties-of-a-push-subscription-to-a-merge-publication"></a>Para exibir ou modificar as propriedades de uma assinatura push para uma publicação de mesclagem  
  
1.  Crie uma conexão com o Assinante usando a classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection>.  
  
2.  Crie uma instância da classe <xref:Microsoft.SqlServer.Replication.MergeSubscription>.  
  
3.  Defina as propriedades <xref:Microsoft.SqlServer.Replication.Subscription.PublicationName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.DatabaseName%2A>, <xref:Microsoft.SqlServer.Replication.Subscription.SubscriberName%2A> e <xref:Microsoft.SqlServer.Replication.Subscription.SubscriptionDBName%2A>.  
  
4.  Defina <xref:Microsoft.SqlServer.Management.Common.ServerConnection> da etapa 1 para definir a propriedade <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>.  
  
5.  Chame o método <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> para obter as propriedades do objeto. Se esse método retornar **false**, as propriedades de assinatura na etapa 3 foram definidas incorretamente ou a assinatura não existe.  
  
6.  (Opcional) Para alterar propriedades, defina um novo valor para uma das propriedades <xref:Microsoft.SqlServer.Replication.MergeSubscription> que podem ser definidas e depois chame o método <xref:Microsoft.SqlServer.Replication.ReplicationObject.CommitPropertyChanges%2A>.  
  
7.  (Opcional) Para exibir as novas configurações, chame o método <xref:Microsoft.SqlServer.Replication.ReplicationObject.Refresh%2A> para recarregar as propriedades da assinatura.  
  
## <a name="see-also"></a>Consulte também  
 [Exibir informações e realizar tarefas para uma assinatura &#40;Replication Monitor&#41;](../../relational-databases/replication/monitor/view-information-and-perform-tasks-for-a-subscription-replication-monitor.md)   
 [Melhores práticas de segurança da replicação](../../relational-databases/replication/security/replication-security-best-practices.md)   
 [Assinar Publicações](../../relational-databases/replication/subscribe-to-publications.md)  
  
  