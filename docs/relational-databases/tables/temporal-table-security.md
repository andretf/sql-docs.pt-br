---
title: "Segurança de tabela temporal | Microsoft Docs"
ms.custom:
- SQL2016_New_Updated
ms.date: 02/21/2016
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- dbe-tables
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 60e5d6f6-a26d-4bba-aada-42e382bbcd38
caps.latest.revision: 9
author: CarlRabeler
ms.author: carlrab
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: f73cdc0f3a240e3d4c795fd67c2913b99748de4a
ms.contentlocale: pt-br
ms.lasthandoff: 06/22/2017

---
# <a name="temporal-table-security"></a>Segurança da tabela temporal
[!INCLUDE[tsql-appliesto-ss2016-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2016-asdb-xxxx-xxx-md.md)]

  Para compreender como a segurança se aplica às tabelas temporais, é importante entender as entidades de segurança que se aplicam a elas. Quando entender esses princípios, você estará pronto para saber mais sobre a segurança das instruções **CREATE TABLE**, **ALTER TABLE**e **SELECT** .  
  
## <a name="security-principles"></a>Princípios de segurança  
 A tabela a seguir descreve os princípios de segurança que se aplicam às tabelas temporais:  
  
|Princípio|Descrição|  
|---------------|-----------------|  
|Habilitar/desabilitar a determinação de versão do sistema requer privilégios mais altos sobre os objetos afetados|Habilitar e desabilitar SYSTEM_VERSIONING requer a permissão CONTROL na tabela atual e na tabela do histórico|  
|Os dados do histórico não podem ser modificados diretamente|Quando SYSTEM_VERSIONING está ATIVADO, os usuários não podem alterar os dados do histórico, independentemente de suas permissões reais na tabela atual ou na tabela do histórico. Isso inclui as modificações dos dados e do esquema.|  
|Consultar dados de histórico requer a permissão **SELECT** para a tabela do histórico|Ter apenas a permissão **SELECT** para a tabela atual não implica em ter a permissão **SELECT** para a tabela do histórico.|  
|Operações de auditoria de superfície que afetam a tabela do histórico de formas específicas:|A auditoria regular da tabela do histórico capta todas as tentativas diretas de acesso aos dados (bem-sucedidas ou não).<br /><br /> A permissão**SELECT** com a extensão de consulta temporal mostra que a tabela do histórico foi afetada com essa operação.<br /><br /> A tabela temporal**CREATE/ALTER** que expõe informações verificadas por essa permissão também ocorre na tabela do histórico. O arquivo de auditoria inclui um registro adicional para a tabela do histórico.<br /><br /> As operações de DML na superfície da tabela atual cuja tabela do histórico foi afetada, exceto additional_info, fornecem o contexto necessário (DML foi resultado de system_versioning).|  
  
## <a name="performing-schema-operations"></a>Executando operações de esquema  
 Quando SYSTEM_VERSIONING é definido como ATIVO, as operações de modificação do esquema são limitadas.  
  
### <a name="disallowed-alter-schema-operations"></a>Operações de esquema ALTER não permitidas  
  
|Operação|Tabela atual|Tabela de histórico|  
|---------------|-------------------|-------------------|  
|**DROP TABLE**|Não permitido|Não permitido|  
|**ALTER TABLE…SWITCH PARTITION**|Somente SWITCH IN (veja [Particionamento de tabelas temporais](../../relational-databases/tables/partitioning-with-temporal-tables.md))|Somente SWITCH OUT (veja [Particionamento de tabelas temporais](../../relational-databases/tables/partitioning-with-temporal-tables.md))|  
|**ALTER TABLE…DROP PERIOD**|Não permitido|-|  
|**ALTER TABLE…ADD PERIOD**|-|Não permitido|  
  
## <a name="allowed-alter-table-operations"></a>Operações ALTER TABLE permitidas  
  
|Operação|Current|Histórico|  
|---------------|-------------|-------------|  
|**ALTER TABLE…REBUILD**|Permitido (de forma independente)|Permitido (de forma independente)|  
|**CREATE INDEX**|Permitido (de forma independente)|Permitido (de forma independente)|  
|**CREATE STATISTICS**|Permitido (de forma independente)|Permitido (de forma independente)|  
  
## <a name="security-of-the-create-temporal-table-statement"></a>Segurança da instrução CREATE Temporal TABLE  
  
