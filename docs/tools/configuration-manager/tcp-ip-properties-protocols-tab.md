---
title: Propriedades de TCP/IP (guia Protocolos) | Microsoft Docs
ms.custom: 
ms.date: 08/24/2016
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- TCP/IP [SQL Server], configuration options
ms.assetid: 007638fc-3a24-4460-adbe-545ded5d6f88
caps.latest.revision: 38
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: c1a3d4995d3cc79f9a31533b918268f14204d511
ms.contentlocale: pt-br
ms.lasthandoff: 08/02/2017

---
# Propriedades do TCP/IP (guia Protocolos)
  Use a caixa de diálogo **Propriedades do TCP/IP** para configurar as opções do protocolo TCP/IP. Clique em **TCP/IP** no painel esquerdo, para mostrar configurações individuais de endereço IP no painel de detalhes.  
  
 O Microsoft SQL Server deve ser reiniciado para que as alterações tenham efeito.  
  
## Opções  
 **Enabled**  
 Os valores possíveis são **Sim** e **Não**.  
  
 **Keep Alive**  
 Especifique o intervalo (em milissegundos) no qual os pacotes keep-alive são transmitidos para verificar se o computador remoto de uma conexão ainda está disponível.  
  
 **Listen All**  
 Especifique se o SQL Server escutará em todos os endereços IP associados às placas de rede no computador. Se for definido como **No**, configure cada endereço IP separadamente usando a caixa de diálogo de propriedades de cada endereço IP. Se for definido como **Yes**, as configurações da caixa de propriedades **IPAll** se aplicarão a todos os endereços IP. O valor padrão é **Yes**.  
  
 **No Delay**  
 O SQL Server não implementa alterações a esta propriedade.  
  
## Consulte também  
 [Escolhendo um protocolo de rede](https://msdn.microsoft.com/library/ms187892(v=sql.130).aspx)   
 [Criando uma cadeia de Conexão válida usando TCP/IP](https://msdn.microsoft.com/library/ms191260.aspx)  
  
  
