---
title: "Exemplos de regras de negócios (Master Data Services) | Microsoft Docs"
ms.custom: 
ms.date: 01/05/2017
ms.prod: sql-non-specified
ms.prod_service: mds
ms.service: 
ms.component: non-specific
ms.reviewer: 
ms.suite: sql
ms.technology:
- master-data-services
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3974b9be-4b7c-4a37-ab26-1a36ef455744
caps.latest.revision: 
author: leolimsft
ms.author: lle
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: e01b4c5141011209f5fdf314711e9cc26595c5f5
ms.sourcegitcommit: 6ac1956307d8255dc544e1063922493b30907b80
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/05/2018
---
# <a name="business-rule-examples-master-data-services"></a>Ações de regras de negócio (Master Data Services)
Este artigo mostra exemplos de regras de negócio do [!INCLUDE[ssMDSshort_md](../includes/ssmdsshort-md.md)]. Você encontrará esses exemplos nos modelos de exemplo incluídos na instalação do [!INCLUDE[ssMDSshort_md](../includes/ssmdsshort-md.md)].   
  
Para obter instruções sobre como implantar os modelos de exemplo, consulte [Instalação e configuração do Master Data Services](../master-data-services/master-data-services-installation-and-configuration.md).  
  
  
## <a name="business-rule-examples"></a>Exemplos de regras de negócio  
Modelo de exemplo |Entidade  |Nome da regra de negócio| Description  
---------|---------|---------|-----------|  
Cliente    | Cliente   | Termos de pgto. de pessoa| Especifica as condições de pagamento padrão para clientes.          
Na regra de negócio a seguir, se o valor do atributo CustomerType atender à `is equal` [rule condition](../master-data-services/business-rule-conditions-master-data-services.md), then the `defaults to` [rule action](../master-data-services/business-rule-conditions-master-data-services.md) is applied to the PaymentTerms attribute. Caso contrário, nenhuma ação será tomada.  
```  
If  
    CustomerType is equal to 2  
Then  
    PaymentTerms defaults to CASH  
Else  
    None      
```  
  
**--------------------------------------------------**  
  
Modelo de exemplo  |Entidade  |Nome da regra de negócio|Description    
---------|---------|---------|---------------  
Cliente     | Cliente    | Termos de pgto. da org. | Especifica as condições de pagamento padrão para organizações.         
Na regra de negócio a seguir, se o valor do atributo CustomerType atender à `is equal` [rule condition](../master-data-services/business-rule-conditions-master-data-services.md), then the `defaults to` [rule action](../master-data-services/business-rule-actions-master-data-services.md) is applied to the PaymentTerms attribute. Caso contrário, nenhuma ação será tomada.  
```  
If  
    CustomerType is equal to 1  
Then  
    PaymentTerms defaults to 210Net30  
Else  
    None  
```  
  
**--------------------------------------------------**  
  
  
Modelo de exemplo  |Entidade  |Nome da regra de negócio| Description    
---------|---------|---------|-----------  
Product     |  Product       | DaysToManufacture |Especifica o intervalo de dias até a fabricação interna.          
Na regra de negócio a seguir, se o valor do atributo InHouseManufacture atender à `is equal` [rule condition](../master-data-services/business-rule-conditions-master-data-services.md), then the `must be between` [rule action](../master-data-services/business-rule-actions-master-data-services.md) is applied to the DaysToManufacture attribute. Caso contrário, nenhuma ação será tomada.  
```  
If  
    InHouseManufacture is equal to Y  
Then  
    DaysToManufacture must be between 1 and 10  
Else  
    None  
```  
  
