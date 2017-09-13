---
title: Objetos com suporte no Assistente para Gerar Scripts | Microsoft Docs
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 071eb2cb-f073-41ca-9f4d-11d3b8803495
caps.latest.revision: 7
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: a4f4804fbc59d9744eaa819ba8f39e1be79de647
ms.contentlocale: pt-br
ms.lasthandoff: 06/22/2017

---
# <a name="objects-supported-by-the-generate-scripts-wizard"></a>Objetos com suporte no Assistente para Gerar Scripts
  O Assistente para Gerar e Publicar Scripts oferece suporte a um subconjunto dos objetos com suporte no [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].  
  
## <a name="supported-objects"></a>Objetos com suporte  
 A seguinte tabela lista os objetos que podem ser publicados e as versões com suporte do Assistente para Gerar e Publicar Scripts.  
  
||||||  
|-|-|-|-|-|  
|Função de aplicativo|Função de banco de dados|Esquema|Agregação definida pelo usuário|Exibição*|  
|Assembly|Restrição DEFAULT|Procedimento armazenado*|Tipo de dados definido pelo usuário|Coleção de esquemas XML|  
|Restrição CHECK|Catálogo de texto completo|Sinônimo|Função definida pelo usuário||  
|Procedimento armazenado CLR (common language runtime)*|Índice|Table|Tabela definida pelo usuário||  
|Função CLR definida pelo usuário|Regra|Usuário**|Tipo definido pelo usuário||  
  
 *Publicado sem criptografia.  
  
 **Qualquer usuário que não seja do sistema existente no banco de dados será publicado como Funções.  
  
  