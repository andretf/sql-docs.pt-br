---
title: "Lição 1: Preparando para criar o pacote de implantação | Microsoft Docs"
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- integration-services
ms.tgt_pltfrm: 
ms.topic: article
applies_to:
- SQL Server 2016
ms.assetid: b6fe283c-9856-4ba1-a497-e3912424fd18
caps.latest.revision: 21
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 0850bf9b55f3960736d45b1730f25f6c96c667a9
ms.contentlocale: pt-br
ms.lasthandoff: 08/03/2017

---
# <a name="lesson-1-preparing-to-create-the-deployment-bundle"></a>Lição 1: Preparando-se para criar o pacote de implantação
Nesta lição, você criará as pastas de trabalho e as variáveis de ambiente que oferecem suporte ao tutorial, criará um projeto [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , adicionará vários pacotes e seus arquivos de suporte ao projeto e implementará configurações em pacotes.  
  
O [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] implanta pacotes em uma base de projeto; portanto, como primeira etapa na criação do pacote de implantação, você deve coletar todos os pacotes e dependências de pacotes em um projeto [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]. Normalmente é útil incluir outras informações com os pacotes implantados: por exemplo, você também adicionará ao projeto um arquivo Leiame, que fornece a documentação básica para esse grupo de pacotes.  
  
Depois que você adicionar os pacotes e os arquivos, adicionará configurações aos pacotes que ainda não usam as configurações. As configurações atualizam as propriedades dos pacotes e os objetos do pacote em tempo de execução. Em uma lição posterior, você modificará os valores dessas configurações durante a implantação de pacotes para oferecer suporte aos pacotes no ambiente implantado.  
  
Depois que você adicionar as configurações, deverá abrir os pacotes no Designer [!INCLUDE[ssIS](../includes/ssis-md.md)] , a ferramenta gráfica do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] para compilação de pacotes ETL, e examinar as propriedades e os elementos do pacote, assim como as configurações de pacote, para entender melhor os problemas que a implantação precisa resolver. Por exemplo, um dos pacotes extrai dados de arquivos de texto, portanto, o local dos arquivos de dados deve ser atualizado antes dos pacotes serem implantados com êxito.  
  
**Tempo estimado para concluir esta lição:** 1 hora  
  
## <a name="lesson-tasks"></a>Tarefas da lição  
Esta lição contém as seguintes tarefas:  
  
-   [Etapa 1: Criando pastas de trabalho e variáveis de ambiente](../integration-services/lesson-1-1-creating-working-folders-and-environment-variables.md)  
  
-   [Etapa 2: Criando o projeto de implantação](../integration-services/lesson-1-2-creating-the-deployment-project.md)  
  
-   [Etapa 3: Adicionando pacotes e outros arquivos](../integration-services/lesson-1-3-adding-packages-and-other-files.md)  
  
-   [Etapa 4: Adicionando configurações de pacote](../integration-services/lesson-1-4-adding-package-configurations.md)  
  
-   [Etapa 5: Testando os pacotes atualizados](../integration-services/lesson-1-5-testing-the-updated-packages.md)  
  
## <a name="start-the-lesson"></a>Iniciar a lição  
[Etapa 1: Criando pastas de trabalho e variáveis de ambiente](../integration-services/lesson-1-1-creating-working-folders-and-environment-variables.md)  
  
  
  