**--------------------------------------------------**  
  
  
Modelo de exemplo  |Entidade  |Nome da regra de negócio|Description    
---------|---------|---------|-------------  
Product     |Product         |Campos obrigatórios| Especifica os atributos necessários para os membros da entidade de produto.           
Na regra de negócio a seguir, em todas as condições, a `is required` [validation action](../master-data-services/business-rule-actions-master-data-services.md) is taken for the specified attributes. Os valores de atributo não podem ser Nulo nem vazio.  
```  
If  
    None  
Then  
    Name is required  
    ProductSubCategory is required  
    Color is required  
    StandardCost is required  
    SafetyStockLevel is required  
    ReorderPoint is required  
    InHouseManufacture is required  
    SellStartDate is required  
    FinishedGoodIndicator is required  
    ProductLine is required  
Else  
    None  
```  
  
**--------------------------------------------------**  
  
  
Modelo de exemplo  |Entidade  |Nome da regra de negócio|Description    
---------|---------|---------|-----------  
Product     | Product        |  Custo padrão| Exige que o custo padrão seja maior que 0.        
Na regra de negócio a seguir, em todas as condições, a `must be greater than` [rule action](../master-data-services/business-rule-actions-master-data-services.md) is applied to the StandardCost attribute of products.  
```  
If  
    None  
Then  
    StandardCost must be greater than 0  
Else  
    None  
```  
  
**--------------------------------------------------**  
  
  
Modelo de exemplo  |Entidade  |Nome da regra de negócio|Description    
---------|---------|---------|------------  
Product     | Product        | FG MSRP Custo|Especifica que, se o produto for uma mercadoria concluída, o MSRP (preço de varejo sugerido pelo fabricante) e os custos do revendedor deverão ser maiores que 0.           
  
Na regra de negócio a seguir, se o valor do atributo FinishedGoodIndicator atender à `is equal` [rule condition](../master-data-services/business-rule-conditions-master-data-services.md), the `must be greater than` [rule action](../master-data-services/business-rule-actions-master-data-services.md) is applied to the MSRP and DealerCost attributes.  
```  
If  
    FinishedGoodIndicator is equal to Y  
Then  
    MSRP must be greater than 0  
    DealerCost must be greater than 0  
Else  
    None  
```  
  
**--------------------------------------------------**  
  
  
Modelo de exemplo  |Entidade  |Nome da regra de negócio|Description    
---------|---------|---------|------------  
Product     | Product        |  Nome padrão| Especifica o nome do produto padrão com base nos valores dos atributos Color e Class. Quando o valor do atributo Color não for YLO e o atributo Class não for NA, o nome padrão será Yellow NA.         
Na regra de negócio a seguir, se os atributos Color e Class não atenderem à condição de regra `is equal` , a `defaults to` [rule action](../master-data-services/business-rule-actions-master-data-services.md) is applied to the Name attribute.  
```  
If  
    (Color is equal to YLO AND Class is equal to NA) is not true  
Then  
    Name defaults to Yellow NA  
Else  
    Name defaults to Other  
```  
  
**--------------------------------------------------**  
  
  
**Para exibir exemplos de regras de negócio nos modelos de exemplo**  
1. Navegue até o site do [!INCLUDE[ssMDSshort_md](../includes/ssmdsshort-md.md)] que você configurou depois de instalar o MDS e clique na caixa **Administração do Sistema** .   
Para obter instruções sobre a configuração do site, consulte [Instalação e configuração do Master Data Services](../master-data-services/master-data-services-installation-and-configuration.md).  
2. Clique no modelo de exemplo que contém a regra de negócio, conforme listado nas tabelas acima, e clique em **Entidades**.  
3. Clique na entidade à qual a regra se aplica, conforme listado nas tabelas acima, e clique em **Regras de Negócio**.  
4. Clique no nome da regra de negócio que você deseja exibir. A interface do usuário se expande para mostrar as instruções **If**, **Then** e **Else** .  
  
## <a name="did-this-article-help-you-were-listening"></a>Este artigo foi útil para você? Estamos atentos   
Quais são as informações que você está procurando? Você as localizou? Estamos atentos aos seus comentários para aprimorar o conteúdo. Envie seus comentários para [sqlfeedback@microsoft.com](mailto:sqlfeedback@microsoft.com).   
  
  
  
  