||Criar nova tabela de histórico|Reutilizar tabela de histórico existente|  
|-|------------------------------|----------------------------------|  
|Permissão necessária|Permissão**CREATE TABLE** no banco de dados<br /><br /> Permissão**ALTER** para os esquemas nos quais a tabela atual e a tabela do histórico são criadas.|Permissão**CREATE TABLE** no banco de dados<br /><br /> Permissão**ALTER** para o esquema no qual a tabela atual será criada.<br /><br /> Permissão**CONTROL** para a tabela de histórico especificada como parte da instrução **CREATE TABLE** que cria a tabela temporal|  
|Auditoria|A auditoria mostra que os usuários tentaram criar dois objetos. A operação pode falhar devido à falta de permissões para criar uma tabela no banco de dados ou devido à falta de permissões para alterar os esquemas dessa tabela.|Auditoria mostra que a tabela temporal foi criada. A operação pode falhar devido à falta de permissão para criar uma tabela no banco de dados, devido à falta de permissões para alterar o esquema da tabela temporal ou à falta de permissões na tabela do histórico.|  
  
## <a name="security-of-the-alter-temporal-table-set-systemversioning-onoff-statement"></a>Segurança da instrução ALTER Temporal TABLE SET (SYSTEM_VERSIONING ATIVADO/DESATIVADO)  
  
||Criar nova tabela de histórico|Reutilizar tabela de histórico existente|  
|-|------------------------------|----------------------------------|  
|Permissão necessária|Permissão**CONTROL** no banco de dados<br /><br /> Permissão**CREATE TABLE** no banco de dados<br /><br /> Permissão**ALTER** para os esquemas nos quais a tabela do histórico é criada|Permissão**CONTROL** para a tabela original que foi alterada<br /><br /> Permissão**CONTROL** para a tabela de histórico especificada como parte da instrução **ALTER TABLE** |  
|Auditoria|A auditoria mostra que a tabela temporal foi alterada e a tabela do histórico foi criada ao mesmo tempo. A operação pode falhar devido à falta de permissões para criar uma tabela no banco de dados, devido à falta de permissões para alterar o esquema da tabela de histórico ou à falta de permissão para modificar a tabela temporal.|A auditoria mostra que a tabela temporal foi alterada, mas a operação requer acesso para a tabela do histórico. A operação pode falhar devido à falta de permissões para a tabela do histórico ou para a tabela atual.|  
  
## <a name="security-of-select-statement"></a>Segurança da instrução SELECT  
 A permissão**SELECT** é inalterada para as instruções **SELECT** que não afetam a tabela do histórico. Para as instruções **SELECT** que afetam a tabela do histórico, a permissão **SELECT** é necessária para a tabela atual e para a tabela do histórico.  
  
## <a name="did-this-article-help-you-were-listening"></a>Este artigo foi útil para você? Estamos atentos  
 Quais são as informações que você está procurando? Você as localizou? Estamos atentos aos seus comentários para aprimorar o conteúdo. Envie seus comentários para [sqlfeedback@microsoft.com](mailto:sqlfeedback@microsoft.com?subject=Your%20feedback%20about%20the%20Temporal%20Table%20Security%20page)  
  
## <a name="see-also"></a>Consulte também  
 [Tabelas temporais](../../relational-databases/tables/temporal-tables.md)   
 [Introdução a Tabelas Temporais com Controle da Versão do Sistema](../../relational-databases/tables/getting-started-with-system-versioned-temporal-tables.md)   
 [Verificações de consistência do sistema de tabela temporal](../../relational-databases/tables/temporal-table-system-consistency-checks.md)   
 [Particionamento de Tabelas Temporais](../../relational-databases/tables/partitioning-with-temporal-tables.md)   
 [Considerações e limitações da tabela temporal](../../relational-databases/tables/temporal-table-considerations-and-limitations.md)   
 [Gerenciar a Retenção de Dados Históricos em Tabelas Temporais com Versão do Sistema](../../relational-databases/tables/manage-retention-of-historical-data-in-system-versioned-temporal-tables.md)   
 [Tabelas temporais com controle da versão do sistema com tabelas com otimização de memória](../../relational-databases/tables/system-versioned-temporal-tables-with-memory-optimized-tables.md)   
 [Funções e exibições de metadados de tabela temporal](../../relational-databases/tables/temporal-table-metadata-views-and-functions.md)  
  
  
