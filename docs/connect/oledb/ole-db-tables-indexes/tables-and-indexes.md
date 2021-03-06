---
title: Tabelas e índices | Microsoft Docs
description: Criando, alterando e droping tabelas e índices usando o Driver do OLE DB para SQL Server
ms.custom: ''
ms.date: 03/26/2018
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.service: ''
ms.component: ole-db-tables-indexes
ms.reviewer: ''
ms.suite: sql
ms.technology:
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- OLE DB, indexes
- OLE DB, tables
- ITableDefinition interface
- tables [OLE DB]
- IIndexDefinition interface
- OLE DB Driver for SQL Server, tables
- OLE DB Driver for SQL Server, indexes
- indexes [OLE DB]
author: pmasl
ms.author: Pedro.Lopes
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 821355c800f2b162665b29cfcadd7d9b776a1fc6
ms.sourcegitcommit: 9f4330a4b067deea396b8567747a6771f35e6eee
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/30/2018
---
# <a name="tables-and-indexes"></a>Tabelas e índices
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]

  O Driver OLE DB para SQL Server expõe o **IIndexDefinition** e **ITableDefinition** interfaces, permitindo que os consumidores criar, alterar e descartar [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] tabelas e índices. As definições válidas de tabela e de índice dependem da versão do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].  
  
 A capacidade de criar ou descartar tabelas e índices depende dos direitos de acesso do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] do usuário do aplicativo de consumidor. Descartar uma tabela pode ser uma operação ainda mais restrita pela presença de restrições de integridade referencial declarativas ou outros fatores.  
  
 A maioria dos aplicativos voltados para [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] usar SQL-DMO em vez desses Driver OLE DB para SQL Server interfaces. SQL-DMO é uma coleção de objetos de automação OLE que dão suporte a todas as funções administrativas do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]. Os aplicativos destinados a vários provedores OLE DB usam essas interfaces OLE DB genéricas suportadas pelos vários provedores OLE DB.  
  
 No conjunto de propriedades específico de provedor DBPROPSET_SQLSERVERCOLUMN, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] define a propriedade a seguir.  
  
|ID da propriedade|Description|  
|-----------------|-----------------|  
|SSPROP_COL_COLLATIONNAME|Tipo: VT_BSTR<br /><br /> Leitura/gravação: gravação<br /><br /> Padrão: Null<br /><br /> Descrição: Esta propriedade é usada somente em **ITableDefinition**. A cadeia de caracteres especificada por esta propriedade é usada ao criar um [CREATE TABLE](../../../t-sql/statements/create-table-transact-sql.md)<br /><br /> .|  
  
## <a name="in-this-section"></a>Nesta seção  
  
-   [Criando tabelas do SQL Server](../../oledb/ole-db-tables-indexes/creating-sql-server-tables.md)  
  
-   [Adicionar uma coluna a uma tabela do SQL Server](../../oledb/ole-db-tables-indexes/adding-a-column-to-a-sql-server-table.md)  
  
-   [Remover uma coluna de uma tabela do SQL Server](../../oledb/ole-db-tables-indexes/removing-a-column-from-a-sql-server-table.md)  
  
-   [Descartando uma tabela do SQL Server](../../oledb/ole-db-tables-indexes/dropping-a-sql-server-table.md)  
  
-   [Criando índices do SQL Server](../../oledb/ole-db-tables-indexes/creating-sql-server-indexes.md)  
  
-   [Descartando um índice do SQL Server](../../oledb/ole-db-tables-indexes/dropping-a-sql-server-index.md)  
  
## <a name="see-also"></a>Consulte também  
 [Driver do OLE DB para SQL Server &#40;OLE DB&#41;](../../oledb/ole-db/oledb-driver-for-sql-server-ole-db.md)   
 [Remover tabela &#40; Transact-SQL &#41;](../../../t-sql/statements/drop-table-transact-sql.md)   
 [CREATE INDEX &#40;Transact-SQL&#41;](../../../t-sql/statements/create-index-transact-sql.md)   
 [DROP INDEX &#40;Transact-SQL&#41;](../../../t-sql/statements/drop-index-transact-sql.md)  
  
  
