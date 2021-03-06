---
title: "Modificar o controlador e contas de serviços | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: sql-tools
ms.service: 
ms.component: distributed-replay
ms.reviewer: 
ms.suite: sql
ms.technology: setup-install
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 44a73ddb-18ad-415c-bfbe-126ab2e3290b
caps.latest.revision: "29"
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 6b43b611e45de9da98954417d5e7a1bfad009eac
ms.sourcegitcommit: b6116b434d737d661c09b78d0f798c652cf149f3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/17/2018
---
# <a name="modify-the-controller-and-client-services-accounts"></a>Modificar as contas dos serviços controlador e cliente
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]Neste tópico, você aprenderá a modificar as contas de serviço do cliente e o controlador do Distributed Replay e depois reaplicar as listas de controle de acesso (ACLs).  
  
### <a name="to-start-or-stop-the-distributed-replay-services-using-computer-management"></a>Para iniciar ou parar os serviços Distributed Replay usando o gerenciamento do computador  
  
1.  No computador em que os serviços Distributed Replay estão instalados, no prompt de comando, digite **dcomcnfg**.  
  
2.  Clique duas vezes em **serviços**, role para baixo e clique  **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay \<nome do serviço >**e, em seguida, clique em **iniciar** ou **parar**.  
  
### <a name="to-modify-the-distributed-replay-controller-service"></a>Para modificar o serviço controlador Distributed Replay  
  
1.  No computador controlador, pare o serviço controlador [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay.  
  
2.  Em **Serviços**, clique com o botão direito do mouse em **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay**e selecione **Propriedades**.  
  
3.  Na janela **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay** , na guia **Logon** , selecione **Esta conta**, digite ou clique em **Procurar** para inserir a nova conta de logon e clique em **OK**.  
  
     **Importante**: Quando você configura o controlador Distributed Replay, pode especificar uma ou mais contas de usuário que serão usadas para executar os serviços de cliente do Distributed Replay. Esta é a lista das contas com suporte:  
  
    -   Conta de usuário do domínio  
  
    -   Conta de usuário local criada pelo usuário  
  
    -   Administrador  
  
    -   Conta virtual e MSA (Conta de Serviço Gerenciada)  
  
    -   Serviços de rede, serviços locais e sistema  
  
     Não são aceitas contas de grupo (local ou domínio) e outras contas internas (como Todos).  
  
4.  Inicie o serviço controlador Distributed Replay.  
  
### <a name="to-modify-the-distributed-replay-client-service"></a>Para modificar o serviço cliente do Distributed Replay  
  
1.  Antes de modificar o serviço cliente Distributed Replay, verifique se a conta do serviço cliente que você está alterando foi especificada durante a configuração (no parâmetro CTLRUSERS no computador controlador). Se a conta de serviço de cliente que você está alterando não foi especificada durante a instalação, execute as etapas a seguir primeiro:  
  
    1.  Pare o serviço controlador do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay.  
  
    2.  No computador controlador em que o serviço controlador está instalado, no prompt de comando, digite **dcomcnfg**.  
  
    3.  Na janela **Serviços de Componente**, navegue até **Raiz do Console -> Serviços de Componente -> Computadores -> Meu Computador -> Configuração de DCOM ->DReplayController**.  
  
    4.  Clique com o botão direito do mouse em **DReplayController** e clique em **Propriedades**.  
  
    5.  Na janela **Propriedades do DReplayController** , na guia **Segurança** , clique em **Editar** na seção **Permissões de Inicialização e Ativação** .  
  
    6.  Conceda à nova conta de logon do serviço cliente permissões de **Ativação Local e Remota** e clique em **OK**.  
  
    7.  Clique em **Editar** na seção **Permissões de Acesso** e conceda à nova conta de logon do serviço cliente permissões de **Acesso Local e Remoto** e clique em **OK**.  
  
    8.  Clique em **OK** para fechar a janela **Propriedades do DReplayController** .  
  
    9. No computador controlador, adicione a conta de logon do serviço cliente alterado para o grupo **Usuários COM Distribuídos** .  
  
    10. Inicie o serviço controlador SQL Server Distributed Replay.  
  
2.  Pare o serviço cliente do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay.  
  
3.  Na janela **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay** , na guia **Logon** , selecione **Esta conta**, digite ou clique em **Procurar** para inserir a nova conta de logon e clique em **OK**.  
  
4.  Inicie o serviço cliente Distributed Replay.  
  
  
