---
title: "Configurar uma implantação de expansão do servidor de relatório do modo nativo | Microsoft Docs"
ms.custom: 
ms.date: 05/30/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- report servers [Reporting Services], deployments
- deploying [Reporting Services], scale-out deployment model
- scale-out deployments [Reporting Services]
ms.assetid: b30d0308-4d9b-4f85-9f83-dece4dcb2775
caps.latest.revision: 13
author: guyinacube
ms.author: asaxton
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: 0eb007a5207ceb0b023952d5d9ef6d95986092ac
ms.openlocfilehash: 6a90a566e3e100fff3bb17e838a368a82ac3f4f5
ms.contentlocale: pt-br
ms.lasthandoff: 08/09/2017

---

# <a name="configure-a-native-mode-report-server-scale-out-deployment"></a>Configurar uma implantação em expansão do servidor de relatório em modo nativo.

  O modo nativo do Reporting Services oferece suporte a um modelo de implantação em expansão que permite executar várias instâncias do servidor de relatório que compartilham um único banco de dados do servidor de relatório. As implantações em expansão são usadas para aumentar a escalabilidade dos servidores de relatório para manipular mais usuários simultâneos e cargas maiores de execução de relatório. Elas também podem ser usadas para dedicar servidores específicos para processar relatórios interativos ou agendados  
  
 Servidores de relatório do modo do SharePoint utilizam a infraestrutura de produtos do SharePoint para expandir. A expansão do modo do SharePoint é executada acrescentando mais servidores de relatório de modo do SharePoint ao farm do SharePoint. Para obter informações sobre expansão no modo do SharePoint, veja [Adicionar um servidor de relatório a um farm &#40;Expansão do SSRS&#41;](../../reporting-services/install-windows/add-an-additional-report-server-to-a-farm-ssrs-scale-out.md).  
 
  Uma *implantação de expansão* é usada nos seguintes cenários:  
  
-   Como um pré-requisito para o balanceamento de carga de vários servidores de relatório em um cluster de servidores. Antes de balancear a carga de vários servidores de relatório, primeiro é necessário configurá-los para compartilhar o mesmo banco de dados do servidor de relatório.  
  
-   Para segmentar aplicativos de servidor de relatório em diferentes computadores, usando um servidor para processamento de relatório interativo e um segundo servidor para processamento de relatório agendado. Neste cenário, cada instância do servidor processa diferentes tipos de solicitações para o mesmo conteúdo do servidor de relatório armazenado no banco de dados do servidor de relatório compartilhado.  
  
 **As implantações em expansão consistem de:**  
  
-   Duas ou mais instâncias do servidor de relatório que compartilham um único banco de dados do servidor de relatório.  
  
-   Opcionalmente, um cluster NLB (balanceamento de carga de rede) para difundir carga de usuário interativo nas instâncias do servidor de relatório.  
  
 Ao implantar o Reporting Services em um cluster NLB, você precisa assegurar que o nome do servidor virtual NLB é usado na configuração das URLs de servidor de relatório e que os servidores estão configurados para compartilhar o mesmo estado de exibição.  
  
 O Reporting Services não participa dos clusters do Microsoft Cluster Services. No entanto, é possível criar um banco de dados do servidor de relatório em uma instância do Mecanismo de Banco de Dados que faz parte de um cluster de failover.  
  
 **Para planejar, instalar e configurar uma implantação em expansão, siga estas etapas:**  
  
-   Revisão [instalar o SQL Server 2016 do Assistente de instalação &#40; Instalação &#41; ](../../database-engine/install-windows/install-sql-server-from-the-installation-wizard-setup.md) na [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Manuais Online para obter instruções sobre como instalar instâncias do servidor de relatório.  
  
-   Se você estiver planejando hospedar a implantação em expansão em um cluster NLB (balanceamento de carga de rede), deverá configurar o cluster NLB antes de configurar a implantação em expansão. Para obter mais informações, consulte [Configure a Report Server on a Network Load Balancing Cluster](../../reporting-services/report-server/configure-a-report-server-on-a-network-load-balancing-cluster.md).  
  
-   Examine os procedimentos neste tópico para obter instruções sobre como compartilhar um banco de dados do servidor de relatório e associar servidores de relatório a uma expansão.  
  
     Os procedimentos explicam como configurar uma implantação em expansão do servidor de relatório com dois nós. Repita as etapas descritas neste tópico para adicionar nós adicionais do servidor de relatório à implantação.  
  
    -   Use a Instalação para instalar cada instância do servidor de relatório que será associada à implantação em expansão.  
  
         Para evitar erros de compatibilidade de banco de dados ao conectar as instâncias de servidor ao banco de dados compartilhado, certifique-se de que todas as instâncias tenham a mesma versão. Por exemplo, se você criar o banco de dados do servidor de relatório usando uma instância de servidor de relatório do SQL Server 2016, todas as outras instâncias na mesma implantação também devem ser SQL Server 2016.  
  
    -   Use o gerenciador de Configuração do Reporting Services para conectar cada servidor de relatório ao banco de dados compartilhado. Você pode se conectar e configurar somente um servidor de relatório de cada vez.  
  
    -   Use a ferramenta Configuração do Reporting Services para concluir a expansão por meio da associação de novas instâncias do servidor de relatório à primeira instância do servidor de relatório já conectada ao banco de dados do servidor de relatório.  
  
## <a name="to-install-a-sql-server-instance-to-host-the-report-server-databases"></a>Para instalar uma instância do SQL Server que hospedará os bancos de dados do servidor de relatório  
  
1.  Instale uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em um computador que hospedará os bancos de dados do servidor de relatório. Instale pelo menos o [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] e o [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].  
  
2.  Se necessário, habilite o servidor de relatório para conexões remotas. Por padrão, algumas versões do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não permitem conexões remotas TCP/IP e de Pipes Nomeados. Para confirmar se conexões remotas são permitidas, use o Gerenciador de Configurações do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e exiba os parâmetros de configuração de rede da instância de destino. Se a instância remota também for uma instância nomeada, verifique se o serviço Navegador do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] está habilitado e em execução no servidor de destino. O Navegador do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fornece o número da porta usado para estabelecer conexão com a instância nomeada. 

## <a name="service-accounts"></a>Contas de serviço

As contas de serviço usadas para a instância do Reporting Services são importantes ao lidar com uma implantação em expansão. Você deve fazer o seguinte ao implantar suas instâncias do Reporting Services.

**Opção 1:** todas as instâncias do Reporting Services devem ser configuradas com a mesma conta de usuário de domínio para a conta de serviço.

**Opção 2:** cada conta de serviço, a conta de domínio ou não, precisa ter permissões de dbadmin dentro da instância do banco de dados do SQL Server que hospeda o banco de dados de catálogo ReportServer.

Se você tiver configurado uma configuração diferente de qualquer uma das opções acima, você pode encontrar a falhas intermitentes de modificação de tarefas com o SQL Agent. Isso aparecerá como logs de erro em ambos os Reporting Services e no portal da web ao editar uma assinatura de relatório.

```
An error occurred within the report server database.  This may be due to a connection failure, timeout or low disk condition within the database.
``` 

O problema será intermitente é que apenas o servidor que criou a tarefa do SQL Agent tenha direitos para exibir, excluir ou editar o item. Se você não fizer uma das opções acima, as operações terá êxito apenas quando o balanceador de carga envia todas as suas solicitações para essa assinatura para o servidor que criou a tarefa do SQL Agent. 
  
## <a name="to-install-the-first-report-server-instance"></a>Para instalar a primeira instância do servidor de relatório  
  
1.  Instale a primeira instância do servidor de relatório que faz parte da implantação. Quando instalar o [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], escolha a opção **Instalar, mas não configurar o servidor** na página Opções de Instalação do Servidor de Relatório.  
  
2.  Inicie a ferramenta Configuração do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .  
  
3.  Configure a URL do serviço Web servidor de relatório, a URL do Portal da Web e o banco de dados do servidor de relatório. Para obter mais informações, veja [Configurar um servidor de relatório &#40;Modo Nativo do Reporting Services&#41;](../../reporting-services/report-server/configure-a-report-server-reporting-services-native-mode.md) nos Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
4.  Verifique se o servidor de relatório está operacional. Para obter mais informações, veja [Verificar uma instalação do Reporting Services](../../reporting-services/install-windows/verify-a-reporting-services-installation.md) nos Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
## <a name="to-install-and-configure-the-second-report-server-instance"></a>Para instalar e configurar a segunda instância do servidor de relatório  
  
1.  Execute a instalação para instalar uma segunda instância do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] em outro computador ou como instância nomeada no mesmo computador. Ao instalar o Reporting Services, escolha a opção **Instalar, mas não configurar o servidor** na página Opções de Instalação do Servidor de Relatório.  
  
2.  Inicie a ferramenta Configuração do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] e conecte-se à nova instância que você acabou de instalar.  
  
