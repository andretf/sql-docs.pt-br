---
title: STBuffer (tipo de dados geography) | Microsoft Docs
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- STBuffer (geography Data Type)
- STBuffer_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- STBuffer (geography Data Type)
ms.assetid: cb4deab8-642b-44d9-b3d9-85114d64021e
caps.latest.revision: 19
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 2fa06f270ad653e9c8e43a5ec5456257e785670e
ms.contentlocale: pt-br
ms.lasthandoff: 09/01/2017

---
# <a name="stbuffer-geography-data-type"></a>STBuffer (tipo de dados geography)
[!INCLUDE[tsql-appliesto-ss2012-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2012-asdb-xxxx-xxx-md.md)]

  Retorna um objeto geográfico que representa a união de todos os pontos cuja distância de uma **geografia** instância é menor ou igual ao valor especificado.  
  
 Esses dados de Geografia digite método dá suporte a **FullGlobe** instâncias ou a instâncias espaciais maiores que um hemisfério.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
  
.STBuffer ( distance )  
```  
  
## <a name="arguments"></a>Argumentos  
 *distância*  
 É um valor do tipo **float** (**duplo** no .NET Framework) Especifica a distância do **geografia** instância em torno da qual calcular o buffer.  
  
 A distância máxima do buffer não pode exceder 0,999 \* *π* * minorAxis \* minorAxis / majorAxis (~0.999 \* 1/2 circunferência da Terra) ou o globo inteiro.  
  
## <a name="return-types"></a>Tipos de retorno  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]tipo de retorno: **geografia**  
  
 Tipo de retorno CLR: **SqlGeography**  
  
## <a name="remarks"></a>Comentários  
 Stbuffer () calcula um buffer da mesma maneira que [BufferWithTolerance](../../t-sql/spatial-geography/bufferwithtolerance-geography-data-type.md), especificando *tolerância* = ABS (Distance) \* .001 e *relativo*  =  **false**.  
  
 Um buffer negativo remove todos os pontos dentro da distância determinada do limite do **geografia** instância.  
  
 `STBuffer()`retornará um **FullGlobe** instância em certos casos; por exemplo, `STBuffer()` retorna um **FullGlobe** instância quando a distância do buffer é maior que a distância do Equador até os polos. Um buffer não pode exceder o globo completo.  
  
 Esse método lançará um **ArgumentException** na **FullGlobe** instâncias onde a distância do buffer excede a seguinte limitação:  
  
 0,999 \* *π* * minorAxis \* minorAxis / majorAxis (~0.999 \* 1/2 circunferência da Terra)  
  
 O limite de distância máximo permite que a construção do buffer seja a mais flexível possível.  
  
 O erro entre o buffer teórico e calculado é max (tolerância, extensões * 1. e-7) onde tolerância = distância \* .001. Para obter mais informações sobre extensões, consulte [referência de método do tipo de dados geography](http://msdn.microsoft.com/library/028e6137-7128-4c74-90a7-f7bdd2d79f5e).  
  
## <a name="examples"></a>Exemplos  
 O exemplo a seguir cria um `LineString``geography` instância. Em seguida, usa `STBuffer()` para retornar a região dentro de 1 metro da instância.  
  
```  
DECLARE @g geography;  
SET @g = geography::STGeomFromText('LINESTRING(-122.360 47.656, -122.343 47.656)', 4326);  
SELECT @g.STBuffer(1).ToString();  
```  
  
## <a name="see-also"></a>Consulte também  
 [BufferWithTolerance &#40; tipo de dados geography &#41;](../../t-sql/spatial-geography/bufferwithtolerance-geography-data-type.md)   
 [Métodos do OGC em instâncias de Geografia](../../t-sql/spatial-geography/ogc-methods-on-geography-instances.md)  
  
  
