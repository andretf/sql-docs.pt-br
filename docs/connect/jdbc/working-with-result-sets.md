---
title: Trabalhando com conjuntos de resultados | Microsoft Docs
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: jdbc
ms.reviewer: 
ms.suite: sql
ms.technology: drivers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4fc4b1c6-3075-4ad7-9244-865d9ede7ae6
caps.latest.revision: "10"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 9d90a11fa3c617f529d4bc13e3b80f5755423310
ms.sourcegitcommit: 2713f8e7b504101f9298a0706bacd84bf2eaa174
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2017
---
# <a name="working-with-result-sets"></a>Trabalhando com conjuntos de resultados
[!INCLUDE[Driver_JDBC_Download](../../includes/driver_jdbc_download.md)]

  Quando você trabalha com os dados contidos em um [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] banco de dados, um método de manipulação de dados é usar um conjunto de resultados. O [!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)] suporta o uso de resultado define por meio de [SQLServerResultSet](../../connect/jdbc/reference/sqlserverresultset-class.md) objeto. Usando o objeto SQLServerResultSet, recuperar os dados retornados por uma instrução SQL ou procedimento armazenado, atualizar os dados conforme necessário e, em seguida, persisti-dados de volta para o banco de dados.  
  
 Além disso, o objeto SQLServerResultSet fornece métodos para navegar pelas respectivas linhas de dados, obter ou definir os dados que ele contém e estabelecer diversos níveis de sensibilidade a alterações no banco de dados subjacente.  
  
> [!NOTE]  
>  Para obter mais informações sobre como gerenciar conjuntos de resultados, inclusive sua sensibilidade a alterações, consulte [Gerenciando conjuntos de resultados com o Driver JDBC](../../connect/jdbc/managing-result-sets-with-the-jdbc-driver.md).  
  
 Os tópicos nesta seção descrevem maneiras diferentes que você pode usar um conjunto de resultados para manipular os dados contidos em um [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] banco de dados.  
  
## <a name="in-this-section"></a>Nesta seção  
  
|Tópico|Description|  
|-----------|-----------------|  
|[Exemplo de recuperação de dados do conjunto de resultados](../../connect/jdbc/retrieving-result-set-data-sample.md)|Descreve como usar um conjunto de resultados para recuperar dados de um [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] de banco de dados e exibi-lo.|  
|[Exemplo de modificação de dados do conjunto de resultados](../../connect/jdbc/modifying-result-set-data-sample.md)|Descreve como usar um conjunto de resultados para inserir, recuperar e modificar dados em um [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] banco de dados.|  
|[Exemplo de armazenamento de dados do conjunto de resultados em cache](../../connect/jdbc/caching-result-set-data-sample.md)|Descreve como usar um conjunto de resultados para recuperar grandes quantidades de dados de um [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] banco de dados e para controlar como dados é armazenada em cache no cliente.|  
  
## <a name="see-also"></a>Consulte também  
 [Aplicativos de exemplo do JDBC Driver](../../connect/jdbc/sample-jdbc-driver-applications.md)  
  
  
