---
title: STIsEmpty (tipo de dados geography) | Microsoft Docs
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database
ms.service: 
ms.component: t-sql|spatial-geography
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- STIsEmpty_TSQL
- STIsEmpty (geography Data Type)
dev_langs:
- TSQL
helpviewer_keywords:
- STIsEmpty method
ms.assetid: 4cbc66e3-9035-4ecf-8f5a-6301f168c26c
caps.latest.revision: 
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: b878e65415f238e7a7451dc238d1677eddb6ac4d
ms.sourcegitcommit: 9e6a029456f4a8daddb396bc45d7874a43a47b45
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/25/2018
---
# <a name="stisempty-geography-data-type"></a>STIsEmpty (tipo de dados geography)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  Retornará 1 se uma instância de **geography** estiver vazia. Retornará 0 se uma instância de **geography** não estiver vazia.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
.STIsEmpty ( )  
```  
  
## <a name="return-types"></a>Tipos de retorno  
 Tipo de retorno do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]: **bit**  
  
 Tipo de retorno do CLR: **SqlBoolean**  
  
## <a name="examples"></a>Exemplos  
 O exemplo a seguir cria uma instância de `geography` vazia e usa `STIsEmpty()` para verificar se a instância está vazia.  
  
```  
DECLARE @g geography;  
SET @g = geography::STGeomFromText('POLYGON EMPTY', 4326);  
SELECT @g.STIsEmpty();  
```  
  
## <a name="see-also"></a>Consulte Também  
 [Métodos OGC em instâncias geography](../../t-sql/spatial-geography/ogc-methods-on-geography-instances.md)  
  
  
