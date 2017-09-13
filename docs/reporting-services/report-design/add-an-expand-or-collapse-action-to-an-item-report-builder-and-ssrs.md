---
title: "Adicionar um expandir ou recolher ação a um Item (construtor de relatórios e SSRS) | Microsoft Docs"
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- reporting-services-sharepoint
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 49f07ad6-242b-4861-8fc1-91ca78c36d6c
caps.latest.revision: 12
author: maggiesMSFT
ms.author: maggies
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: dcd1af4aee2c0267f1443d87d80be1e3cc2ad8b3
ms.contentlocale: pt-br
ms.lasthandoff: 08/09/2017

---
# <a name="add-an-expand-or-collapse-action-to-an-item-report-builder-and-ssrs"></a>Adicionar uma ação de expandir ou recolher a um item (Construtor de Relatórios e SSRS)
  Você pode permitir que um usuário expanda ou recolha interativamente itens de relatório ou expanda ou recolha linhas e colunas associadas a um grupo para uma tabela ou matriz. Para permitir que os usuários expandam ou recolham um item, defina as propriedades de visibilidade do item. A definição de trabalhos de visibilidade em um visualizador de relatórios HTML às vezes é chamada de uma ação de *detalhamento* .  
  
 Na exibição de design de relatório, você especifica o nome da caixa de texto no relatório onde deseja exibir os ícones de alternância para expandir e recolher. No relatório renderizado, a caixa de texto exibe um sinal de mais (+) ou de menos (-) além de seu conteúdo. Quando o usuário clica na alternância, a exibição do relatório é atualizada para mostrar ou ocultar o item de relatório nas configurações de visibilidade atuais dos itens do relatório.  
  
 Em geral, as ações de expansão e recolhimento são usadas inicialmente para exibir apenas os dados de resumo e permitir que o usuário clique no sinal de adição para mostrar os dados detalhados. Por exemplo, é possível ocultar inicialmente uma tabela que exibe valores de um gráfico ou grupos filho de uma tabela com grupos de linhas e de colunas aninhados, como em um relatório detalhado.  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-expand-and-collapse-action-to-a-group"></a>Para adicionar uma ação de expansão e recolhimento a um grupo  
  
1.  Na exibição de design de relatório, clique na tabela ou na matriz para selecioná-la. O painel Agrupamento exibe os grupos de linhas e colunas.  
  
     ![Painel de agrupamento](../../reporting-services/report-design/media/groupingpane.png "painel de agrupamento")  
  
     Se o painel Agrupamento não aparecer, clique no menu **Exibir** e clique em **Agrupamento**.  
  
2.  Clique com o botão direito do mouse em qualquer lugar na barra de título do painel Agrupamento e clique em **Avançado**. O modo do painel Agrupamento é alternado para mostrar a estrutura de exibição subjacente de linhas e colunas na superfície de design.  
  
     ![Painel de agrupamento ao menu Modo avançado](../../reporting-services/report-design/media/groupingpane-advancedmode.png "painel de agrupamento ao menu Modo Avançado")  
  
3.  No painel de grupo apropriado, clique no nome do grupo de linhas ou de colunas do qual você deseja ocultar as linhas ou colunas associadas. O grupo é selecionado e o painel Propriedades mostra as propriedades do **Membro do Tablix** .  
  
    > [!NOTE]  
    >  Se o painel Propriedades não for exibido, clique em **Exibir** na Faixa de opções e clique em **Propriedades**.  
  
4.  Em **Oculto**, escolha uma das opções a seguir para definir a visibilidade desse item de relatório na primeira vez em que o relatório for executado:  
  
    -   Selecione **False** para exibir o item de relatório.  
  
    -   Selecione **True** para ocultar o item de relatório.  
  
    -   Selecione  **\<expressão >** para abrir o **expressão** caixa de diálogo para criar uma expressão que é avaliada em tempo de execução para determinar a visibilidade.  
  
