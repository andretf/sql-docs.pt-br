---
title: sp_validate_replica_hosts_as_publishers (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-stored-procedures
ms.reviewer: 
ms.suite: sql
ms.technology:
- replication
ms.tgt_pltfrm: 
ms.topic: language-reference
applies_to:
- SQL Server
f1_keywords:
- sp_validate_replica_hosts_as_publishers_TSQL
- sp_validate_replica_hosts_as_publishers
helpviewer_keywords:
- sp_validate_replica_hosts_as_publishers
ms.assetid: 45001fc9-2dbd-463c-af1d-aa8982d8c813
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 2f4cd7135f5773300e1d95291c778463cece6a85
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="spvalidatereplicahostsaspublishers-transact-sql"></a>sp_validate_replica_hosts_as_publishers (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2012-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2012-xxxx-xxxx-xxx-md.md)]

  **sp_validate_replica_hosts_as_publishers** é uma extensão de **sp_validate_redirected_publisher** que permite que todas as réplicas secundárias ser validada, em vez de apenas a réplica primária atual. **sp_validate_replicat_hosts_as_publisher** valida uma topologia de replicação AlwaysOn inteira. **sp_validate_replica_hosts_as_publishers** deve ser executado diretamente no distribuidor usando uma sessão de área de trabalho remota para evitar um erro de segurança de salto duplo (21892).  
  
 ![Ícone de link do tópico](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Convenções da sintaxe Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
sp_validate_replica_hosts_as_publishers   
    [ @original_publisher = ] 'original_publisher',  
    [ @publisher_db = ] 'database_name',   
    [ @redirected_publisher = ] 'new_publisher' output  
```  
  
## <a name="arguments"></a>Argumentos  
 [  **@original_publisher**  =] **'***original_publisher***'**  
 O nome da instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que publicou originalmente o banco de dados. *original_publisher* é **sysname**, sem padrão.  
  
 [  **@publisher_db**  =] **'***publisher_db***'**  
 O nome do banco de dados que está sendo publicado. *publisher_db* é **sysname**, sem padrão.  
  
 [  **@redirected_publisher**  =] **'***redirected_publisher***'**  
 O destino de redirecionamento quando **sp_redirect_publisher** foi chamado para o publicador original/publicado par de banco de dados. *redirected_publisher* é **sysname**, sem padrão.  
  
## <a name="return-code-values"></a>Valores do código de retorno  
 **0** (êxito) ou **1** (falha)  
  
## <a name="result-sets"></a>Conjuntos de resultados  
 Nenhum.  
  
## <a name="remarks"></a>Comentários  
 Se não houver nenhuma entrada para o publicador e o banco de dados de publicação, **sp_validate_redirected_publisher** retorna um valor nulo para o parâmetro de saída  *@redirected_publisher* . Caso contrário, o publicador redirecionado associado será retornado, nos casos de êxito e de falha.  
  
 Se a validação for bem-sucedida, **sp_validate_redirected_publisher** retorna uma indicação de sucesso.  
  
 Se a validação falhar, serão emitidos erros apropriados.  **sp_validate_redirected_publisher** faz um melhor esforço para levantar todos os problemas e não apenas o primeiro encontrado.  
  
> [!NOTE]  
>  **sp_validate_replica_hosts_as_publishers** falhará com o erro a seguir ao validar hosts de réplica secundária que não permitirem acesso de leitura ou exigirem a especificação da intenção de leitura.  
>   
>  Msg 21899, Level 11, State 1, Procedure **sp_hadr_verify_subscribers_at_publisher**, Line 109  
>   
>  A consulta ao publicador redirecionado 'MyReplicaHostName' para determinar se havia entradas de sysserver para os assinantes do publicador original 'MyOriginalPublisher' falhou com erro '976', mensagem de erro 'Erro 976, Nível 14, Estado 1, Mensagem: O banco de dados de destino, 'MyPublishedDB', está participando de um grupo de disponibilidade e no momento não está acessível para consultas. Qualquer movimento de dados é suspenso ou a réplica de disponibilidade não é habilitada para acesso de leitura. Para permitir o acesso somente leitura a esse banco de dados e a outros no grupo de disponibilidade, habilite o acesso de leitura para uma ou mais réplicas de disponibilidade secundárias no grupo.  Para obter mais informações, consulte a instrução **ALTER AVAILABILITY GROUP** nos Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
>   
>  Foram encontrados um ou mais erros de validação de publicador para o host de réplica 'MyReplicaHostName'.  
  
## <a name="permissions"></a>Permissões  
 Chamador deve ser um membro do **sysadmin** função de servidor fixa, o **db_owner** função fixa de banco de dados para o banco de dados de distribuição ou um membro de uma lista de acesso da publicação para uma publicação definida associado com o banco de dados do publicador.  
  
## <a name="see-also"></a>Consulte também  
 [Procedimentos armazenados de replicação &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/replication-stored-procedures-transact-sql.md)   
 [sp_get_redirected_publisher &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sp-get-redirected-publisher-transact-sql.md)   
 [sp_redirect_publisher &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sp-redirect-publisher-transact-sql.md)   
 [sp_validate_redirected_publisher &#40; Transact-SQL &#41;](../../relational-databases/system-stored-procedures/sp-validate-redirected-publisher-transact-sql.md)  
  
  
