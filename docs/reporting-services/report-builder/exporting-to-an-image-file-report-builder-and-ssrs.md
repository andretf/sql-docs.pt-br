---
title: "Exportando para um arquivo de imagem (construtor de relatórios e SSRS) | Microsoft Docs"
ms.custom: 
ms.date: 03/07/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- reporting-services-sharepoint
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 020d8ea2-de07-4212-a2bb-2ed0df2c8db8
caps.latest.revision: 12
author: maggiesMSFT
ms.author: maggies
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: 0eb007a5207ceb0b023952d5d9ef6d95986092ac
ms.openlocfilehash: bf6d4979db2a3b68c34b05fa96f81b47d8034a0b
ms.contentlocale: pt-br
ms.lasthandoff: 08/09/2017

---
# <a name="exporting-to-an-image-file-report-builder-and-ssrs"></a>Exportando para um arquivo de imagem (Construtor de Relatórios e SSRS)
  A extensão de renderização da Imagem renderiza um relatório para um bitmap ou metarquivo. Por padrão, a extensão de renderização da Imagem produz um arquivo TIFF do relatório, que pode ser exibido em várias páginas. Quando o cliente receber a imagem, ela pode ser exibida em um visualizador de imagem e impressa. Este tópico fornece as informações específicas do processador de Imagem e descreve as exceções às regras de renderização.  
  
 A extensão de renderização de Imagem pode gerar arquivos em qualquer um dos formatos que tenham o suporte do [!INCLUDE[ndptecgdiplus](../../includes/ndptecgdiplus-md.md)]: BMP, EMF, EMFPlus, GIF, JPEG, PNG e TIFF. Para o formato TIFF, o nome de arquivo do fluxo primário é *NomedoRelatório*.tif. Para todos os outros formatos, que renderizam como uma página única por arquivo, o nome do arquivo é *ReportName_Page.ext* . *ext* é a extensão do arquivo para o formato selecionado. Para gerar um arquivo em outro formato com suporte da Imagem, especifique qualquer uma das cadeias de caracteres listadas anteriormente na configuração **OutputFormatDeviceInfo** .  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
##  <a name="SupportedImageFormats"></a> Formatos de imagem com suporte  
 A tabela a seguir mostra a extensão de arquivo e MimeType para cada formato do processador de Imagem.  
  
|**Tipo**|**Extensão**|**MIMEType**|  
|--------------|-------------------|------------------|  
|BMP|BMP|image/bmp|  
|GIF|GIF|image/gif|  
|JPEG|JPEG|image/jpeg|  
|PNG|PNG|image/png|  
|TIFF|tif|imagem/tiff|  
|EMF|EMF|imagem/emf|  
|EMFPlus|EMF|imagem/emf|  
  
  
##  <a name="RenderingMultiplePages"></a> Renderizando várias páginas  
 TIFF é o único formato que dá suporte a documentos de várias páginas em um único arquivo. Os demais formatos, como JPG ou PNG, emitem uma página por vez e requerem uma chamada separada para a extensão de renderização de cada página.  
  
  
##  <a name="Interactivity"></a> Interatividade  
 A interatividade não tem suporte em formatos de Imagem gerados por esse renderizador. Os elementos interativos a seguir não são renderizados:  
  
-   Hiperlinks  
  
-   Mostrar ou ocultar  
  
-   Mapa do documento  
  
-   Links de detalhamento ou de clique  
  
-   Classificação de usuário final  
  
-   Cabeçalhos fixos  
  
-   Indicadores  
  
  
##  <a name="DeviceInfo"></a> Configurações de informações de dispositivo  
 Você pode alterar algumas configurações padrão desse renderizador alterando as configurações de informações de dispositivo. Para obter mais informações, consulte [Image Device Information Settings](../../reporting-services/image-device-information-settings.md).  
  
  
## <a name="see-also"></a>Consulte também  
 [Paginação no Reporting Services &#40; Construtor de relatórios e SSRS &#41;](../../reporting-services/report-design/pagination-in-reporting-services-report-builder-and-ssrs.md)   
 [Comportamentos de renderização &#40; Construtor de relatórios e SSRS &#41;](../../reporting-services/report-design/rendering-behaviors-report-builder-and-ssrs.md)   
 [Funcionalidade interativa para extensões &#40; de renderização de relatório diferente Construtor de relatórios e SSRS &#41;](../../reporting-services/report-builder/interactive-functionality-different-report-rendering-extensions.md)   
 [Renderizando itens de relatório &#40; Construtor de relatórios e SSRS &#41;](../../reporting-services/report-design/rendering-report-items-report-builder-and-ssrs.md)   
 [Tabelas, matrizes e listas de &#40; Construtor de relatórios e SSRS &#41;](../../reporting-services/report-design/tables-matrices-and-lists-report-builder-and-ssrs.md)  
  
  