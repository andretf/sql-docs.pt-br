---
title: Projeto de Scripts no SQL Server Management Studio do Analysis Services | Microsoft Docs
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- analysis-services/multidimensional-tabular
- analysis-services/data-mining
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- scripts [Analysis Services]
- scripts [Analysis Services], projects
- projects [Analysis Services], Analysis Server Scripts project
- projects [Analysis Services], creating
- Analysis Server Scripts project
- items [Analysis Services]
ms.assetid: c4f5a06b-e2e4-4660-a3a8-6fd356742c02
caps.latest.revision: 38
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 9edf723461387a102050c299f05d63281a4dd5a2
ms.contentlocale: pt-br
ms.lasthandoff: 09/01/2017

---
# <a name="analysis-services-scripts-project-in-sql-server-management-studio"></a>Projeto de scripts do Analysis Services no SQL Server Management Studio
  No [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], você pode criar um projeto do Analysis Server Scripts no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para agrupar scripts relacionados para uso em desenvolvimento, gerenciamento e controle do código-fonte. Se não houver uma solução carregada no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], a criação de um novo projeto do Analysis Server Scripts criará automaticamente uma nova solução. Caso contrário, o novo projeto do Analysis Server Scripts pode ser adicionado à solução existente ou criado em uma solução nova.  
  
 Siga estas etapas básicas para criar um projeto do Analysis Server Scripts no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]:  
  
1.  No menu Arquivo, aponte para **Novo**e clique em **Projeto**.  
  
     Selecione o modelo de projeto **Scripts do Analysis Server** e especifique um nome e um local para o novo projeto.  
  
2.  Clique com o botão direito do mouse em **Conexões** para criar uma nova conexão na pasta Conexões do projeto do Analysis Server Scripts no Gerenciador de Soluções.  
  
     Esta pasta contém cadeias de conexão com instâncias do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , nas quais os scripts contidos no projeto do Analysis Server Scripts podem ser executados. Podem existir várias conexões em um projeto do Analysis Server Scripts e você pode escolher uma delas para executar um script contido no projeto no momento da execução.  
  
3.  Clique com o botão direito do mouse em **Consultas** para criar scripts MDX (expressão MDX), DMX (extensões DMX) e XMLA (XML for Analysis) na pasta Scripts do projeto do Analysis Server Scripts no Gerenciador de Soluções.
  
4.  Clique com o botão direito do mouse no projeto, aponte para **Adicionar**e selecione **Item Existente** para adicionar arquivos diversos, como arquivos de texto com observações sobre o projeto, na pasta **Diversos** do Analysis Server Scripts no Gerenciador de Soluções. Esses arquivos são ignorados pelo [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].  
  
## <a name="file-types"></a>Tipos de arquivo  
 A solução do [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] pode conter vários tipos de arquivo, dependendo dos projetos incluídos nela e de seus itens. Para obter mais informações sobre tipos de arquivo para soluções em [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], consulte [Arquivos que gerenciam soluções e projetos](http://msdn.microsoft.com/library/e19d2859-0b97-4727-ac27-c4c226d86b2f). Em geral, os arquivos de cada projeto de uma solução do [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] são armazenados na pasta da solução, em uma pasta separada para cada projeto.  
  
 A pasta de um projeto do Analysis Server Scripts pode conter os tipos de arquivo listados na tabela a seguir.  
  
|Tipo de arquivo|Description|  
|---------------|-----------------|  
|Arquivo de definição do projeto do Analysis Server Scripts (.ssmsasproj)|Contém metadados sobre as pastas mostradas no Gerenciador de Soluções, além de informações que indicam quais pastas devem exibir os arquivos incluídos no projeto.<br /><br /> O arquivo de definição do projeto também contém os metadados das conexões do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] contidas no projeto, além dos metadados que associam conexões aos arquivos de script incluídos no projeto.|  
|Arquivo de script DMX (.dmx)|Contém um script DMX incluído no projeto.|  
|Arquivo de script MDX (.mdx)|Contém um script MDX incluído no projeto.|  
|Arquivo de script XMLA (.xmla)|Contém um script XMLA incluído no projeto.|  
  
## <a name="analysis-services-templates"></a>Modelos do Analysis Services  
 Ao adicionar novos scripts MDX, DMX ou XMLA a um projeto do Analysis Server Scripts, você tem a opção de usar o Explorador de Modelos para localizar os modelos do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , uma coleção de scripts ou instruções predefinidos(as) que demonstram como executar a ação especificada. O Explorador de Modelos está disponível no menu **Exibir** e inclui modelos para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]e [!INCLUDE[ssEW](../../includes/ssew-md.md)]. Para obter mais informações, consulte [Usar modelos do Analysis Services no SQL Server Management Studio](../../analysis-services/instances/use-analysis-services-templates-in-sql-server-management-studio.md).  
  
## <a name="see-also"></a>Consulte também  
 [Criação de modelos multidimensionais usando o SSDT &#40;SQL Server Data Tools&#41;](../../analysis-services/multidimensional-models/creating-multidimensional-models-using-sql-server-data-tools-ssdt.md)   
 [Referência de expressões multidimensionais &#40;MDX&#41;](../../mdx/multidimensional-expressions-mdx-reference.md)   
 [Referência de DMX &#40;extensões DMX&#41;](../../dmx/data-mining-extensions-dmx-reference.md)   
 [Linguagem de script do Analysis Services &#40;ASSL para XMLA&#41;](../../analysis-services/scripting/analysis-services-scripting-language-assl-for-xmla.md)   
 [Analysis Services Scripting Language &#40; ASSL para XMLA &#41;](../../analysis-services/scripting/analysis-services-scripting-language-assl-for-xmla.md)  
  
  