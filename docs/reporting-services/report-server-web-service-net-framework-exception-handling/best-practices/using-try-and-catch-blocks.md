---
title: Usando Try e Catch blocos | Microsoft Docs
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- docset-sql-devref
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- exceptions [Reporting Services], try/catch blocks
- try/catch blocks [Reporting Services]
ms.assetid: a7a9ef53-e3b6-4bf7-81f3-d85615954e6f
caps.latest.revision: 29
author: guyinacube
ms.author: asaxton
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: 0eb007a5207ceb0b023952d5d9ef6d95986092ac
ms.openlocfilehash: 659707603a24ff8d59bfc1b001d80e8184c119e1
ms.contentlocale: pt-br
ms.lasthandoff: 08/09/2017

---
# <a name="using-try-and-catch-blocks"></a>Usando Try e blocos Catch
  Depois de limitar solicitações inválidas feitas ao servidor de relatório ao adicionar instruções condicionais ao seu código, forneça a manipulação de exceções adequada usando blocos try/catch. Essa técnica oferece outra camada de proteção contra solicitações que não são válidas. Se uma solicitação feita ao servidor de relatório for encapsulada em um bloco try e se essa solicitação fizer com que o servidor de relatório lance uma exceção, a exceção será capturada em um bloco catch, impedindo que o seu aplicativo seja interrompido inesperadamente. Depois que a exceção tiver sido capturada, você poderá usá-la para instruir o usuário a fazer algo diferente ou simplesmente avisá-lo, de uma forma amigável, de que houve um erro. Por fim, você poderá usar um bloco finally para limpar qualquer recurso. Idealmente, você deve gerar um plano de manipulação de exceções gerais para evitar a duplicação desnecessária de blocos try/catch.  
  
 O exemplo a seguir usa blocos try/catch para aumentar a confiabilidade do código de manipulação de exceções.  
  
```  
// C#  
private void PublishReport()  
{  
   int index;  
   string reservedChar;  
   string message;  
  
   // Check the text value of the name text box for "/",  
   // a reserved character  
   index = nameTextBox.Text.IndexOf(@"/");  
  
   if ( index != -1) // The text contains the character  
   {  
      reservedChar = nameTextBox.Text.Substring(index, 1);  
      // Build a user-friendly error message  
      message = "The name of the report cannot contain the reserved character " +  
         "\"" + reservedChar + "\". " +  
         "Please enter a valid name for the report. " +  
         "For more information about reserved characters, " +  
         "consult the online documentation";  
  
      MessageBox.Show(message, "Invalid Input Error");  
   }  
   else // Publish the report  
   {  
      Byte[] definition = null;  
      Warning[] warnings = {};  
      string name = nameTextBox.Text;  
  
      try  
      {  
         FileStream stream = File.OpenRead("MyReport.rdl");  
         definition = new Byte[stream.Length];  
         stream.Read(definition, 0, (int) stream.Length);  
         stream.Close();  
         // Create report with user-defined name  
         rs.CreateCatalogItem("Report", name, "/Samples", false, definition, null, out warnings);  
         MessageBox.Show("Report: {0} created successfully", name);  
      }  
  
      // Catch expected exceptions beginning with the most specific,  
      // moving to the least specific  
      catch(IOException ex)  
      {  
         MessageBox.Show(ex.Message, "File IO Exception");  
      }  
  
      catch (SoapException ex)  
      {  
         // The exception is a SOAP exception, so use  
         // the Detail property's Message element.  
         MessageBox.Show(ex.Detail["Message"].InnerXml, "SOAP Exception");   
      }  
  
      catch (Exception ex)  
      {  
         MessageBox.Show(ex.Message, "General Exception");  
      }  
   }  
}  
```  
  
## <a name="see-also"></a>Consulte também  
 [Introdução ao tratamento de exceção no Reporting Services](../../../reporting-services/report-server-web-service-net-framework-exception-handling/introducing-exception-handling-in-reporting-services.md)   
 [Reporting Services classe SoapException](../../../reporting-services/report-server-web-service-net-framework-exception-handling/soapexception-class/reporting-services-soapexception-class.md)  
  
  