3.  Conecte o servidor de relatório ao mesmo banco de dados usado para a primeira instância do servidor de relatório:  
  
    1.  Selecione **Banco de Dados** para abrir a página Banco de Dados.  
  
    2.  Selecione **Alterar Banco de Dados**.  
  
    3.  Selecione **Escolher um banco de dados existente do servidor de relatório**.  
  
    4.  Digite o nome do servidor da instância do Mecanismo de Banco de Dados do SQL Server que hospeda o banco de dados do servidor de relatório a ser usado. Esse deve ser o mesmo servidor ao qual você se conectou no conjunto de instruções anterior.  
  
    5.  Selecione **Testar Conexão**e **Avançar**.  
  
    6.  Em **Banco de Dados do Servidor de Relatório**, selecione o banco de dados que você criou para o primeiro servidor de relatório e clique em **Avançar**. O nome padrão é ReportServer. Não selecione ReportServerTempDB; ele é usado somente para armazenar dados temporários durante o processamento de relatórios. Se a lista de bancos de dados estiver vazia, repita as quatro etapas anteriores para estabelecer uma conexão com o servidor.  
  
    7.  Na página Credenciais, selecione o tipo de conta e as credenciais que o servidor de relatório usará para se conectar ao banco de dados do servidor de relatório. Você pode usar as mesmas credenciais que as da primeira instância do servidor de relatório ou credenciais diferentes. Selecione **Avançar**.  
  
    8.  Selecione **Resumo** e **Concluir**.  
  
