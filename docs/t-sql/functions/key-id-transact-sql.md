---
title: KEY_ID (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- Key_ID
- Key_ID_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- identification numbers [SQL Server], symmetric keys
- KEY_ID function
- symmetric keys [SQL Server], IDs
- IDs [SQL Server], symmetric keys
ms.assetid: d7309542-dbbe-41dc-b42e-5d9a1c8b4838
caps.latest.revision: 27
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: bb4684105e8f8e4a13c1df77437271c1e820dce2
ms.contentlocale: pt-br
ms.lasthandoff: 09/01/2017

---
# <a name="keyid-transact-sql"></a>KEY_ID (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

  Retorna a ID de uma chave simétrica no banco de dados atual.  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Convenções da sintaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
Key_ID ( 'Key_Name' )  
```  
  
## <a name="arguments"></a>Argumentos  
 **'** *Key_Name* **'**  
 Nome de uma chave simétrica no banco de dados.  
  
## <a name="return-types"></a>Tipos de retorno  
 **int**  
  
## <a name="remarks"></a>Comentários  
 O nome de uma chave temporária deve começar com um sinal de número (#).  
  
## <a name="permissions"></a>Permissões  
 Como as chaves temporárias estão disponíveis somente na sessão em que foram criadas, nenhuma permissão é necessária para acessá-las. Para acessar uma chave que não é temporária, o chamador precisa de algumas permissões na chave e não deve ter a permissão VIEW negada na chave.  
  
## <a name="examples"></a>Exemplos  
  
### <a name="a-returning-the-id-of-a-symmetric-key"></a>A. Retornando a ID de uma chave simétrica  
 O exemplo a seguir retorna a ID de uma chave chamada `ABerglundKey1`.  
  
```  
SELECT KEY_ID('ABerglundKey1');  
```  
  
### <a name="b-returning-the-id-of-a-temporary-symmetric-key"></a>B. Retornando a ID de uma chave simétrica temporária  
 O exemplo a seguir retorna a ID de uma chave simétrica temporária. Observe que `#` vem antes do nome da chave.  
  
```  
SELECT KEY_ID('#ABerglundKey2');  
```  
  
## <a name="see-also"></a>Consulte também  
 [KEY_GUID &#40; Transact-SQL &#41;](../../t-sql/functions/key-guid-transact-sql.md)   
 [CREATE SYMMETRIC KEY &#40;Transact-SQL&#41;](../../t-sql/statements/create-symmetric-key-transact-sql.md)   
 [symmetric_keys &#40; Transact-SQL &#41;](../../relational-databases/system-catalog-views/sys-symmetric-keys-transact-sql.md)   
 [sys.key_encryptions &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-key-encryptions-transact-sql.md)   
 [Hierarquia de criptografia](../../relational-databases/security/encryption/encryption-hierarchy.md)  
  
  