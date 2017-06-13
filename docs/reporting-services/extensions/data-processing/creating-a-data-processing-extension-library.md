---
title: "Criando uma biblioteca de extensões de processamento de dados | Microsoft Docs"
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
- data processing extensions [Reporting Services], namespace assignments
- library [Reporting Services]
- assigning namespaces to extensions
ms.assetid: 82f4b71b-dd39-467d-8d8c-6771eb2b12de
caps.latest.revision: 39
author: sabotta
ms.author: carlasab
manager: erikre
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0eb007a5207ceb0b023952d5d9ef6d95986092ac
ms.openlocfilehash: 2832e65cb5cad2effa4c551a9842e37244d99c28
ms.contentlocale: pt-br
ms.lasthandoff: 06/13/2017

---
# <a name="creating-a-data-processing-extension-library"></a>Criando uma biblioteca de extensões de processamento de dados
  Cada extensão de processamento de dados do [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] que você cria deve ser atribuída a um namespace exclusivo e criada em uma biblioteca ou em um arquivo de assembly. O nome exato do namespace não é importante, mas deve ser exclusivo e não deve ser compartilhado com qualquer outra extensão. O [!INCLUDE[msCoName](../../../includes/msconame-md.md)] usa o namespace <xref:Microsoft.ReportingServices.DataProcessing> para as extensões de processamento de dados fornecidas com o [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]. Crie os seus próprios namespaces exclusivos para as extensões de processamento de dados de sua empresa.  
  
 O exemplo a seguir mostra o código para iniciar uma extensão de processamento de dados do [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], que usa os espaços para nome que contêm as interfaces de processamento de dados e qualquer classe utilitária.  
  
```vb  
Imports System  
Imports Microsoft.ReportingServices.DataProcessing  
Imports Microsoft.ReportingServices.Interfaces  
  
Namespace CompanyName.ExtensionName  
   ...  
```  
  
```csharp  
using System;  
using Microsoft.ReportingServices.DataProcessing;  
using Microsoft.ReportingServices.Interfaces;  
  
namespace CompanyName.ExtensionName  
{  
   ...  
```  
  
 Durante a compilação de uma extensão de processamento de dados do [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], forneça ao compilador uma referência a Microsoft.ReportingServices.Interfaces.dll, já que as interfaces de extensão de processamento de dados estão contidas ali. O namespace <xref:Microsoft.ReportingServices.DataProcessing> é necessário para implementar as interfaces de extensão de processamento de dados e o namespace <xref:Microsoft.ReportingServices.Interfaces> é necessário para implementar a interface <xref:Microsoft.ReportingServices.Interfaces.IExtension>. Por exemplo, se todos os arquivos com código para implementar uma extensão de processamento de dados do [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] escrita em C# estivessem em um único diretório com a extensão .cs, o comando a seguir seria emitido a partir desse diretório para compilar os arquivos armazenados em CompanyName.ExtensionName.dll.  
  
```csharp  
csc /t:library /out:CompanyName.ExtensionName.dll *.cs /r:System.dll /r:Microsoft.ReportingServices.Interfaces.dll  
```  
  
 O exemplo de código a seguir mostra o comando que seria usado para [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] arquivos com a extensão. vb.  
  
```vb  
vbc /t:library /out:CompanyName.ExtensionName.dll *.vb /r:System.dll /r:Microsoft.ReportingServices.Interfaces.dll  
```  
  
> [!NOTE]  
>  Você também pode criar, desenvolver e compilar sua própria extensão de processamento de dados usando o [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]. Para obter mais informações sobre como desenvolver assemblies no [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], consulte a documentação do [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].  
  
## <a name="see-also"></a>Consulte também  
 [Extensões do Reporting Services](../../../reporting-services/extensions/reporting-services-extensions.md)   
 [Implementando uma extensão de processamento de dados](../../../reporting-services/extensions/data-processing/implementing-a-data-processing-extension.md)   
 [Biblioteca de extensões do Reporting Services](../../../reporting-services/extensions/reporting-services-extension-library.md)  
  
  