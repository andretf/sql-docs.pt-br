---
title: Driver do PHP para SQL Server High Availability, Disaster Recovery | Microsoft Docs
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 73a80821-d345-4fea-b076-f4aabeb4af3e
caps.latest.revision: 15
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: 24b65a4c4572638cff243bcf46e49a30453f0550
ms.contentlocale: pt-br
ms.lasthandoff: 09/09/2017

---
# <a name="php-driver-for-sql-server-support-for-high-availability-disaster-recovery"></a>Driver do PHP para o suporte do SQL Server para alta disponibilidade e recuperação de desastre
[!INCLUDE[Driver_PHP_Download](../../includes/driver_php_download.md)]

Este tópico discute [!INCLUDE[ssDriverPHP](../../includes/ssdriverphp_md.md)] suporte (adicionado na versão 3.0) para alta disponibilidade, recuperação de desastres – [!INCLUDE[ssHADR](../../includes/sshadr_md.md)].  O suporte ao [!INCLUDE[ssHADR](../../includes/sshadr_md.md)] foi adicionado no [!INCLUDE[ssSQL11](../../includes/sssql11_md.md)]. Para obter mais informações sobre o [!INCLUDE[ssHADR](../../includes/sshadr_md.md)], consulte os Manuais Online do [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] .  
  
Na versão 3.0 do [!INCLUDE[ssDriverPHP](../../includes/ssdriverphp_md.md)], você pode especificar o ouvinte do grupo de disponibilidade de uma (alta disponibilidade, recuperação de desastres) o grupo de disponibilidade (AG) na propriedade de conexão. Se um [!INCLUDE[ssDriverPHP](../../includes/ssdriverphp_md.md)] aplicativo está conectado ao banco de dados AlwaysOn que efetua failover, a conexão original será interrompida e o aplicativo deverá abrir uma nova conexão para continuar o trabalho após o failover.  
  
Se você não estiver se conectando a um ouvinte de grupo de disponibilidade, e se vários endereços IP estão associados com um nome de host, o [!INCLUDE[ssDriverPHP](../../includes/ssdriverphp_md.md)] irá iterar em sequência todos os endereços IP associados à entrada DNS. Isso pode demorar muito se o primeiro endereço IP retornado pelo servidor DNS não estiver associado a nenhuma NIC (placa de interface de rede). Ao se conectar a um ouvinte de grupo de disponibilidade, o [!INCLUDE[ssDriverPHP](../../includes/ssdriverphp_md.md)] tenta estabelecer conexões com todos os endereços IP em paralelo e se tenta uma conexão for bem-sucedida, o driver descartará as tentativas de conexão pendentes.  
  
> [!NOTE]  
> O aumento do tempo limite de conexão e a implementação de lógica de repetição de conexão aumentarão a probabilidade de um aplicativo se conectar a um grupo de disponibilidade. Além disso, como uma conexão pode falhar devido a um failover de grupo de disponibilidade, você deve implementar lógica de repetição de conexão, repetindo uma conexão com falha até se reconectar.  
  
## <a name="connecting-with-multisubnetfailover"></a>Conectando-se ao MultiSubnetFailover  
O **MultiSubnetFailover** propriedade de conexão indica que o aplicativo está sendo implantado em um grupo de disponibilidade ou instância de Cluster de Failover e que o [!INCLUDE[ssDriverPHP](../../includes/ssdriverphp_md.md)] tentará se conectar ao banco de dados na réplica primária [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] instância tentando se conectar a todos os IPs de endereços. Quando **MultiSubnetFailover = true** é especificado para uma conexão, o cliente repete as tentativas de conexão TCP mais rápido do que os intervalos de retransmissão de TCP do sistema operacional padrão. Isto permite uma reconexão mais rápida depois de failover de um Grupo de disponibilidade AlwaysOn ou uma Instância de Cluster de Failover AlwaysOn e é aplicável a Grupos de disponibilidade único e de várias sub-redes e Instâncias de Cluster de Failover.  
  
Sempre especifique **MultiSubnetFailover = True** ao se conectar a um ouvinte de grupo de disponibilidade do SQL Server 2012 ou instância de Cluster de Failover do SQL Server 2012. **MultiSubnetFailover** permite o failover mais rápido para todos os grupos de disponibilidade e as instâncias de cluster de failover do SQL Server 2012 e reduz significativamente o tempo de failover para topologias AlwaysOn de uma ou várias sub-redes. Durante um failover de várias sub-redes, o cliente tentará conexões em paralelo. Durante um failover de sub-rede, o [!INCLUDE[ssDriverPHP](../../includes/ssdriverphp_md.md)] repetirá agressivamente a conexão TCP.  
  
Para obter mais informações sobre palavras-chave de cadeia de caracteres de conexão em [!INCLUDE[ssDriverPHP](../../includes/ssdriverphp_md.md)], consulte [opções de Conexão](../../connect/php/connection-options.md).  
  
Especificando **MultiSubnetFailover = true** ao conectar-se a algo que não seja um ouvinte de grupo de disponibilidade ou instância de Cluster de Failover pode resultar em um impacto negativo no desempenho e não é suportado.  
  
Use as diretrizes a seguir para conectar-se a um servidor em um grupo de disponibilidade:  
  
-   Use a propriedade de conexão **MultiSubnetFailover** quando estiver se conectando a uma ou várias sub-redes; isso melhorará o desempenho em ambos os casos.  
  
