---
title: "Atualização do banco de dados (MySQLToSQL) | Microsoft Docs"
ms.prod: sql-non-specified
ms.prod_service: sql-tools
ms.service: 
ms.component: ssma-mysql
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: sql
ms.technology: sql-ssma
ms.tgt_pltfrm: 
ms.topic: article
applies_to:
- Azure SQL Database
- SQL Server
ms.assetid: 59a6db8f-2db6-4071-9005-928a7231de92
caps.latest.revision: "4"
author: Shamikg
ms.author: Shamikg
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 18656f8929e52d23e10ccc5fafe8139544bf44a5
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/21/2017
---
# <a name="refresh-from-database-mysqltosql"></a>Atualização do banco de dados (MySQLToSQL)
O **de atualização do banco de dados** caixa de diálogo permite que você selecione quais objetos para atualização do banco de dados MySQL. Linhas na caixa de diálogo estão codificados por cores com base no estado de metadados:  
  
-   Se os metadados do objeto foi alterado localmente e no banco de dados MySQL, a linha azul.  
  
-   Se os metadados do objeto foi alterado no banco de dados MySQL, mas não em SSMA, a linha é amarela.  
  
-   Se os metadados do objeto foi alterado localmente, mas não no banco de dados MySQL, a linha é verde.  
  
-   Se o objeto for novo no banco de dados MySQL, a linha é rosa.  
  
Você pode especificar as configurações padrão do objeto atualização o **configurações de projeto** caixa de diálogo. Para obter mais informações, consulte [configurações de projeto &#40; Sincronização &#41; &#40; MySQLToSQL &#41;](../../ssma/mysql/project-settings-synchronization-mysqltosql.md)  
  
Para acessar o **de atualização do banco de dados** caixa de diálogo, o botão direito do mouse, um objeto no Gerenciador de metadados do MySQL e clique em **de atualização do banco de dados**.  
  
## <a name="options"></a>Opções  
  
|||  
|-|-|  
|**Termo**|**Definição**|  
|**Recolher (-)**|Recolha todos os grupos de objeto para ocultar objetos individuais.|  
|**Expandir (+)**|Expanda todos os grupos de objeto para mostrar os objetos individuais.|  
|**Mostrar/ocultar objetos iguais**|Oculta os objetos da lista se os metadados do objeto são o mesmo em um banco de dados MySQL em SSMA.|  
|**Atualização do banco de dados (botão de seta)**|Use o botão de seta para especificar que os metadados para os objetos selecionados devem ser atualizados em SSMA.|  
|**Fazer a atualização não do banco de dados (botão X)**|Use o botão X para especificar que os metadados para os objetos selecionados não devem ser atualizados em SSMA.|  
|**Legenda**|Exibe um **legenda** caixa de diálogo. A legenda contém o mapeamento entre as cores de linha e estados de metadados.<br /><br />Para manter o **legenda** caixa de diálogo sobre o **de atualização do banco de dados** caixa de diálogo, selecione o **Mostrar na parte superior** caixa de seleção.|  
  
