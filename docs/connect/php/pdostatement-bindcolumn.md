---
title: PDOStatement::bindColumn | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: ''
ms.component: php
ms.reviewer: ''
ms.suite: sql
ms.technology:
- drivers
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bbdcea53-d23d-4769-89a0-95c7cf4d5390
caps.latest.revision: ''
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: d5f85c59eec602a483dd68da5df030f4d5cf18d6
ms.sourcegitcommit: 2e130e9f3ce8a7ffe373d7fba8b09e937c216386
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="pdostatementbindcolumn"></a>PDOStatement::bindColumn
[!INCLUDE[Driver_PHP_Download](../../includes/driver_php_download.md)]

Associa uma variável a uma coluna em um conjunto de resultados.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
bool PDOStatement::bindColumn($column, &$param[, $type[, $maxLen[, $driverdata ]]] );  
```  
  
#### <a name="parameters"></a>Parâmetros  
$*coluna*: O número (misto) da coluna (índice de base 1) ou o nome da coluna no conjunto de resultados.  
  
&$*param*: O nome (misto) da variável PHP à qual a coluna será associada.  
  
$*tipo*: O tipo de dados opcional do parâmetro, representado por uma constante PDO::PARAM_ *.  
  
$*maxLen*: inteiro opcional, não usado pelos Drivers da Microsoft para PHP para SQL Server.  
  
$*driverdata*: mistos opcionais parâmetros para o driver. Por exemplo, você poderia especificar PDO::SQLSRV_ENCODING_UTF8 para associar a coluna a uma variável como uma cadeia de caracteres codificada em UTF-8.  
  
## <a name="return-value"></a>Valor de retorno  
TRUE se bem-sucedido; caso contrário, FALSE.  
  
## <a name="remarks"></a>Remarks  
O suporte para PDO foi adicionado na versão 2.0 dos [!INCLUDE[ssDriverPHP](../../includes/ssdriverphp_md.md)].  
  
## <a name="example"></a>Exemplo  
Este exemplo mostra como uma variável pode ser associada a uma coluna em um conjunto de resultados.  
  
```  
<?php  
$database = "AdventureWorks";  
$server = "(local)";  
$conn = new PDO( "sqlsrv:server=$server ; Database = $database", "", "");  
  
$query = "SELECT Title, FirstName, EmailAddress FROM Person.Contact where LastName = 'Estes'";  
$stmt = $conn->prepare($query);  
$stmt->execute();  
  
$stmt->bindColumn('EmailAddress', $email);  
while ( $row = $stmt->fetch( PDO::FETCH_BOUND ) ){  
   echo "$email\n";  
}  
?>  
```  
  
## <a name="see-also"></a>Consulte também  
[PDOStatement Class](../../connect/php/pdostatement-class.md)

[PDO](http://php.net/manual/book.pdo.php)  
  
