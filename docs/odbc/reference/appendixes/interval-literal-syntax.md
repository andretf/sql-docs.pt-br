---
title: Sintaxe de literais de intervalo | Microsoft Docs
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: odbc
ms.reviewer: 
ms.suite: sql
ms.technology: drivers
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- literals [ODBC], interval
- interval literals [ODBC]
- ODBC literals [ODBC], interval
ms.assetid: 2f2d22c1-51d6-4055-9f5a-53bc31e9fea0
caps.latest.revision: "6"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 867bcf39a1cfb7807d8156a172e0a0b764a149f7
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/21/2017
---
# <a name="interval-literal-syntax"></a>Sintaxe de literais de intervalo
A sintaxe a seguir é usada para literais de intervalo no ODBC.  
  
 *literal de intervalo:: = intervalo* [+*&#124;* -] *qualificador de intervalo de cadeia de caracteres de intervalo*  
  
 *intervalo de cadeia de caracteres* :: = *aspas* { *ano-mês-literal* &#124; *literal de hora do dia* } *aspas*  
  
 *ano-mês-literal* :: = *anos valor* &#124; [*anos valor* -] *valor de meses*  
  
 *literal de hora do dia* :: = *intervalo de tempo do dia* &#124; *intervalo de tempo*  
  
 *intervalo de tempo do dia* :: = *valor de dias* [*valor de horas* [:*valor de minutos*[:*valor de segundos*]]]  
  
 *intervalo de tempo* :: = *valor de horas* [:*valor de minutos* [:*valor de segundos* ]]  
  
 &#124; *valor de minutos* [:*valor de segundos* ]  
  
 &#124; *valor de segundos*  
  
 *valor de ano* :: = *valor datetime*  
  
 *valor de meses* :: = *valor datetime*  
  
 *valor de dias* :: = *valor datetime*  
  
 *valor de horas* :: = *valor datetime*  
  
 *valor de minutos* :: = *valor datetime*  
  
 *valor de segundos* :: = *valor de inteiro de segundos* [. [ *fração de segundos*]]  
  
 *valor de inteiro de segundos* :: = *inteiro não assinado*  
  
 *fração de segundos* :: = *inteiro não assinado*  
  
 *valor de DateTime* :: = *inteiro não assinado*  
  
 *qualificador de intervalo* :: = *campo Início* para *campo final* &#124; *único campo de data e hora*  
  
 *campo de início* :: = *campo Data e hora que não é segundo* [(*intervalo à esquerda-campo precisão* )]  
  
 *campo final* :: = *campo Data e hora que não é segundo* &#124; SEGUNDO [(*intervalo--segundos-precisão fracionária*)]  
  
 *campo de data/hora único* :: = *campo Data e hora que não é segundo* [(*intervalo à esquerda-campo precisão*)] &#124; SEGUNDO [(*intervalo à esquerda-campo precisão* [, (*intervalo--segundos-precisão fracionária*)]  
  
 *campo de data/hora* :: = *campo Data e hora que não é segundo* &#124; SEGUNDO  
  
 *campo Data e hora que não é segundo* :: = ano &#124; MÊS &#124; DIA &#124; HORA &#124; MINUTO  
  
 *intervalo de--segundos-precisão fracionária* :: = *inteiro não assinado*  
  
 *intervalo à esquerda-campo precisão* :: = *inteiro não assinado*  
  
 *aspas* :: = '  
  
 *inteiro não assinado* :: = *dígitos...*
