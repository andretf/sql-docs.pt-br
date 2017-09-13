---
title: "Dividir um conjunto de dados usando a transformação divisão condicional | Microsoft Docs"
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
- Conditional Split transformation
- splitting dataset
- datasets [Integration Services], splitting
ms.assetid: 23b3e84f-9296-4dc9-81c0-c7f06ae3f1ff
caps.latest.revision: 40
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: c3e47e4a5ae297202ba43679fba393421880a7ea
ms.openlocfilehash: 8248e068541c6bd72b21f78d121811f4851850bb
ms.contentlocale: pt-br
ms.lasthandoff: 08/03/2017

---
# <a name="split-a-dataset-by-using-the-conditional-split-transformation"></a>Dividir um conjunto de dados por meio da transformação Divisão Condicional
  Para adicionar e configurar uma transformação Divisão Condicional, o pacote já deve incluir pelo menos uma tarefa de Fluxo de Dados e uma origem.  
  
### <a name="to-conditionally-split-a-dataset"></a>Para dividir um conjunto de dados condicionalmente  
  
1.  No [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], abra o projeto do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] que contém o pacote desejado.  
  
2.  No Gerenciador de Soluções, clique duas vezes no pacote para abri-lo.  
  
3.  Clique na guia **Fluxo de Dados** e, na **Caixa de Ferramentas**, arraste a transformação de Divisão Condicional para a superfície de design.  
  
4.  Conecte a transformação de Divisão Condicional ao fluxo de dados arrastando o m conector da fonte de dados ou da transformação anterior para a transformação de Divisão Condicional.  
  
5.  Clique duas vezes na transformação de Divisão Condicional.  
  
6.  No **Editor da Transformação de Divisão Condicional**, construa as expressões para usar como condições arrastando variáveis, colunas, funções e operadores para a coluna **Condição** na grade. Ou, é possível digitar a expressão na coluna **Condição** .  
  
    > [!NOTE]  
    >  Uma variável ou coluna pode ser usada em diversas expressões.  
  
    > [!NOTE]  
    >  Se a expressão não for válida, o texto da expressão será realçado e uma Dica de Ferramenta na coluna descreverá os erros.  
  
7.  Como opção, modifique os valores na coluna **Nome da Saída** . Os nomes padrão são Maiúscula 1, Maiúscula 2 e assim por diante.  
  
8.  Para modificar a sequência na qual as condições são avaliadas, clique na seta para cima ou na seta para abaixo.  
  
    > [!NOTE]  
    >  Coloque as condições que são mais prováveis de serem encontradas no topo da lista.  
  
9. Como opção, modifique o nome da saída padrão para obter linhas de dados que não correspondem com nenhuma condição.  
  
10. Para configurar uma saída de erro, clique em **Configurar Saída de Erro**. Para obter mais informações, consulte [Debugging Data Flow](../../../integration-services/troubleshooting/debugging-data-flow.md).  
  
11. Clique em **OK**.  
  
12. Para salvar o pacote atualizado, clique em **Salvar Itens Selecionados** no menu **Arquivo** .  
  
## <a name="see-also"></a>Consulte também  
 [Transformação de divisão condicional](../../../integration-services/data-flow/transformations/conditional-split-transformation.md)   
 [Transformações do Integration Services](../../../integration-services/data-flow/transformations/integration-services-transformations.md)   
 [Caminhos do Integration Services](../../../integration-services/data-flow/integration-services-paths.md)   
 [Tipos de dados do Integration Services](../../../integration-services/data-flow/integration-services-data-types.md)   
 [Tarefa de fluxo de dados](../../../integration-services/control-flow/data-flow-task.md)   
 [Integration Services &#40; SSIS &#41; Expressões](../../../integration-services/expressions/integration-services-ssis-expressions.md)  
  
  