5.  Em **ToggleItem**, na caixa suspensa, selecione o nome de uma caixa de texto à qual adicionar a imagem de alternância.  
  
     Na imagem a seguir, o grupo de linhas Cor está configurado para permitir que os usuários expandam e recolham linhas associadas.  
  
     ![Configurando um grupo de linhas a ser expandido](../../reporting-services/report-design/media/expandcollapse-confighiddentoggleitemwithnumbers.png "Configurando um grupo de linhas a ser expandido")  
  
    > [!NOTE]  
    >  A caixa de texto com a imagem de alternância não pode ser o grupo de linhas ou de colunas do qual você deseja ocultar as linhas ou colunas associadas. Ela deve estar no mesmo grupo que o item que está sendo ocultado ou em um grupo ancestral. Por exemplo, para alternar a visibilidade de linhas associadas a um grupo filho, selecione uma caixa de texto em uma linha associada ao grupo pai.  
  
6.  Para testar a alternância, execute o relatório e clique na caixa de texto com a imagem de alternância. A exibição do relatório é atualizada para mostrar grupos de linhas e de colunas com a visibilidade alternada.  
  
     ![Executando relatório com grupo de linhas expansível](../../reporting-services/report-design/media/expandcollapse-runreport-rowgroup.png "executando relatório com grupo de linhas expansível")  
  
### <a name="to-add-expand-and-collapse-action-to-a-report-item"></a>Para adicionar uma ação de expansão e recolhimento a um item de relatório  
  
1.  No modo de design do relatório, clique no item de relatório para mostrar ou ocultar e, em seguida, clique em  *\<item de relatório >* **propriedades**. O  *\<item de relatório >* **propriedades** abre a caixa de diálogo para o item de relatório.  
  
2.  Clique em **Visibilidade**.  
  
3.  Em **Quando o relatório for executado inicialmente**, escolha uma das opções a seguir para definir a visibilidade desse item de relatório na primeira vez em que o relatório for executado:  
  
    -   Selecione **Mostrar** para exibir o item de relatório.  
  
    -   Selecione **Ocultar** para ocultar o item de relatório.  
  
    -   Selecione **Mostrar ou ocultar com base em uma expressão** para usar uma expressão avaliada em tempo de execução para determinar a visibilidade. Clique em (**fx**) para abrir a caixa de diálogo **Expressão** para criar uma expressão.  
  
        > [!NOTE]  
        >  Quando você especifica uma expressão para visibilidade, está configurando a propriedade Hidden do item de relatório. A expressão avalia como um valor **Booliano** **True** para ocultar o item e **False** para mostrar o item.  
  
4.  Em **A exibição pode ser alternada por este item de relatório**, na caixa suspensa, digite ou selecione o nome de uma caixa de texto no relatório na qual exibir uma imagem de alternância, por exemplo, Textbox1.  
  
     Na imagem a seguir, a tabela está configurada para permitir que os usuários expandam e recolham-na. A exibição da tabela é alternada pela caixa de texto Tabela de Produtos.  
  
     ![Configurar uma tabela de relatório a ser expandido](../../reporting-services/report-design/media/expandcollapse-reporttable.png "configurar uma tabela de relatório a ser expandida")  
  
    > [!NOTE]  
    >  A caixa de texto que você escolher deve estar no escopo atual ou de contenção para esse item de relatório (até e incluindo o corpo do relatório). Por exemplo, para alternar a visibilidade de um gráfico, selecione uma caixa de texto que esteja no mesmo escopo de contenção que o gráfico. Por exemplo, o corpo do relatório ou um retângulo. A caixa de texto deve estar na mesma ou em uma hierarquia de contêiner superior.  
  
5.  Para testar a alternância, execute o relatório e clique na caixa de texto com a imagem de alternância. A exibição do relatório é atualizada para mostrar itens de relatório com a visibilidade alternada.  
  
     ![Executando relatório com uma tabela de expansão](../../reporting-services/report-design/media/expandcollapse-runreport-reporttable.png "executando relatório com uma tabela de expansão")  
  
## <a name="see-also"></a>Consulte também  
 [Ação de análise detalhada &#40;Construtor de Relatórios e SSRS&#41;](../../reporting-services/report-design/drilldown-action-report-builder-and-ssrs.md)   
 [Ocultar um Item &#40; Construtor de relatórios e SSRS &#41;](../../reporting-services/report-builder/hide-an-item-report-builder-and-ssrs.md)  
  
  