---
title: Visualizador de dados | Microsoft Docs
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- integration-services
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sql13.dts.designer.dataviewer.f1
helpviewer_keywords:
- Data Viewer dialog box
ms.assetid: 6351309a-688f-4e82-9697-1712130f10a1
caps.latest.revision: 13
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: a04115502f54ce1731c0d8aa14b2f264bc66709f
ms.contentlocale: pt-br
ms.lasthandoff: 08/03/2017

---
# <a name="data-viewer"></a>Visualizador de Dados
  Se um caminho for configurado para usar um visualizador de dados, o Visualizador de Dados exibirá o buffer de dados por buffer à medida que os dados se movimentarem entre dois componentes de fluxo de dados.  
  
## <a name="options"></a>Opções  
 **Seta Verde**  
 Clique para exibir os dados do próximo buffer. Se os dados puderem ser movidos em um único buffer, esta opção não estará disponível.  
  
 **Desanexar**  
 Desanexe o visualizador de dados.  
  
 **Observação** Desanexar um visualizador de dados não exclui o visualizador de dados. Se o visualizador de dados foi desanexado, os dados continuarão fluindo pelo caminho, mas os dados no visualizador não são atualizados para corresponder aos dados em cada buffer.  
  
 **Anexar**  
 Anexe um visualizador de dados.  
  
 **Observação** Quando o visualizador de dados é anexado, ele exibe informações de cada buffer no fluxo de dados e, em seguida, pausa. Você pode avançar pelos buffers usando a seta verde.  
  
 **Copiar Dados**  
 Copie os dados no buffer atual para a Área de Transferência.  
  
## <a name="see-also"></a>Consulte também  
 [Depurando o fluxo de dados](../../integration-services/troubleshooting/debugging-data-flow.md)  
  
  