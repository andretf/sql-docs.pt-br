---
title: "Gerenciador de Conexões do Azure Resource Manager | Microsoft Docs"
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-non-specified
ms.prod_service: integration-services
ms.service: 
ms.component: connection-manager
ms.reviewer: 
ms.suite: sql
ms.technology:
- integration-services
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SQL13.DTS.DESIGNER.AFPARMCM.F1
- SQL14.DTS.DESIGNER.AFPARMCM.F1
ms.assetid: 8ce8024f-153f-4066-b607-0d36fefc79ed
caps.latest.revision: 
author: Lingxi-Li
ms.author: lingxl
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: b00b3556469d9f35e4edd7365b214a0b17b79e61
ms.sourcegitcommit: 9e6a029456f4a8daddb396bc45d7874a43a47b45
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/25/2018
---
# <a name="azure-resource-manager-connection-manager"></a>Gerenciador de Conexões do Azure Resource Manager
O **Gerenciador de Conexões do Azure Resource Manager** permite que um pacote do SSIS gerencie recursos do Azure usando uma [entidade de serviço](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-create-service-principal-portal).

O **Gerenciador de Conexões do Azure Resource Manager** é um componente do [Feature Pack do SSIS (SQL Server Integration Services) para Azure](../../integration-services/azure-feature-pack-for-integration-services-ssis.md).

Para criar e configurar um **gerenciador de conexões do Azure Resource Manager**, siga as etapas abaixo:

1. Na caixa de diálogo **Adicionar gerenciador de conexões do SSIS**, selecione **AzureResourceManager** e clique em **Adicionar**.
2. Na caixa de diálogo **Editor do gerenciador de conexões do Azure Resource Manager**, especifique a **ID do Aplicativo**, a **Chave do Aplicativo** e a **ID do Locatário** da entidade de serviço. Para obter detalhes sobre essas propriedades, consulte [este](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-create-service-principal-portal) artigo.
3. Clique em **OK** para fechar a caixa de diálogo.
4. Você pode ver as propriedades do gerenciador de conexões criado na janela **Propriedades** .
