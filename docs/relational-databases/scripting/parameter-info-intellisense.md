---
title: "Informações sobre parâmetros (IntelliSense) | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: sql-tools
ms.service: 
ms.component: ssms-scripting
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Parameter Info option [IntelliSense]
- stored function parameter completion [Intellisense]
- language references [SQL Server]
- IntelliSense [SQL Server], Parameter Info option
ms.assetid: 56c2aac9-c65c-4679-b62c-d9f689876dde
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: e05c98b19cf3db1b6bae3e0e4f7196f92b989b02
ms.sourcegitcommit: a0aa5e611a0e6ebb74ac1e2f613e8916dc7a7617
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/24/2018
---
# <a name="parameter-info-intellisense"></a>Informações sobre Parâmetros (IntelliSense)
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)] A opção **Informações sobre Parâmetros** do [!INCLUDE[msCoName](../../includes/msconame-md.md)] IntelliSense abre uma lista de parâmetros com informações sobre número, nomes e tipos dos parâmetros requeridos por uma função ou um procedimento armazenado. O parâmetro em negrito indica o próximo parâmetro exigido à medida que você digita uma função ou um procedimento armazenado.  
  
 A lista de parâmetros também é exibida para funções aninhadas. Se você digitar uma função como um parâmetro para outra função, a lista de parâmetros exibirá os parâmetros da função interna. Em seguida, quando a lista de parâmetros da função interna estiver completa, a lista de parâmetros é revertida para exibir os parâmetros da função externa.  
  
#### <a name="to-view-parameter-info-for-functions-or-stored-procedures"></a>Para exibir Informações sobre Parâmetros para funções ou procedimentos armazenados  
  
1.  Depois do nome de uma função, digite um parêntese de abertura como normalmente o faz para abrir a lista de parâmetros. Após digitar o nome de um procedimento armazenado, digite um espaço como normalmente o faz para obter informações sobre os parâmetros do procedimento.  
  
     O IntelliSense exibe a declaração completa da função ou os parâmetros de um procedimento armazenado em uma janela pop-up sob o ponto de inserção. O primeiro parâmetro da lista aparece em negrito.  
  
2.  À medida que você digita os parâmetros, a fonte em negrito se altera para refletir o próximo parâmetro que você precisa digitar.  
  
3.  Pressione ESC a qualquer momento para fechar a lista ou continue digitando até concluir a função.  
  
     Para uma função, se você digitar o parêntese de fechamento, também fechará a lista de parâmetros.  
  
#### <a name="to-manually-start-parameter-info"></a>Para iniciar manualmente as Informações sobre Parâmetros  
  
1.  No menu **Editar** , selecione **IntelliSense** e selecione **Informações sobre Parâmetros**.  
  
2.  Pressione as teclas de atalho CTRL+SHIFT+ESPAÇO.  
  
 Para obter mais informações, consulte [Configurar IntelliSense &#40;SQL Server Management Studio&#41;](../../relational-databases/scripting/configure-intellisense-sql-server-management-studio.md).  
  
> [!NOTE]  
>  A opção **Informações sobre Parâmetros** só está disponível para o Editor de Consultas do [!INCLUDE[ssDE](../../includes/ssde-md.md)] e o Editor de Consultas XML.  
  
  
