---
title: Suporte do Azure Active Directory no SSDT (SQL Server Data Tools) | Microsoft Docs
ms.custom: 
ms.date: 03/05/2018
ms.prod: sql-non-specified
ms.prod_service: sql-tools
ms.service: 
ms.component: ssdt
ms.reviewer: 
ms.suite: sql
ms.technology:
- tools-ssdt
ms.tgt_pltfrm: 
ms.topic: article
author: stevestein
ms.author: sstein
manager: craigg
ms.workload: Active
ms.openlocfilehash: 14a6ae78a0ed5969ce3ab65dbd09b81680076fdb
ms.sourcegitcommit: ab25b08a312d35489a2c4a6a0d29a04bbd90f64d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/08/2018
---
# <a name="azure-active-directory-support-in-sql-server-data-tools-ssdt"></a>Suporte do Azure Active Directory no SSDT (SQL Server Data Tools)

[!INCLUDE[appliesto-xx-asdb-xxxx-xxx-md.md](../includes/appliesto-xx-asdb-xxxx-xxx-md.md)]

O SSDT (SQL Server Data Tools) fornece vários métodos de autenticação do [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-whatis).

![Caixa de diálogo de conexão do SSDT](media/azure-active-directory/interactive.png)

## <a name="active-directory-password-authentication"></a>Autenticação da Senha do Active Directory

A Autenticação de Senha do Active Directory é um mecanismo de conexão com o Banco de Dados SQL do Azure, que usa identidades no Azure Active Directory (Microsoft Azure AD).  Use esse método para se conectar, caso você entre no Windows usando as credenciais de um domínio que não seja federado ao Azure ou usando a autenticação do Azure AD com base no domínio inicial ou do cliente. Para obter mais informações, veja [Conectar-se ao Banco de Dados SQL usando a Autenticação do Azure Active Directory](https://docs.microsoft.com/azure/sql-database/sql-database-aad-authentication).  

## <a name="active-directory-integrated-authentication"></a>Autenticação Integrada do Active Directory

A Autenticação Integrada do Active Directory é um mecanismo de conexão com o Banco de Dados SQL do Azure que usa identidades no Azure Active Directory (Microsoft Azure AD). Use esse método para se conectar, caso você entre no Windows com as credenciais de um domínio federado do Azure Active Directory. Para obter mais informações, veja [Conectar-se ao Banco de Dados SQL usando a Autenticação do Azure Active Directory](https://docs.microsoft.com/azure/sql-database/sql-database-aad-authentication).

## <a name="active-directory-interactive-authentication-preview"></a>Autenticação Interativa do Active Directory (visualização)

O SSDT fornece um novo método de autenticação para conexão com o Banco de Dados SQL do Azure: a **Autenticação Interativa do Active Directory**.


> [!NOTE]
> A Autenticação Interativa do Active Directory está disponível durante a conexão com o SSDT na [visualização do Visual Studio 2017](https://www.visualstudio.com/vs/preview/) e exige instalar a [visualização do .NET 4.7.2 (KB4038188)](https://go.microsoft.com/fwlink/?linkid=867317) no computador com SSDT. Se não instalar a visualização do .NET 4.7.2 (KB4038188), a opção do recurso Autenticação Interativa do Active Directory não estará disponível.


A Autenticação Interativa do Active Directory tem suporte para uma autenticação interativa que permite usar a MFA (Autenticação Multifator) do Azure AD (Active Directory) para se autenticar no Banco de Dados SQL do Azure. Este método tem suporte para usuários federados e nativos do Microsoft Azure AD e para usuários convidados de outras contas (inclusive usuários B2B, contas da Microsoft e de outras plataformas, como @outlook.com, @hotmail.com, @live.com e @gmail.com). Se este método estiver especificado, é necessário especificar o **nome de usuário** e o campo Senha será desabilitado. 

Quando o usuário se autentica com o recurso *Autenticação Interativa do Active Directory*, o sistema exibe uma janela de autenticação que exige inserir uma senha manualmente.

![caixa de diálogo de entrada](media/azure-active-directory/sign-in.png)

A imposição da MFA é fornecida pelo Microsoft Azure AD por meio dessa janela pop-up adicional da MFA durante o processo de autenticação.

> [!NOTE]
> Como a *Autenticação Interativa do Active Directory* exige ao usuário inserir uma senha manualmente (de forma interativa), não recomendamos este método para fluxos de trabalho automatizados.


## <a name="known-issues-and-limitations"></a>Limitações e problemas conhecidos

- O recurso *Autenticação Interativa do Active Directory* tem suporte apenas para conexão com um Banco de Dados SQL do Azure. Ele não tem suporte para SQL Server (local ou em uma VM) nem para SQL Data Warehouse do Azure.
- A *Autenticação Interativa do Active Directory* não tem suporte na Caixa de Diálogo de Conexão do *Gerenciador de Servidores*, portanto você deve se conectar usando o SSDT com o *Pesquisador de Objetos do SQL Server*.
- A integração de logon único com a conta conectada do Visual Studio não tem suporte para SSDT.
- O SQLPackage.exe instalado nas Extensões do Diretório durante a instalação do Visual Studio não deve ser usado nesse local. Para usar o SQLpackage.exe com o AAD, vá para https://www.microsoft.com/pt-br/download/details.aspx?id=55088 
- A Comparação de Dados do SSDT não tem suporte para a autenticação do AAD nem para o novo método de autenticação.  





## <a name="see-also"></a>Consulte Também  
[Autenticação multifator](https://docs.microsoft.com/azure/sql-database/sql-database-ssms-mfa-authentication)  
[Autenticação do Azure Active Directory com o Banco de Dados SQL](https://docs.microsoft.com/azure/sql-database/sql-database-aad-authentication-configure)  
[SQL Server Data Tools no Visual Studio](https://msdn.microsoft.com/library/hh272686(v=vs.103).aspx)  
[Fórum do MSDN do SSDT](https://social.msdn.microsoft.com/Forums/sqlserver/home?forum=ssdt)  
[Blog da equipe do SSDT](http://blogs.msdn.com/b/ssdt/)  
[Referência DACFx API](https://msdn.microsoft.com/library/dn645454.aspx)  
[Baixar o SQL Server Management Studio (SSMS)](../ssms/download-sql-server-management-studio-ssms.md)  
