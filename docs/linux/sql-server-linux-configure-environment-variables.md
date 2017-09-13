---
title: "Configurar o SQL Server com variáveis de ambiente | Microsoft Docs"
description: "Este tópico descreve como usar variáveis de ambiente para configurar as configurações específicas de 2017 do SQL Server no Linux."
author: rothja
ms.author: jroth
manager: jhubbard
ms.date: 07/21/2017
ms.topic: article
ms.prod: sql-linux
ms.technology: database-engine
ms.assetid: 
ms.translationtype: MT
ms.sourcegitcommit: ea75391663eb4d509c10fb785fcf321558ff0b6e
ms.openlocfilehash: 4951f503a7b5c395f86cb6daf2ba705ca69fbd83
ms.contentlocale: pt-br
ms.lasthandoff: 08/02/2017

---
# <a name="configure-sql-server-settings-with-environment-variables-on-linux"></a>Configurar o SQL Server com variáveis de ambiente no Linux

[!INCLUDE[tsql-appliesto-sslinux-only](../includes/tsql-appliesto-sslinux-only.md)]

Você pode usar diversas variáveis de ambiente diferentes para configurar o SQL Server de 2017 RC2 no Linux. Essas variáveis são usadas em dois cenários:

- Para configurar a instalação inicial com o `mssql-conf setup` comando.
- Para configurar um novo [contêiner do SQL Server no Docker](quickstart-install-connect-docker.md).

> [!TIP]
> Se você precisa configurar o SQL Server após esses cenários de instalação, consulte [configurar o SQL Server no Linux com a ferramenta mssql conf](sql-server-linux-configure-mssql-conf.md).

## <a name="environment-variables"></a>Variáveis de ambiente

| Variável de ambiente | Description |
|-----|-----|
| **ACCEPT_EULA** | Aceite o contrato de licença do SQL Server quando definido como qualquer valor (por exemplo, ' Y'). |
| **MSSQL_SA_PASSWORD** | Configure a senha do usuário. |
| **MSSQL_PID** | Defina a chave de produto ou a edição do SQL Server. Os valores possíveis incluem: avaliação, Developer, Express, Web, Standard, Enterprise ou uma chave de produto na forma de # # #-# # #-# # #-# # #-# # #, onde '#' é um número ou uma letra. |
| **MSSQL_LCID** | Define a ID do idioma a ser usado para o SQL Server. Por exemplo, 1036 é francês. |
| **MSSQL_COLLATION** | Define o agrupamento padrão do SQL Server. Isso substitui o mapeamento padrão de id de idioma (LCID) para agrupamento. |
| **MSSQL_MEMORY_LIMIT_MB** | Define a quantidade máxima de memória (em MB) que pode usar o SQL Server. Por padrão é 80% da memória física total. |
| **MSSQL_TCP_PORT** | Configure a porta TCP que o SQL Server escuta (padrão 1433). |
| **MSSQL_IP_ADDRESS** | Defina o endereço IP. Atualmente, o endereço IP deve ser IPv4 estilo (0.0.0.0). |
| **MSSQL_BACKUP_DIR** | Defina o local do diretório de backup padrão. |
| **MSSQL_DATA_DIR** | Altere o diretório onde os arquivos de dados de banco de dados do SQL Server de novo (. mdf) são criados. |
| **MSSQL_LOG_DIR** | Altere o diretório em que os novos arquivos de log (. ldf) do banco de dados do SQL Server são criados. |
| **MSSQL_DUMP_DIR** | Altere o diretório em que a do SQL Server será colocar os despejos de memória e outros arquivos de solução de problemas por padrão. |
| **MSSQL_ENABLE_HADR** | Habilite grupos de disponibilidade. |

## <a name="example-initial-setup"></a>Exemplo: instalação inicial

Este exemplo executa `mssql-conf setup` com configurado variáveis de ambiente. As seguintes variáveis de ambiente especificadas:

- **ACCEPT_EULA** aceita o contrato de licença de usuário final.
- **MSSSQL_PID** Especifica o Licenciado livremente Developer Edition do SQL Server para uso de não produção.
- **MSSQL_SA_PASSWORD** define uma senha forte.
- **MSSQL_TCP_PORT** define a porta TCP que o SQL Server escuta 1234.

```bash
sudo ACCEPT_EULA='Y' MSSQL_PID='Developer' MSSQL_SA_PASSWORD='<YourStrong!Passw0rd>' MSSQL_TCP_PORT=1234 /opt/mssql/bin/mssql-conf setup
```

## <a name="example-docker"></a>Exemplo: Docker

Este exemplo de comando do docker usa as seguintes variáveis de ambiente para criar um novo contêiner de 2017 do SQL Server:

- **ACCEPT_EULA** aceita o contrato de licença de usuário final.
- **MSSSQL_PID** Especifica o Licenciado livremente Developer Edition do SQL Server para uso de não produção.
- **MSSQL_SA_PASSWORD** define uma senha forte.
- **MSSQL_TCP_PORT** define a porta TCP que o SQL Server escuta 1234. Isso significa que, em vez de mapeamento a porta 1433 (padrão) para uma porta de host, a porta TCP personalizada deve ser mapeada com o `-p 1234:1234` comando neste exemplo.

Se você estiver executando o Docker no Linux/macOS, use a seguinte sintaxe com aspas simples:

```bash
docker run -e ACCEPT_EULA=Y -e MSSQL_PID='Developer' -e MSSQL_SA_PASSWORD='<YourStrong!Passw0rd>' -e MSSQL_TCP_PORT=1234 --cap-add SYS_PTRACE -p 1234:1234 -d microsoft/mssql-server-linux
```

Se você estiver executando o Docker no Windows, use a seguinte sintaxe com aspas duplas:

```bash
docker run -e ACCEPT_EULA=Y -e MSSQL_PID="Developer" -e MSSQL_SA_PASSWORD="<YourStrong!Passw0rd>" -e MSSQL_TCP_PORT=1234 --cap-add SYS_PTRACE -p 1234:1234 -d microsoft/mssql-server-linux
```

## <a name="next-steps"></a>Próximas etapas

Para outras configurações do SQL Server não está listadas aqui, consulte [configurar o SQL Server no Linux com a ferramenta mssql conf](sql-server-linux-configure-mssql-conf.md).

Para obter mais informações sobre como instalar e executar o SQL Server no Linux, consulte [instalar o SQL Server no Linux](sql-server-linux-setup.md).
