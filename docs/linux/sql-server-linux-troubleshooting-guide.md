---
title: Solucionar problemas do SQL Server no Linux | Microsoft Docs
description: "Fornece dicas de solução de problemas para usar o SQL Server 2017 no Linux."
author: annashres
ms.author: anshrest
manager: jhubbard
ms.date: 05/08/2017
ms.topic: article
ms.prod: sql-linux
ms.technology: database-engine
ms.assetid: 99636ee8-2ba6-4316-88e0-121988eebcf9S
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: 21b7d94bcf15e1ae2d99dd44f4b0030929b92111
ms.contentlocale: pt-br
ms.lasthandoff: 08/02/2017

---
# <a name="troubleshoot-sql-server-on-linux"></a>Solucionar problemas do SQL Server no Linux

[!INCLUDE[tsql-appliesto-sslinux-only](../includes/tsql-appliesto-sslinux-only.md)]

Este documento descreve como solucionar problemas de Microsoft SQL Server em execução no Linux ou em um contêiner do Docker. Ao solucionar problemas do SQL Server no Linux, verifique se lembrar as limitações dessa versão de visualização particular. Você pode encontrar uma lista no [notas de versão](sql-server-linux-release-notes.md).

## <a id="connection"></a>Solucionar problemas de falhas de conexão
Se você estiver tendo dificuldade para se conectar ao seu SQL Server do Linux, há algumas coisas para verificar. 

