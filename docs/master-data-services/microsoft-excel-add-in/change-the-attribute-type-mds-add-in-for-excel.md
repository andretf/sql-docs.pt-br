---
title: Alterar o tipo de atributo (suplemento MDS para Excel) | Microsoft Docs
ms.custom: 
ms.date: 03/15/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- master-data-services
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9d3001d9-8d0f-4e4a-8e04-4f666bf0df69
caps.latest.revision: 8
author: sabotta
ms.author: carlasab
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 21847b911f58646a4a6afd7238d8852b70ca3f51
ms.contentlocale: pt-br
ms.lasthandoff: 08/02/2017

---
# <a name="change-the-attribute-type-mds-add-in-for-excel"></a>Alterar o tipo de atributo (suplemento MDS para Excel)
  No [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], os administradores podem alterar o tipo de atributo quando o tipo de dados ou número de caracteres permitido está incorreto.  
  
 Se você quiser alterar o tipo de atributo para criar uma lista restrita (atributo baseado em domínio), consulte [Criar um atributo baseado em domínio &#40;Suplemento MDS para Excel&#41;](../../master-data-services/microsoft-excel-add-in/create-a-domain-based-attribute-mds-add-in-for-excel.md).  
  
> [!NOTE]  
>  Não é possível atualizar o tipo ou o tamanho da coluna **Nome** ou **Código**.  
  
## <a name="prerequisites"></a>Pré-requisitos  
 Para executar esse procedimento:  
  
-   Você precisa ter permissão para acessar as áreas funcionais **Administração do Sistema** e **Gerenciador** .  
  
-   Você deve ser um administrador de modelo. Para obter mais informações, veja [Administradores &#40;Master Data Services&#41;](../../master-data-services/administrators-master-data-services.md).  
  
-   Deve haver um modelo, entidade e atributo existente.  
  
### <a name="to-change-the-attribute-type"></a>Para alterar o tipo de atributo  
  
1.  No Excel, carregue a entidade que contém a coluna (atributo) a ser alterada. Para obter mais informações, consulte [Exportar dados para o Excel do Master Data Services](../../master-data-services/microsoft-excel-add-in/export-data-to-excel-from-master-data-services.md).  
  
2.  Clique em qualquer célula da coluna que você deseja alterar.  
  
3.  No grupo **Compilar Modelo** , clique em **Propriedades do Atributo**.  
  
4.  Na caixa de diálogo **Propriedades do Atributo** , é necessário atualizar as configurações.  
  
5.  Clique em **OK**.  
  
## <a name="what-happens-when-you-change-the-attribute-type"></a>O que acontece quando você altera o tipo de atributo?  
 Se houver qualquer dependência no atributo, por exemplo, o atributo ser referenciado por qualquer regra de negócio do MDS ou hierarquia derivada, não será possível alterar o tipo de dados do atributo. Você obterá um erro informando que o tipo de atributo não pode ser modificado, pois é referenciado por um objeto.  
  
 Se houver algum erro durante a conversão do tipo de dados para os valores do atributo, o MDS fará o seguinte.  
  
-   Altera o tipo de dados do atributo.  
  
-   Gera uma cópia do atributo com o sufixo “_old” que contém os valores anteriores. Isso é chamado de atributo preterido.  
  
## <a name="see-also"></a>Consulte também  
 [Atributos &#40;Master Data Services&#41;](../../master-data-services/attributes-master-data-services.md)   
 [Criar um modelo &#40;Suplemento MDS para Excel&#41;](../../master-data-services/microsoft-excel-add-in/building-a-model-mds-add-in-for-excel.md)  
  
  