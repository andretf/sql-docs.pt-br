---
title: "Instalação do PolyBase | Microsoft Docs"
ms.custom: 
ms.date: 02/23/2018
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: polybase
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine-polybase
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- PolyBase, installation
author: barbkess
ms.author: barbkess
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: 4aefc608d16245a2cb28245a87beb6b165489fab
ms.sourcegitcommit: f0c5e37c138be5fb2cbb93e9f2ded307665b54ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/24/2018
---
# <a name="polybase-installation"></a>Instalação do PolyBase
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]

  Para instalar uma versão de avaliação do SQL Server, vá para [avaliações do SQL Server](https://www.microsoft.com/evalcenter/evaluate-sql-server-2016). 
  
## <a name="prerequisites"></a>Prerequisites  
  
-   Edição de avaliação do SQL Server de 64 bits  
  
-   Microsoft .NET Framework 4.5.  
  
-   Oracle Java SE RunTime Environment (JRE) versão 7.51 ou 8 (64 bits) (tanto o [JRE](http://www.oracle.com/technetwork/java/javase/downloads/jre8-downloads-2133155.html) quanto o [JRE do Servidor](http://www.oracle.com/technetwork/java/javase/downloads/server-jre8-downloads-2133154.html) funcionarão). Vá para [Downloads de Java SE](http://www.oracle.com/technetwork/java/javase/downloads/index.html). O instalador falhará se o JRE não estiver presente. O JRE 9 ou superior não funcionará a menos que você tenha a atualização cumulativa 4 do SQL Server 2017 ou superior. Você pode instalar o JRE 8, instalar o PolyBase e, em seguida, atualizar para o JRE 9. 
  
-   Memória mínima: 4 GB  
  
-   Espaço mínimo no disco rígido: 2 GB  
  
-   O TCP/IP deve estar habilitada para o Polybase para funcionar corretamente. O TCP/IP está habilitado por padrão em todas as edições do SQL Server, exceto nas edições Developer e Express do SQL Server. Para que o Polybase funcione corretamente nas edições Developer e Express, é necessário habilitar a conectividade TCP/IP (consulte [Habilitar ou Desabilitar um Protocolo de Rede do Servidor](../../database-engine/configure-windows/enable-or-disable-a-server-network-protocol.md)).
  
 **Observações**  
  
 O PolyBase pode ser instalado apenas em uma instância SQL Server por computador.  
  
## <a name="single-node-or-polybase-scaleout-group"></a>Nó único ou grupo ScaleOut do PolyBase
Antes de iniciar a instalação do PolyBase nas Instâncias do SQL Server, é bom planejar se você deseja uma instalação de nó único ou um grupo de escala horizontal do PolyBase. Para um grupo de escala horizontal do PolyBase, você precisará garantir que: 
- Todos os computadores estão no mesmo domínio.
- A mesma conta de serviço e senha sejam usadas durante a instalação.
- As Instâncias do SQL Server podem se comunicar entre si pela rede.
- As instâncias do SQL Server são todas da mesma versão do SQL Server.

Depois de instalar o PolyBase como um grupo autônomo ou de escala horizontal, não é possível alterar essa configuração. Você precisará desinstalar e reinstalar o recurso para alterar essa configuração.

## <a name="install-using-the-installation-wizard"></a>Instalar usando o assistente de instalação  
  
1.  Execute a **Central de Instalação do SQL Server**. Insira a mídia de instalação do SQL Server e clique duas vezes em **Setup.exe**.  
  
2.  Clique em **Instalação**, em **Nova instalação autônoma do SQL Server ou adicionar recursos**.  
  
3.  Na página de seleção de recursos, escolha **Serviço de Consulta do PolyBase para Dados Externos**.  
  
4.  Na página Configuração do Servidor, configure o **Serviço de Mecanismo de PolyBase do SQL Server** e Serviço de Movimentação de Dados de PolyBase do Servidor para execução na mesma conta.  
  
    > **IMPORTANTE:** Em um grupo de escala horizontal do PolyBase, o serviço de movimentação de dados e de mecanismo de PolyBase em todos os nós devem ser executados na mesma conta de domínio.  
    > Consulte escala horizontal PolyBase.  
  
5.  Na página **Configuração do PolyBase**, escolha uma das duas opções. Consulte [grupos de escala horizontal do PolyBase](../../relational-databases/polybase/polybase-scale-out-groups.md) para obter mais informações.  
  
    -   Use a instância do SQL Server como uma instância habilitada para PolyBase autônoma.  
  
         Escolha essa opção para usar a instância do SQL Server como um nó de cabeçalho autônomo.  
  
    -   Use a instância do SQL Server como parte de um grupo de escala horizontal do PolyBase.  A seleção dessa opção abre o firewall para permitir conexões de entrada com o Mecanismo de Banco de Dados do SQL Server, Mecanismo de PolyBase do SQL Server, serviço de Movimentação de Dados de PolyBase do SQL Server e SQL Browser. O firewall é aberto para permitir conexões de entrada de outros nós em um grupo de escala horizontal de PolyBase.  
  
         Esta opção também habilita conexões de firewall do MSDTC (Coordenador de Transações Distribuídas da Microsoft) e modifica as configurações de registro do MSDTC.  
  
6.  Na **página Configuração do PolyBase**, especifique um intervalo de portas com pelo menos seis portas. A instalação do SQL Server alocará as primeiras seis portas disponíveis do intervalo.  
  
##  <a name="installing"></a> Instalar usando um prompt de comando  
 Use os valores nesta tabela para criar scripts de instalação. Os dois serviços, **Mecanismo de PolyBase do SQL Server** e **Serviço de Movimentação de Dados de PolyBase do SQL Server** devem ser executados na mesma conta. Em um grupo de escala horizontal do PolyBase, os serviços do PolyBase em todos os nós devem ser executados na mesma conta de domínio.  
  
|Componente do SQL Server|Parâmetro e valores|Description|  
|--------------------------|--------------------------|-----------------|  
|Controle de instalação do SQL Server|**Required**<br /><br /> /FEATURES=PolyBase|Seleciona o recurso PolyBase.|  
|Mecanismo de PolyBase do SQL Server|**Opcional**<br /><br /> /PBENGSVCACCOUNT|Especifica a conta do serviço de mecanismo. O padrão é **NT Authority\NETWORK SERVICE**.|  
|Mecanismo PolyBase do SQL Server|**Opcional**<br /><br /> /PBENGSVCPASSWORD|Especifica a senha da conta de serviço de mecanismo.|  
|Mecanismo PolyBase do SQL Server|**Opcional**<br /><br /> /PBENGSVCSTARTUPTYPE|Especifica o modo de inicialização do serviço de mecanismo PolyBase: Automático (padrão), Desabilitado e Manual|  
|Serviço de Movimentação de Dados de PolyBase do SQL Server|**Opcional**<br /><br /> /PBDMSSVCACCOUNT|Especifica a conta do serviço de movimentação de dados. O padrão é **NT Authority\NETWORK SERVICE**.|  
|Serviço de movimentação de dados de PolyBase do SQL Server|**Opcional**<br /><br /> /PBDMSSVCPASSWORD|Especifica a senha para a conta de movimentação de dados.|  
|Serviço de movimentação de dados de PolyBase do SQL Server|**Opcional**<br /><br /> /PBDMSSVCSTARTUPTYPE|Especifica o modo de inicialização para o serviço de movimentação de dados: Automático (padrão), Desabilitado e Manual|  
|PolyBase|**Opcional**<br /><br /> /PBSCALEOUT|Especifica se a instância do SQL Server será usada como parte do grupo computacional de escala horizontal do PolyBase. <br />Valores com suporte: **True**, **False**|  
|PolyBase|**Opcional**<br /><br /> /PBPORTRANGE|Especifica um intervalo de portas com pelo menos 6 portas para serviços do PolyBase. Exemplo:<br /><br /> `/PBPORTRANGE=16450-16460`|  
  
 **Exemplo**  
  
 Mostra um exemplo de script de instalação.  
  
```  
  
Setup.exe /Q /ACTION=INSTALL /IACCEPTSQLSERVERLICENSETERMS /FEATURES=SQLEngine,Polybase   
/INSTANCENAME=MSSQLSERVER /SQLSYSADMINACCOUNTS="\<fabric-domain>\Administrator"   
/INSTANCEDIR="C:\Program Files\Microsoft SQL Server" /PBSCALEOUT=TRUE   
/PBPORTRANGE=16450-16460 /SECURITYMODE=SQL /SAPWD="<StrongPassword>"   
/PBENGSVCACCOUNT="<DomainName>\<UserName>" /PBENGSVCPASSWORD="<StrongPassword>"   
/PBDMSSVCACCOUNT="<DomainName>\<UserName>" /PBDMSSVCPASSWORD="<StrongPassword>"  
  
```  
  
## <a name="post-installation-notes"></a>Notas de pós-instalação  
 O PolyBase instala três bancos de dados de usuário: DWConfiguration, DWDiagnostics e DWQueue.   Eles são para uso do PolyBase e devem não ser alterados ou excluídos.  
  
### <a name="how-to-confirm-installation"></a>Como confirmar a instalação  
 Execute o comando a seguir. Se o PolyBase estiver instalado, retornará 1; caso contrário, 0.  
  
```sql  
SELECT SERVERPROPERTY ('IsPolybaseInstalled') AS IsPolybaseInstalled;  
```  
  
### <a name="firewall-rules"></a>Regras de firewall  
 A instalação do PolyBase do SQL Server cria as seguintes regras de firewall no computador.  
  
-   PolyBase do SQL Server – Mecanismo de Banco de Dados – \<SQLServerInstanceName> (TCP-In)  
  
-   PolyBase do SQL Server – Serviços do PolyBase – \<SQLServerInstanceName> (TCP-In)  
  
-   PolyBase do SQL Server – Navegador do SQL – (UDP-In)  
  
 Durante a instalação, se você optar por usar a instância do SQL Server como parte de um grupo de escala horizontal do PolyBase, essas regras serão habilitadas e o firewall será aberto para permitir conexões de entrada com o mecanismo de banco de dados do SQL Server, o mecanismo PolyBase do SQL Server, o serviço de movimentação de dados do SQL Server PolyBase e o navegador do SQL. No entanto, se o serviço de firewall no computador não estiver em execução durante a instalação, a instalação do SQL Server falhará ao habilitar essas regras. Nesse caso, você deve iniciar o serviço de Firewall no computador e habilitar pós-instalação essas regras.  
  
#### <a name="to-enable-the-firewall-rules"></a>Para habilitar as regras de firewall  
  
-   Abra o **Painel de Controle**.  
  
-   Clique em **Sistema e Segurança**e depois em **Firewall do Windows**.  
  
-   Clique em **Configurações Avançadas**e em **Regras de entrada**.  
  
-   Clique com o botão direito do mouse na regra desabilitada e depois clique em **Habilitar regra**.  
  
### <a name="polybase-service-accounts"></a>Contas de serviço do PolyBase
Para alterar as contas de serviço para o Mecanismo de PolyBase e os Serviços de Movimentação de Dados do PolyBase, desinstale e reinstale o recurso PolyBase.
   
## <a name="next-steps"></a>Próximas etapas  
 Veja [Configuração do PolyBase](../../relational-databases/polybase/polybase-configuration.md).  
  
  
