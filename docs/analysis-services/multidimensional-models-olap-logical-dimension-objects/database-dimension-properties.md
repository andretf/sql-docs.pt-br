---
title: "Propriedades de dimensão de banco de dados | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
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
- metadata [Analysis Services]
- dimensions [Analysis Services], characteristics
- properties [Analysis Services], dimensions
ms.assetid: 075548ef-08a3-413c-8ee0-4a074c276fcc
caps.latest.revision: 
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: d05ca23a224bd7c702bd54ef4355c568cf593327
ms.sourcegitcommit: 7519508d97f095afe3c1cd85cf09a13c9eed345f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2018
---
# <a name="database-dimension-properties"></a>Propriedades de dimensão do banco de dados
[!INCLUDE[ssas-appliesto-sqlas](../../includes/ssas-appliesto-sqlas.md)]
Em [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], as características de uma dimensão são definidas pelos metadados da dimensão, com base nas configurações de várias propriedades de dimensão e os atributos ou hierarquias contidas pela dimensão. A tabela a seguir descreve as propriedades de dimensão no [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].  
  
|Propriedade|Description|  
|--------------|-----------------|  
|**AttributeAllMemberName**|Especifica o nome de todos os membros para atributos em uma dimensão.|  
|**Agrupamento**|Determina o agrupamento usado pela dimensão.|  
|**CurrentStorageMode**|Contém o modo de armazenamento atual para a dimensão.|  
|**DependsOnDimension**|Contém o ID de outra dimensão da qual a dimensão depende, se houver.|  
|**Descrição**|Contém a descrição da dimensão.|  
|**ErrorConfiguration**|Contém definições configuráveis de tratamento de erros para tratamento de chaves duplicadas, chaves desconhecidas, limites de erro, ação devido à detecção de erros, arquivo de log de erros e tratamento de chaves nulas.|  
|**ID**|Contém o identificador exclusivo (ID) da dimensão.|  
|**Idioma**|Especifica o idioma padrão para a dimensão.|  
|**MdxMissingMemberMode**|Determina como são tratados membros ausentes para linguagens MDX.|  
|**MiningModelID**|Contém o ID do modelo de mineração com o qual a dimensão de mineração de dados está associada. Essa propriedade só será aplicável se a dimensão for uma dimensão de modelo de mineração.|  
|**Nome**|Especifica o nome da dimensão.|  
|**ProactiveCaching**|Define configurações de cache pró-ativas para a dimensão.|  
|**ProcessingGroup**|Especifica o grupo de processamento. Os valores são ByAttribute ou ByTable. O padrão é **ByAttribute**.|  
|**ProcessingMode**|Indica se o [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] deve fazer indexação e agregação durante ou após o processamento.|  
|**ProcessingPriority**|Determina a prioridade de processamento da dimensão durante as operações em segundo plano, como agregações lentas, indexação ou cluster.|  
|**Origem**|Identifica a exibição da fonte de dados à qual a dimensão está associada.|  
|**StorageMode**|Determina o modo de armazenamento da dimensão.|  
|**Tipo**|Especifica o tipo da dimensão.|  
|**UnknownMember**|Indica se o membro desconhecido é visível.|  
|**UnknownMemberName**|Especifica a legenda, no idioma padrão da dimensão, para o membro desconhecido da dimensão.|  
|**WriteEnabled**|Indica se write-backs de dimensão estão disponíveis (sujeito a permissões de segurança).|  
  
> [!NOTE]  
>  Para obter mais informações sobre como definir valores para as propriedades ErrorConfiguration e UnknownMember quando trabalhar com valores nulos e outros problemas de integridade de dados, consulte [Handling Data Integrity Issues in Analysis Services 2005](http://go.microsoft.com/fwlink/?LinkId=81891).  
  
## <a name="see-also"></a>Consulte também  
 [Atributos e hierarquias de atributo](../../analysis-services/multidimensional-models-olap-logical-dimension-objects/attributes-and-attribute-hierarchies.md)   
 [Hierarquias do usuário](../../analysis-services/multidimensional-models-olap-logical-dimension-objects/user-hierarchies.md)   
 [Relações de dimensão](../../analysis-services/multidimensional-models-olap-logical-cube-objects/dimension-relationships.md)   
 [Dimensões &#40; Analysis Services - dados multidimensionais &#41;](../../analysis-services/multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md)  
  
  
