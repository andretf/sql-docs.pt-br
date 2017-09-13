---
title: "Código de segurança de acesso no Reporting Services | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- docset-sql-devref
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- code groups [Reporting Services]
- code access security [Reporting Services]
- permission sets [Reporting Services]
- evidence [Reporting Services]
- code access security [Reporting Services], about code access security
- named permission sets [Reporting Services]
ms.assetid: 97480368-1fc3-4c32-b1b0-63edfb54e472
caps.latest.revision: 30
author: guyinacube
ms.author: asaxton
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: a6aab5e722e732096e9e4ffdf458ac25088e09ae
ms.openlocfilehash: d34c2136e148bcd5297160f1776b13b86c343a7f
ms.contentlocale: pt-br
ms.lasthandoff: 08/12/2017

---
# <a name="code-access-security-in-reporting-services"></a>Segurança de acesso do código no Reporting Services
  A segurança de acesso do código gira em torno desses conceitos centrais: evidência, grupos de código e conjuntos de permissões nomeadas. No [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], os componentes Gerenciador de Relatórios, Desingner de Relatórios e Servidor de Relatório têm um arquivo de política que configura a segurança de acesso do código para assemblies personalizados, bem como para extensões de dados, entrega, renderização e segurança. As seções a seguir fornecem uma visão geral da segurança de acesso do código. Para obter mais informações sobre os tópicos abordados nesta seção, consulte "Modelo de política de segurança" o [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] documentação do SDK.  
  
 O [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] usa a segurança de acesso do código porque, embora o servidor de relatório esteja incorporado na tecnologia [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)], há uma diferença significativa entre um aplicativo [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] típico e o servidor de relatório. Um aplicativo [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] típico não executa o código de usuário. Por outro lado, [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] usa uma arquitetura aberta e extensível que permite aos usuários programar os arquivos de definição de relatório usando o **código** elemento de linguagem de definição de relatório e desenvolver funcionalidades especializadas em um assembly personalizado para uso em relatórios. Além disso, os desenvolvedores podem projetar e implantar extensões avançadas que aumentam as capacidades do servidor de relatório. Junto com este avanço e flexibilidade, existe a necessidade de fornecer o máximo de proteção e segurança possível.  
  
 Os desenvolvedores de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] podem usar qualquer assembly do [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] em seus relatórios e chamar de modo nativo toda a funcionalidade dos assemblies implantados no cache de assembly global. A única coisa que o servidor de relatório pode controlar são as permissões concedidas para expressões de relatório e assemblies personalizados carregados. Em [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], assemblies personalizados recebem **Execute**-somente permissões por padrão.  
  
## <a name="evidence"></a>Evidência  
 Evidência são as informações que a CLR (Common Language Runtime) usa para determinar uma política de segurança para assemblies de código. A evidência indica ao tempo de execução que o código tem uma característica específica. As formas comuns de evidência incluem assinaturas digitais e o local de um assembly. A evidência também pode ser personalizada para representar outras informações que são significativas para o aplicativo.  
  
 Os domínios de assembly e de aplicativo recebem permissões com base na evidência. Por exemplo, o local de um assembly que o [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] está tentando acessar é uma forma comum de evidência para assemblies nomeados fracos. Isto é conhecido como evidência de URL. A evidência de URL para uma extensão personalizada de processamento de dados implantada em um servidor de relatório seria “C:\Arquivos de Programas\Microsoft SQL Server\MSRS10_50.MSSQLSERVER\Reporting Services\ReportServer\bin\Microsoft.Samples.ReportingServices.FsiDataExtension.dll". O nome forte ou a assinatura digital de um assembly é outra forma comum de evidência. Neste caso, a evidência corresponde às informações de chave pública para um assembly.  
  
