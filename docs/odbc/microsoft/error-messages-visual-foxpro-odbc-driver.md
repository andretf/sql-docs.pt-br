---
title: Mensagens de erro (Driver ODBC do Visual FoxPro) | Microsoft Docs
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- error messages [ODBC], Visual FoxPro ODBC driver
- Visual FoxPro ODBC driver [ODBC], error messages
- SQLSTATE [ODBC]
- FoxPro ODBC driver [ODBC], error messages
ms.assetid: 58ea9734-4edf-44da-ba80-938aa7b340e4
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: e561aab3359acb1f236aea38e76da33289e630ef
ms.contentlocale: pt-br
ms.lasthandoff: 09/09/2017

---
# <a name="error-messages-visual-foxpro-odbc-driver"></a>Mensagens de erro (Driver ODBC do Visual FoxPro)
Quando ocorre um erro, o driver do Visual FoxPro retorna as seguintes informações:  
  
-   O número de erro nativo e o texto da mensagem de erro  
  
-   O texto da mensagem de erro e SQLSTATE (um código de erro ODBC)  
  
 Acessar essas informações de erro chamando [SQLError](../../odbc/microsoft/sqlerror-visual-foxpro-odbc-driver.md).  
  
## <a name="native-errors"></a>Erros nativos  
 Para erros que ocorrem na fonte de dados, o driver do Visual FoxPro retorna o número de erro nativo e o texto da mensagem de erro. Para obter uma lista de números de erro nativo, consulte [Visual FoxPro ODBC Driver nativo mensagens de erro](../../odbc/microsoft/visual-foxpro-odbc-driver-native-error-messages.md).  
  
## <a name="sqlstate-odbc-error-codes"></a>SQLSTATE (códigos de erro ODBC)  
 Para erros que são detectados e retornados pelo driver do Visual FoxPro, o driver mapeia o número de erro nativo retornado para o SQLSTATE apropriado. Se um número de erro nativo não tiver um código de erro ODBC para mapear para, o driver do Visual FoxPro retornará SQLSTATE S1000 (erro geral).  
  
 Para obter uma lista de valores SQLSTATE gerado pelo Visual FoxPro ODBC Driver para erros do Visual FoxPro correspondentes, consulte [códigos de erro de ODBC](../../odbc/microsoft/odbc-error-codes-visual-foxpro-odbc-driver.md).  
  
## <a name="syntax"></a>Sintaxe  
 Mensagens de erro têm o seguinte formato:  
  
 **[** *fornecedor* **] [** *ODBC_component* **]** *error_message*  
  
 Os prefixos de colchetes ([]) identificam a origem do erro, conforme definido na tabela a seguir.  
  
|Fonte de dados|Prefixo|Valor|  
|-----------------|------------|-----------|  
|Gerenciador de Driver|[fornecedor]<br />[ODBC_component]<br />[data_source]|[Microsoft]<br />[Gerenciador de Driver ODBC]<br />N/A|  
|Driver do Visual FoxPro|fornecedor]<br />[ODBC_component]<br />[data_source]|[Microsoft]<br />[Driver do Visual FoxPro ODBC]<br />N/A|  
  
 Por exemplo, se o Driver de ODBC do Visual FoxPro não foi possível encontrar a Employee. dbf de arquivo, ele pode retornar a seguinte mensagem de erro:  
  
 "[*Microsoft*] [*Driver ODBC do Visual FoxPro*] não existe arquivo 'Employee. dbf'"