---
title: Tipos de assinante | Microsoft Docs
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- replication
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sql13.rep.newpubwizard.subscribertypes.f1
ms.assetid: a70656cb-21c9-4489-be77-ccd396747e3b
caps.latest.revision: 28
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: ae9c8cf11d6a95554f56d6c6bde1b2eb18b36d70
ms.contentlocale: pt-br
ms.lasthandoff: 06/22/2017

---
# <a name="subscriber-types"></a>Tipos de Assinantes
  A replicação de mesclagem permite especificar a que tipos de Assinantes uma publicação deve dar suporte. A seleção dos tipos de Assinantes define o *nível de compatibilidade da publicação*, que determina quais recursos podem ser usados por uma publicação.  
  
 Depois que um instantâneo de publicação é criado, o nível de compatibilidade da publicação pode ser aumentado (tornado mais restrito) na página **Geral** da caixa de diálogo **Propriedades de Publicação** ; o nível de compatibilidade não pode ser diminuído.  
  
## <a name="options"></a>Opções  
 Selecione cada tipo de Assinante a que esta publicação deve dar suporte.  
  
 [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]  
 A publicação pode usar todos os recursos.  
  
 [!INCLUDE[ssEW](../../includes/ssew-md.md)]  
 A publicação exige que os arquivos de instantâneo estejam no formato de caractere (isto é tratado automaticamente pelo Agente de Instantâneo). O[!INCLUDE[ssEW](../../includes/ssew-md.md)] também tem várias restrições não relacionadas ao nível de compatibilidade.  
  
 Se essa opção for selecionada, a opção de sincronização da Web estará habilitada para a publicação. Para obter mais informações sobre a sincronização da Web, consulte [Web Synchronization for Merge Replication](../../relational-databases/replication/web-synchronization-for-merge-replication.md).  
  
## <a name="see-also"></a>Consulte também  
 [Publicar dados e objetos de banco de dados](../../relational-databases/replication/publish/publish-data-and-database-objects.md)   
 [Criar uma publicação](../../relational-databases/replication/publish/create-a-publication.md)   
 [Exibir e modificar propriedades de Publicador e Distribuidor](../../relational-databases/replication/view-and-modify-distributor-and-publisher-properties.md)   
 [Referência de propriedades &#40;Replicação&#41;](../../relational-databases/replication/properties-reference-replication.md)  
  
  