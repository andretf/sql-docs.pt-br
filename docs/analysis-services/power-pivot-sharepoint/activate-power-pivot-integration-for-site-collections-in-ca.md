---
title: "Ativar a integração do Power Pivot para coleções de sites no Canadá | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: 
ms.component: data-mining
ms.reviewer: 
ms.suite: pro-bi
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 62a27e53-446a-42d7-b5db-c009e02d4904
caps.latest.revision: 
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 52fb43ddd40e432cb174c9d0794a3919fc48ff7a
ms.sourcegitcommit: 7519508d97f095afe3c1cd85cf09a13c9eed345f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2018
---
# <a name="activate-power-pivot-integration-for-site-collections-in-ca"></a>Ativar a integração do Power Pivot para coleções de sites no Canadá
[!INCLUDE[ssas-appliesto-sqlas](../../includes/ssas-appliesto-sqlas.md)]
Ativar a [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] integração de recursos para coleções de sites específicas será necessário se você usou a opção de instalação Farm Existente para instalar o [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] para SharePoint do SQL Server. Se você instalou o [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] para SharePoint usando a opção Novo Servidor, poderá ignorar esta tarefa porque a Instalação do SQL Server já ativou a integração do recurso [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] para a coleção-raiz de sites quando configurou sua implantação.  
  
 A ativação de recursos no nível da coleção de sites é necessária para tornar as páginas do aplicativo e os modelos disponíveis para seus sites, incluindo as páginas de configuração para a atualização agendada dos dados e as páginas do aplicativo para as bibliotecas da Galeria e Feed de Dados do [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] .  
  
 Você deve ativar a integração do [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] para cada coleção de sites que oferece suporte para o processamento de consulta do [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] .  
  
## <a name="prerequisites"></a>Prerequisites  
 Você deve ser um administrador de conjunto de sites.  
  
## <a name="activate-power-pivot-features"></a>Ativar Recursos do Power Pivot  
  
1.  Em um site do SharePoint, clique em **Ações do Site**.  
  
     Por padrão, os aplicativos Web do SharePoint são acessados pela porta 80. Isso significa que você geralmente pode acessar um site do SharePoint digitando http://\<nome do computador > para abrir o conjunto de sites raiz.  
  
2.  Clique em **Configurações de Site**.  
  
3.  Em Administração do Conjunto de Sites, clique em **Recursos do conjunto de sites**.  
  
4.  Role a página até encontrar o **[!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] Recurso da Coleção de Sites de Integração**.  
  
5.  Clique em **Ativar**.  
  
6.  Repita a operação em outros conjuntos de sites, abrindo cada site e clicando em **Ações do Site**.  
  
## <a name="see-also"></a>Consulte também  
 [Administração e configuração de servidor do Power Pivot na Administração Central](../../analysis-services/power-pivot-sharepoint/power-pivot-server-administration-and-configuration-in-central-administration.md)   
 [Configuração inicial (Power Pivot para SharePoint)](http://msdn.microsoft.com/en-us/3a0ec2eb-017a-40db-b8d4-8aa8f4cdc146)   
 [Instalação do Power Pivot para SharePoint 2010](http://msdn.microsoft.com/en-us/8d47dde7-c941-4280-a934-e2fe3f9a938f)  
  
  
