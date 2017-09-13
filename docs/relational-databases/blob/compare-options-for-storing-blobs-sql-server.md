---
title: "Comparar opções para Armazenamento de Blobs (SQL Server) | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- dbe-blob
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6038697b-36a9-49e8-a02a-2ad9e2e60e5a
caps.latest.revision: 10
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 98538bd77f81cd6a1f16857b70a866ee3f6d171a
ms.contentlocale: pt-br
ms.lasthandoff: 06/22/2017

---
# <a name="compare-options-for-storing-blobs-sql-server"></a>Comparar opções de armazenamento de Blobs (SQL Server)
  Discute e compara as opções disponíveis para armazenar arquivos e documentos no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
##  <a name="Expectations"></a> Armazenando arquivos no banco de dados - benefícios e expectativas  
 Um grande percentual de dados corporativos é não estruturado por natureza, e é normalmente armazenado como arquivos e documentos em sistemas de arquivos. A maioria desses dados é produzida, gerenciada e consumida por aplicativos que acessam os arquivos por meio de APIs do Windows. As empresas geralmente mantêm esses dados no sistema de arquivos, enquanto armazenam os metadados relacionados dos arquivos em um banco de dados relacional.  
  
 A integração de dados não estruturados no banco de dados relacional oferece benefícios significativos. Esses benefícios incluem o seguinte:  
  
-   Recursos de armazenamento integrado e gerenciamento de dados, inclusive backup.  
  
-   Serviços integrados, como pesquisa de texto completo e pesquisa semântica em dados e metadados.  
  
-   Facilidade de administração e gerenciamento de políticas nos dados não estruturados.  
  
 Basicamente, contudo, não tem sido conveniente armazenar dados não estruturados em um banco de dados relacional. Antes não era possível executar aplicativos existentes baseados no Windows sobre sistemas relacionais. Não é prático reescrever aplicativos estabelecidos (como Microsoft Word ou Adobe Reader) para executar APIs de banco de dados relacional. Esses aplicativos simplesmente esperam que os dados estejam acessíveis por meio de APIs do Windows. Em outras palavras, as expectativas incluem o seguinte:  
  
-   Aplicativos do Windows não estão cientes das transações de banco de dados e não as requerem.  
  
-   Aplicativos do Windows requerem compatibilidade com APIs do sistema de arquivos para dados de arquivos e diretórios.  
  
##  <a name="Filestream"></a> FILESTREAM  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] já inclui o recurso de FILESTREAM, que fornece armazenamento eficiente, gerenciamento e streaming de dados não estruturados armazenados como arquivos no sistema de arquivos. Entretanto, uma solução FILESTREAM exige a programação personalizada e não satisfaz o requisito de compatibilidade total de aplicativos do Windows, descrito anteriormente.  
  
##  <a name="FileTables"></a> Tabelas de arquivos  
 O recurso FileTable se baseia nos recursos de FILESTREAM existentes para permitir que os clientes corporativos armazenem dados de arquivos não estruturados e hierarquias de diretório em um banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , atendendo aos requisitos de acesso não transacional e compatibilidade de aplicativos do Windows para obter dados baseados em arquivos.  
  
##  <a name="CompareFileTable"></a> Comparando FILESTREAM e FileTable  
  
|Recurso|Servidor de arquivos e solução de banco de dados|Solução FILESTREAM|Solução FileTable|  
|-------------|---------------------------------------|-------------------------|------------------------|  
|**Armazenamento único para tarefas de gerenciamento**|Não|Sim|**Sim**|  
|**Conjunto único de serviços**: pesquisa, relatório, consulta etc.|Não|Sim|**Sim**|  
|**Modelo de segurança integrada**|Não|Sim|**Sim**|  
|**Atualizações in loco de dados FILESTREAM**|Sim|Não|**Sim**|  
|**Hierarquia de arquivos e diretórios mantida no banco de dados**|Não|Não|**Sim**|  
|**Compatibilidade de aplicativos do Windows**|Sim|Não|**Sim**|  
|**Acesso relacional a atributos de arquivo**|Não|Não|**Sim**|  
  
##  <a name="CompareRBS"></a> Comparando FILESTREAM e repositório de BLOB remoto (RBS)  
 Para uma comparação destes dois recursos, consulte esta postagem de blog da equipe de RBS: [Comparação de recursos do Repositório de BLOB Remoto do SQL Server e do FILESTREAM](http://go.microsoft.com/fwlink/?LinkId=210317).  
  
##  <a name="more"></a> Mais informações  
 [FILESTREAM &#40;SQL Server&#41;](../../relational-databases/blob/filestream-sql-server.md)  
 [FileTables &#40;SQL Server&#41;](../../relational-databases/blob/filetables-sql-server.md)  
 [Remote Blob Store &#40;RBS&#41; &#40;SQL Server&#41;](../../relational-databases/blob/remote-blob-store-rbs-sql-server.md)  
  