---
title: Parâmetros com valor de tabela (OLE DB) | Microsoft Docs
description: Parâmetros com valor de tabela (OLE DB)
ms.custom: ''
ms.date: 03/26/2018
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.service: ''
ms.component: ole-db-table-valued-parameters
ms.reviewer: ''
ms.suite: sql
ms.technology:
- docset-sql-devref
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- OLE DB, table-valued parameters
- table-valued parameters (OLE DB)
author: pmasl
ms.author: Pedro.Lopes
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: f8f219346a4ed5ed6e03d6cca707bbf14091df1a
ms.sourcegitcommit: 9f4330a4b067deea396b8567747a6771f35e6eee
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/30/2018
---
# <a name="table-valued-parameters-ole-db"></a>Parâmetros com valor de tabela (OLE DB)
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]

  Esta seção descreve o suporte para parâmetros com valor de tabela no Driver do OLE DB para SQL Server. Para obter informações adicionais, consulte [parâmetros com valor de tabela &#40;OLE DB Driver para SQL Server&#41;](../../oledb/features/table-valued-parameters-oledb-driver-for-sql-server.md). Para obter um exemplo, consulte [usar parâmetros &#40;OLE DB&#41;](../../oledb/ole-db-how-to/use-table-valued-parameters-ole-db.md).  
  
## <a name="remarks"></a>Remarks  
 No momento, você pode enviar dados em várias linhas para o servidor como parâmetros para um procedimento com conjuntos de parâmetros (o parâmetro DBPARAMS em **ICommand:: execute**). Com conjuntos de parâmetros, todo elemento do conjunto tem que ser enviado ao servidor em uma solicitação RPC (chamada de procedimento remoto) separada. Os parâmetros com valor de tabela fornecem uma funcionalidade semelhante, mas interagem melhor com o servidor. Ele reduz o número de solicitações RPC e permite que as operações de conjunto com base no servidor.  
  
 Parâmetros de valor de tabela têm suporte no Driver do OLE DB para SQL Server como banco de dados OLE **linhas** objetos. Qualquer **linhas** objeto pode ser fornecido pelo consumidor (ou seja, o aplicativo cliente usando o Driver do OLE DB para SQL Server) como um espaço reservado para parâmetros com valor de tabela. Os parâmetros com valor de tabela são tratados como os outros tipos de parâmetro do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]. O Driver OLE DB para SQL Server fornece criação, descoberta, especificação, associação e interfaces de esquema.  
  
## <a name="in-this-section"></a>Nesta seção  
  
-   [Criação do conjunto de linhas do parâmetro com valor de tabela](../../oledb/ole-db-table-valued-parameters/table-valued-parameter-rowset-creation.md)  
  
-   [Descoberta do tipo de parâmetro com valor de tabela](../../oledb/ole-db-table-valued-parameters/table-valued-parameter-type-discovery.md)  
  
-   [Executando comandos que contêm parâmetros com valor de tabela](../../oledb/ole-db-table-valued-parameters/executing-commands-containing-table-valued-parameters.md)  
  
-   [Inserindo dados em parâmetros com valor de tabela](../../oledb/ole-db-table-valued-parameters/inserting-data-into-table-valued-parameters.md)  
  
-   [Conjuntos de linhas de esquema alterados para parâmetros com valor de tabela de OLE DB](../../oledb/ole-db-table-valued-parameters/schema-rowsets-changed-for-ole-db-table-valued-parameters.md)  
  
-   [Suporte ao tipo de parâmetro com valor de tabela OLE DB](../../oledb/ole-db-table-valued-parameters/ole-db-table-valued-parameter-type-support.md)  
  
-   [Suporte ao tipo de parâmetro com valor de tabela de banco de dados OLE &#40;métodos&#41;](../../oledb/ole-db-table-valued-parameters/ole-db-table-valued-parameter-type-support-methods.md)  
  
-   [Suporte ao tipo de parâmetro com valor de tabela de banco de dados OLE &#40;propriedades&#41;](../../oledb/ole-db-table-valued-parameters/ole-db-table-valued-parameter-type-support-properties.md)  
  
## <a name="see-also"></a>Consulte também  
 [Driver do OLE DB para SQL Server &#40;OLE DB&#41;](../../oledb/ole-db/oledb-driver-for-sql-server-ole-db.md)   
 [Usar com valor de tabela parâmetros &#40; OLE DB &#41;](../../oledb/ole-db-how-to/use-table-valued-parameters-ole-db.md)  
  
  
