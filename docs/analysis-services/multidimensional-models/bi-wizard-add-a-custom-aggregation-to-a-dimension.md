---
title: "Adicionar uma agregação personalizada a uma dimensão | Microsoft Docs"
ms.custom: 
ms.date: 03/01/2017
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
- dimensions [Analysis Services], Business Intelligence enhancements
- Business Intelligence enhancements [Analysis Services], custom aggregations
- aggregations [Analysis Services], custom
- unary operators
- custom aggregations [Analysis Services]
ms.assetid: 3199a6c2-a06d-47b9-bd1c-604dbb085318
caps.latest.revision: 
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 9188ba67de899aa9bb63f1593da9e67c140a4cc2
ms.sourcegitcommit: 7519508d97f095afe3c1cd85cf09a13c9eed345f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2018
---
# <a name="bi-wizard---add-a-custom-aggregation-to-a-dimension"></a>Assistente de BI - adicionar uma agregação personalizada a uma dimensão
[!INCLUDE[ssas-appliesto-sqlas](../../includes/ssas-appliesto-sqlas.md)]
Adicione um aprimoramento de agregação personalizada a um cubo ou dimensão para substituir as agregações padrão associadas a um membro da dimensão por outro operador unário. Esse aprimoramento especifica uma coluna de operador unário na tabela de dimensões que define o acúmulo de membros em uma hierarquia pai-filho. O operador unário age no atributo pai em uma hierarquia pai-filho.  
  
> [!NOTE]  
>  Uma agregação personalizada estará disponível somente para dimensões baseadas em fontes de dados existentes. Para dimensões que foram criadas sem usar uma fonte de dados, execute o Assistente de Geração de Esquema para criar uma exibição da fonte de dados antes de adicionar a agregação personalizada.  
  
 Para adicionar uma agregação personalizada, use o Assistente de Business Intelligence e selecione a opção **Especificar um operador unário** na página **Escolher Aprimoramento** . Esse assistente orientará você durante as etapas para selecionar a dimensão à qual você deseja aplicar uma agregação personalizada e para identificar a agregação personalizada.  
  
> [!NOTE]  
>  Antes de executar o Assistente de Business Intelligence para adicionar uma agregação personalizada, confirme se a dimensão que você deseja aprimorar contém uma hierarquia de atributo pai-filho. Para obter mais informações, consulte [Dimensões pai-filho](../../analysis-services/multidimensional-models/parent-child-dimension.md).  
  
## <a name="selecting-a-dimension"></a>Selecionando uma dimensão  
 Na primeira página **Especificar um Operador Unário** do assistente, especifique a dimensão à qual você deseja aplicar uma agregação personalizada. A agregação personalizada adicionada à dimensão selecionada fará alterações na dimensão. Essas alterações serão herdadas por todos os cubos que tiverem a dimensão selecionada.  
  
## <a name="adding-custom-aggregation-unary-operator"></a>Adicionando agregação personalizada (operador unário)  
 Na segunda página **Especificar um Operador Unário** do assistente, especifique o atributo pai desejado para a agregação personalizada e a coluna de origem da tabela de dimensões para o operador unário. O**Atributo pai** lista atributos cuja propriedade **Usage** foi configurada como **Parent**. Se houver mais de um atributo pai, escolha o atributo pai que corresponde à relação pai-filho que você deseja usar. Se não houver um atributo pai listado, a dimensão não possui uma hierarquia pai-filho válida.  
  
 Em **Coluna de origem**, selecione a coluna de cadeia de caracteres que contém os operadores unários. (Essa seleção configura a propriedade **UnaryOperatorColumn** do atributo pai.) A tabela de dimensões também deve ter uma coluna de cadeia de caracteres que especifica o operador de acúmulo unário. Os valores da cadeia de caracteres dessa coluna devem conter operadores de agregação válidos. Se houver uma linha vazia, o membro correspondente será calculado normalmente. Se a fórmula de uma coluna não for válida, ocorrerá um erro de tempo de execução quando o valor de uma célula que usa o membro for recuperado. Para obter mais informações, consulte [Operadores unários nas dimensões pai-filho](../../analysis-services/multidimensional-models/parent-child-dimension-attributes-unary-operators.md).  
  
  
