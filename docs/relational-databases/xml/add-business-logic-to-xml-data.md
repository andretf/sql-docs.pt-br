---
title: "Adicionar lógica de negócios a dados XML | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: xml
ms.reviewer: 
ms.suite: sql
ms.technology:
- dbe-xml
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- business logic [XML]
ms.assetid: 0877fb38-f1a2-43d8-86cf-4754be224dc1
caps.latest.revision: 
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: c6794df397b0cdb304a03f5d18c5facfd43dc146
ms.sourcegitcommit: 37f0b59e648251be673389fa486b0a984ce22c81
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2018
---
# <a name="add-business-logic-to-xml-data"></a>Adicionar lógica de negócios a dados XML
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]
Sua lógica comercial pode ser adicionada a dados XML de vários modos:  
  
-   Você pode gravar restrições de linha ou de coluna para impor restrições específicas ao domínio durante inserção e modificação de dados XML.  
  
-   Você pode gravar um gatilho na coluna XML que seja disparado quando valores forem inseridos ou atualizados na coluna. O gatilho pode conter regras de validação específicas ao domínio ou popular tabelas de propriedades.  
  
-   O Mecanismo de Banco de Dados inclui a capacidade de executar código gerenciado. É possível usar essa integração de CLR (Common Language Runtime) para gravar funções em código gerenciado para as quais você passa valores XML, e usar recursos de processamento do XML fornecidos pelo namespace System.Xml. Um exemplo é aplicar a transformação XSL a dados XML. Como alternativa, é possível desserializar o XML em uma ou mais classes gerenciadas e operar sobre elas usando código gerenciado.  
  
-   É possível gravar funções e procedimentos armazenados Transact-SQL que começam o processamento na coluna XML para suas necessidades comerciais.  
  
## <a name="example-applying-xsl-transformation"></a>Exemplo: Aplicando XSL Transformation  
 Considere uma função CLR **TransformXml()** que aceita uma instância de tipo de dados **xml** e uma transformação XSL armazenada em um arquivo, aplica a transformação nos dados XML e retorna o XML transformado no resultado. O seguinte é um função em esqueleto escrita em C#:  
  
```  
public static SqlXml TransformXml (SqlXml XmlData, string xslPath) {  
   // Load XSL transformation  
   XslCompiledTransform xform = new XslCompiledTransform();  
   XPathDocument xslDoc = new XPathDocument (xslPath);  
   xform.Load(xslDoc);  
  
   // Load XML data   
   XPathDocument xDoc = new XPathDocument (XmlData.CreateReader());  
  
   // Return the transformed value  
   MemoryStream xsltResult = new MemoryStream();  
   xform.Transform(xDoc, null, xsltResult);  
   SqlXml retSqlXml = new SqlXml(xsltResult);  
   return (retSqlXml);  
}   
```  
  
 Após o assembly ser registrado e a função [!INCLUDE[tsql](../../includes/tsql-md.md)] definida pelo usuário ser criada, **SqlXslTransform()** correspondente a **TransformXml()**, a função pode ser invocada no Transact-SQL conforme mostrado na consulta a seguir:  
  
```  
SELECT SqlXslTransform (xCol, 'C:\MyFile\xsltransform.xsl')  
FROM    T  
WHERE  xCol.exist('/book/title/text()[contains(.,"custom")]') =1;  
```  
  
 O resultado da consulta contém um conjunto de linhas do XML transformado.  
  
 A integração CLR no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] expande as possibilidades de decomposição de dados XML em tabelas ou promoção de propriedades e consultar dados XML usando classes gerenciadas no namespace System.Xml. Para obter mais informações, veja [Dados XML &#40;SQL Server&#41;](../../relational-databases/xml/xml-data-sql-server.md).  
  
  
