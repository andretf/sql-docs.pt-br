---
title: Conectar componentes em um fluxo de dados | Microsoft Docs
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- integration-services
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- components [Integration Services], connections
- connections [Integration Services], data flow components
ms.assetid: 70616a58-8921-4218-85bf-f3e90c5a9dbf
caps.latest.revision: 41
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: c3e47e4a5ae297202ba43679fba393421880a7ea
ms.openlocfilehash: 73a379b190f05f4eedc361b4557afefd700a9664
ms.contentlocale: pt-br
ms.lasthandoff: 08/03/2017

---
# <a name="connect-components-in-a-data-flow"></a>Conectar componentes em um fluxo de dados
  Este procedimento descreve como conectar a saída dos componentes em um fluxo de dados para outros componentes dentro do mesmo fluxo de dados.  
Você constrói o fluxo de dados em um pacote na superfície de design da guia **Fluxo de Dados** no Designer [!INCLUDE[ssIS](../../includes/ssis-md.md)] . Se o fluxo de dados contiver dois componentes de fluxo de dados, você poderá conectá-los vinculando a saída de uma fonte ou transformação à entrada de uma transformação ou destino. O conector entre dois componentes de fluxo de dados é chamado de caminho.  
  
 O diagrama a seguir mostra um simples fluxo de dados com um componente de fonte, duas transformações, um componente de destino e os caminhos que os conecta.  
  
 ![Data flow](../../integration-services/data-flow/media/mw-dts-08.gif "Data flow")  
  
 Depois de dois componentes terem sido conectados, você pode visualizar os metadados dos dados que se movimentam através do caminho e as propriedades do caminho em **Editor de Caminho de Fluxo de Dados**. Para obter mais informações, consulte [Integration Services Paths](../../integration-services/data-flow/integration-services-paths.md).  
  
 Você também pode adicionar os visualizadores de dados aos caminhos. Um visualizador de dados torna possível visualizar os dados que se movem entre os componentes de fluxo de dados quando o pacote é executado.  
  
### <a name="connect-components-in-a-data-flow"></a>Conectar componentes em um fluxo de dados  
  
1.  No [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contém o pacote desejado.  
  
2.  No Gerenciador de Soluções, clique duas vezes no pacote para abri-lo.  
  
3.  Clique na guia **Fluxo de Controle** e clique duas vezes na tarefa Fluxo de Dados que contém o fluxo de dados no qual você deseja conectar componentes.  
  
4.  Na superfície de design da guia **Fluxo de Dados** , selecione a transformação ou fonte que você quer conectar.  
  
5.  Arraste a seta de saída verde de uma transformação ou uma fonte para uma transformação ou para um destino. Alguns componentes de fluxo de dados têm saídas de erro, que você pode conectar da mesma maneira.  
  
    > [!NOTE]  
    >  Alguns componentes de fluxo de dados podem ter múltiplas saídas, sendo possível conectar cada saída para uma transformação ou destino diferentes.  
  
6.  Para salvar o pacote atualizado, clique em **Salvar Itens Selecionados** no menu **Arquivo** .  
  
## <a name="see-also"></a>Consulte também  
 [Adicionar ou excluir um componente de fluxo de dados](../../integration-services/data-flow/add-or-delete-a-component-in-a-data-flow.md)   
 [Depurando o fluxo de dados](../../integration-services/troubleshooting/debugging-data-flow.md) [fluxo de dados](../../integration-services/data-flow/data-flow.md)  
  
  