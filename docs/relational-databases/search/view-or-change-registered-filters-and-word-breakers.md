---
title: Exibir ou alterar filtros registrados e separadores de palavras | Microsoft Docs
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- dbe-search
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- full-text search [SQL Server], word breakers
- full-text search [SQL Server], filters
- filters [full-text search]
- word breakers [full-text search]
ms.assetid: f88c54df-b1aa-4701-807f-dc92c32363fd
caps.latest.revision: 22
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 2032d8aaaa75352d64aa4ed19ec53670afe6d8a7
ms.contentlocale: pt-br
ms.lasthandoff: 06/22/2017

---
# <a name="view-or-change-registered-filters-and-word-breakers"></a>Exibir ou alterar filtros registrados e separadores de palavras
  Depois da instalação ou da desinstalação de qualquer separador de palavras ou de filtros em um sistema, as alterações não entram em vigor automaticamente em instâncias de servidor. Este tópico descreve como exibir o separador de palavras ou os filtros registrados atualmente, e como registrar separadores de palavras e filtros instalados recentemente em uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
### <a name="to-view-a-list-of-languages-whose-word-breakers-are-currently-registered"></a>Para exibir uma lista de idiomas cujos separadores de palavras estão registrados atualmente  
  
1.  Use a exibição de catálogo [sys.fulltext_languages](../../relational-databases/system-catalog-views/sys-fulltext-languages-transact-sql.md) , da seguinte maneira:  
  
    ```  
    SELECT * FROM sys.fulltext_languages;   
    ```  
  
### <a name="to-view-a-list-of-the-filters-that-are-currently-registered"></a>Para exibir uma lista dos filtros que estão registrados atualmente  
  
1.  Use o procedimento armazenado do sistema [sp_help_fulltext_system_components](../../relational-databases/system-stored-procedures/sp-help-fulltext-system-components-transact-sql.md) , da seguinte maneira:  
  
    ```  
    EXEC sp_help_fulltext_system_components 'filter';    
    ```  
  
### <a name="to-register-newly-installed-word-breakers-and-filters"></a>Para registrar separadores de palavras e filtros instalados recentemente  
  
1.  Use o procedimento armazenado do sistema [sp_fulltext_service](../../relational-databases/system-stored-procedures/sp-fulltext-service-transact-sql.md) para atualizar a lista de idiomas, da seguinte maneira:  
  
    ```  
    exec sp_fulltext_service 'update_languages';   
    ```  
  
### <a name="to-unregister-uninstalled-word-breakers-and-filters"></a>Para cancelar o registro de separadores de palavras e filtros desinstalados  
  
1.  Use **sp_fulltext_service** para atualizar a lista de idiomas, da seguinte maneira:  
  
    ```  
    exec sp_fulltext_service 'update_languages'  
    ```  
  
2.  Use **sp_fulltext_service** para reiniciar os processos do host daemon do filtro (fdhost.exe), da seguinte maneira:  
  
    ```  
    exec sp_fulltext_service 'restart_all_fdhosts';  
    ```  
  
### <a name="to-replace-existing-word-breakers-or-filters-when-installing-new-ones"></a>Para substituir separadores de palavras ou filtros existentes ao instalar novos  
  
1.  Ao preparar a instalação de um arquivo DLL que contém novos separadores de palavras ou filtros, verifique se ele tem um nome de arquivo diferente de qualquer um dos arquivos DLL existentes instalados na instância do servidor.  
  
2.  Copie o novo arquivo DLL no diretório que contém os arquivos DLL padrão do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para a instância do servidor. O local padrão é:  
  
     C:\Arquivos de Programas\Microsoft SQL Server\MSSQL.*instance_name*\MSSQL\Binn  
  
    > [!IMPORTANT]  
    >  É altamente recomendável carregar apenas componentes assinados e verificados. Além disso, é recomendável executar o Serviço do Iniciador FDHOST (MSSQLFDLauncher) com o mínimo possível de privilégios.  
  
3.  Instale o novo separador de palavras ou filtros.  
  
     **Para instalar e carregar o Microsoft Filter Pack IFilters**  
  
    -   [Como registrar o Microsoft Filter Pack IFilters no SQL Server](http://go.microsoft.com/fwlink/?LinkId=130439)  
  
4.  Use **sp_fulltext_service** para carregar os separadores de palavras e filtros recentemente instalados na instância de servidor, da seguinte maneira:  
  
    ```  
    EXEC sp_fulltext_service @action='load_os_resources', @value=1;  
    ```  
  
5.  Use **sp_fulltext_service** para atualizar a lista de idiomas, da seguinte maneira:  
  
    ```  
    EXEC sp_fulltext_service 'update_languages';  
    ```  
  
6.  Reinicie os processos do host daemon do filtro (fdhost.exe), usando **sp_fulltext_service** da seguinte forma:  
  
    ```  
    EXEC sp_fulltext_service 'restart_all_fdhosts';   
    ```  
  
## <a name="see-also"></a>Consulte também  
 [Definir a conta de serviço do Iniciador do Daemon de Filtro de Texto Completo](../../relational-databases/search/set-the-service-account-for-the-full-text-filter-daemon-launcher.md)   
 [Configurar e gerenciar filtros para pesquisa](../../relational-databases/search/configure-and-manage-filters-for-search.md)   
 [Configurar e gerenciar separadores de palavras e lematizadores de pesquisa](../../relational-databases/search/configure-and-manage-word-breakers-and-stemmers-for-search.md)  
  
  