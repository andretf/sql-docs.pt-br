---
title: "Propriedades - hierarquias de usuário de nível | Microsoft Docs"
ms.custom: 
ms.date: 03/04/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: 
ms.component: 
ms.reviewer: 
ms.suite: pro-bi
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- user hierarchies [Analysis Services]
- hierarchies [Analysis Services], user
ms.assetid: dabb7335-887b-442a-b67c-4901ba1242b7
caps.latest.revision: 
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: db94622cfc84d97cb6f8e7578421f4933a63af94
ms.sourcegitcommit: 7519508d97f095afe3c1cd85cf09a13c9eed345f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2018
---
# <a name="user-hierarchies---level-properties"></a>Hierarquias de usuário - propriedades de nível
[!INCLUDE[ssas-appliesto-sqlas](../../includes/ssas-appliesto-sqlas.md)]
A tabela a seguir lista e descreve as propriedades de um nível em uma hierarquia definida pelo usuário.  
  
|Propriedade|Description|  
|--------------|-----------------|  
|Description|Contém a descrição do nível.|  
|HideMemberIf|Indica se, e quando, um membro em um nível ficará oculto pelos aplicativos cliente. Essa propriedade pode ter os seguintes valores:<br /><br /> Never<br /> Membros nunca são ocultados. Este é o valor padrão.<br /><br /> OnlyChildWithNoName<br /> Um membro é ocultado quando o membro for o único filho de seu pai e seu nome estiver vazio.<br /><br /> OnlyChildWithParentName<br /> Um membro é ocultado quando o membro for o único filho de seu pai e seu nome for idêntico ao de seu pai.<br /><br /> NoName<br /> Um membro é ocultado quando o nome do membro estiver vazio.<br /><br /> ParentName<br /> Um membro é ocultado quando o nome do membro for idêntico ao de seu pai.|  
|ID|Contém o identificador exclusivo (ID) do nível.|  
|Nome|Contém o nome amigável do nível. Por padrão, o nome de um nível é igual ao nome do atributo de origem.|  
|SourceAttribute|Contém o nome do atributo de origem no qual o nível tem como base.|  
  
## <a name="see-also"></a>Consulte também  
 [Propriedades de hierarquia de usuário](../../analysis-services/multidimensional-models-olap-logical-dimension-objects/user-hierarchies-properties.md)  
  
  
