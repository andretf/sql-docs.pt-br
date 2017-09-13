---
title: "Definir opções padrão para o construtor de relatórios | Microsoft Docs"
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
f1_keywords:
- "10427"
ms.assetid: 423360de-9bed-462e-921f-60a5abab004f
caps.latest.revision: 15
author: maggiesMSFT
ms.author: maggies
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 38dd786c1f1caabb5e949784bb4c9dd98eab7281
ms.contentlocale: pt-br
ms.lasthandoff: 08/09/2017

---
# <a name="set-default-options-for-report-builder"></a>Definir opções padrão para o Construtor de Relatórios
  No Construtor de Relatórios, você pode definir um número de padrões úteis para tornar a criação de relatórios mais rápida e fácil.  Por exemplo, se você puder definir ou alterar o servidor de relatório padrão, o Construtor de Relatórios salva seus relatórios no mesmo servidor de relatório automaticamente, a menos que você especifique o contrário.  
  
-   No Construtor de Relatórios, clique em **Arquivo** > **Opções**.  
  
## <a name="uielement-list"></a>Lista de elementos de interface do usuário  
 **Usar este servidor de relatório ou site do SharePoint por padrão**  
 Pode ser que o administrador tenha configurado essa opção. O valor pode ser uma URL bem formada que inicia com http:// ou https://. Essa configuração determina quais conexões da fonte de dados aparecem por padrão nos assistentes de Tabela/Matriz e de Gráfico. Além disso, seus relatórios serão processados neste servidor e você poderá referenciar recursos deste servidor.  
  
 Se você selecionar um servidor de relatório diferente, talvez seja necessário reiniciar o Construtor de Relatórios para que essa alteração tenha efeito.  
  
 **Publicar partes de relatórios para esta pasta por padrão**  
 O Construtor de Relatórios salvará as partes do relatório que você publicar nesta pasta. Se a pasta ainda não existir e você tiver permissões para criar pastas no servidor de relatório, o Construtor de Relatórios criará essa pasta.  
  
 Você não precisa reiniciar o Construtor de Relatórios para que essa configuração tenha efeito.  
  
 **Mostrar este número de sites e servidores recentes**  
 Especifica o número de sites e conexões recentes a serem mostrados nas caixas de diálogo **Abrir Relatório** e **Salvar como Relatório** .  
  
 **Mostrar este número de conjuntos de dados compartilhados e conexões da fonte de dados compartilhadas recentes**  
 Especifica o número de conjuntos de dados compartilhados e conexões de fonte de dados recentes a serem mostrados na caixa de diálogo **Propriedades do Conjunto de dados** e na página **Escolher uma conexão com uma fonte de dados** do Assistente de Regiões de Dados.  
  
 **Mostrar este número de documentos recentes**  
 Especifica o número de documentos recentes a serem mostrados quando você clicar no botão Construtor de Relatórios.  
  
 **Limpar todas as listas de itens recentes**  
 Limpa as listas atuais de sites e servidores recentes, bancos de dados compartilhados, conexões da fontes de dados compartilhadas e documentos.  
  
## <a name="see-also"></a>Consulte também  
 [Iniciar o Construtor de Relatórios](../../reporting-services/report-builder/start-report-builder.md)  
  
  