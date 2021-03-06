---
title: sp_delete_firewall_rule (banco de dados do SQL Azure) | Microsoft Docs
ms.custom: 
ms.date: 07/27/2016
ms.prod: 
ms.prod_service: sql-database, sql-data-warehouse
ms.reviewer: 
ms.service: sql-database
ms.component: system-stored-procedures
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- sp_delete_firewall_rule_TSQL
- sp_delete_firewall_rule
- sys.sp_delete_firewall_rule
- sys.sp_delete_firewall_rule_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sp_delete_firewall_rule procedure
ms.assetid: cf93eed1-ba97-4850-9fcc-b9c5a9317908
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: aa2815c27668bc680ce5da72b6713e29b517f43b
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="spdeletefirewallrule-azure-sql-database"></a>sp_delete_firewall_rule (Banco de Dados SQL do Azure)
[!INCLUDE[tsql-appliesto-xxxxxx-asdb-asdw-xxx-md](../../includes/tsql-appliesto-xxxxxx-asdb-asdw-xxx-md.md)]

  Remove as configurações de firewall no nível do servidor do [!INCLUDE[ssSDS](../../includes/sssds-md.md)]. Este procedimento armazenado só está disponível no banco de dados mestre para o logon principal do nível do servidor.  

  
## <a name="syntax"></a>Sintaxe  
  
```  
sp_delete_firewall_rule [@name =] 'name' 
[ ; ] 
```  
  
## <a name="arguments"></a>Argumentos  
 O argumento do procedimento armazenado é:  
  
 [@name =] '*nome*'  
 O nome da configuração de firewall de nível de servidor que será removida. *nome* é **nvarchar (128)** sem nenhum padrão.  
  
## <a name="remarks"></a>Comentários  
 Em [!INCLUDE[ssSDS](../../includes/sssds-md.md)], dados de logon necessárias para autenticar uma conexão e as regras de firewall de nível de servidor são armazenados em cache temporariamente em cada banco de dados. Esse cache é atualizado periodicamente. Para forçar uma atualização do cache de autenticação e certifique-se de que um banco de dados tem a versão mais recente da tabela de logons, execute [DBCC FLUSHAUTHCACHE &#40; Transact-SQL &#41; ](../../t-sql/database-console-commands/dbcc-flushauthcache-transact-sql.md).  
  
## <a name="permissions"></a>Permissões  
 Somente o logon de entidade de segurança no nível do servidor criado pelo processo de provisionamento pode excluir as regras de firewall de nível de servidor. O usuário deve estar conectado ao banco de dados mestre para executar sp_delete_firewall_rule.  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir remove a configuração de firewall de nível de servidor chamada 'Configuração de exemplo 1'. Execute a instrução no banco de dados mestre virtual.  
  
```   
EXEC sp_delete_firewall_rule N'Example setting 1';   
```  
  
## <a name="see-also"></a>Consulte também  
 [Firewall de banco de dados SQL do Azure](https://azure.microsoft.com/documentation/articles/sql-database-firewall-configure/)   
 [Como: definir configurações de Firewall (banco de dados do SQL Azure)](https://azure.microsoft.com/documentation/articles/sql-database-configure-firewall-settings/)   
 [sp_set_firewall_rule &#40; Banco de dados SQL do Azure &#41;](../../relational-databases/system-stored-procedures/sp-set-firewall-rule-azure-sql-database.md)   
 [sys. firewall_rules &#40; Banco de dados SQL do Azure &#41;](../../relational-databases/system-catalog-views/sys-firewall-rules-azure-sql-database.md)  
  
  


