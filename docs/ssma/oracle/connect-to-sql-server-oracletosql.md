---
title: Conecte-se ao SQL Server (OracleToSQL) | Microsoft Docs
ms.prod: sql-non-specified
ms.prod_service: sql-tools
ms.service: 
ms.component: ssma-oracle
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: sql
ms.technology: sql-ssma
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4ef384ea-5f3e-4f70-ad7c-b62d7b0da628
caps.latest.revision: "3"
author: Shamikg
ms.author: Shamikg
manager: v-pelars
ms.workload: Inactive
ms.openlocfilehash: a5632152d76ea821022dd2915396d69efe722a8b
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/21/2017
---
# <a name="connect-to-sql-server--oracletosql"></a>Conecte-se ao SQL Server (OracleToSQL)
Use o **conectar ao SQL Server** caixa de diálogo para se conectar à instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] que você deseja migrar para o. Para acessar o **conectar ao SQL Server** caixa de diálogo de **arquivo** menu, clique em **conectar ao SQL Server**.  
  
## <a name="options"></a>Opções  
**Nome do servidor**  
Insira ou selecione a instância do SQL Server para se conectar ao. Por padrão, a instância que tenha se conectado mais recentemente é exibida.  
  
-   Se você estiver se conectando à instância padrão no computador local, você pode inserir **localhost** ou um ponto (**.**).  
  
-   Se você estiver se conectando à instância padrão em outro computador, digite o nome do computador.  
  
-   Se você estiver se conectando a uma instância nomeada em outro computador, insira o nome do computador, uma barra invertida e o nome da instância, como *MyServer*\\*MyInstance*.  
  
**Porta do servidor**  
Se sua instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] não está configurado para aceitar conexões o padrão (1433) de porta, digite o número da porta. Caso contrário, deixe esse valor em branco.  
  
**Backup de banco de dados**  
Especifique o banco de dados para migrar objetos e dados. Essa opção não está disponível ao reconectar a [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)].  
  
**Autenticação**  
Selecione o método de autenticação que é usado para se conectar ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]. Para usar sua conta atual do Windows, selecione autenticação do Windows. Para especificar um [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] logon e senha, selecione [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] autenticação.  
  
**User name**  
Se você estiver usando [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] autenticação, insira o logon para a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]. Se você estiver usando autenticação do Windows, essa opção não está disponível.  
  
**Senha**  
Se você estiver usando [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] autenticação, digite a senha para o logon nessa instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]. Se você estiver usando autenticação do Windows, essa opção não está disponível.  
  
**Criptografar conexão**  
Se você quiser se conectar com segurança para o SQL Server, uso de conexão Encrypt, verificando o **criptografar conexão** caixa de seleção.  
  
**Confiar em Certificado do Servidor**  
Se você quiser usar essa opção, selecione o **confiar em certificado do servidor** caixa de seleção.  
  
> [!NOTE]  
> Para habilitar **confiar em certificado do servidor**, "Criptografar" deve ser definido como **True**.  
  
