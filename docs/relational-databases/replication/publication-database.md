---
title: "Banco de dados de publicação | Microsoft Docs"
ms.custom: 
ms.date: 03/03/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: replication
ms.reviewer: 
ms.suite: sql
ms.technology:
- replication
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sql13.rep.newpubwizard.publicationdatabase.f1
ms.assetid: a9fafc9b-9963-4b59-97a0-3472158fa665
caps.latest.revision: 
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 23969b740711c3c3184438d984953a1535820f34
ms.sourcegitcommit: ab25b08a312d35489a2c4a6a0d29a04bbd90f64d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/08/2018
---
# <a name="publication-database"></a>Banco de dados de publicação
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  O banco de dados de publicação é o banco de dados no publicador que é a fonte dos dados e objetos de banco de dados a serem replicados. Cada banco de dados de publicação usado na replicação deve ser habilitado. O banco de dados está habilitado quando um membro da função de servidor fixa **sysadmin** :  
  
-   Cria uma publicação naquele banco de dados usando o Assistente para Nova Publicação.  
  
-   Seleciona o banco de dados na caixa de diálogo **Propriedades do Publicador** .  
  
-   Executa **sp_replicationdboption** e define a opção **publish** (para publicações transacionais ou de instantâneo) ou **merge publish** (para publicações de mesclagem) como **True**.  
  
## <a name="options"></a>Opções  
 **Bancos de dados**  
 Selecione o nome do banco de dados que contém os dados e os objetos de banco de dados que você quer publicar.  
  
## <a name="see-also"></a>Consulte Também  
 [Publicar dados e objetos de banco de dados](../../relational-databases/replication/publish/publish-data-and-database-objects.md)   
 [Create a Publication](../../relational-databases/replication/publish/create-a-publication.md)   
 [Exibir e modificar propriedades de Publicador e Distribuidor](../../relational-databases/replication/view-and-modify-distributor-and-publisher-properties.md)   
 [sp_replicationdboption &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql.md)  
  
  
