---
title: "Visão geral da programação do Integration Services | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- Integration Services, programming
- architecture [Integration Services]
- assemblies [Integration Services]
- SSIS, programming
- SQL Server Integration Services, programming
- run-time engine [Integration Services]
- packages [Integration Services], programming
- data flow engine [Integration Services]
- languages [Integration Services]
ms.assetid: 262babc6-eea5-4609-bc65-07d64cbcfee9
caps.latest.revision: 42
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: 47cb31613e30199902335d891b9f5777757feed3
ms.contentlocale: pt-br
ms.lasthandoff: 09/26/2017

---
# <a name="integration-services-programming-overview"></a>Visão geral da programação do Integration Services
  [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)][!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] tem uma arquitetura que separa a movimentação de dados e a transformação de fluxo de controle do pacote e o gerenciamento. Há dois mecanismos distintos que definem essa arquitetura e isso pode ser automatizado e estendido na programação do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]. O mecanismo de tempo de execução implementa a infraestrutura de gerenciamento de fluxos de controle e pacotes que permite aos desenvolvedores controlar o fluxo de execução e definir opções para registro de log, manipuladores de eventos e variáveis. O mecanismo de fluxo de dados é um mecanismo de desempenho alto, especializado, dedicado exclusivamente a extrair, transformar e carregar dados. Sua programação do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] se baseará nesses dois mecanismos.  
  
 A imagem a seguir descreve a arquitetura do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].  
  
 ![Arquitetura do Integration Services](../integration-services/media/mw-dts-01.gif "arquitetura do Integration Services")  
  
## <a name="integration-services-run-time-engine"></a>Mecanismo de tempo de execução do Integration Services  
 O mecanismo de tempo de execução do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] controla o gerenciamento e a execução de pacotes, implementando a infraestrutura que habilita a ordem de execução, o registro em log, variáveis e a manipulação de eventos. A programação do mecanismo de tempo de execução do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] permite que os desenvolvedores automatizem a criação, a configuração e a execução de pacotes e criem tarefas personalizadas e outras extensões.  
  
 Para obter mais informações, consulte [estendendo o pacote com a tarefa de Script](../integration-services/extending-packages-scripting/task/extending-the-package-with-the-script-task.md), [desenvolvendo uma tarefa personalizada](../integration-services/extending-packages-custom-objects/task/developing-a-custom-task.md), e [compilando pacotes programaticamente](../integration-services/building-packages-programmatically/building-packages-programmatically.md).  
  
## <a name="integration-services-data-flow-engine"></a>Mecanismo de fluxo de dados do Integration Services  
 O mecanismo de fluxo de dados gerencia a tarefa de fluxo de dados, que é especializada, de alto desempenho, dedicada à movimentação e transformação de dados de origens distintas. Diferente de outras tarefas, a tarefa de fluxo de dados contém objetos adicionais chamados de componentes de fluxo de dados, que podem ser origens, transformações ou destinos. Esses componentes são as principais partes de movimentação da tarefa. Eles definem a movimentação e a transformação de dados. A programação do mecanismo de fluxo de dados permite que desenvolvedores automatizem a criação e a configuração dos componentes em uma tarefa de fluxo de dados e criem componentes personalizados.  
  
 Para obter mais informações, consulte [estendendo o fluxo de dados com o componente Script](../integration-services/extending-packages-scripting/data-flow-script-component/extending-the-data-flow-with-the-script-component.md), [desenvolvendo um componente de fluxo de dados personalizada](../integration-services/extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md), e [compilando pacotes programaticamente](../integration-services/building-packages-programmatically/building-packages-programmatically.md).  
  
## <a name="supported-languages"></a>Idiomas com suporte  
 [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]oferece suporte a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)]. Isso permite que desenvolvedores programem o [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] ao escolherem idiomas compatíveis com .NET. Embora o mecanismo de tempo de execução e o mecanismo de fluxo de dados sejam escritos em código nativo, ambos estão disponíveis através de um modelo de objeto totalmente gerenciado.  
  
 Você pode programar [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] pacotes, tarefas personalizadas e componentes no [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] ou em outro editor de texto ou código. O [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] oferece ao desenvolvedor muitas ferramentas e recursos para simplificar e acelerar os ciclos iterativos de codificação, depuração e teste. O [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] também facilita a implantação. Porém, você não precisa do [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] para compilar e criar projetos de código do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]. O SDK do [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] inclui os compiladores [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] e [!INCLUDE[csprcs](../includes/csprcs-md.md)] e as ferramentas relacionadas.  
  
> [!IMPORTANT]  
>  Por padrão, o [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] é instalado com o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], mas não com o SDK de [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)].  A menos que o SDK esteja instalado no computador e a documentação do SDK esteja incluída na coleção de manuais online, os links para o conteúdo do SDK desta seção não funcionarão. Depois de ter instalado o [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] SDK, você pode adicionar a documentação do SDK para a coleção de Manuais Online e o sumário seguindo as instruções em [adicionar ou remover a documentação de produto do SQL Server](http://msdn.microsoft.com/library/ef798cc8-87cf-4d60-a7bf-9e061bdd0052).  
  
 O [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] tarefa Script e componente Script usam [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Tools for Applications (VSTA) como um ambiente de script incorporado. O VSTA dá suporte ao [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual Basic e ao [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual C#.  
  
> [!NOTE]  
>  As interfaces de programação de aplicativo [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] são incompatíveis com as linguagens de scripts baseadas em COM, como VBScript.  
  
## <a name="locating-assemblies"></a>Localizando assemblies  
 No [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)], os assemblies do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] foram atualizados para o .NET 4.0. Há um cache de assembly global separado para o .NET 4, localizado em * \<drive >*: \windows\microsoft.net\assembly.. Você pode localizar todos os assemblies do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] nesse caminho, normalmente na pasta GAC_MSIL.  
  
 Nas versões anteriores do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], o núcleo [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] arquivos. dll de extensibilidade também estão localizados em * \<drive >*: \Program Files\Microsoft SQL Server\100\SDK\Assemblies.  
  
## <a name="commonly-used-assemblies"></a>Assemblies comumente usados  
 A tabela a seguir lista os assemblies usados com frequência durante a programação do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] através do [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)].  
  
|Assembly|Description|  
|--------------|-----------------|  
|Microsoft.SqlServer.ManagedDTS.dll|Contém o mecanismo de tempo de execução gerenciado.|  
|Microsoft.SqlServer.RuntimeWrapper.dll|Contém o assembly de interoperabilidade primária (PIA), ou wrapper, para o mecanismo de tempo de execução nativo.|  
|Microsoft.SqlServer.PipelineHost.dll|Contém o mecanismo de fluxo de dados gerenciado.|  
|Microsoft.SqlServer.PipelineWrapper.dll|Contém o assembly de interoperabilidade primária (PIA), ou wrapper, para o mecanismo de fluxo de dados nativo.|  
  
  