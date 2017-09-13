---
title: "Configurar a opção de configuração de servidor query wait | Microsoft Docs"
ms.custom: 
ms.date: 03/02/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- queries [SQL Server], timing out
- time [SQL Server], query wait time
- query wait option [SQL Server]
ms.assetid: 0fc4aa01-65a3-4a33-9ef4-caca41add238
caps.latest.revision: 26
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: HT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 01ad4ae8b2d274dcb7f510f4f91b9830aa478a0f
ms.contentlocale: pt-br
ms.lasthandoff: 08/02/2017

---
# <a name="configure-the-query-wait-server-configuration-option"></a>Configurar a opção de configuração de servidor query wait
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Este tópico descreve como configurar a opção de configuração de servidor **query wait** no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)]. As consultas que solicitam muita memória (como as que envolvem classificação e hash) são enfileiradas quando não há memória disponível executar a consulta. A opção **espera de consulta** especifica o tempo em segundos (de 0 a 2147483647) que uma consulta deve esperar por recursos antes de o tempo limite ser excedido. O valor padrão dessa opção é -1. Isso significa que o tempo limite é calculado como 25 vezes o custo de consulta estimado.  
  
> [!IMPORTANT]  
>  Uma transação que contém a consulta de espera pode manter bloqueios enquanto a consulta espera por memória. Em situações raras, é possível que um erro de deadlock indetectável ocorra. Diminuir o tempo de espera da consulta reduz a probabilidade desses deadlocks. Eventualmente, uma consulta em espera será encerrada e o bloqueio da transação liberado. Porém, aumentar o tempo de espera máximo pode aumentar a quantidade de tempo da consulta a ser encerrada. Não é recomendado alterar essa opção.  
  
 **Neste tópico**  
  
-   **Antes de começar:**  
  
     [Recomendações](#Recommendations)  
  
     [Segurança](#Security)  
  
-   **Para configurar a opção query wait usando:**  
  
     [SQL Server Management Studio](#SSMSProcedure)  
  
     [Transact-SQL](#TsqlProcedure)  
  
-   **Acompanhamento:**  [depois de configurar a opção query wait](#FollowUp)  
  
##  <a name="BeforeYouBegin"></a> Antes de começar  
  
###  <a name="Recommendations"></a> Recomendações  
  
-   Esta é uma opção avançada e deve ser alterada somente por um administrador de banco de dados experiente ou técnico certificado do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
###  <a name="Security"></a> Segurança  
  
####  <a name="Permissions"></a> Permissões  
 Permissões de execução sem parâmetros ou com apenas o primeiro parâmetro em **sp_configure** são concedidas a todos os usuários por padrão. Para executar **sp_configure** com ambos os parâmetros para alterar uma opção de configuração ou executar a instrução RECONFIGURE, o usuário deve ter a permissão ALTER SETTINGS no nível do servidor. A permissão ALTER SETTINGS é implicitamente mantida pelas funções de servidor fixas **sysadmin** e **serveradmin** .  
  
##  <a name="SSMSProcedure"></a> Usando o SQL Server Management Studio  
  
#### <a name="to-configure-the-query-wait-option"></a>Para configurar a opção query wait  
  
1.  No Pesquisador de Objetos, clique com o botão direito do mouse em um servidor e selecione **Propriedades**.  
  
2.  Clique no nó **Avançado** .  
  
3.  Em **Paralelismo**, digite o valor desejado para a opção **query wait** .  
  
##  <a name="TsqlProcedure"></a> Usando Transact-SQL  
  
#### <a name="to-configure-the-query-wait-option"></a>Para configurar a opção query wait  
  
1.  Conecte-se ao [!INCLUDE[ssDE](../../includes/ssde-md.md)].  
  
2.  Na barra Padrão, clique em **Nova Consulta**.  
  
3.  Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**. Este exemplo mostra como usar [sp_configure](../../relational-databases/system-stored-procedures/sp-configure-transact-sql.md) para definir o valor da opção `query wait` como `7500` segundos.  
  
```tsql  
USE AdventureWorks2012 ;  
GO  
EXEC sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE ;  
GO  
EXEC sp_configure 'query wait', 7500 ;  
GO  
RECONFIGURE;  
GO  
  
```  
  
 Para obter mais informações, consulte [Opções de configuração do servidor &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md).  
  
##  <a name="FollowUp"></a> Acompanhamento: depois de configurar a opção query wait  
 A configuração entra em vigor imediatamente sem reiniciar o servidor.  
  
## <a name="see-also"></a>Consulte também  
 [RECONFIGURE &#40;Transact-SQL&#41;](../../t-sql/language-elements/reconfigure-transact-sql.md)   
 [Opções de configuração do servidor &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md)   
 [sp_configure &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-configure-transact-sql.md)  
  
  
