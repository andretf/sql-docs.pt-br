---
title: "Adicionar a grade de dados para relatórios móveis | O Reporting Services | Microsoft Docs"
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fe98a970-90d3-44d1-9189-9141c237f141
caps.latest.revision: 4
author: maggiesMSFT
ms.author: maggies
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: c51169b12265eea7e6d57e0daa7539322e338851
ms.contentlocale: pt-br
ms.lasthandoff: 08/09/2017

---
# <a name="add-data-grids-to-mobile-reports--reporting-services"></a>Adicionar grades de dados aos relatórios móveis | Reporting Services
Às vezes, a melhor visualização são os próprios dados. Saiba mais sobre as três *grades de dados*, ou tabelas, para exibir dados em [!INCLUDE[SS_MobileReptPub_Long](../../includes/ss-mobilereptpub-long.md)]:
* Grade de dados simples
* Grade de dados de indicador
* Grade de dados do gráfico

## <a name="simple-data-grid"></a>Grade de dados simples
A grade de dados mais básica e simples pode exibir várias colunas de dados com formatação e cabeçalhos personalizados. 

![mobile-report-simple-data-grid](../../reporting-services/mobile-reports/media/mobile-report-simple-data-grid.png)

Depois de adicionar uma grade de dados à superfície de design, você pode conectá-lo aos dados reais.

1. Arraste uma grade de dados simples na guia **Layout** para a grade de design e deixe-a do tamanho desejado.

2. Obter [dados do Excel ou de um conjunto de dados compartilhado](../../reporting-services/mobile-reports/data-for-reporting-services-mobile-reports.md).

3. Selecione a guia **Dados** e, no painel **Propriedades de dados** , em **Dados para a exibição de grade** , selecione uma tabela de dados.

4. No painel **Colunas** , selecione as colunas desejadas. Reordene-as, renomeie-as e defina seu formato e agregação. 

 
##  <a name="indicator-data-grid"></a>Grade de dados de indicador
Você pode adicionar colunas com indicadores para uma grade de dados do indicador.

![mobile-report-indicator-data-grid](../../reporting-services/mobile-reports/media/mobile-report-indicator-data-grid.png)

1. Arraste uma grade de dados de indicador na guia **Layout** para a grade de design e deixe-a do tamanho desejado.

2. Na guia **Dados** , no painel **Colunas** , selecione **Adicionar coluna do medidor**. 

3. Selecione **Opções**e **Tipo de medidor**. 

4. Defina os campos **Valor** , **Comparação** e **Direção de valor**, bem como em [medidores adicionados diretamente ao relatório móvel](../../reporting-services/mobile-reports/add-gauges-to-mobile-reports-reporting-services.md).

A grade de dados alimenta automaticamente o medidor apenas com os dados específicos a essa linha da grade de dados.  

## <a name="chart-data-grid"></a>Grade de dados do gráfico
Você pode adicionar colunas com medidores ou gráficos para uma grade de dados de gráfico. 

![mobile-report-chart-data-grid](../../reporting-services/mobile-reports/media/mobile-report-chart-data-grid.png)

Quando você adiciona uma coluna de gráfico a uma grade de dados, você precisa adicionar uma tabela de dados separada para fornecer dados para o gráfico em cada linha. Essa segunda tabela de dados precisa compartilhar um campo com a tabela de dados principal para vincular cada linha aos seus dados de gráfico associados. 

1. Arraste uma grade de dados de gráfico da guia **Layout** para a grade de design e deixe-a do tamanho desejado.

2. Na guia **Dados** , no painel **Colunas** , selecione **Adicionar coluna do gráfico**. 

3. Obtenha [dados do Excel ou de um conjunto de dados compartilhado](../../reporting-services/mobile-reports/data-for-reporting-services-mobile-reports.md) para adicionar uma segunda tabela de dados que compartilha um campo com a tabela de dados principal, se ainda não tiver feito isso.

4. Em **Propriedades de dados**, selecione a tabela de dados principal em **Dados para exibição de grade**e escolha a segunda tabela em **Dados de referência para visualizações de gráfico**.

5. Selecione **Opções**e **Tipo de gráfico**.
 
6. Selecione o **Campo de dados de gráfico**, **Pesquisa de origem**e **Pesquisa de destino**. 
   Essas três propriedades determinam como a grade de dados fornece dados para cada gráfico na coluna.
   
   *   **Pesquisa de origem** é definida como um campo na tabela de dados em **Dados para exibição de grade**. Este campo age como um filtro por linha que será aplicado à tabela de dados de referência do gráfico para fornecer dados para o gráfico inserido de cada linha. 
   * **Pesquisa de destino** é o campo na tabela de dados **Dados de referência para visualizações de gráfico**. Os dados do gráfico em cada linha serão unido nesses dois campos.   
   * O**Campo de dados do gráfico** determina qual métrica na tabela de dados **Dados de referência para visualizações do gráfico** será usada como o valor do eixo y ou série no gráfico em cada linha.  

## <a name="see-also"></a>Consulte também 
* [Mapas nos relatórios móveis do Reporting Services](../../reporting-services/mobile-reports/maps-in-reporting-services-mobile-reports.md)
* [Navegadores nos relatórios móveis do Reporting Services](../../reporting-services/mobile-reports/add-navigators-to-reporting-services-mobile-reports.md)
* [Visualizações nos relatórios móveis do Reporting Services](../../reporting-services/mobile-reports/add-visualizations-to-reporting-services-mobile-reports.md)
* [Medidores nos relatórios móveis do Reporting Services](../../reporting-services/mobile-reports/add-gauges-to-mobile-reports-reporting-services.md)  
 
  
