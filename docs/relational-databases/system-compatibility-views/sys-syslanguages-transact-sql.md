---
title: sys.syslanguages (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/15/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.service: 
ms.component: system-compatibility-views
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- sys.syslanguages
- sys.syslanguages_TSQL
- syslanguages
- syslanguages_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- syslanguages system table
- sys.syslanguages compatibility view
ms.assetid: f216d1cd-997c-42f0-a737-abbdfcd88383
caps.latest.revision: 
author: rothja
ms.author: jroth
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: 47eb77543c650a16650680435e5d0db7d395eade
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2018
---
# <a name="syssyslanguages-transact-sql"></a>sys.syslanguages (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-all-md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  Contém uma linha para cada idioma presente na instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
|Nome da coluna|Tipo de dados|Description|  
|-----------------|---------------|-----------------|  
|langid|**smallint**|ID exclusiva de idioma.|  
|dateformat|**nchar(3)**|Ordem de data, por exemplo, DMA.|  
|datefirst|**tinyint**|Primeiro dia da semana: 1 para segunda-feira, 2 para terça-feira e assim por diante, até 7 para domingo.|  
|atualização|**Int**|Reservado para uso do sistema.|  
|name|**sysname**|Nome oficial do idioma, por exemplo, francês.|  
|alias|**sysname**|Nome de idioma alternativo, por exemplo, francês.|  
|months|**nvarchar(372)**|Lista de nomes de meses completos separados por vírgula, de janeiro a dezembro, com cada nome contendo até 20 caracteres.|  
|shortmonths|**nvarchar(132)**|Lista de nomes de meses abreviados separados por vírgula, de janeiro a dezembro, com cada nome contendo até 9 caracteres.|  
|dias|**nvarchar(217)**|Lista de nomes de dias separados por vírgula, de segunda-feira a domingo, com cada nome contendo até 30 caracteres.|  
|lcid|**Int**|[!INCLUDE[msCoName](../../includes/msconame-md.md)] ID de localidade do Windows para o idioma.|  
|msglangid|**smallint**|[!INCLUDE[ssDE](../../includes/ssde-md.md)] ID do grupo de mensagem.|  
  
 O [!INCLUDE[ssDE](../../includes/ssde-md.md)] contém os seguintes idiomas instalados.  
  
|Nome em inglês|LCID do Windows|[!INCLUDE[ssDE](../../includes/ssde-md.md)] ID do grupo de mensagem|  
|---------------------|------------------|-----------------------------------------|  
|Inglês|1046|1046|  
|Alemão|1031|1031|  
|Francês|1036|1036|  
|Japonês|1041|1041|  
|Danish|1030|1030|  
|Espanhol|3082|3082|  
|Italiano|1040|1040|  
|Holandês|1043|1043|  
|Norueguês|2068|2068|  
|Português|2070|2070|  
|Finlandês|1035|1035|  
|Sueco|1053|1053|  
|Czech|1029|1029|  
|Húngaro|1038|1038|  
|Polonês|1045|1045|  
|Romeno|1048|1048|  
|Croata|1050|1050|  
|Eslovaco|1051|1051|  
|Slovene|1060|1060|  
|Greek|1032|1032|  
|Búlgaro|1026|1026|  
|Russo|1049|1049|  
|Turco|1055|1055|  
|British English|2057|1046|  
|Estoniano|1061|1061|  
|Letão|1062|1062|  
|Lituano|1063|1063|  
|Português do Brasil|1046|1046|  
|Chinês tradicional|1028|1028|  
|Coreano|1042|1042|  
|Chinês simplificado|2052|2052|  
|Árabe|1025|1025|  
|Tailandês|1054|1054|  
  
## <a name="see-also"></a>Consulte também  
 [Exibições de compatibilidade &#40; Transact-SQL &#41;](~/relational-databases/system-compatibility-views/system-compatibility-views-transact-sql.md)   
 [Mapeando tabelas do sistema para exibições do sistema &#40; Transact-SQL &#41;](../../relational-databases/system-tables/mapping-system-tables-to-system-views-transact-sql.md)  
  
  
