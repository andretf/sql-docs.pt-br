---
title: SQLGetStmtOption (Driver ODBC do Visual FoxPro) | Microsoft Docs
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
helpviewer_keywords: SQLGetStmtOption function [ODBC], Visual FoxPro ODBC Driver
ms.assetid: 984a8b1d-f12c-420c-8be4-f555114c764b
caps.latest.revision: "5"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 9042a1a951d08c60e8dc795cd58f2a525cf39cda
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/21/2017
---
# <a name="sqlgetstmtoption-visual-foxpro-odbc-driver"></a>SQLGetStmtOption (Driver ODBC do Visual FoxPro)
> [!NOTE]  
>  Este tópico contém informações específicas do Driver ODBC do Visual FoxPro. Para obter informações gerais sobre esta função, consulte o tópico apropriado em [referência da API ODBC](../../odbc/reference/syntax/odbc-api-reference.md).  
  
 Suporte: completo  
  
 Conformidade de API de ODBC: Um nível  
  
 Retorna a configuração atual de uma opção de instrução.  
  
|*FOption*|Retorna|  
|---------------|-------------|  
|SQL_GET_BOOKMARK|valor inteiro de 32 bits que é o indicador para o número de registro atual|  
|SQL_ROW_NUMBER|Especifica a posição da linha atual em que o resultado de inteiro de 32 bits definido|  
|SQL_TRANSLATE_DLL|Erro: "o Driver não funciona"|  
  
 O Driver de ODBC do Visual FoxPro não tem nenhuma conversão DLLs.  
  
 Para obter mais informações, consulte [SQLGetStmtOption](../../odbc/reference/syntax/sqlgetstmtoption-function.md) no *referência do programador de ODBC*.
