---
title: Criar uma tabela para armazenar dados FILESTREAM | Microsoft Docs
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: blob
ms.reviewer: 
ms.suite: sql
ms.technology:
- dbe-blob
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- FILESTREAM [SQL Server], table storage
ms.assetid: 029c3059-5c83-43e2-a859-9027031b7de1
caps.latest.revision: 
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: f68e1867254caeb5257fe0c2c28fa291b45fd901
ms.sourcegitcommit: 37f0b59e648251be673389fa486b0a984ce22c81
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2018
---
# <a name="create-a-table-for-storing-filestream-data"></a>Criar uma tabela para armazenar dados FILESTREAM
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
Este tópico mostra como criar uma tabela para armazenar dados FILESTREAM.  
  
 Quando o banco de dados tiver um grupo de arquivos FILESTREAM, será possível criar ou modificar tabelas para armazenar dados FILESTREAM. Para especificar que uma coluna contém dados FILESTREAM, crie a coluna **varbinary(max)** e adicione o atributo FILESTREAM.  
  
### <a name="to-create-a-table-to-store-filestream-data"></a>Para criar uma tabela para armazenar dados FILESTREAM  
  
1.  No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], clique em **Nova Consulta** para exibir o Editor de Consultas.  
  
2.  Copie o código [!INCLUDE[tsql](../../includes/tsql-md.md)] do exemplo a seguir no Editor de Consultas. Este código [!INCLUDE[tsql](../../includes/tsql-md.md)] cria uma tabela habilitada para FILESTREAM chamada Registros.  
  
3.  Para criar a tabela, clique em **Executar**.  
  
## <a name="example"></a>Exemplo  
 O exemplo de código a seguir mostra como criar uma tabela chamada `Records`. A coluna `Id` é uma coluna `ROWGUIDCOL` exigida para usar dados de FILESTREAM com APIs de Win32. A coluna `SerialNumber` é uma coluna `UNIQUE INTEGER`. A coluna `Chart` é uma coluna `FILESTREAM` usada para armazenar `Chart` no sistema de arquivos.  
  
> [!NOTE]  
>  Este tópico requer o banco de dados Archive que foi criado em [Criar um banco de dados habilitado para FILESTREAM](../../relational-databases/blob/create-a-filestream-enabled-database.md).  
  
 [!code-sql[FILESTREAM#FS_CreateTable](../../relational-databases/blob/codesnippet/tsql/create-a-table-for-stori_1.sql)]  
  
## <a name="see-also"></a>Consulte Também  
 [CREATE TABLE &#40;Transact-SQL&#41;](../../t-sql/statements/create-table-transact-sql.md)   
 [ALTER TABLE &#40;Transact-SQL&#41;](../../t-sql/statements/alter-table-transact-sql.md)  
  
  
