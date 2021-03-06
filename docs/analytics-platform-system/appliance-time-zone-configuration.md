---
title: "Configuração de fuso horário do dispositivo (Analytics Platform System)"
author: barbkess
ms.author: barbkess
manager: jhubbard
ms.prod: analytics-platform-system
ms.prod_service: mpp-data-warehouse
ms.service: 
ms.component: 
ms.technology: mpp-data-warehouse
ms.custom: 
ms.date: 01/05/2017
ms.reviewer: na
ms.suite: sql
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: cea9eeb9-fe05-4e65-b229-539de02ab20a
caps.latest.revision: "18"
ms.openlocfilehash: 0dc20594fa45375fe07b4ec374da9c752d3cc8b0
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/21/2017
---
# <a name="appliance-time-zone-configuration"></a>Configuração de fuso horário do dispositivo
O **fuso horário** página permite que você defina o fuso horário para todos os nós no seu dispositivo de PDW do SQL Server.  
  
## <a name="to-set-the-time-zone"></a>Para definir o fuso horário  
  
1.  Inicie o Gerenciador de configuração. Para obter mais informações, consulte [iniciar o Configuration Manager &#40; Analytics Platform System &#41; ](launch-the-configuration-manager.md).  
  
2.  Interromper os serviços de aplicativo usando o **Status de serviços** página no Configuration Manager. Consulte [PDW serviços Status &#40; Analytics Platform System &#41; ](pdw-services-status.md) para obter instruções.  
  
3.  No painel esquerdo do Gerenciador de configuração, clique em **fuso horário**. Selecione o fuso horário desejado do **fuso horário** menu suspenso. Dependendo de seu local, você também poderá marcar a caixa ao lado **ajustar automaticamente o relógio para horário de verão**.  
  
4.  Clique em **aplicar** para salvar suas alterações.  
  
5.  Reinicie os serviços de aplicativo usando o **Status de serviços** página no Configuration Manager. Se você também estiver planejando alterar os privilégios, você pode fazer isso antes de reiniciar o dispositivo.  
  
![Hora do dispositivo DWConfig](./media/appliance-time-zone-configuration/SQL_Server_PDW_DWConfig_ApplTopTime.png "SQL_Server_PDW_DWConfig_ApplTopTime")  
  
## <a name="see-also"></a>Consulte Também  
[Inicie o Gerenciador de configuração &#40; Analytics Platform System &#41;](launch-the-configuration-manager.md)  
  
