---
title: Palavras reservadas para MDX | Microsoft Docs
ms.custom: 
ms.date: 03/02/2016
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- kbMDX
helpviewer_keywords:
- reserved words [MDX]
- Multidimensional Expressions [Analysis Services], reserved words
- MDX [Analysis Services], reserved words
ms.assetid: 8d059a8c-d578-4713-a615-2404d94ce32d
caps.latest.revision: 26
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: 8bec4b29379b4ad31c8da4074786e95dc058ad10
ms.contentlocale: pt-br
ms.lasthandoff: 08/02/2017

---
# <a name="mdx-reserved-words"></a>Palavras reservadas para MDX
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  A tabela a seguir contém palavras reservadas para serem usadas pela linguagem MDX. Em MDX, não use essas palavras como parte de nenhum identificador, como o nome de um cubo ou o nome de uma função definida pelo usuário.  
  
|||||  
|-|-|-|-|  
|ABSOLUTE|DESC|LEAVES|SELF_BEFORE_AFTER|  
|ACTIONPARAMETERSET|DESCENDANTS|LEVEL|SESSION|  
|ADDCALCULATEDMEMBERS|DESCRIPTION|LEVELS|SET|  
|AFTER|DIMENSION|LINKMEMBER|SETTOARRAY|  
|AGGREGATE|DIMENSIONS|LINREGINTERCEPT|SETTOSTR|  
|ALL|DISTINCT|LINREGPOINT|SORT|  
|ALLMEMBERS|DISTINCTCOUNT|LINREGR2|STDDEV|  
|ANCESTOR|DRILLDOWNLEVEL|LINREGSLOPE|STDDEVP|  
|ANCESTORS|DRILLDOWNLEVELBOTTOM|LINREGVARIANCE|STDEV|  
|AND|DRILLDOWNLEVELTOP|LOOKUPCUBE|STDEVP|  
|AS|DRILLDOWNMEMBER|MAX|STORAGE|  
|ASC|DRILLDOWNMEMBERBOTTOM|MEASURE|STRIPCALCULATEDMEMBERS|  
|ASCENDANTS|DRILLDOWNMEMBERTOP|MEDIAN|STRTOMEMBER|  
|AVERAGE|DRILLUPLEVEL|MEMBER|STRTOSET|  
|AXIS|DRILLUPMEMBER|MEMBERS|STRTOTUPLE|  
|BASC|DROP|MEMBERTOSTR|STRTOVAL|  
|BDESC|EMPTY|MIN|STRTOVALUE|  
|BEFORE|END|MTD|SUBSET|  
|BEFORE_AND_AFTER|ERROR|NAME|SUM|  
|BOTTOMCOUNT|EXCEPT|NAMETOSET|TAIL|  
|BOTTOMPERCENT|EXCLUDEEMPTY|NEST|THIS|  
|BOTTOMSUM|EXTRACT|NEXTMEMBER|TOGGLEDRILLSTATE|  
|BY|FALSE|NO_ALLOCATION|TOPCOUNT|  
|CACHE|FILTER|NO_PROPERTIES|TOPPERCENT|  
|CALCULATE|FIRSTCHILD|NON|TOPSUM|  
|CALCULATION|FIRSTSIBLING|NONEMPTYCROSSJOIN|TOTALS|  
|CALCULATIONCURRENTPASS|FOR|NOT_RELATED_TO_FACTS|trEE|  
|CALCULATIONPASSVALUE|FREEZE|NULL|TRUE|  
|CALCULATIONS|FROM|ON|TUPLETOSTR|  
|CALL|GENERATE|OPENINGPERIOD|TYPE|  
|CELL|GLOBAL|OU|UNION|  
|CELLFORMULASETLIST|GROUP|PAGES|UNIQUE|  
|CHAPTERS|GROUPING|PARALLELPERIOD|UNIQUENAME|  
|CHILDREN|HEAD|PARENT|UPDATE|  
|CLEAR|HIDDEN|PASS|USE|  
|CLOSINGPERIOD|HIERARCHIZE|PERIODSTODATE|USE_EQUAL_ALLOCATION|  
|COALESCEEMPTY|HIERARCHY|POST|USE_WEIGHTED_ALLOCATION|  
|COLUMN|IGNORE|PREDICT|USE_WEIGHTED_INCREMENT|  
|COLUMNS|IIF|PREVMEMBER|USERNAME|  
|CORRELATION|INCLUDEEMPTY|PROPERTIES|VALIDMEASURE|  
|COUNT|INDEX|PROPERTY|VALUE|  
|COUSIN|INTERSECT|QTD|VAR|  
|COVARIANCE|IS|RANK|VARIANCE|  
|COVARIANCEN|ISANCESTOR|RECURSIVE|VARIANCEP|  
|CREATE|ISEMPTY|RELATIVE|VARP|  
|CREATEPROPERTYSET|ISGENERATION|ROLLUPCHILDREN|VISUAL|  
|CREATEVIRTUALDIMENSION|ISLEAF|ROOT|VISUALTOTALS|  
|CROSSJOIN|ISSIBLING|ROWS|WHERE|  
|CUBE|ITEM|SCOPE|com|  
|CURRENT|LAG|SECTIONS|WTD|  
|CURRENTCUBE|LASTCHILD|SELECT|XOR|  
|CURRENTMEMBER|LASTPERIODS|SELF|YTD|  
|DEFAULT_MEMBER|LASTSIBLING|SELF_AND_AFTER||  
|DEFAULTMEMBER|LEAD|SELF_AND_BEFORE||  
  
## <a name="see-also"></a>Consulte também  
 [Palavras-chave reservadas &#40; Sintaxe MDX &#41;](../mdx/reserved-keywords-mdx-syntax.md)   
 [Referência de linguagem MDX &#40; MDX &#41;](../mdx/mdx-language-reference-mdx.md)  
  
  
