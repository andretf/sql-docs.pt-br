---
title: Configurar a conectividade do PolyBase para dados externos (Analytics Platform System)
author: barbkess
ms.author: barbkess
manager: jhubbard
ms.prod: sql-non-specified
ms.prod_service: mpp-data-warehouse
ms.service: 
ms.component: analytics-platform-system
ms.technology: mpp-data-warehouse
ms.custom: 
ms.date: 01/05/2017
ms.reviewer: na
ms.suite: sql
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 6f14ac21-a086-4c05-861f-0a12bf278259
caps.latest.revision: "43"
ms.openlocfilehash: 7d486992f688b5bc914508ef000f23209b4bde89
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2017
---
# <a name="configure-polybase-connectivity-to-external-data"></a>Configurar a conectividade do PolyBase para dados externos
Explica como configurar o PolyBase no SQL Server PDW para se conectar ao Microsoft Azure ou Hadoop armazenamento blob fontes de dados externas. Use o PolyBase para executar consultas que integram dados de várias fontes, incluindo Hadoop, armazenamento de BLOBs do Azure e SQL Server PDW.  
  
### <a name="to-configure-connectivity"></a>Para configurar a conectividade  
  
1.  Abra uma ferramenta de consulta, como sqlcmd ou SQL Server Data Tools (SSDT) e executar sp_configure para exibir as configurações de 'conectividade do hadoop' atual.  
  
    ![configuração de conectividade do Hadoop](./media/configure-polybase-connectivity-to-external-data/APS_PDW_sp_configure.png "APS_PDW_sp_configure")  
  
2.  Decida qual configuração necessário e se você precisar alterar a configuração atual de conectividade do Hadoop. Essa opção se aplica a toda a região PDW do SQL Server. Para obter uma lista completa das definições de configuração e versões, consulte [sp_configure](../relational-databases/system-stored-procedures/sp-configure-transact-sql.md).  
  
3.  Para alterar a configuração de 'conectividade do hadoop', execute sp_configure com RECONFIGURE. Aqui estão alguns exemplos.  
  
    ```sql  
    --Enable connectivity to Hortonworks Data Platform for Windows Server (HDP), HDInsight on Analytics Platform System, or HDInsight’s Microsoft Azure blob storage  
    EXEC sp_configure 'hadoop connectivity', 4;   
    RECONFIGURE;  
  
    -- Enable connectivity to Hortonworks Data Platform (HDP)for Linux   
    EXEC sp_configure 'hadoop connectivity', 5;   
    RECONFIGURE;  
  
    -- Enable connectivity to Cloudera CDH for Linux   
    EXEC sp_configure 'hadoop connectivity', 3;   
    RECONFIGURE;  
  
    -- Disable the Hadoop connectivity option   
    EXEC sp_configure 'hadoop connectivity', 0;  
    RECONFIGURE;  
    ```  
  
    Sp_configure em execução com RECONFIGURE define o valor de configuração. Reiniciar a região é necessária para definir o valor de execução. Já que uma reinicialização é necessária após a interrupção da próxima, você não precisa fazer a reinicialização até a próxima etapa que altera Core-site.XML.  
  
