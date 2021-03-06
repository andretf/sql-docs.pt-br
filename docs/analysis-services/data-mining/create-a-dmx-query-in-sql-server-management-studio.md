---
title: Criar uma consulta DMX no SQL Server Management Studio | Microsoft Docs
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
helpviewer_keywords:
- templates [Analysis Services], queries
- SQL Server Management Studio [Analysis Services], DMX queries
- predictions [Analysis Services], DMX prediction queries
- predictions [DMX]
- prediction queries [DMX]
- queries [DMX], prediction queries
- mining models [Analysis Services], DMX
ms.assetid: 568ce40a-1f53-47eb-8c79-14347cdfde83
caps.latest.revision: 
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: edb3f0ab17369a4a1df4a69d80e07bfa1ff84012
ms.sourcegitcommit: 7519508d97f095afe3c1cd85cf09a13c9eed345f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2018
---
# <a name="create-a-dmx-query-in-sql-server-management-studio"></a>Criar uma consulta DMX no SQL Server Management Studio
[!INCLUDE[ssas-appliesto-sqlas](../../includes/ssas-appliesto-sqlas.md)]
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fornece um conjunto de recursos para ajudar a criar consultas de previsão, consultas de conteúdo e consultas de definição de dados em modelos de mineração e estruturas de mineração.  
  
-   O Construtor de consulta de previsão gráfico está disponível no [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] e no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], para simplificar o processo de escrever consultas de previsão e conjuntos de dados de mapeamento em um modelo.  
  
-   Os modelos de consulta fornecidos no Gerenciador de Modelos iniciam a criação de muitos tipos de consultas DMX, incluindo muitos tipos de consultas de previsão. Os modelos são fornecidos para consultas de conteúdo, consultas que usaram conjuntos de dados aninhados, consulta que retornaram casos da estrutura de mineração e até mesmo consultas de definição de dados.  
  
-   O Gerenciador de Metadados nos painéis de consulta MDX e DMX fornece uma lista de modelos e estruturas disponíveis que você pode arrastar e soltar no construtor de consultas, assim como uma lista de funções DMX. Este recurso facilita a obtenção correta de nomes de objetos, sem digitar.  
  
 Este tópico descreve como criar uma consulta DMX usando o Gerenciador de Metadados e o editor de consultas DMX.  
  
##  <a name="BKMK_Templates"></a> Modelos de consulta DMX  
 Modelos para criar consultas DMX básicas estão disponíveis no Explorador de Modelos. A pasta **DMX** contém modelos de mineração de dados que estão divididos nestas categorias:  
  
-   **Conteúdo do modelo**  
  
-   **Gerenciamento de modelo**  
  
-   **Consultas de previsão**  
  
-   **Conteúdo da estrutura**  
  
 Você também pode criar modelos personalizados, para consultas ou comandos que você executa com frequência.  
  
## <a name="xmla-query-templates"></a>Modelos de consulta XMLA  
 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] também fornece modelos para consultas XMLA.  
  
 Há alguma sobreposição entre os tipos de consultas que você pode executar usando XMLA e DMX. Por exemplo, você pode criar algumas consultas de conteúdo de modelo usando DMX ou os conjuntos de linhas de esquema de mineração de dados, mas os conjuntos de linhas de esquema às vezes contêm informações que não são expostas em consultas de conteúdo DMX.  
  
 Também há algumas diferenças principais no modo como as operações são tratadas no DMX e no XMLA. Por exemplo, você pode usar XMLA para executar operações administrativas como backup de um banco de dados do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] inteiro, mas, se você deseja fazer backup de um único modelo de mineração, o DMX fornece um comando simples, [EXPORT &#40;DMX&#41;](../../dmx/export-dmx.md) que é mais adequado a esse propósito.  
  
##  <a name="BKMK_Building_Queries"></a> Criar e executar uma consulta DMX  
  
#### <a name="open-a-new-dmx-query-window"></a>Abrir nova janela de consulta DMX  
  
1.  Clique em **Nova Consulta** no [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]e selecione **Nova Consulta DMX do Analysis Server**.  
  
2.  Quando a caixa de diálogo **Conectar ao Servidor** é exibida, selecione a instância do [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] que contém os modelos de mineração com os quais deseja trabalhar.  
  
#### <a name="open-template-explorer"></a>Abrir o Explorador de Modelos  
  
1.  No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], no menu **Exibir** , selecione o **Explorador de Modelos**.  
  
2.  Clique em **Analysis Server** para ver uma exibição de árvore do modelo aplicável ao [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].  
  
#### <a name="apply-a-template-to-build-a-query"></a>Aplicar um modelo para criar uma consulta  
  
-   Clique com o botão direito do mouse no tipo de consulta apropriado e selecione **Abrir**.  
  
-   Ou arraste o modelo para o editor de consulta.  
  
-   Você também pode preencher os parâmetros para a consulta usando a opção **Especificar Valores para Parâmetros**no menu **Consulta** .  
  
 Para obter exemplos de como criar tipos específicos de consultas de modelos, consulte os seguintes tópicos:  
  
 [Criar uma consulta de previsão Singleton a partir de um modelo](../../analysis-services/data-mining/create-a-singleton-prediction-query-from-a-template.md)  
  
 [Criar uma consulta de conteúdo em um modelo de mineração](../../analysis-services/data-mining/create-a-content-query-on-a-mining-model.md)  
  
## <a name="see-also"></a>Consulte também  
 [Ferramentas de Consulta de Mineração de Dados](../../analysis-services/data-mining/data-mining-query-tools.md)   
 [Extensões de mineração de dados &#40; DMX &#41; Referência](../../dmx/data-mining-extensions-dmx-reference.md)  
  
  
