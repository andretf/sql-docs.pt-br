---
title: Gerenciamento de senhas (OracleToSQL) | Microsoft Docs
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
helpviewer_keywords:
- Managing Passwords in Oracle, Exporting or Importing Encrypted Password
- Managing passwords in Oracle, Securing Password
ms.assetid: 8c7d9f8e-06bb-476c-bbd2-15b61d5bba3c
caps.latest.revision: "24"
author: Shamikg
ms.author: Shamikg
manager: v-thobro
ms.workload: Inactive
ms.openlocfilehash: 6f4203119231c6792d46d3287394dd3bab1b46a1
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/21/2017
---
# <a name="managing-passwords-oracletosql"></a>Gerenciamento de senhas (OracleToSQL)
Esta seção é sobre como proteger senhas de banco de dados e o procedimento para importar ou exportá-los entre servidores:  
  
1.  Proteção de senha  
  
2.  Exportar ou importar a senha criptografada  
  
## <a name="securing-password"></a>Proteção de senha  
O SSMA permite proteger sua senha de um banco de dados.  
  
Use o procedimento a seguir para implementar uma conexão segura:  
  
Especifique uma senha válida usando um dos três métodos a seguir:  
  
1.  **Texto não criptografado:** digite a senha do banco de dados no atributo de valor do nó 'senha'. Ele é encontrado sob o nó de definição de servidor na seção de servidor do arquivo de script ou arquivo de conexão do servidor.  
  
    Senhas em texto não criptografado não são seguras. Portanto, você encontrará a seguinte mensagem de aviso na saída do console: *"servidor &lt;id do servidor&gt; senha é fornecida no formato de texto não criptografado não seguras, aplicativo de Console SSMA fornece uma opção para proteger a senha por meio de criptografia, consulte a opção – securepassword no arquivo de Ajuda do SSMA para obter mais informações."*  
  
    **Senhas criptografadas:** a senha especificada, nesse caso, é armazenada em um formato criptografado no computador local em ProtectedStorage.ssma.  
  
    -   **Proteção de senhas**  
  
        -   Execute o `SSMAforOracleConsole.exe` com o `–securepassword` e adicione a opção na linha de comando, passando o servidor de conexão ou arquivo de script que contém o nó de senha na seção de definição de servidor.  
  
        -   No prompt, o usuário será solicitado a digitar a senha do banco de dados e confirmá-la.  
  
            As ids de definição de servidor e suas senhas criptografadas correspondentes são armazenadas em um arquivo no computador local  
            
            Exemplo 1:  
            
                Specify password
                
                C:\SSMA\SSMAforOracleConsole.EXE –securepassword –add all –s "D:\Program Files\Microsoft SQL Server Migration Assistant for Oracle\Sample Console Scripts\AssessmentReportGenerationSample.xml" –v "D:\Program Files\Microsoft SQL Server Migration Assistant for Oracle\Sample Console Scripts\ VariableValueFileSample.xml"
                
                Enter password for server_id 'XXX_1': xxxxxxx
                
                Re-enter password for server_id 'XXX_1': xxxxxxx
            
            Exemplo 2:
            
                C:\SSMA\SSMAforOracleConsole.EXE –securepassword –add "source_1,target_1" –c "D:\Program Files\Microsoft SQL Server Migration Assistant for Oracle\Sample Console Scripts\ServersConnectionFileSample.xml" – v "D:\Program Files\Microsoft SQL Server Migration Assistant for Oracle\Sample Console Scripts\ VariableValueFileSample.xml" -o
                
                Enter password for server_id 'source_1': xxxxxxx
                
                Re-enter password for server_id 'source_1': xxxxxxx
                
                Enter password for server_id 'target_1': xxxxxxx
                
                Re-enter password for server_id 'target _1': xxxxxxx  
    
    -   **Remover senhas criptografadas**  
  
        Execute o `SSMAforOracleConsole.exe` com o`–securepassword` e `–remove` alternar na linha de comando, passando as ids do servidor, para remover as senhas criptografadas do armazenamento protegido arquivo presente no computador local.  
        
        Exemplo:  
        
            C:\SSMA\SSMAforOracleConsole.EXE –securepassword –remove all
            C:\SSMA\SSMAforOracleConsole.EXE –securepassword –remove "source_1,target_1"  
  
    -   **Listando as Ids do servidor cujas senhas são criptografadas**  
  
        Execute o `SSMAforOracleConsole.exe` com o `–securepassword` e `–list` alternar na linha de comando para listar todas as ids de servidor cujas senhas foram criptografadas.  
  
        Exemplo:  
        
            C:\SSMA\SSMAforOracleConsole.EXE –securepassword –list  
  
    > [!NOTE]  
    > 1.  A senha em texto não criptografado mencionado no arquivo de conexão de servidor ou de script tem precedência sobre a senha criptografada no arquivo protegido.  
    > 2.  Quando não existe nenhuma senha na seção de servidor de arquivo de conexão do servidor ou o arquivo de script ou se ele não foi protegido no computador local, o console solicita que você digite a senha.  
  
## <a name="exporting-or-importing-encrypted-passwords"></a>Exportando ou importando senhas criptografadas  
O aplicativo de Console SSMA permite exportar o banco de dados criptografado senhas presente em um arquivo no computador local para um arquivo protegido e vice-versa. Ele ajuda a tornar a máquina de senhas criptografadas independentes. Funcionalidade de exportação lê a id do servidor e a senha do local protegido armazenamento e salva as informações em um arquivo criptografado. O usuário é solicitado a inserir a senha para o arquivo protegido. Verifique se a senha digitada é 8 caracteres ou mais. Este arquivo protegido é portátil em máquinas diferentes. Funcionalidade de importação lê o servidor de informações de id e a senha do arquivo protegido. O usuário é solicitado a inserir a senha para o arquivo protegido e acrescenta as informações para o armazenamento protegido local.  
  
Exemplo:  

    Export password
    
    Enter password for protecting the exported file C:\SSMA\SSMAforOracleConsole.EXE –securepassword –export all "machine1passwords.file"
    
    Enter password for protecting the exported file: xxxxxxxx
    
    Please confirm password: xxxxxxxx
    
    C:\SSMA\SSMAforOracleConsole.EXE –p –e "OracleDB_1_1,Sql_1" "machine2passwords.file"
    
    Enter password for protecting the exported file: xxxxxxxx
    
    Please confirm password: xxxxxxxx  
  
Exemplo:  

    Import an encrypted password
    
    Enter password for protecting the imported file C:\SSMA\SSMAforOracleConsole.EXE –securepassword –import all "machine1passwords.file"
    
    Enter password to import the servers from encrypted file: xxxxxxxx
    
    Please confirm password: xxxxxxxx
    
    C:\SSMA\SSMAforOracleConsole.EXE –p –i "OracleDB_1,Sql_1" "machine2passwords.file"
    
    Enter password to import the servers from encrypted file: xxxxxxxx
    
    Please confirm password: xxxxxxxx  
  
## <a name="see-also"></a>Consulte Também  
[Executar o Console do SSMA (Oracle)](http://msdn.microsoft.com/en-us/7228ccba-c69f-4b4c-8664-01a2750183c5)  
  
