---
title: Elemento Restore (XMLA) | Microsoft Docs
ms.custom: 
ms.date: 03/14/2017
ms.prod: analysis-services
ms.prod_service: analysis-services, azure-analysis-services
ms.service: 
ms.component: 
ms.reviewer: 
ms.suite: pro-bi
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: Restore Element
apilocation: http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to: SQL Server 2016 Preview
f1_keywords:
- http://schemas.microsoft.com/analysisservices/2003/engine#Restore
- urn:schemas-microsoft-com:xml-analysis#Restore
- microsoft.xml.analysis.restore
helpviewer_keywords: Restore command
ms.assetid: bb5a0c92-3927-4fa4-975b-6e4d79e0a912
caps.latest.revision: "26"
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 4aca6a4028390f9edd704ae6671f1904ea627f2c
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2018
---
# <a name="restore-element-xmla"></a>Elemento Restore (XMLA)
[!INCLUDE[ssas-appliesto-sqlas-aas](../../../includes/ssas-appliesto-sqlas-aas.md)]Restaura um [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] banco de dados de um arquivo de backup.  
  
## <a name="syntax"></a>Sintaxe  
  
```xml  
  
<Command>  
   <Restore>  
      <DatabaseName>...</DatabaseName>  
      <DatabaseID>...</DatabaseID>  
      <File>...</File>  
      <Security>...</Security>  
      <AllowOverwrite>...</AllowOverwrite>  
      <Password>...</Password>  
      <Locations>...</Locations>  
      <DbStorageLocation>...</DbStorageLocation>  
   </Restore>  
</Command>  
```  
  
## <a name="element-characteristics"></a>Características do elemento  
  
|Característica|Description|  
|--------------------|-----------------|  
|Comprimento e tipo de dados|Nenhum|  
|Valor padrão|Nenhum|  
|Cardinalidade|0-n: Elemento opcional que pode ocorrer mais de uma vez.|  
  
## <a name="element-relationships"></a>Relações do elemento  
  
|Relação|Elemento|  
|------------------|-------------|  
|Elementos pai|[Comando](../../../analysis-services/xmla/xml-elements-properties/command-element-xmla.md)|  
|Elementos filho|[AllowOverwrite](../../../analysis-services/xmla/xml-elements-properties/allowoverwrite-element-xmla.md), [DatabaseName](../../../analysis-services/xmla/xml-elements-properties/databasename-element-xmla.md), [DatabaseID](../../../analysis-services/xmla/xml-elements-properties/databaseid-element-xmla.md), [arquivo](../../../analysis-services/xmla/xml-elements-properties/file-element-xmla.md), [locais](../../../analysis-services/xmla/xml-elements-properties/locations-element-xmla.md), [senha](../../../analysis-services/xmla/xml-elements-properties/password-element-xmla.md), [segurança](../../../analysis-services/xmla/xml-elements-properties/security-element-xmla.md), [DbStorageLocation](../../../analysis-services/xmla/xml-elements-properties/dbstoragelocation-element.md)|  
  
## <a name="remarks"></a>Remarks  
 O **restaurar** comando restaura um [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] banco de dados especificado no **DatabaseName** elemento de um arquivo de backup e, opcionalmente, restaura partições remotas de arquivos de backup remotos.  
  
 Dependendo do modo de armazenamento usado por objetos armazenados no arquivo de backup, o comando **Restore** restaura informações conforme listado na tabela a seguir.  
  
|Modo de armazenamento|Informações|  
|------------------|-----------------|  
|OLAP multidimensional (MOLAP)|Dados de origem, agregações e metadados|  
|OLAP híbrido (HOLAP)|Agregações e metadados|  
|OLAP relacional (ROLAP)|Metadados|  
  
 Durante uma **restaurar** de comando, um bloqueio exclusivo é colocado no [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] banco de dados especificado no **DatabaseName** elemento. O bloqueio é liberado depois de o comando **Restore** ser concluído.  
  
 Para obter mais informações sobre backup e restaurando bancos de dados, consulte [fazendo backup, restauração e sincronizando bancos de dados &#40; XMLA &#41; ](../../../analysis-services/multidimensional-models-scripting-language-assl-xmla/backing-up-restoring-and-synchronizing-databases-xmla.md).  
  
> [!IMPORTANT]  
>  Para cada arquivo de backup, o usuário que executar o comando de restauração deve ter permissão para ler no local de backup especificado para cada arquivo. Para restaurar um banco de dados do [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] que não esteja instalado no servidor, o usuário também deve ser membro da função de servidor dessa instância do [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] . Para substituir um banco de dados do [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] , o usuário deve ter uma das seguintes funções: membro da função de servidor da instância do [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] ou membro de uma função de banco de dados com permissões de Controle Total (Administrador) no banco de dados a ser restaurado.  
  
> [!NOTE]  
>  Após restaurar um banco de dados existente, o usuário que o restaurou poderá perder o acesso ao banco de dados restaurado. Essa perda de acesso pode ocorrer se, no momento da execução do backup, o usuário não for membro da função de servidor, nem membro da função de banco de dados com permissões de Controle total (Administrador).  
  
## <a name="see-also"></a>Consulte Também  
 [Elemento de backup &#40; XMLA &#41;](../../../analysis-services/xmla/xml-elements-commands/backup-element-xmla.md)   
 [Elemento batch &#40; XMLA &#41;](../../../analysis-services/xmla/xml-elements-commands/batch-element-xmla.md)   
 [Elemento Parallel &#40; XMLA &#41;](../../../analysis-services/xmla/xml-elements-properties/parallel-element-xmla.md)   
 [Sincronizar o elemento &#40; XMLA &#41;](../../../analysis-services/xmla/xml-elements-commands/synchronize-element-xmla.md)   
 [Comandos &#40; XMLA &#41;](../../../analysis-services/xmla/xml-elements-commands/xml-elements-commands.md)  
  
  
