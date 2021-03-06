---
title: "Caixa de diálogo de Ferramentas Externas | Microsoft Docs"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.prod_service: sql-tools
ms.service: 
ms.component: ssms
ms.reviewer: 
ms.suite: sql
ms.technology: tools-ssms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adding external tools
- external tools [SQL Server Management Studio]
- SQL Server Management Studio [SQL Server], external tools
ms.assetid: ba797203-24d0-4922-9b97-8ab483f1db14
caps.latest.revision: "5"
author: stevestein
ms.author: sstein
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: eee32bf86aca8d55ca8ebddceb3f46e635f11ad8
ms.sourcegitcommit: b6116b434d737d661c09b78d0f798c652cf149f3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/17/2018
---
# <a name="external-tools-dialog-box"></a>Caixa de diálogo Ferramentas Externas
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../includes/appliesto-ss-asdb-asdw-pdw-md.md)] Use a caixa de diálogo **Ferramentas Externas** para adicionar ferramentas externas como SQLCMD ou o Bloco de Notas ao menu **Ferramentas**. Adicionar ferramentas externas permite a inicialização de outros aplicativos facilmente enquanto você trabalha no ambiente do [!INCLUDE[msCoName](../includes/msconame_md.md)] [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull_md.md)] . Você pode especificar argumentos e um diretório de trabalho na execução da ferramenta. Além disso, a saída de algumas ferramentas pode ser exibida na janela **Saída** . A caixa de diálogo **Ferramentas Externas** está disponível no menu **Ferramentas** .  
  
## <a name="options"></a>Opções  
**Conteúdos de menu**  
Relaciona os títulos dos itens atuais adicionados ao menu **Ferramentas** . Use as setas **Mover para Cima** e **Mover para Baixo** para alterar a ordem dos itens que aparecem no menu. Use o botão **Excluir** para remover um item do menu.  
  
**Mover para Cima**  
Mova a ferramenta selecionada para cima na lista de ferramentas exibida no menu **Ferramentas** .  
  
**Mover para Baixo**  
Mova a ferramenta selecionada para baixo na lista de ferramentas exibida no menu **Ferramentas** .  
  
**Adicionar**  
Desmarque as caixas de texto para que você possa especificar uma nova ferramenta.  
  
**Delete (excluir)**  
Remova a ferramenta ou o comando da lista **Conteúdo do Menu** , bem como do menu **Ferramentas** .  
  
**Título**  
Insira o nome da ferramenta ou do comando que será exibido no submenu **Ferramentas Externas** do menu **Ferramentas** . Coloque um E comercial (&) antes de uma letra no nome da ferramenta para especificar essa letra como uma tecla de atalho. Por exemplo, "&SQLCMD" mostrará SQLCMD no menu **Ferramentas**.  
  
**Comando**  
Especifique o caminho do arquivo a ser iniciado.  
  
**Argumentos**  
Especifique as variáveis que serão passadas à ferramenta quando a ferramenta for selecionada no menu. Os argumentos podem especificar valores que são passados à ferramenta ou ao comando quando são iniciados. Por exemplo, um valor pode especificar um nome de arquivo ou diretório. Use o botão de seta para fazer a seleção em uma lista de argumentos predefinidos. Você pode adicionar mais de um argumento. Para obter uma lista completa de argumentos predefinidos e suas definições, consulte [Arguments for External Tools](../ssms/use-of-sql-server-features-and-capabilities-wwi-oltp.md). Você também pode inserir argumentos personalizados (por exemplo, opções de linha de comando), dependendo do comando ou da ferramenta usada.  
  
**Usar a janela Saída**  
Abre a janela Saída do [!INCLUDE[ssManStudio](../includes/ssmanstudio_md.md)] para exibir a saída do comando que está sendo executado. Nem todas as ferramentas apresentam saída em um formato que pode ser exibido na janela Saída. Para obter mais informações, consulte [Janela Saída](http://msdn.microsoft.com/en-us/9808e00c-c8f6-45cc-896e-192b8420f747).  
  
**Tratar saída como Unicode**  
Interpreta a saída como Unicode.  
  
**Diretório inicial**  
Especifique o diretório de trabalho da ferramenta. Use o botão de seta para selecionar diretórios. Você pode selecionar mais de um argumento.  
  
**Solicitar argumentos**  
Exibe a caixa de diálogo **Argumentos** para permitir a inserção ou edição dos valores para os argumentos sempre que você iniciar a ferramenta externa.  
  
**Fechar na saída**  
Fecha a janela aberta pela ferramenta quando ela for encerrada.  
  
## <a name="example"></a>Exemplo  
Inserir os valores a seguir na caixa de diálogo **Ferramentas Externas** criará um item de menu rotulado como "DAC" que, quando selecionado, abrirá um prompt de comando e executará o utilitário **sqlcmd** usando a conexão de administrador dedicada.  
  
|Box|Valor|  
|-------|---------|  
|**Título**|DAC|  
|**Comando**|[!INCLUDE[ssInstallPath](../includes/ssinstallpath_md.md)]Tools\Binn\SQLCMD.exe|  
|**Argumentos**|-A|  
  
## <a name="see-also"></a>Consulte Também  
[Argumentos para ferramentas externas](../ssms/use-of-sql-server-features-and-capabilities-wwi-oltp.md)  
[Elementos gerais da interface de usuário](../ssms/general-user-interface-elements.md)  
  