4.  Configure a **URL do serviço Web**Servidor de Relatórios. Não teste a URL neste momento. Ela não será resolvida até que o servidor de relatório seja associado à implantação em expansão.  
  
5.  Configurar a **URL do Portal da Web**. Não teste a URL neste momento nem tente verificar a implantação. O servidor de relatório estará indisponível até que ele seja associado à implantação em expansão.  
  
## <a name="to-join-the-second-report-server-instance-to-the-scale-out-deployment"></a>Para unir a segunda instância do servidor de relatório à implantação em expansão  
  
1.  Abra a ferramenta Configuração do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] e se reconecte à primeira instância do servidor de relatório. O primeiro servidor de relatório já está inicializado para operações de criptografia reversível, portanto ele pode ser usado para unir instâncias adicionais do servidor de relatório à implantação em expansão.  
  
2.  Clique em **Implantação em Expansão** para abrir a página Implantação em Expansão. Você deve ver duas entradas, um para cada instância do servidor de relatório que está conectada ao banco de dados do servidor de relatório. A primeira instância do servidor de relatório deve estar associada. O segundo servidor de relatório deve estar "Aguardando para unir". Se não vir entradas semelhantes para a sua implantação, verifique se você está conectado ao primeiro servidor de relatório que já está configurado e inicializado para usar o banco de dados do servidor de relatório.  
  
     ![Captura de tela parcial da página implantação em expansão](../../reporting-services/install-windows/media/scaloutscreen.gif "captura de tela parcial da página implantação em expansão")  
  
3.  Na página Implantação em Expansão, selecione a instância do servidor de relatório que está aguardando para se unir à implantação e selecione **Adicionar Servidor**.  
  
    > [!NOTE]  
    >  **Problema:** quando você tenta unir uma instância do servidor de relatório do Reporting Services à implantação em expansão, pode receber mensagens de erro semelhantes a “Acesso negado”.  
    >   
    >  **Solução alternativa:** faça backup da chave de criptografia do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] da primeira instância do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] e restaure a chave para o segundo servidor de relatório do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] . Tente unir o segundo servidor à implantação em expansão do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .  
  
4.  Agora, deverá ser possível verificar que ambas as instâncias do servidor de relatório estão operacionais. Para verificar a segunda instância, você pode usar a ferramenta Configuração do Reporting Services para se conectar ao servidor de relatório e clicar na **URL do Serviço Web** ou na **URL do Portal da Web**.  
  
 Se você planejar executar os servidores de relatório em um cluster de servidores com balanceamento de carga, será necessária uma configuração adicional. Para obter mais informações, consulte [Configure a Report Server on a Network Load Balancing Cluster](../../reporting-services/report-server/configure-a-report-server-on-a-network-load-balancing-cluster.md).  

## <a name="next-steps"></a>Próximas etapas

[Configurar uma conta de serviço](http://msdn.microsoft.com/library/25000ad5-3f80-4210-8331-d4754dc217e0)   
[Configurar uma URL](../../reporting-services/install-windows/configure-a-url-ssrs-configuration-manager.md)   
[Criar um banco de dados do servidor de relatório do modo nativo](../../reporting-services/install-windows/ssrs-report-server-create-a-native-mode-report-server-database.md)   
[Configurar as URLs do servidor de relatório](../../reporting-services/install-windows/configure-report-server-urls-ssrs-configuration-manager.md)   
[Configurar uma Conexão de banco de dados do servidor de relatório](../../reporting-services/install-windows/configure-a-report-server-database-connection-ssrs-configuration-manager.md)   
[Adicionar e remover chaves de criptografia para implantação em expansão](../../reporting-services/install-windows/add-and-remove-encryption-keys-for-scale-out-deployment.md)   
[Gerenciar um servidor de relatório do Reporting Services modo nativo](../../reporting-services/report-server/manage-a-reporting-services-native-mode-report-server.md)  

Mais perguntas? [Tente fazer o fórum do Reporting Services](http://go.microsoft.com/fwlink/?LinkId=620231)