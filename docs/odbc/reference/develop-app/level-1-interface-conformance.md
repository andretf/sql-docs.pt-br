---
title: "Conformidade de Interface de nível 1 | Microsoft Docs"
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
- interface conformance levels [ODBC]
- conformance levels [ODBC], interface
- level 1 interface conformance levels [ODBC]
ms.assetid: ee3f5c08-0583-4f3b-8354-ef71b6086a7e
caps.latest.revision: 6
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: c1f9e266e4379b2d1cfc9ee771ac49694cd3c58b
ms.contentlocale: pt-br
ms.lasthandoff: 09/09/2017

---
# <a name="level-1-interface-conformance"></a>Conformidade de Interface de nível 1
O nível de conformidade de interface de nível 1 inclui a funcionalidade do nível de conformidade do interface principal mais recursos adicionais, como transações, que geralmente estão disponíveis em um DBMS relacional OLTP. Um driver de interface – em conformidade com o nível 1 permite que o aplicativo faça o seguinte, além dos recursos em nível de conformidade a principal interface:  
  
|||  
|-|-|  
|101|Especifique o esquema do banco de dados de tabelas e modos de exibição (usando a nomeação de duas partes). (Para obter mais informações, consulte a nomeação de três partes recurso 201 no [nível 2 Interface conformidade](../../../odbc/reference/develop-app/level-2-interface-conformance.md).)|  
|102|Invocar true execução assíncrona de funções ODBC, onde aplicável funções ODBC são todos síncrono ou assíncrono em uma determinada conexão.|  
|103|Usar cursores roláveis e, assim, obter acesso a um conjunto de resultados em métodos em vez de somente avanço, chamando **SQLFetchScroll** com o *FetchOrientation* argumento que não seja SQL_FETCH_NEXT. (O SQL_FETCH_BOOKMARK *FetchOrientation* é no recurso 204 no [nível 2 Interface conformidade](../../../odbc/reference/develop-app/level-2-interface-conformance.md).)|  
|104|Obter chaves primárias das tabelas, chamando **SQLPrimaryKeys**.|  
|105|Use os procedimentos armazenados, por meio de sequência de escape ODBC para chamadas de procedimento e consultar o dicionário de dados sobre procedimentos armazenados, chamando **SQLProcedureColumns** e **SQLProcedures**. (O processo pelo qual os procedimentos são criados e armazenados na fonte de dados está fora do escopo deste documento.)|  
|106|Conectar a uma fonte de dados navegando interativamente os servidores disponíveis, chamando **SQLBrowseConnect**.|  
|107|Use funções ODBC em vez de instruções SQL para executar determinadas operações de banco de dados: **SQLSetPos** com SQL_POSITION e SQL_REFRESH.|  
|108|Obter acesso ao conteúdo de vários conjuntos de resultados gerados por lotes e procedimentos armazenados, chamando **SQLMoreResults**.|  
|109|Delimitar transações abrangência várias funções ODBC com atomicidade true e a capacidade de especificar SQL_ROLLBACK em **SQLEndTran**.|