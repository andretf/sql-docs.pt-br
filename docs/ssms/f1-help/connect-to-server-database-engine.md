---
title: Conectar ao Servidor (Mecanismo de Banco de Dados) | Microsoft Docs
ms.custom:
- SQL2016_New_Updated
ms.date: 08/14/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- tools-ssms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sql13.swb.connectoserverunknownservertype.f1
- sql13.swb.connection.login.sqlce.f1
- sql13.swb.connecttoce.f1
- SQL13.SWB.CONNECTION.LOGIN.SQLSERVER.F1
- sql13.swb.connection.login.sqlserver.f1
- sql13.swb.manageSS2k.f1
ms.assetid: ee9017b4-8a19-4360-9003-9e6484082d41
caps.latest.revision: 6
author: stevestein
ms.author: sstein
manager: jhubbard
ms.translationtype: HT
ms.sourcegitcommit: 21f0cfd102a6fcc44dfc9151750f1b3c936aa053
ms.openlocfilehash: 240201bd70521dcfd92a24c920d941c4ccfa3498
ms.contentlocale: pt-br
ms.lasthandoff: 08/28/2017

---
# <a name="connect-to-server-database-engine"></a>Conectar ao Servidor (Mecanismo de Banco de Dados)
Use essa caixa de diálogo para exibir ou especificar opções ao se conectar com o [!INCLUDE[msCoName](../../includes/msconame_md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion_md.md)]. Na maioria das vezes, é possível conectar-se informando o nome do computador do servidor de banco de dados na caixa **Nome do servidor** e clicando em **Conectar**. Se você estiver se conectando a uma instância nomeada, use o nome do computador seguido por uma barra invertida e o nome da instância. Por exemplo, `mycomputer\myinstance`. Se você estiver se conectando ao [!INCLUDE[ssExpress](../../includes/ssexpress_md.md)], use o nome do computador seguido por **\sqlexpress**.  
  
Muitos fatores podem afetar sua possibilidade de conexão com o [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]. Para obter ajuda, consulte os seguintes recursos:  
- [Lição 1 do tutorial: Conectar-se ao mecanismo de banco de dados](../../relational-databases/lesson-1-connecting-to-the-database-engine.md)  
- [Solucionar problemas na conexão com o Mecanismo de Banco de Dados do SQL Server](../../database-engine/configure-windows/troubleshoot-connecting-to-the-sql-server-database-engine.md)  
- [Solving Connectivity errors to SQL Server](https://support.microsoft.com/help/4009936/solving-connectivity-errors-to-sql-server) (Resolvendo erros de conectividade com o SQL Server)   
  
## <a name="options"></a>Opções  
**Tipo de servidor**  
Ao registrar um servidor a partir do Pesquisador de Objetos, selecione o tipo de servidor ao qual se conectar: [!INCLUDE[ssDE](../../includes/ssde_md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion_md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion_md.md)]ou [!INCLUDE[ssISnoversion](../../includes/ssisnoversion_md.md)]. O restante da caixa de diálogo mostra somente as opções que válidas ao tipo de servidor selecionado. Ao registrar um servidor de Servidores Registrados, a caixa **Tipo de servidor** é somente leitura e corresponde ao tipo de servidor exibido no componente Servidores Registrados. Para registrar um tipo diferente de servidor, selecione [!INCLUDE[ssDE](../../includes/ssde_md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion_md.md)], [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion_md.md)], [!INCLUDE[ssEW](../../includes/ssew_md.md)]ou [!INCLUDE[ssISnoversion](../../includes/ssisnoversion_md.md)] na barra de ferramentas Servidores Registrados antes de começar a registrar um novo servidor.  
  
**Nome do servidor**  
Selecione a instância do servidor com a qual se conectar. Por padrão, é exibida a instância de servidor usada na última conexão.  
  
> [!NOTE]  
> Para conectar-se a uma instância de usuário ativa do [!INCLUDE[ssExpress](../../includes/ssexpress_md.md)], conecte-se usando o protocolo de pipes nomeados especificando o nome do pipe, por exemplo, `np:\\.\pipe\3C3DF6B1-2262-47\tsql\query`. Para obter mais informações, consulte a documentação do [!INCLUDE[ssExpress](../../includes/ssexpress_md.md)].  
  
**Autenticação**  
A versão atual do SSMS oferece cinco modos de autenticação ao conectar-se a uma instância do [!INCLUDE[ssDE](../../includes/ssde_md.md)]. Se a caixa de diálogo Autenticação não corresponder à lista a seguir, baixe a versão mais recente do SSMS em [Baixar o SQL Server Management Studio (SSMS)](../download-sql-server-management-studio-ssms.md).  

  
  > **Autenticação do Windows**  
