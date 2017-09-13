---
title: "Construtor de expressões | Microsoft Docs"
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- integration-services
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sql13.dts.designer.expressionbuilder.f1
helpviewer_keywords:
- Expression Builder dialog box
ms.assetid: 4717ce33-bd4e-44bc-81e0-002de075b4d1
caps.latest.revision: 18
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 820179477a33b18a634c509d2793d8f0bac79ddd
ms.contentlocale: pt-br
ms.lasthandoff: 08/03/2017

---
# <a name="expression-builder"></a>Construtor de Expressões
  Use a caixa de diálogo **Construtor de Expressões** para criar e editar uma expressão de propriedade ou para gravar a expressão que define o valor de uma variável usando uma interface gráfica do usuário que lista as variáveis e oferece uma referência interna às funções, às conversões de tipo e aos operadores que a linguagem de expressão [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] inclui.  
  
 Uma expressão de propriedades é uma expressão que é atribuída a uma propriedade. Quando a expressão é avaliada, a propriedade é atualizada de forma dinâmica para usar o resultado da avaliação da expressão. Do mesmo modo, uma expressão usada em uma variável permite que o valor da mesma seja atualizado com o resultado da avaliação da expressão.  
  
 Há vários modos em que usar as expressões:  
  
-   **Tarefas** Atualize a linha Para que uma tarefa Enviar Mensagem usa inserindo um endereço de email armazenado em uma variável ou atualize a linha do Assunto concatenando uma cadeia de caracteres como “Vendas para:” e a data atual retornada pela função GETDATE.  
  
-   **Variáveis** Defina o valor de uma variável para o mês atual usando uma expressão como `DATEPART("mm",GETDATE())`; ou defina o valor de uma cadeia de caracteres concatenando esta cadeia literal e a data atual usando a expressão `"Today's date is " + (DT_WSTR,30)(GETDATE())`.  
  
-   **Gerenciadores de Conexões** Defina a página do código de um gerenciador de conexões de Arquivo Simples usando uma variável que contém um identificador de página de código diferente ou especifique o número de linhas no arquivo de dados a serem ignoradas, digitando um inteiro positivo como 3 na expressão.  
  
 Para saber mais sobre expressões de propriedade e como escrever expressões, consulte [Usar expressões de propriedade em pacotes](../../integration-services/expressions/use-property-expressions-in-packages.md) e [Expressões do Integration Services &#40;SSIS&#41;](../../integration-services/expressions/integration-services-ssis-expressions.md).  
  
## <a name="options"></a>Opções  
  
|Termo|Definição|  
|----------|----------------|  
|**Variáveis**|Expanda a pasta de **Variáveis** e arraste as mesmas para a caixa **Expressão** .|  
|**Funções Matemáticas**<br /><br /> **Funções de cadeia de caracteres**<br /><br /> **Funções Data/Hora**<br /><br /> **Funções NULL**<br /><br /> **Conversões de Tipos**<br /><br /> **Operadores**|Expanda as pastas e arraste as funções, conversões de tipos e operadores para a caixa **Expressão** .|  
|**Expressão**|Edite ou digite uma expressão.'|  
|**Valor avaliado**|Lista o resultado da avaliação da expressão.|  
|**Avaliar Expressão**|Clique em **Avaliar Expressão** para exibir o resultado de avaliação da expressão.|  
  
## <a name="see-also"></a>Consulte também  
 [Página expressões](../../integration-services/expressions/expressions-page.md)   
 [Editor de expressões de propriedade](../../integration-services/expressions/property-expressions-editor.md)   
 [Integration Services &#40; SSIS &#41; Variáveis](../../integration-services/integration-services-ssis-variables.md)   
 [Variáveis do sistema](../../integration-services/system-variables.md)  
  
  