---
title: "Função do Driver | Microsoft Docs"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: odbc
ms.reviewer: 
ms.suite: sql
ms.technology: drivers
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- driver error checking [ODBC]
- diagnostic information [ODBC], driver error checking
ms.assetid: cac64c24-a27d-4884-96c0-ea7988351711
caps.latest.revision: "5"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 7381b239b87d4979545504e01f552a9be21fd694
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/21/2017
---
# <a name="role-of-the-driver"></a>Função do Driver
O driver verifica todos os erros e avisos não verificados pelo Gerenciador de Driver e ordena os registros de status que ele gera. (Um ODBC 2. *x* driver não ordena os registros de status.) Isso inclui erros e avisos em truncamento de dados, a conversão de dados, a sintaxe e algumas transições de estado. O driver também pode verificar erros e avisos parcialmente verificados pelo Gerenciador de Driver. Por exemplo, embora o Gerenciador de Driver verifica se o valor de *operação* na **SQLSetPos** for válido, o driver deve verificar se há suporte.  
  
 O driver também mapeia *erros nativos* — ou seja, os erros retornados pela fonte de dados — para SQLSTATEs. Por exemplo, o driver pode mapear um número de diferentes erros nativos para SQL sintaxe inválida para SQLSTATE 42000 (sintaxe ou violação de acesso). O driver retorna o número de erro nativo no campo SQL_DIAG_NATIVE do registro de status. Documentação do driver deve mostrar como erros e avisos são mapeados da fonte de dados para argumentos em **SQLGetDiagRec** e **SQLGetDiagField**.
