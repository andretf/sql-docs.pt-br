---
title: "Excluir restrições exclusivas | Microsoft Docs"
ms.custom: 
ms.date: 10/12/2016
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database
ms.service: 
ms.component: tables
ms.reviewer: 
ms.suite: sql
ms.technology:
- dbe-tables
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- removing constraints
- UNIQUE constraints [SQL Server], deleting
- constraints [SQL Server], deleting
- deleting constraints
- constraints [SQL Server], unique
ms.assetid: 71e563fc-f5d7-4c2e-a42f-f0695a831f32
caps.latest.revision: 
author: stevestein
ms.author: sstein
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: 89d8fc0d3d2583f4e2fdbcedc1489b0fd191afac
ms.sourcegitcommit: d8ab09ad99e9ec30875076acee2ed303d61049b7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/23/2018
---
# <a name="delete-unique-constraints"></a>Excluir restrições exclusivas
[!INCLUDE[tsql-appliesto-ss2016-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2016-asdb-xxxx-xxx-md.md)]

  Você pode excluir uma restrição exclusiva no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou o [!INCLUDE[tsql](../../includes/tsql-md.md)]. Excluir uma restrição exclusiva remove o requisito de exclusividade dos valores inseridos na coluna ou da combinação de colunas incluídas na expressão de restrição e exclui o índice exclusivo correspondente.  
  
 **Neste tópico**  
  
-   **Antes de começar:**  
  
     [Segurança](#Security)  
  
-   **Para excluir uma restrição exclusiva usando:**  
  
     [SQL Server Management Studio](#SSMSProcedure)  
  
     [Transact-SQL](#TsqlProcedure)  
  
##  <a name="BeforeYouBegin"></a> Antes de começar  
  
###  <a name="Security"></a> Segurança  
  
####  <a name="Permissions"></a> Permissões  
 Exige a permissão ALTER na tabela.  
  
##  <a name="SSMSProcedure"></a> Usando o SQL Server Management Studio  
  
#### <a name="to-delete-a-unique-constraint-using-object-explorer"></a>Para excluir uma restrição exclusiva usando o Pesquisador de Objetos  
  
1.  No Pesquisador de Objetos, expanda a tabela que contém a restrição exclusiva e expanda **Restrições**.  
  
2.  Clique com o botão direito do mouse na chave e selecione **Excluir**.  
  
3.  Na caixa de diálogo **Excluir Objeto** , verifique se a chave correta foi especificada e clique em **OK**.  
  
#### <a name="to-delete-a-unique-constraint-using-table-designer"></a>Para excluir uma restrição exclusiva usando o Designer de Tabela  
  
1.  No **Pesquisador de Objetos**, clique com o botão direito do mouse na tabela com a restrição exclusiva e clique em **Design**.  
  
2.  No menu **Designer de Tabela** , clique em **Índices/Chaves**.  
  
3.  Na caixa de diálogo **Índices/Chaves** , selecione a chave exclusiva na lista **Índice e Chave Primária / Exclusiva Selecionada** .  
  
4.  Clique em **Excluir**.  
  
5.  No menu **Arquivo**, clique em **Salvar** *nome da tabela*.  
  
##  <a name="TsqlProcedure"></a> Usando Transact-SQL  
  
#### <a name="to-delete-a-unique-constraint"></a>Para excluir uma restrição exclusiva  
  
1.  No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)].  
  
2.  Na barra Padrão, clique em **Nova Consulta**.  
  
3.  Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.  
  
    ```  
    -- Return the name of unique constraint.  
    SELECT name  
    FROM sys.objects  
    WHERE type = 'UQ' AND OBJECT_NAME(parent_object_id) = N' DocExc';  
    GO  
    -- Delete the unique constraint.  
    ALTER TABLE dbo.DocExc   
    DROP CONSTRAINT UNQ_ColumnB_DocExc;  
    GO  
    ```  
  
 Para obter mais informações, veja [ALTER TABLE &#40;Transact-SQL&#41;](../../t-sql/statements/alter-table-transact-sql.md) e [sys.objects &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-objects-transact-sql.md).  
  
###  <a name="TsqlExample"></a>  
