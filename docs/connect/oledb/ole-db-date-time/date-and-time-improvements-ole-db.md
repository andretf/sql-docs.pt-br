---
title: Data e hora melhorias (OLE DB) | Microsoft Docs
description: Aprimoramentos de data e hora (OLE DB)
ms.custom: ''
ms.date: 03/26/2018
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.service: ''
ms.component: ole-db-date-time
ms.reviewer: ''
ms.suite: sql
ms.technology:
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- date/time [OLE DB]
- OLE DB, date/time improvements
author: pmasl
ms.author: Pedro.Lopes
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 979c73a2bc5d05ea33b626b441452b3dc8256269
ms.sourcegitcommit: 9f4330a4b067deea396b8567747a6771f35e6eee
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/30/2018
---
# <a name="date-and-time-improvements-ole-db"></a>Data e hora melhorias (OLE DB)
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]

  O [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] apresenta novos tipos de dados de data e hora. Esta seção descreve como esses novos tipos são expostos como extensões no Driver do OLE DB para SQL Server. Para obter uma visão geral do Driver OLE DB para suporte do SQL Server para a nova data e tipos de dados de tempo, consulte [data e hora melhorias](../../oledb/features/date-and-time-improvements.md). Para obter um exemplo, consulte [Use aprimorados de data e hora recursos &#40;OLE DB&#41;](../../oledb/ole-db-how-to/use-enhanced-date-and-time-features-ole-db.md).  
  
 Para obter mais informações sobre tipos de dados de data e hora, consulte [datetime &#40;Transact-SQL&#41;](../../../t-sql/data-types/datetime-transact-sql.md).  
  
## <a name="in-this-section"></a>Nesta seção  
 [Suporte a tipos de dados para melhorias de data e hora do OLE DB](../../oledb/ole-db-date-time/data-type-support-for-ole-db-date-and-time-improvements.md)  
 Fornece informações sobre o OLE DB (OLE DB Driver para SQL Server) tipos que oferecem suporte a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] tipos de dados de data e hora.  
  
 [Metadados &#40;OLE DB&#41;](../../oledb/ole-db-date-time/metadata-parameter-and-rowset.md)  
 Contém informações sobre a estrutura DBBINDING, **ICommandWithParameters:: Getparameterinfo**, **ICommandWithParameters:: SetParameterInfo**, **IColumnsRowset:: GetColumnsRowset**e**ColumnsInfo::GetColumnInfo**. Também fornece informações sobre atualizações de conjuntos de linhas de esquemas OLE DB.  
  
 [Associações e conversões &#40;OLE DB&#41;](../../oledb/ole-db-date-time/conversions-ole-db.md)  
 Descreve as regras para conversão entre servidor e cliente de tipos de data novos e existentes.  
  
 [Em massa copia alterações para tipos aprimorados de data e hora &#40;OLE DB&#41;](../../oledb/ole-db-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db.md)  
 Descreve aprimoramentos de data/hora para dar suporte a operações de cópia em massa.  
  
 [Suporte da API do OLE DB para aprimoramentos de data e hora](../../oledb/ole-db-date-time/ole-db-api-support-for-date-and-time-enhancements.md)  
 Descreve as APIs OLE DB que dão suporte a recursos de data/hora aprimorados.  
  
 [Comparações de IRowsetFind](../../oledb/ole-db-date-time/comparability-for-irowsetfind.md)  
 Descreve os tipos de data/hora e **IRowsetFind**.  
 
  
## <a name="see-also"></a>Consulte também  
 [Driver do OLE DB para SQL Server &#40;OLE DB&#41;](../../oledb/ole-db/oledb-driver-for-sql-server-ole-db.md)  
  
  
