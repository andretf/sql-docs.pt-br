---
title: "Especificar uma escala logarítmica (construtor de relatórios e SSRS) | Microsoft Docs"
ms.custom: 
ms.date: 03/03/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- reporting-services-sharepoint
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f3092c1c-b128-433d-9a95-983508b2a8d4
caps.latest.revision: 7
author: maggiesMSFT
ms.author: maggies
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 3cbd1de3393757c20cf31c76be12d2911ecf7f9f
ms.contentlocale: pt-br
ms.lasthandoff: 08/09/2017

---
# <a name="specify-a-logarithmic-scale-report-builder-and-ssrs"></a>Especificar uma escala logarítmica (Construtor de Relatórios e SSRS)
  Se você tem dados que são logaritmicamente proporcionais, é recomendável usar uma escala logarítmica em um gráfico em um relatório paginado do [!INCLUDE[ssRSnoversion_md](../../includes/ssrsnoversion-md.md)] . Isso ajuda a melhorar a aparência do gráfico tornando seus dados mais gerenciáveis. A maioria das escalas logarítmicas usa uma base de 10.  
  
 Esse recurso está disponível somente no eixo de valor. Geralmente, o eixo de valor é o eixo vertical, ou eixo y. No entanto, em gráficos de barras, ele é o eixo horizontal, ou eixo x.  
  
 Se seu eixo for logarítmico, todas as outras propriedades relacionadas ao eixo serão logaritmicamente escaladas. Por exemplo, se você especificar uma escala logarítmica de base 10 em seu eixo, definir um intervalo de eixo de 2 gerará intervalos em magnitudes de 10 para a potência de 2 ou 100. Isso significa que os valores do eixo lerão 1, 100, 10.000, em vez do resultado padrão de 1, 10, 100, 1.000, 10.000.  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="to-specify-a-logarithmic-scale"></a>Para especificar uma escala logarítmica  
  
1.  Clique com o botão direito do mouse no eixo y de seu gráfico e clique em **Propriedades VerticalAxis**. A caixa de diálogo **Propriedades VerticalAxis** aparece.  
  
2.  Em **Opções de Eixo**, selecione **Escala Uselogarithmic**.  
  
3.  Na caixa de texto **Base de log** , digite um valor positivo para a base logarítmica. Se nenhum valor for especificado, a base logarítmica assumirá 10 como padrão.  
  
## <a name="see-also"></a>Consulte também  
 [Formatando rótulos dos eixos de um gráfico de &#40; Construtor de relatórios e SSRS &#41;](../../reporting-services/report-design/formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md)   
 [Formatando um gráfico de &#40; Construtor de relatórios e SSRS &#41;](../../reporting-services/report-design/formatting-a-chart-report-builder-and-ssrs.md)   
 [Formatar rótulos de eixo como datas ou moedas &#40; Construtor de relatórios e SSRS &#41;](../../reporting-services/report-design/format-axis-labels-as-dates-or-currencies-report-builder-and-ssrs.md)   
 [Gráficos de &#40; Construtor de relatórios e SSRS &#41;](../../reporting-services/report-design/charts-report-builder-and-ssrs.md)  
  
  