---
title: Elemento NullProcessing (ASSL) | Microsoft Docs
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- NullProcessing Element
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
f1_keywords:
- NullProcessing
helpviewer_keywords:
- NullProcessing element
ms.assetid: 697be5c6-e9a6-4f74-9ff4-5f31400c2178
caps.latest.revision: 36
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: bc5c99e52f8868251d7d5b581bdefcea6e5d3097
ms.contentlocale: pt-br
ms.lasthandoff: 09/01/2017

---
# <a name="nullprocessing-element-assl"></a>NullProcessing Element (ASSL)
  Define como valores nulos são processados.  
  
## <a name="syntax"></a>Sintaxe  
  
```xml  
  
<DataItem>  
   ...  
   <NullProcessing>...</NullProcessing>  
   ...  
</DataItem>  
```  
  
## <a name="element-characteristics"></a>Características do elemento  
  
|Característica|Descrição|  
|--------------------|-----------------|  
|Comprimento e tipo de dados|Cadeia de caracteres (enumeração)|  
|Valor padrão|*Automático*|  
|Cardinalidade|0-1: elemento obrigatório que pode ocorrer apenas uma vez.|  
  
## <a name="element-relationships"></a>Relações do elemento  
  
|Relação|Elemento|  
|------------------|-------------|  
|Elemento pai|[O item de dados](../../../analysis-services/scripting/data-type/dataitem-data-type-assl.md)|  
|Elementos filho|Nenhuma|  
  
## <a name="remarks"></a>Comentários  
 O valor desse elemento é limitado a uma das cadeias de caracteres listadas na tabela a seguir.  
  
|Valor|Description|  
|-----------|-----------------|  
|*Preservar*|Preserva o valor nulo.<br /><br /> Observação: Esse valor não é suportado para medidas de contagem distinta.|  
|*Erro*|Gera um erro de chave nula. O valor de [NullKeyNotAllowed](../../../analysis-services/scripting/properties/nullkeynotallowed-element-assl.md) determina como a instância reage ao erro.<br /><br /> Observação: Esse valor não é suportado para medidas.|  
|*UnknownMember*|Gera um membro desconhecido e um erro de conversão nula. O valor de [NullKeyConvertedToUnknown](../../../analysis-services/scripting/properties/nullkeyconvertedtounknown-element-assl.md) determina como a instância reage ao erro.<br /><br /> Observação: Esse valor não tem suporte para colunas associadas às medidas.|  
|*ZeroOrBlank*|Converte o valor nulo em zero (para itens de dados numéricos) ou em uma cadeia de caracteres vazia (para itens de dados de cadeia de caracteres).<br /><br /> Observação: Esse valor fornece compatibilidade com versões anteriores do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].|  
|*Automático*|Usa o processamento padrão apropriado para o elemento:<br /><br /> *ZeroOrBlank* para itens de dados OLAP.<br /><br /> *UnknownMember* para itens de dados de mineração de dados.|  
  
 A enumeração que corresponde aos valores permitidos para **NullProcessing** no objeto Analysis Management Objects (AMO) o modelo é <xref:Microsoft.AnalysisServices.NullProcessing>.  
  
## <a name="see-also"></a>Consulte também  
 [Propriedades &#40; ASSL &#41;](../../../analysis-services/scripting/properties/properties-assl.md)  
  
  