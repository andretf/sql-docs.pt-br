---
title: MSSQLSERVER_1904 | Microsoft Docs
ms.custom: 
ms.date: 04/04/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: errors-events
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
helpviewer_keywords:
- 1904 (Database Engine error)
ms.assetid: 2a35d57d-74e2-45a2-8f67-3f2e51d69712
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 4f2267a8410f134aafad64634e9682e05b2ed466
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="mssqlserver1904"></a>MSSQLSERVER_1904
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  
## <a name="details"></a>Detalhes  
  
|||  
|-|-|  
|Nome do produto|SQL Server|  
|ID do evento|1904|  
|Origem do evento|MSSQLSERVER|  
|Componente|SQLEngine|  
|Nome simbólico|KEYCOUNT|  
|Texto da mensagem|O %S_MSG '%.*ls' na tabela '%.\*ls' tem %d nomes de coluna na lista de chaves %S_MSG. O limite máximo para lista de colunas de chaves de índice ou de estatísticas é de %d.|  
  
## <a name="explanation"></a>Explicação  
A lista de colunas de chaves do índice ou das estatísticas especificadas excede o número máximo de colunas permitidas.  
  
## <a name="user-action"></a>Ação do usuário  
Modifique a lista de colunas de chaves para incluir não mais do que o número máximo de colunas especificado.  
  
Para índices não clusterizados, considere a possibilidade de usar a cláusula INCLUDE na instrução CREATE INDEX para adicionar colunas ao índice como colunas não chave. Com esse método, você evita exceder o limite atual de tamanho de índice, que é de até 16 colunas de chave. Para obter mais informações, consulte [Create Indexes with Included Columns](~/relational-databases/indexes/create-indexes-with-included-columns.md).  
  
## <a name="see-also"></a>Consulte também  
[CREATE INDEX &#40;Transact-SQL&#41;](~/t-sql/statements/create-index-transact-sql.md)  
[CREATE STATISTICS &#40;Transact-SQL&#41;](~/t-sql/statements/create-statistics-transact-sql.md)  
  