4.  Para habilitar o armazenamento de BLOBs do Microsoft Azure como uma fonte de dados externa, adicione uma ou mais chaves de acesso de conta de armazenamento Microsoft Azure ao arquivo de Core-site.XML do PDW. Para adicionar uma chave:  
  
    1.  Localize o nome de conta de armazenamento do Microsoft Azure. Para exibir suas contas de armazenamento, o logon para o[portal do Azure](https://portal.azure.com) e clique em **contas de armazenamento (clássico)**.  
  
        ![O nome de conta de armazenamento do Windows Azure](./media/configure-polybase-connectivity-to-external-data/APS_PDW_AzureStorageAccountName.png "APS_PDW_AzureStorageAccountName")  
  
    2.  Encontre sua chave de acesso da conta de armazenamento do Azure. Para fazer isso, clique no nome da conta de armazenamento e, na folha de configurações, clique em **chaves**. Isso mostrará as chaves de armazenamento e o nome da conta.  
  
        ![Chaves de acesso da conta de armazenamento do Windows Azure](./media/configure-polybase-connectivity-to-external-data/APS_PDW_AzureStorageAccountAccessKey.png "APS_PDW_AzureStorageAccountAccessKey")  
  
    3.  Abra uma conexão de área de trabalho remota para o nó de controle do PDW.  
  
    4.  Abra o arquivo C:\Program Files\Microsoft SQL Server Parallel Data Warehouse\100\Hadoop\conf\core-site.xml.  
  
    5.  Adicione a seguinte propriedade com os atributos nome e valor para Core-site.XML.  
  
        ```xml  
        <property>  
          <name>fs.azure.account.key.<your storage account name>.blob.core.windows.net</name>  
          <value><your storage account access key></value>  
        </property>  
        ```  
  
        Este exemplo usa a chave de acesso e do nome de conta mostrada anteriormente.  
  
        ```xml  
        <property>  
          <name>fs.azure.account.key.CustomerX.blob.core.windows.net</name>  
          <value>yyeTfCxxxxxxxxQ5WdnapXw77W+FwzHUhX/p/f26fIpnNFGtewzyRN90e1/qmTOl1xxxxxxxxa0goG71LsNcw==</value>  
        </property>  
        ```  
  
        > [!CAUTION]  
        > Tome precauções de segurança antes de armazenar a chave de acesso em Core-site.XML. Qualquer usuário que tenha a permissão CONTROL SERVER ou ALTER ANY EXTERNAL DATA SOURCE pode criar uma fonte de dados externa que acessa a essa conta. Depois de criar a fonte de dados externa, todos os usuários do SQL Server PDW que têm permissão para criar tabelas podem criar uma tabela externa que acessa a conta de armazenamento. Os usuários serão capazes de acessar os dados da conta e consomem recursos na conta.  
  
    6.  Salve as alterações para Core-site.XML.  
  
5.  Adicione propriedade yarn e os valores para o arquivo yarn-site.XML.  
  
    Ignore esta etapa se você estiver conectando a um 1.3 Hadoop externo.  
  
    A partir do Hadoop 2.0, o arquivo yarn-site.XML contém definições de configuração para a estrutura de Hadoop YARN. Esse arquivo está localizado no nó de controle em **C:\program files\Microsoft SQL Server Parallel Data Warehouse\100\Hadoop\conf\\**.  
  
    Para executar consultas do PolyBase em um Cluster de 2.0 externo do Hadoop no Windows ou Linux, você precisa configurar a propriedade de yarn e valores para ser consistente com as configurações de yarn-site.XML no seu Cluster de Hadoop externo. Essa configuração é necessária mesmo que o Hadoop Cluster externa usa as configurações padrão.  
  
    Exemplo de configurações padrão:  
  
    ```xml  
    <property>  
        <name>yarn.application.classpath</name>  
        <value>  
          %HADOOP_CONF_DIR%,  
          %HADOOP_COMMON_HOME%/share/hadoop/common/*,  
          %HADOOP_COMMON_HOME%/share/hadoop/common/lib/*,  
          %HADOOP_HDFS_HOME%/share/hadoop/hdfs/*,  
          %HADOOP_HDFS_HOME%/share/hadoop/hdfs/lib/*,  
          %HADOOP_YARN_HOME%/share/hadoop/yarn/*,  
          %HADOOP_YARN_HOME%/share/hadoop/yarn/lib/*  
         </value>  
      </property>  
    ```  
  
    Quando qualquer propriedade é definida no yarn-site.XML, o PolyBase usará essas configurações de propriedade ao executar consultas em relação a região de HDInsight. Se você planeja executar consultas do PolyBase em relação a região de HDInsight e um Cluster de 2.0 externo do Hadoop no Windows, deve haver consistência entre todos os arquivos yarn-site.XML, caso contrário haverá falha nas consultas do PolyBase.  
  
    Para executar o PolyBase em relação a região de HDInsight e um Cluster de 2.0 Hadoop externo, use as configurações padrão de yarn-site.XML no Cluster de Hadoop externo.  
  
6.  Reinicie a região PDW. Para fazer isso, use a ferramenta Gerenciador de configuração. Consulte [iniciar o Configuration Manager &#40; Analytics Platform System &#41; ](launch-the-configuration-manager.md).  
  
7.  Verifique as configurações de segurança para conexões do Hadoop. Se o **autenticação fraco** Hadoop lado é ativada usando `dfs.permission = true`, você deve criar um usuário do Hadoop **pdw_user** conceda leitura completa e permissões de gravação a esse usuário. SQL Server PDW e as chamadas correspondentes do SQL Server PDW sempre são emitidas como **pdw_user** que é um nome de usuário fixo e não pode ser alterado nesta versão de conectividade do Hadoop e a versão do SQL Server PDW. Se a segurança no Hadoop está desabilitada usando `dfs.permission = false`, nenhuma ação adicional precisa ser executada.  
  
8.  Decida quais usuários podem criar uma fonte de dados externa para o armazenamento de BLOBs do Microsoft Azure. Dê o nome da conta de armazenamento a cada um desses usuários e também **ALTER ANY EXTERNAL DATA SOURCE** ou **CONTROL SERVER** permissão.  
  
9. Para conexões do Hadoop, decida quais usuários podem criar uma fonte de dados externa para o Hadoop. Dê a cada um desses usuários o número de porta e endereço IP de cada nó do nome de Hadoop e conceder a eles **ALTER ANY EXTERNAL DATA SOURCE** ou **CONTROL SERVER** permissão.  
  
10. Conectando-se a WASB também requer o encaminhamento de DNS a ser configurado no dispositivo. Para configurar o encaminhamento de DNS, consulte [usar um encaminhador de DNS para resolver nomes de DNS do dispositivo não &#40; Analytics Platform System &#41; ](use-a-dns-forwarder-to-resolve-non-appliance-dns-names.md).  
  
Os usuários autorizados agora podem criar tabelas externas de fontes de dados externas e formatos de arquivo externo. Eles podem usá-los para integrar dados de várias fontes, incluindo Hadoop, armazenamento de BLOBs do Microsoft Azure e SQL Server PDW.  
  
## <a name="see-also"></a>Consulte também  
[Configuração de dispositivo &#40; Analytics Platform System &#41;](appliance-configuration.md)  
<!-- MISSING LINKS [PolyBase &#40;SQL Server PDW&#41;](../sqlpdw/polybase-sql-server-pdw.md)  -->  
  