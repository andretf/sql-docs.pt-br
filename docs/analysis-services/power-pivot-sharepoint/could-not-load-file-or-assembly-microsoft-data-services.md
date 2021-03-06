---
title: "Não foi possível carregar arquivo ou assembly serviços de dados Microsoft | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: 
ms.component: 
ms.reviewer: 
ms.suite: pro-bi
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 81ed0f44-8782-462d-af8f-0ba5b975df27
caps.latest.revision: 
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 0daa7111e93a81c367fda433cc7b530a4c90e8f4
ms.sourcegitcommit: 7519508d97f095afe3c1cd85cf09a13c9eed345f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2018
---
# <a name="could-not-load-file-or-assembly-microsoft-data-services"></a>Não foi possível carregar arquivo ou assembly serviços de dados Microsoft
[!INCLUDE[ssas-appliesto-sqlas](../../includes/ssas-appliesto-sqlas.md)]
Em ambientes do SharePoint 2010 com o [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] para SharePoint, este erro ocorrerá se você tentar fazer uma exportação de feed de dados e o sistema não contiver a versão necessária do Microsoft ADO.NET Data Services.  
  
## <a name="details"></a>Detalhes  
  
|||  
|-|-|  
|Aplica-se a|[!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] para SharePoint|  
|Versão do Produto|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]|  
|Causa|O ADO.NET Data Services 3.5 SP1 não foi localizado.|  
|Texto da mensagem|Não foi possível carregar o arquivo ou assembly 'Microsoft.Data.Services, Version=3.5.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089' ou uma de suas dependências. O sistema não pôde localizar o arquivo especificado|  
  
## <a name="explanation"></a>Explicação  
 O SharePoint 2010 inclui um botão Exportar como Feed de Dados que pode ser usado para exportar uma lista do SharePoint como um feed de dados XML. Além disso, o Reporting Services no modo do SharePoint e o [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] para SharePoint dão suporte aos recursos de feed de dados que exigem o ADO.NET Data Services.  
  
 Se o ADO.NET Data Services não estiver instalado, esse erro ocorrerá quando você solicitar um feed de dados.  
  
## <a name="user-action"></a>Ação do usuário  
  
1.  Consulte a documentação de requisitos de hardware e software para SharePoint 2010 em [Requisitos de hardware e software (SharePoint 2010)](http://go.microsoft.com/fwlink/?LinkId=169734) (http://go.microsoft.com/fwlink/?LinkId=169734).  
  
2.  Em **Instalando pré-requisitos de software**, localize o link para o ADO.NET Data Services 3.5 que corresponde ao sistema operacional você está usando.  
  
3.  Clique no link e execute o programa de instalação que instala o serviço.  
  
## <a name="see-also"></a>Consulte também  
 [Implantar soluções Power Pivot para SharePoint](../../analysis-services/power-pivot-sharepoint/deploy-power-pivot-solutions-to-sharepoint.md)  
  
  