-   Para conectar-se a um grupo de disponibilidade, especifique o ouvinte do grupo de disponibilidade como o servidor em sua cadeia de conexão.  
  
-   Conectar-se a uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] configurada com mais de 64 endereços IP causará uma falha de conexão.  
  
-   O comportamento de um aplicativo que usa a propriedade de conexão **MultiSubnetFailover** não é afetado com base no tipo de autenticação: [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Autenticação, Autenticação Kerberos ou Autenticação do Windows.  
  
-   Aumente o valor de **loginTimeout** para acomodar o tempo de failover e reduzir as tentativas de repetição de conexão do aplicativo.  
  
-   Não há suporte a transações distribuídas.  
  
Se o roteamento somente leitura não estiver em ação, conectar-se a um local de réplica secundária em um grupo de disponibilidade apresentará falha nas seguintes situações:  
  
1.  Se o local de réplica secundário não for configurado para aceitar conexões.  
  
2.  Se um aplicativo usar **ApplicationIntent=ReadWrite** (discutido abaixo) e o local de réplica secundária estiver configurado para acesso somente leitura.  
  
Uma conexão falhará se uma réplica primária for configurada para rejeitar cargas de trabalho somente leitura e a cadeia de conexão contiver **ApplicationIntent=ReadOnly**.  
  
## <a name="upgrading-to-use-multi-subnet-clusters-from-database-mirroring"></a>Atualizando para usar clusters de várias sub-redes a partir do espelhamento de banco de dados  
Um erro de conexão ocorrerá se as palavras-chave de conexão **MultiSubnetFailover** e **Failover_Partner** estiverem presentes na cadeia de conexão. Um erro também ocorrerá se a palavra-chave **MultiSubnetFailover** for usada e o [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] retornar uma resposta de parceiro de failover indicando que ela faz parte de um par de espelhamento de banco de dados.  
  
Se você atualizar um [!INCLUDE[ssDriverPHP](../../includes/ssdriverphp_md.md)] aplicativo que usa espelhamento de banco de dados em um cenário de várias sub-redes, você deve remover o **Failover_Partner** propriedade de conexão e substituí-lo por **MultiSubnetFailover ** definida como **Sim** e substitua o nome do servidor na cadeia de conexão com um ouvinte de grupo de disponibilidade. Se uma cadeia de caracteres de conexão usa **Failover_Partner** e **MultiSubnetFailover = true**, o driver gerará um erro. No entanto, se uma cadeia de caracteres de conexão usa **Failover_Partner** e **MultiSubnetFailover = false** (ou **ApplicationIntent = ReadWrite**), o aplicativo usará o banco de dados o espelhamento.  
  
O driver retornará um erro se o espelhamento de banco de dados é usado no banco de dados primário no AG e se **MultiSubnetFailover = true** é usado na cadeia de conexão que se conecta a um banco de dados primário em vez de um grupo de disponibilidade ouvinte.  
  
## <a name="specifying-application-intent"></a>Especificando a intenção do aplicativo  
Quando **ApplicationIntent=ReadOnly**, o cliente solicita uma carga de trabalho de leitura ao se conectar a um banco de dados habilitado para AlwaysOn. O servidor irá impor a intenção no momento da conexão e durante uma instrução USE de banco de dados, mas somente para um banco de dados habilitado para AlwaysOn.  
  
A palavra-chave **ApplicationIntent** não funciona com bancos de dados herdados somente leitura.  
  
Um banco de dados pode permitir ou não cargas de trabalho de leitura no banco de dados AlwaysOn de destino. (Isso é feito com a cláusula **ALLOW_CONNECTIONS** das instruções **PRIMARY_ROLE** e **SECONDARY_ROLE**[!INCLUDE[tsql](../../includes/tsql_md.md)].)  
  
A palavra-chave **ApplicationIntent** é usada para habilitar o roteamento somente leitura.  
  
## <a name="read-only-routing"></a>Roteamento somente leitura  
O roteamento somente leitura é um recurso que pode assegurar a disponibilidade de uma réplica somente leitura de um banco de dados. Para habilitar roteamento somente leitura:  
  
1.  Você deve conectar-se a um ouvinte de grupo de disponibilidade AlwaysOn.  
  
2.  A palavra-chave de cadeia de conexão **ApplicationIntent** deve ser definida como **ReadOnly**.  
  
3.  O grupo de disponibilidade deve ser configurado pelo administrador de banco de dados para permitir o roteamento somente leitura.  
  
É possível que nem todas as várias conexões que usam roteamento somente leitura se conectem à mesma réplica somente leitura. Alterações na sincronização de banco de dados ou alterações na configuração de roteamento de servidor podem resultar em conexões de cliente com réplicas somente leitura diferentes. Para garantir que todas as solicitações somente leitura conectem-se à mesma réplica somente leitura, não transmita um ouvinte de grupo de disponibilidade à palavra-chave de cadeia de conexão **Server**. Em vez disso, especifique o nome da instância somente leitura.  
  
O roteamento somente leitura pode demorar mais tempo do que a conexão ao primário porque o roteamento somente leitura conecta-se primeiramente ao primário e depois procura o melhor secundário legível disponível. Por isso, você deve aumentar seu tempo limite de logon.  
  
## <a name="see-also"></a>Consulte também  
[Conectando-se ao servidor](../../connect/php/connecting-to-the-server.md)  
  
