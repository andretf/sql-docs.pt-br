---
title: "Depurando o código de extensão de processamento de dados | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: reporting-services
ms.prod_service: reporting-services-native
ms.service: 
ms.component: extensions
ms.reviewer: 
ms.suite: pro-bi
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: reference
applies_to: SQL Server 2016 Preview
helpviewer_keywords:
- debugging data processing extensions [Reporting Services]
- troubleshooting [Reporting Services], data processing extensions
- data processing extensions [Reporting Services], debugging
ms.assetid: e963e205-9ae0-446d-97df-028a1d2727d9
caps.latest.revision: "40"
author: markingmyname
ms.author: maghan
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 6a21ea00e93516c6e6fd60e3102c618674a4304d
ms.sourcegitcommit: 7e117bca721d008ab106bbfede72f649d3634993
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2018
---
# <a name="debugging-data-processing-extension-code"></a>Depurando o código de extensão de processamento de dados
  O [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] fornece várias ferramentas de depuração que podem ajudar você a analisar o código de extensão de processamento de dados e localizar erros nele. A ferramenta mais adequada dependerá do que você está tentando realizar. Este exemplo usa o [!INCLUDE[vsOrcas](../../../includes/vsorcas-md.md)].  
  
#### <a name="to-debug-your-data-processing-extension-code"></a>Para depurar seu código de extensão de processamento de dados  
  
1.  Inicie o [!INCLUDE[vsOrcas](../../../includes/vsorcas-md.md)] e abra seu projeto de extensão de processamento de dados.  
  
2.  Crie o projeto e implante seu assembly de extensão de processamento de dados e o arquivo .pdb anexo ao Designer de Relatórios. Para obter mais informações sobre a implantação, consulte [Como implantar uma extensão de processamento de dados no Designer de Relatórios](../../../reporting-services/extensions/data-processing/deploying-a-data-processing-extension-to-report-designer.md).  
  
3.  Abra um novo Projeto de Relatório no [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] enquanto deixa seu código de extensão de processamento de dados aberto em uma janela separada do [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].  
  
4.  Navegue até a janela do [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] que contém seu projeto de extensão de processamento de dados e defina alguns pontos de quebra em seu código.  
  
5.  Com a janela do projeto de extensão de processamento de dados ainda ativa, clique em **Anexar ao Processo** no menu **Depurar**.  
  
     A caixa de diálogo **Anexar ao Processo** será aberta.  
  
6.  Na lista de processos, selecione o processo devenv.exe que corresponde ao Projeto de Relatório e clique em **Anexar**.  
  
7.  Defina a fonte de dados do relatório usando a guia **Dados do Relatório** do Projeto de Relatório. Você provavelmente usará o Designer de Consulta genérico para executar uma consulta na fonte de dados personalizada. Isso deve chamar o depurador e executar o código correspondente a seus pontos de quebra.  
  
8.  Percorra seu código usando a tecla F11. Para obter mais informações sobre como usar o [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] para depuração, consulte a documentação do [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].  
  
## <a name="see-also"></a>Consulte Também  
 [Implantando uma extensão de processamento de dados](../../../reporting-services/extensions/data-processing/deploying-a-data-processing-extension.md)   
 [Extensões do Reporting Services](../../../reporting-services/extensions/reporting-services-extensions.md)   
 [Implementando uma extensão de processamento de dados](../../../reporting-services/extensions/data-processing/implementing-a-data-processing-extension.md)   
 [Biblioteca de extensões do Reporting Services](../../../reporting-services/extensions/reporting-services-extension-library.md)  
  
  
