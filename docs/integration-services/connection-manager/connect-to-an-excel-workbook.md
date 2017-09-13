---
title: Conecte-se para uma pasta de trabalho do Excel | Microsoft Docs
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- integration-services
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Excel [Integration Services]
ms.assetid: d9746318-3669-4ce2-bbb0-4a1bd471c9dd
caps.latest.revision: 22
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 2800075091835b2d6f2b07ee34e9b897fe86634e
ms.openlocfilehash: f8fb1db80ac1b750950a3401516b54af5ee29686
ms.contentlocale: pt-br
ms.lasthandoff: 08/17/2017

---
# <a name="connect-to-an-excel-workbook"></a>Conectar-se a uma pasta de trabalho do Excel
  A conexão de um pacote do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] a uma pasta de trabalho do Microsoft Office Excel requer um gerenciador de conexões do Excel.  
  
 Você pode criar esses gerenciadores de conexões na área Gerenciadores de Conexões do [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer ou no Assistente de Importação e Exportação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
 
## <a name="connectivity-components-for-microsoft-excel-and-access-files"></a>Componentes de conectividade para os arquivos do Microsoft Excel e Access
  
Você precisará baixar os componentes de conectividade para arquivos do Microsoft Office se eles ainda não estiverem instalados. Baixar a versão mais recente dos componentes de conectividade para o Excel e acessar arquivos aqui: [redistribuível de 2016 do mecanismo de banco de dados Microsoft Access](https://www.microsoft.com/download/details.aspx?id=54920).
  
A versão mais recente dos componentes pode abrir arquivos criados por versões anteriores do Excel.

Se o computador tiver uma versão de 32 bits do Office, em seguida, você precisa instalar a versão de 32 bits dos componentes e você também precisa garantir que você execute o pacote no modo de 32 bits.

Se você tiver uma assinatura do Office 365, certifique-se de que você baixe o redistribuível de 2016 do mecanismo de banco de dados de acesso e não o Microsoft Access 2016 Runtime. Quando você executar o instalador, você verá uma mensagem de erro que você não pode instalar a download lado a lado com componentes do Office clique para executar. Para ignorar essa mensagem de erro e instalar os componentes com êxito, execute a instalação no modo silencioso abrindo uma janela de Prompt de comando e executando o. Arquivo EXE baixado com o `/quiet` alternar. Por exemplo:

`C:\Users\<user name>\Downloads\AccessDatabaseEngine.exe /quiet`

## <a name="create-an-excel-connection-manager"></a>Criar uma Excel Gerenciador de conexão

### <a name="to-create-an-excel-connection-manager-from-the-connection-managers-area"></a>Para criar um gerenciador de conexões do Excel na área Gerenciadores de Conexões  
  
1.  No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra o pacote.  
  
2.  Na área **Gerenciadores de Conexões** , clique com o botão direito do mouse em qualquer lugar da área e, em seguida, selecione **Nova Conexão**.  
  
3.  Na caixa de diálogo **Adicionar Gerenciador de Conexões SSIS** , selecione **Excel**e configure o gerenciador de conexões.  
  
     Para obter informações sobre as opções de configuração que estão disponíveis para este gerenciador de conexões, consulte [Editor de Gerenciador de Conexões Excel](../../integration-services/connection-manager/excel-connection-manager-editor.md).  
  
### <a name="to-create-an-excel-connection-from-the-sql-server-import-and-export-wizard"></a>Para criar uma conexão do Excel a partir do Assistente de Importação e Exportação do SQL Server  
  
1.  Inicie a versão de 32 bits do Assistente de Importação e Exportação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
2.  Na página **Escolher uma Fonte de Dados** , para **Fonte de Dados**, selecione **Microsoft Excel**e configure a conexão do Excel.  
  
     Para obter informações sobre as opções de configuração que estão disponíveis para este tipo de conexão, consulte [Editor de Gerenciador de Conexões Excel](../../integration-services/connection-manager/excel-connection-manager-editor.md).  
  
## <a name="see-also"></a>Consulte também  
 [Conectar-se a um banco de dados do Access](../../integration-services/connection-manager/connect-to-an-access-database.md)  
  
  