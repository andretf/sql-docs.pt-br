---
title: Descartando um índice do SQL Server | Microsoft Docs
description: Descartando um índice do sql server usando o Driver do OLE DB para SQL Server
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
- removing indexes
- deleting indexes
- DropIndex function
- dropping indexes
- OLE DB Driver for SQL Server, indexes
- indexes [OLE DB]
author: pmasl
ms.author: Pedro.Lopes
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 60e7198d6c6ab18f84640cd0531cd9d0bac63a90
ms.sourcegitcommit: 9f4330a4b067deea396b8567747a6771f35e6eee
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/30/2018
---
# <a name="dropping-a-sql-server-index"></a>Descartando um índice do SQL Server

  O Driver OLE DB para SQL Server expõe o **iindexdefinition:: Dropindex** função. Isso permite que os consumidores removam um índice de um [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] tabela.  
  
 O Driver OLE DB para SQL Server expõe algumas [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] restrições PRIMARY KEY e UNIQUE como índices. O proprietário da tabela, o proprietário de banco de dados e alguns membros de função administrativa podem modificar um [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] tabela, descartando uma restrição. Por padrão, somente o proprietário da tabela pode descartar um índice existente. Portanto, **DropIndex** êxito ou falha depende não apenas os direitos de acesso do usuário do aplicativo mas também no tipo de índice indicado.  
  
 Os consumidores especificam o nome da tabela como uma cadeia de caracteres Unicode na *pwszName* membro a *uName* união na *pTableID* parâmetro. O *eKind* membro *pTableID* deve ser DBKIND_NAME.  
  
 Os consumidores especificam o nome do índice como uma cadeia de caracteres Unicode no *pwszName* membro do *uName* união no *pIndexID* parâmetro. O *eKind* membro *pIndexID* deve ser DBKIND_NAME. O Driver OLE DB para SQL Server não oferece suporte ao recurso de OLE DB de descartar todos os índices em uma tabela quando *pIndexID* é nulo. Se *pIndexID* é nulo, E_INVALIDARG será retornado.  
  
## <a name="see-also"></a>Consulte também  
 [Tabelas e índices](../../oledb/ole-db-tables-indexes/tables-and-indexes.md)   
 [ALTER TABLE &#40;Transact-SQL&#41;](../../../t-sql/statements/alter-table-transact-sql.md)   
 [DROP INDEX &#40;Transact-SQL&#41;](../../../t-sql/statements/drop-index-transact-sql.md)  
  
  
