---
title: "Repetir até um ponto de interrupção (SQL Server Profiler) | Microsoft Docs"
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- breakpoints [SQL Server]
- traces [SQL Server], replaying
ms.assetid: 3caf751e-df3b-40c7-b5e8-4490ae178e0c
caps.latest.revision: 25
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 795eaf0f1e2ac0079dd6387d6b15395d4a26704e
ms.contentlocale: pt-br
ms.lasthandoff: 08/02/2017

---
# <a name="replay-to-a-breakpoint-sql-server-profiler"></a>Repetir até um ponto de interrupção (SQL Server Profiler)
  Este tópico descreve como definir pontos de interrupção em um arquivo ou tabela de rastreamento que se deseja repetir, usando o [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]. Definir pontos de interrupção em um arquivo ou tabela de rastreamento antes de dar início à repetição do rastreamento permite que você pause a repetição em eventos específicos. Usar pontos de interrupção ao repetir um rastreamento dá suporte à depuração, pois é possível dividir a repetição de scripts de rastreamento longos em segmentos curtos que podem ser analisados incrementalmente.  
  
### <a name="to-replay-to-a-breakpoint"></a>Para repetir até um ponto de interrupção  
  
1.  Abra o arquivo ou tabela de rastreamento que deseja repetir. Para obter mais informações, consulte [Abrir um arquivo de rastreamento &#40;SQL Server Profiler&#41;](../../tools/sql-server-profiler/open-a-trace-file-sql-server-profiler.md) ou [Abrir uma tabela de rastreamento &#40;SQL Server Profiler&#41;](../../tools/sql-server-profiler/open-a-trace-table-sql-server-profiler.md).  
  
     Certifique-se de que o arquivo ou tabela de rastreamento aberto contém as classes de evento necessárias para a repetição. Para obter mais informações, consulte [Replay Requirements](../../tools/sql-server-profiler/replay-requirements.md).  
  
2.  Na janela de rastreamento, clique em um evento que você deseje usar como ponto de interrupção. Use um destes três métodos para definir um ponto de interrupção:  
  
    -   Pressione F9.  
  
    -   No menu **Repetir** , clique em **Alternar Ponto de Interrupção**.  
  
    -   Clique com o botão direito do mouse no evento e clique em **Alternar Ponto de Interrupção**.  
  
     Um marcador vermelho aparecerá próximo ao evento de rastreamento selecionado, indicando que se trata de um ponto de interrupção do rastreamento.  
  
     Repita essa etapa para definir vários pontos de interrupção.  
  
3.  No menu **Repetir** , clique em **Iniciar**e conecte-se ao servidor em que deseja repetir o rastreamento.  
  
4.  Na caixa de diálogo **Configuração de Repetição** , verifique as definições e clique em **OK**.  
  
     A repetição tem início, sendo pausada quando o ponto de interrupção é alcançado.  
  
5.  Pressione F5 para retomar a repetição e prosseguir até o próximo ponto de interrupção.  
  
6.  Repita a Etapa 5 até o término do rastreamento.  
  
## <a name="see-also"></a>Consulte também  
 [Repetir até um Cursor &#40; SQL Server Profiler &#41;](../../tools/sql-server-profiler/replay-to-a-cursor-sql-server-profiler.md)   
 [Repetir rastreamentos](../../tools/sql-server-profiler/replay-traces.md)   
 [SQL Server Profiler](../../tools/sql-server-profiler/sql-server-profiler.md)  
  
  