- Verifique se o nome do servidor ou endereço IP acessível a partir do computador cliente.

   > [!TIP]
   > Para localizar o endereço IP do seu computador Ubuntu, você pode executar o comando ifconfig como no exemplo a seguir:
   >
   >   ```bash
   >   sudo ifconfig eth0 | grep 'inet addr'
   >   ```
   > Para o Red Hat, você pode usar o endereço ip, como no exemplo a seguir:
   >
   >   ```bash
   >   sudo ip addr show eth0 | grep "inet"
   >   ```
   > Uma exceção a essa técnica se relaciona com VMs do Azure. Para VMs do Azure, [localizar o IP público para a VM no portal do Azure](sql-server-linux-azure-virtual-machine.md#connect).

- Se aplicável, verifique que você abriu a porta do SQL Server (padrão 1433) no firewall.

- Para VMs do Azure, verifique se você tem um [regra do grupo de segurança de rede para a porta do SQL Server padrão](sql-server-linux-azure-virtual-machine.md#remote).

- Verifique se o nome de usuário e a senha não contém quaisquer erros de digitação ou espaços adicionais ou incorretova maiusculas e minúsculas.

- Tente definir explicitamente o número de porta e protocolo com o nome do servidor com o seguinte: **tcp:servername, 1433**.

- Problemas de conectividade de rede também podem causar tempos limite e erros de conexão. Depois de verificar as informações de conexão e a conectividade de rede, tente novamente a conexão.

## <a name="manage-the-sql-server-service"></a>Gerenciar o serviço SQL Server

As seções a seguir mostram como iniciar, parar, reiniciar e verificar o status do serviço do SQL Server. 

### <a name="manage-the-mssql-server-service-in-red-hat-enterprise-linux-rhel-and-ubuntu"></a>Gerenciar o serviço mssql server no Red Hat Enterprise Linux (RHEL) e no Ubuntu 

Verifique o status do status do serviço do SQL Server usando este comando:

   ```bash
   sudo systemctl status mssql-server
   ```

Você pode parar, iniciar ou reiniciar o serviço SQL Server conforme necessário usando os seguintes comandos:

   ```bash
   sudo systemctl stop mssql-server
   sudo systemctl start mssql-server
   sudo systemctl restart mssql-server
   ```

### <a name="manage-the-execution-of-the-mssql-docker-container"></a>Gerenciar a execução do contêiner Docker mssql

Você pode obter a ID de status e o contêiner do contêiner do Docker do SQL Server mais recente criado executando o comando a seguir (a ID será sob a coluna "ID do CONTÊINER"):

   ```bash
   sudo docker ps -l
   ```
   
Você pode interromper ou reiniciar o serviço SQL Server, conforme necessário usando os seguintes comandos:
   
   ```bash
   sudo docker stop <container ID>
   sudo docker restart <container ID>
   ```

> [!TIP]
> Para mais dicas de solução de problemas para Docker, consulte [contêineres de solução de problemas Docker do SQL Server](sql-server-linux-configure-docker.md#troubleshooting).

## <a name="access-the-log-files"></a>Acessar os arquivos de log
   
Os logs de mecanismo do SQL Server para o arquivo /var/opt/mssql/log/errorlog nas instalações do Linux e o Docker. Você precisa estar no modo de "superusuário" para procurar esse diretório.

O instalador registra aqui: / var/opt/mssql/instalação-< carimbo de hora que representa o tempo de instalação > você pode procurar os arquivos de log de erros com qualquer ferramenta compatível UTF-16 como 'vim' ou 'cat' esta aparência: 

   ```bash
   sudo cat errorlog
   ```

Se preferir, você também pode converter os arquivos UTF-8 para lê-los com 'mais' ou 'menos' com o seguinte comando:
   
   ```bash
   sudo iconv –f UTF-16LE –t UTF-8 <errorlog> -o <output errorlog file>
   ```
## <a name="extended-events"></a>Eventos estendidos

Eventos estendidos podem ser consultados por meio de um comando SQL.  Para obter mais informações sobre eventos estendidos podem ser encontradas [aqui](https://technet.microsoft.com/en-us/library/bb630282.aspx):

## <a name="crash-dumps"></a>Despejos de memória 

Procure os despejos de memória no diretório de log no Linux. Verifique no diretório /var/opt/mssql/log de despejos de memória do núcleo do Linux (. tar.gz2 extensão) ou SQL minidespejos (extensão. mdmp)

Para dumps principais 
   ```bash
   sudo ls /var/opt/mssql/log | grep .tar.gz2 
   ```

Para despejos de memória do SQL 
   ```bash
   sudo ls /var/opt/mssql/log | grep .mdmp 
   ```

## <a name="common-issues"></a>Problemas comuns

1. Você não pode se conectar à instância do SQL Server remota.

   Consulte a seção solução de problemas do tópico, [conectar-se ao SQL Server no Linux](#connection).

2. Erro: O nome do host deve ter 15 caracteres ou menos.

   Este é um problema conhecido que ocorre sempre que o nome do computador que está tentando instalar o pacote Debian do SQL Server é maior do que 15 caracteres. Atualmente, não há nenhuma solução alternativa diferente alterando o nome da máquina. É uma maneira de fazer isso editando o arquivo de nome de host e reinicializar o computador. O seguinte [guia site](http://www.cyberciti.biz/faq/ubuntu-change-hostname-command/) isso explica detalhadamente.

3. Redefinindo a senha de administração (SA) do sistema.

   Se você tiver esquecido a senha de administrador do sistema ou precisa redefini-la por algum outro motivo, siga estas etapas.

   > [!NOTE]
   > Siga estas etapas temporariamente interromperá o serviço do SQL Server.

   Faça logon no terminal host, execute os seguintes comandos e siga os prompts para redefinir a senha de SA:

   ```bash
   sudo systemctl stop mssql-server
   sudo /opt/mssql/bin/mssql-conf setup
   ```

4. Usar caracteres especiais na senha.

   Se você usar alguns caracteres na senha de logon do SQL Server, você precisará reservá-los quando usá-los no terminal Linux. Você precisará de escape de $ a qualquer momento usando o caractere de barra invertida é usado em um script de shell de comando/terminal:

   Não funciona:

   ```bash
   sudo sqlcmd -S myserver -U sa -P Test$$
   ```

   Como funciona:

   ```bash
   sqlcmd -S myserver -U sa -P Test\$\$
   ```

   Recursos: [caracteres especiais](http://tldp.org/LDP/abs/html/special-chars.html)
   [Escaping](http://tldp.org/LDP/abs/html/escapingsection.html)

## <a name="support"></a>Suporte

O suporte está disponível por meio da comunidade e monitorados pela equipe de engenharia. Para dúvidas específicas, use os seguintes recursos:

- [DBA pilha Exchange](https://dba.stackexchange.com/questions/tagged/sql-server): faça perguntas de administração de banco de dados
- [Estouro de pilha](http://stackoverflow.com/questions/tagged/sql-server): faça perguntas de desenvolvimento
- [Fóruns do MSDN](https://social.msdn.microsoft.com/Forums/en-US/home?category=sqlserver): questões técnicas
- [Microsoft Connect](https://connect.microsoft.com/SQLServer/Feedback): relatório de bugs e o recurso de solicitação
- [Reddit](https://www.reddit.com/r/SQLServer/): discutir do SQL Server