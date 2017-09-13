---
title: "Relatório de migração de dados (AccessToSQL) | Microsoft Docs"
ms.prod: sql-non-specified
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- sql-ssma
ms.tgt_pltfrm: 
ms.topic: article
applies_to:
- Azure SQL Database
- SQL Server
ms.assetid: b090b327-cec6-4d9a-a670-8f96e8ff0046
caps.latest.revision: 4
author: Shamikg
ms.author: Shamikg
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: 8cdc3a878c24f53cbadefdee49dc300ce616c009
ms.contentlocale: pt-br
ms.lasthandoff: 08/02/2017

---
# <a name="data-migration-report-accesstosql"></a>Relatório de migração de dados (AccessToSQL)
O **relatório de migração de dados** caixa de diálogo é exibida depois de migrar dados para [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)].  
  
## <a name="options"></a>Opções  
**Status**  
Mostra o status de migração de dados da fonte de dados de destino.  
  
**De**  
A tabela de origem.  
  
**Para**  
A tabela de destino.  
  
**Número total de linhas**  
O número de linhas de dados na tabela de origem.  
  
**Número de linhas migradas com êxito**  
O número de linhas de dados migrados com êxito para a tabela de destino.  
  
**Taxa de**  
A porcentagem de linhas foi migrado com êxito.  
  
**Detalhes**  
Se a falha de migração de dados, clique para exibir detalhes de migração para a linha selecionada no relatório. O SSMA exibirá o motivo da falha.  
  
**Salvar relatório**  
Salva o relatório para um. CSV, arquivo (valores separados por vírgula), que pode ser examinado usando o Microsoft Excel.  
  
