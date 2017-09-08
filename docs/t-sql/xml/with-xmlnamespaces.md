---
title: WITH XMLNAMESPACES (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 06/10/2016
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- WITH_XMLNAMESPACES_TSQL
- WITH XMLNAMESPACES
dev_langs:
- TSQL
helpviewer_keywords:
- adding XML namespaces
- XML namespace declarations [SQL Server]
- clauses [SQL Server], WITH XMLNAMESPACES
- WITH XMLNAMESPACES clause
- declaring XML namespaces
ms.assetid: 3b32662b-566f-454d-b7ca-e247002a9a0b
caps.latest.revision: 17
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: c34d67133c083c0dba5325548971997e8b95d6c5
ms.contentlocale: pt-br
ms.lasthandoff: 09/01/2017

---
# <a name="with-xmlnamespaces"></a>WITH XMLNAMESPACES
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Declara um ou mais namespaces XML.  
  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Convenções da sintaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
WITH XMLNAMESPACES ( <XML namespace declaration item>  
[ { , <XML namespace declaration item> }...] )   
  
<XML namespace declaration item> ::=  
<xml_namespace_uri> AS <xml_namespace_prefix>  
| <XML default namespace declaration item>  
<xml_namespace_uri> ::= <character string literal>  
```  
  
```  
  
<xml_namespace_prefix> ::= <identifier>  
```  
  
```  
  
<XML default namespace declaration item> ::=  
DEFAULT <xml_namespace_uri>  
  
```  
  
## <a name="arguments"></a>Argumentos  
 *xml_namespace_uri*  
 Um URI que identifica o namespace XML que está sendo declarado. *xml_namespace_uri* é uma cadeia de caracteres SQL.  
  
 *xml_namespace_prefix*  
 Especifica um prefixo a ser mapeado e associado com o valor URI de namespace especificado em *xml_namespace_uri*. *xml_namespace_prefix* deve ser um [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] identificador.  
  
## <a name="remarks"></a>Comentários  
 Quando você usa a cláusula WITH XMLNAMESPACES em uma instrução que também inclui uma expressão de tabela comum, a cláusula WITH XMLNAMESPACES deve preceder a expressão na instrução.  
  
 Os seguintes itens são regras gerais de sintaxe que se aplicam quando você usa a cláusula WITH XMLNAMESPACES:  
  
-   Cada declaração de namespace XML deve conter pelo menos um item de declaração de namespace padrão XML.  
  
-   Cada prefixo de namespace XML usado deve ser um NCName (non-colonized name) no qual o dois-pontos (:) não faz parte do nome.  
  
-   Você não pode definir um prefixo de namespace duas vezes.  
  
-   Prefixos de namespace XML e URIs diferenciam maiúsculas de minúsculas.  
  
-   O prefixo de namespace XML `xmlns` não pode ser declarado.  
  
-   O prefixo de namespace XML `xml` não pode ser substituído por um namespace diferente do URI de namespaces `'http://www.w3.org/XML/1998/namespace'`, e este URI não pode receber um prefixo diferente.  
  
-   O prefixo de namespace XML `xsi` não pode ser redeclarado quando a diretiva ELEMENTS XSINIL está sendo usada na consulta.  
  
-   Os valores de cadeia de caracteres URI são codificados de acordo com a página de código de agrupamento de banco de dados atual e são convertidos internamente em Unicode.  
  
-   O namespace XML URI será espaço em branco reduzido segundo espaço em branco XSD recolher regras que são usadas para **xs: anyURI**. Além disso, observe que são executados definições de entidade ou cancelamentos de definição em valores URI de namespaces XML.  
  
-   Será verificado no URI de namespace XML se há caracteres XML 1.0 que não sejam válidos, e será gerado um erro se algum for encontrado (por exemplo, U+0007).  
  
-   O URI de namespace XML (após todo o espaço em branco ser reduzido) não pode ser uma cadeia de caracteres de comprimento ou ocorrerá um erro relacionado a URI de namespace vazio inválido.  
  
-   A palavra-chave XMLNAMESPACES é reservada no contexto da cláusula WITH.  
  
## <a name="examples"></a>Exemplos  
 Para obter exemplos, consulte [adicionar Namespaces a consultas com WITH XMLNAMESPACES](../../relational-databases/xml/add-namespaces-to-queries-with-with-xmlnamespaces.md).  
  
## <a name="see-also"></a>Consulte também  
 [Referência de linguagem XQuery &#40;SQL Server&#41;](../../xquery/xquery-language-reference-sql-server.md)  
  
  
