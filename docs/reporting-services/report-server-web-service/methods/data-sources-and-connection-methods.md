---
title: "Fontes de dados e os métodos de Conexão | Microsoft Docs"
ms.custom: 
ms.date: 03/06/2017
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
- connections [Reporting Services], data sources
- reports [Reporting Services], data
- data sources [Reporting Services], methods
ms.assetid: 50999b52-fc7c-4333-9fb0-d04c37a4c90f
caps.latest.revision: 38
author: guyinacube
ms.author: asaxton
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: a6aab5e722e732096e9e4ffdf458ac25088e09ae
ms.openlocfilehash: 922c7fbd680a9d82713db30d8df5f0ae5a40401a
ms.contentlocale: pt-br
ms.lasthandoff: 08/12/2017

---
# <a name="data-sources-and-connection-methods"></a>Fontes de dados e métodos de conexão
  Você pode usar estes métodos para definir e gerenciar conexões e credenciais da fonte de dados.  
  
|Método|Ação|  
|------------|------------|  
|<xref:ReportService2010.ReportingService2010.CreateDataSource%2A>|Cria uma nova fonte de dados no banco de dados do servidor de relatório ou na biblioteca do SharePoint.|  
|<xref:ReportService2010.ReportingService2010.DisableDataSource%2A>|Desabilita uma fonte de dados que está habilitada.|  
|<xref:ReportService2010.ReportingService2010.EnableDataSource%2A>|Habilita uma fonte de dados que está desabilitada.|  
|<xref:ReportService2010.ReportingService2010.GetDataSourceContents%2A>|Retorna o conteúdo de uma fonte de dados.|  
|<xref:ReportService2010.ReportingService2010.GetItemDataSourcePrompts%2A>|Obtém os avisos de fonte de dados de um item especificado.|  
|<xref:ReportService2010.ReportingService2010.GetItemDataSources%2A>|Retorna as fontes de dados de um item no catálogo.|  
|<xref:ReportService2010.ReportingService2010.ListDependentItems%2A>|Retorna uma lista dos itens de catálogo que fazem referência a um item de catálogo especificado.|  
|<xref:ReportService2010.ReportingService2010.ListSubscriptionsUsingDataSource%2A>|Retorna uma lista de assinaturas associadas a uma determinada fonte de dados.|  
|<xref:ReportService2010.ReportingService2010.SetDataSourceContents%2A>|Define as propriedades da conexão associadas a uma fonte de dados.|  
|<xref:ReportService2010.ReportingService2010.SetItemDataSources%2A>|Define as fontes de dados de um item em um banco de dados do servidor de relatório ou na biblioteca do SharePoint.|  
|<xref:ReportService2010.ReportingService2010.TestConnectForDataSourceDefinition%2A>|Testa a conexão de uma fonte de dados. Esse método oferece suporte aos testes diretos da fonte de dados.|  
|<xref:ReportService2010.ReportingService2010.TestConnectForItemDataSource%2A>|Testa a conexão de uma fonte de dados. Esse método dá suporte aos testes de fontes de dados publicadas usadas por relatórios ou modelos e fontes de dados compartilhadas.|  
  
## <a name="see-also"></a>Consulte também  
 [Criando aplicativos que usam o serviço Web e o .NET Framework](../../../reporting-services/report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md)   
 [Serviço Web servidor de relatório](../../../reporting-services/report-server-web-service/report-server-web-service.md)   
 [Métodos de Web do serviço do servidor de relatório](../../../reporting-services/report-server-web-service/methods/report-server-web-service-methods.md)   
 [Referência técnica &#40; SSRS &#41;](../../../reporting-services/technical-reference-ssrs.md)  
  
  