[!INCLUDE[msCoName](../../includes/msconame_md.md)] O modo de Autenticação do Windows permite que um usuário se conecte por uma conta de usuário Windows.  
  
  > **Autenticação do SQL Server**  
  > Quando um usuário se conecta com um nome de logon e uma senha especificados em uma conexão não confiável, o próprio [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] efetua a autenticação verificando se foi definida uma conta de logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] e se a senha especificada corresponde a uma senha já registrada. Se o [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] não tiver uma conta de logon definida, ocorrerá falha na autenticação e o usuário receberá uma mensagem de erro. Quando possível, use a Autenticação do Windows ou a autenticação de senha do Active Directory.  

  > **Active Directory – Universal com suporte do MFA**  
Active Directory – Universal com MFA é um fluxo de trabalho interativo que dá suporte à MFA (Autenticação Multifator do Azure). A MFA do Azure ajuda a proteger o acesso a dados e aplicativos enquanto atende à demanda do usuário para um processo de entrada simples. Ela fornece autenticação forte com uma variedade de opções de verificação fácil – chamada telefônica, mensagem de texto, cartões inteligentes com PIN ou notificação por aplicativos móveis – permitindo que os usuários escolham o método que preferirem. Quando a conta de usuário é configurada para MFA, o fluxo de trabalho de autenticação interativa requer interação adicional do usuário por meio de caixas de diálogo pop-up, uso de cartão inteligente etc. Quando a conta de usuário é configurada para MFA, o usuário deve selecionar Autenticação Universal do Azure para se conectar. Se a conta de usuário não exigir MFA, o usuário ainda poderá usar as outras duas opções de Autenticação do Azure Active Directory. Para obter mais informações, consulte [Suporte ao SSMS para MFA do Azure AD com o banco de dados SQL e o SQL Data Warehouse](https://azure.microsoft.com/documentation/articles/sql-database-ssms-mfa-authentication/). Se necessário, você pode alterar o domínio que autentica o logon, clicando em **Opções**, selecionando guia **Propriedades de Conexão** e, em seguida, preenchendo a caixa **ID de locatário ou de nome de domínio do AD**.  

  > **Active Directory – Senha**  
A Autenticação do Azure Active Directory é um mecanismo para se conectar ao [!INCLUDE[msCoName](../../includes/msconame_md.md)][!INCLUDE[ssSDSfull](../../includes/sssdsfull_md.md)] usando identidades no Azure AD (Azure Active Directory).  Use esse método para conectar-se ao [!INCLUDE[ssSDS](../../includes/sssds_md.md)] se você tiver feito logon no Windows usando as credenciais de um domínio que não seja federado ao Azure ou usando a autenticação do Azure AD usando o Azure AD com base no domínio inicial ou do cliente. Para obter mais informações, veja [Conectar-se ao Banco de Dados SQL usando a Autenticação do Azure Active Directory](https://azure.microsoft.com/documentation/articles/sql-database-aad-authentication/).  
  
  > **Active Directory – Integrado**  
A Autenticação do Azure Active Directory é um mecanismo para se conectar ao [!INCLUDE[msCoName](../../includes/msconame_md.md)][!INCLUDE[ssSDSfull](../../includes/sssdsfull_md.md)] usando identidades no Azure AD (Azure Active Directory). Use esse método para conectar-se ao [!INCLUDE[ssSDS](../../includes/sssds_md.md)] se você tiver feito logon no Windows usando suas credenciais do Azure Active Directory de um domínio federado. Para obter mais informações, veja [Conectar-se ao Banco de Dados SQL usando a Autenticação do Azure Active Directory](https://azure.microsoft.com/documentation/articles/sql-database-aad-authentication/).  
  
**Nome de usuário**  
O nome de usuário Windows com o qual se conectar. Essa opção estará disponível somente se você decidiu se conectar usando a **Autenticação da Senha do Active Directory**. Ele é somente leitura quando você seleciona a **Autenticação do Windows** ou a autenticação do **Active Directory – Integrado**.  
  
**Logon**  
Insira o logon com o qual se conectar. Essa opção estará disponível somente se você tiver decidido se conectar usando a Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] ou a Autenticação de Senha do Active Directory.  
  
**Senha**  
Digite a senha do logon. Essa opção estará editável somente se você tiver decidido se conectar usando a Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] ou a Autenticação de Senha do Active Directory.  
  
**Conectar**  
Clique para conectar-se ao servidor.  
  
**Opções**  
Clique para exibir as guias **Propriedades de Conexão** e **Parâmetros Adicionais de Conexão**.  
  
