---
title: Rolando e buscando linhas (ODBC) | Microsoft Docs
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
- scrollable cursors [ODBC]
- fetches [ODBC], scrollable cursors
- cursors [ODBC], scrollable
- scrolling rows [ODBC]
ms.assetid: c43764cb-5841-4b89-9dc0-984a7488b3c1
caps.latest.revision: "7"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 304baeafe4918433ab5c9495d54e4cd8970eb628
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/21/2017
---
# <a name="scrolling-and-fetching-rows-odbc"></a>Rolando e buscando linhas (ODBC)
Ao usar um cursor rolável, aplicativos chamam **SQLFetchScroll** para posicionar os cursor e busca linhas. **SQLFetchScroll** oferece suporte à rolagem relativo (próximo, anterior e relativo  *n*  linhas), rolando absoluto (, sobrenome e linha  *n* ), e posicionamento pelo indicador. O *FetchOrientation* e *FetchOffset* argumentos **SQLFetchScroll** especificar qual conjunto de linhas para buscar, conforme mostrado nos diagramas a seguir.  
  
 ![Buscando o próximo, anterior, primeiro e último conjuntos de linhas](../../../odbc/reference/develop-app/media/pr20_2.gif "pr20_2")  
  
 **Em seguida, busca anterior, primeiro e últimos conjuntos de linhas**  
  
 ![Busca de linhas absoluta, relativa e indicada](../../../odbc/reference/develop-app/media/pr20_1.gif "pr20_1")  
  
 **Busca de conjuntos de linhas absolutos, relativos e indicadores**  
  
 **SQLFetchScroll** posiciona o cursor para a linha especificada e retorna as linhas no conjunto de linhas a partir dessa linha. Se o conjunto de linhas especificado sobrepõe o fim do conjunto de resultados, será retornado um conjunto de linhas parcial. Se o conjunto de linhas especificado sobrepõe o início do resultado definido, o primeiro conjunto de linhas no resultado do conjunto é normalmente retornado; Para obter detalhes completos, consulte o [SQLFetchScroll](../../../odbc/reference/syntax/sqlfetchscroll-function.md) descrição da função.  
  
 Em alguns casos, o aplicativo talvez queira posicionar o cursor sem recuperar todos os dados. Por exemplo, ele poderá testar se existe uma linha ou obtém apenas o indicador da linha, sem colocar outros dados através da rede. Para fazer isso, ele define o atributo de instrução SQL_ATTR_RETRIEVE_DATA para SQL_RD_OFF. A variável associada à coluna de indicador (se houver) é sempre atualizada, independentemente da configuração deste atributo de instrução.  
  
 Após recuperar o conjunto de linhas, o aplicativo pode chamar **SQLSetPos** para posicionar uma linha específica no conjunto de linhas ou de atualização de linhas no conjunto de linhas. Para obter mais informações sobre como usar **SQLSetPos**, consulte [atualizando dados com SQLSetPos](../../../odbc/reference/develop-app/updating-data-with-sqlsetpos.md).  
  
> [!NOTE]  
>  Há suporte para a rolagem no ODBC 2. *x* drivers por **SQLExtendedFetch**. Para obter mais informações, consulte [cursores em bloco, cursores roláveis e compatibilidade com versões anteriores](../../../odbc/reference/appendixes/block-cursors-scrollable-cursors-and-backward-compatibility.md)no Apêndice g: Driver diretrizes para compatibilidade com versões anteriores.