## <a name="code-groups"></a>Grupos de código  
 Um grupo de código é um agrupamento lógico de código que tem uma condição especificada para associação. Qualquer código que satisfaça a condição de associação é incluído no grupo. Os administradores configuram uma política de segurança gerenciando grupos de código e os conjuntos de permissões associados.  
  
 A condição de associação para um grupo de código é baseada na evidência. Por exemplo, uma associação de URL para um grupo de código é baseada na evidência de URL. A CLR (Common Language Runtime) usa características de identificação, como a evidência de URL, para descrever o código e determinar se a condição de associação de um grupo foi cumprida. Por exemplo, se a condição de associação de um grupo de código for “código no assembly C:\Arquivos de Programas\Microsoft SQL Server\MSRS10_50.MSSQLSERVER\Reporting Services\ReportServer\bin\Microsoft.Samples.ReportingServices.FsiDataExtension.dll", o tempo de execução examinará a evidência para determinar se o código é originado desse local. O exemplo de uma entrada de configuração para este tipo de grupo de código poderia parecer com o seguinte:  
  
```  
<CodeGroup class="UnionCodeGroup"  
   version="1"  
   PermissionSetName="FullTrust"  
   Name="MyCodeGroup"  
   Description="Code group for my data processing extension">  
      <IMembershipCondition class="UrlMembershipCondition"  
         version="1"  
         Url="C:\Program Files\Microsoft SQL Server\MSRS10_50.MSSQLSERVER\Reporting Services\ReportServer\bin\Microsoft.Samples.ReportingServices.FsiDataExtension.dll"  
       />  
</CodeGroup>  
```  
  
 Você deve trabalhar junto com o administrador do sistema ou o especialista em implantação do aplicativo para determinar o tipo de segurança de acesso do código e os grupos de código necessários para os assemblies personalizados ou para as extensões do [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].  
  
## <a name="named-permission-sets"></a>Conjuntos de permissões nomeadas  
 Um conjunto de permissões nomeadas é um conjunto de permissões pode ser associado a um grupo de código pelos administradores. A maioria dos conjuntos de permissões nomeadas consiste em pelo menos uma permissão, um nome e uma descrição para o conjunto de permissões. Os administradores podem usar conjuntos de permissões nomeadas para estabelecer ou modificar a política de segurança para grupos de código. Mais de um grupo de código pode ser associado ao mesmo conjunto de permissões nomeadas. O CLR fornece conjuntos de permissões nomeadas internos; entre elas estão **nada**, **execução**, **Internet**, **LocalIntranet**, **tudo**, e **FullTrust**.  
  
> [!NOTE]  
>  Extensões de dados, entrega, renderização e segurança personalizadas no [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] deve ser executado sob o **FullTrust** conjunto de permissões. Trabalhe junto com o administrador do sistema para adicionar o grupo de código apropriado e as condições de associação às extensões do [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].  
  
 Você pode associar seus próprios níveis personalizados de permissões para assemblies personalizados usados com os relatórios. Por exemplo, se desejar permitir que um assembly acesse um arquivo específico, você pode criar um novo conjunto de permissões nomeadas com acesso de E/S específico do arquivo e, em seguida, atribuir o conjunto de permissões ao seu grupo de código. O conjunto de permissões a seguir concede acesso somente leitura ao arquivo MyFile.xml:  
  
```  
<PermissionSet class="NamedPermissionSet"  
   version="1"  
   Name="MyNewFilePermissionSet"  
   Description="A special permission set that grants read access to my file.">  
    <IPermission class="FileIOPermission"  
       version="1"  
       Read="C:\MyFile.xml"/>  
    <IPermission class="SecurityPermission"  
       version="1"  
       Flags="Assertion, Execution"/>  
</PermissionSet>  
```  
  
 Um grupo de código com este conjunto de permissões poderia parecer com o seguinte:  
  
```  
<CodeGroup class="UnionCodeGroup"  
   version="1"  
   PermissionSetName="MyNewFilePermissionSet"  
   Name="MyNewCodeGroup"  
   Description="A special code group for my custom assembly.">  
   <IMembershipCondition class="UrlMembershipCondition"  
      version="1"  
      Url="C:\Program Files\Microsoft SQL Server\MSRS10_50.MSSQLSERVER\Reporting Services\ReportServer\bin\MyCustomAssembly.dll"/>  
</CodeGroup>  
```  
  
## <a name="see-also"></a>Consulte também  
 [Proteger o desenvolvimento de &#40; Reporting Services &#41;](../../../reporting-services/extensions/secure-development/secure-development-reporting-services.md)  
  
  