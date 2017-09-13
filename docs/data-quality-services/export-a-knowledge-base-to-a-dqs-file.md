---
title: "Exportar uma base de dados de conhecimento para um arquivo .dqs | Microsoft Docs"
ms.custom: ""
ms.date: "03/01/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "data-quality-services"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a324ead5-c8aa-4e26-abe3-ef415add00f8
caps.latest.revision: 19
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 19
---
# Exportar uma base de dados de conhecimento para um arquivo .dqs
  Este tópico descreve como exportar uma base de dados de conhecimento inteira para um arquivo de dados .dqs no [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS). Você pode exportar um domínio ou uma base de dados de conhecimento inteira para um arquivo de dados. Para obter informações sobre como exportar um domínio, consulte [Exportar um domínio para um arquivo. DQS](../data-quality-services/export-a-domain-to-a-dqs-file.md).  
  
 A exportação de uma base de dados de conhecimento para um arquivo .dqs e sua subsequente importação como outra base de dados de conhecimento simplifica o processo de geração de conhecimento, economizando tempo e esforço. Isso permite que você compartilhe uma base de dados de conhecimento e seu conhecimento com outras pessoas. O arquivo .dqs conterá todas as informações da base de dados de conhecimento, inclusive domínios e a política de correspondência, exceto as informações de dados de referência anexadas. Você deve anexar novamente os domínios requeridos aos serviços de dados de referência, se necessário, depois de importar o arquivo .dqs. Os dados publicados e não publicados em uma base de dados de conhecimento são exportados.  
  
 O arquivo de dados .dqs criado pelo processo de exportação é criptografado; portanto, o conteúdo não pode ser exibido.  
  
##  <a name="BeforeYouBegin"></a> Antes de começar  
  
###  <a name="Prerequisites"></a> Pré-requisitos  
 Para exportar uma base de dados de conhecimento para um arquivo de dados .dqs, você precisa ter criado e aberto uma base de dados de conhecimento. Você não precisa ter um arquivo .dqs para exportação; um arquivo será criado para você.  
  
###  <a name="Security"></a> Segurança  
  
####  <a name="Permissions"></a> Permissões  
 Você deve ter a função dqs_kb_editor ou dqs_administrator no banco de dados DQS_MAIN para exportar uma base de dados de conhecimento para um arquivo de dados .dqs.  
  
##  <a name="Export"></a> Exportar uma base de dados de conhecimento para um arquivo .dqs  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)] [Executar o aplicativo de cliente de qualidade de dados](../data-quality-services/run-the-data-quality-client-application.md).  
  
2.  Na tela inicial do [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , abra uma base de dados de conhecimento na atividade Gerenciamento de Domínio.  
  
3.  Na página de gerenciamento de domínio (com qualquer guia selecionada), clique o **Exportar Base de dados de Conhecimento dados** ícone acima da lista de domínios e clique **Exportar Base de dados de Conhecimento**. Como alternativa, você pode também com o botão direito no **domínio** lista, focalize **exportar**, e, em seguida, clique em **Exportar Base de dados de Conhecimento**.  
  
4.  No **Exportar para arquivo de dados** caixa de diálogo, vá para a pasta que você deseja salvar o arquivo no nome do arquivo ou mantenha o nome da base de dados de Conhecimento, mantenha **arquivos de dados do DQS (\*. DQS)** como o **Salvar como** Digite e clique **Salvar**.  
  
5.  Na caixa de diálogo **Exportar Base de Dados de Conhecimento** , verifica se a linha de status indica que a exportação foi concluída. Clique em **OK**.  
  
##  <a name="FollowUp"></a> Acompanhamento: após exportar um domínio para um arquivo .dqs  
 Após exportar uma base de dados de conhecimento para um arquivo .dqs, você poderá importar a base de dados de conhecimento para o mesmo [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] (com um novo nome) ou para outro [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].  
  
  