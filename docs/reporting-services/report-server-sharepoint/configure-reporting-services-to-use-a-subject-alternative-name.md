---
title: Configurar o Reporting Services para usar um nome alternativo da entidade | Microsoft Docs
ms.custom: 
ms.date: 03/20/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- reporting-services-sharepoint
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ce458f9f-4b4f-4a58-aa75-9a90dda1e622
caps.latest.revision: 6
author: guyinacube
ms.author: asaxton
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 4c4d975e93e77f43c481b44644faaa310963527b
ms.contentlocale: pt-br
ms.lasthandoff: 08/09/2017

---
# <a name="configure-reporting-services-to-use-a-subject-alternative-name"></a>Configurar o Reporting Services para usar um nome alternativo da entidade
  Este tópico explica como configurar o [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] (SSRS) para usar um SAN (Nome alternativo da entidade) modificando o arquivo rsreportserver.config e usando a ferramenta Netsh.exe.  
  
||  
|-|  
|**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Modo nativo|  
  
 As instruções aplicam-se à URL do Reporting Service e à URL do Serviço Web.  
  
 Para usar um SAN, o certificado SSL deve estar registrado no servidor, assinado e ter a chave privada. Você não pode usar um certificado autoassinado  
  
 Você pode configurar as URLs do [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] para usarem um certificado SSL. Um certificado normalmente tem apenas um nome de entidade, o que permite apenas uma URL por sessão SSL (protocolo SSL). O SAN é um campo adicional no certificado que permite que um serviço SSL ouça e seja válido para muitas URLs e compartilhe a porta SSL com outros aplicativos. O SAN é semelhante ao seguinte: www.s2.com.  
  
 Para obter mais informações sobre configurações SSL para [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], consulte [Configurar conexões SSL em um servidor de relatório do modo nativo](../../reporting-services/security/configure-ssl-connections-on-a-native-mode-report-server.md).  
  
### <a name="configure-ssrs-to-use-a-subject-alternative-name-for-web-service-url"></a>Configurar o SSRS para usar um nome alternativo da entidade para a URL do Web Service  
  
1.  Iniciar o Gerenciador de Configuração do Reporting Services.  
  
     Para obter mais informações, consulte [Reporting Services Configuration Manager &#40;Modo Nativo&#41;](../../reporting-services/install-windows/reporting-services-configuration-manager-native-mode.md).  
  
2.  Na página **URL do Serviço Web** , escolha uma porta SSL e o certificado SSL.  
  
     ![Gerenciador de configuração do Reporting Services](../../reporting-services/report-server-sharepoint/media/reportingservices-configurationmanager.png "Gerenciador de configuração do Reporting Services")  
  
     O gerente de configuração registra o certificado SSL para a porta.  
  
3.  Abra o arquivo rsreportserver.config.  
  
     Para o SSRS no modo Nativo, o arquivo RSReportServer.config está localizado por padrão na pasta abaixo.  
  
    ```  
    \Program Files\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer  
    ```  
  
4.  Copie a seção da URL para o aplicativo Report Server Web Service.  
  
     Por exemplo, esta é a seção de URL original.  
  
    ```  
        <URL>  
         <UrlString>https://localhost:443</UrlString>  
         <AccountSid>S-1-5-20</AccountSid>  
         <AccountName>NT Authority\NetworkService</AccountName>  
        </URL>  
  
    ```  
  
     Esta é a seção de URL modificada.  
  
    ```  
    <URL>  
         <UrlString>https://www.s1.com:443</UrlString>  
         <AccountSid>S-1-5-20</AccountSid>  
         <AccountName>NT Authority\NetworkService</AccountName>  
        </URL>  
        <URL>  
         <UrlString>https://www.s2.com:443</UrlString>  
         <AccountSid>S-1-5-20</AccountSid>  
         <AccountName>NT Authority\NetworkService</AccountName>  
        </URL>  
  
    ```  
  
5.  Salve o arquivo rsreportserver.config.  
  
6.  Inicie um prompt de comando como administrador e execute a ferramenta Netsh.exe.  
  
    ```  
    C:\windows\system32\netsh  
    ```  
  
7.  Mude para o contexto http, digitando o seguinte:  
  
    ```  
    Netsh>http  
    ```  
  
8.  Mostre as urlacls existentes digitando o seguinte:  
  
    ```  
    Netsh http>show urlacl  
    ```  
  
     Uma entrada como a seguinte é exibida:  
  
    ```  
    Reserved URL            : https:// www.s1.com:443/ReportServer/  
        User: NT SERVICE\ReportServer  
            Listen: Yes  
            Delegate: No  
            SDDL: D:(A;;GX;;;S-1-5-80-1234567890-123456789-123456789-123456789-1234567890)  
    ```  
  
     Uma urlacl é uma DACL (lista de controle de acesso discricionário) para uma URL reservada.  
  
9. Crie uma nova entrada para o nome alternativo da entidade, com o mesmo usuário e SDDL que a entrada existente, digitando o seguinte:  
  
    ```  
    netsh http>add urlacl  url=https://www.s2.com:443/ReportServer    
    user="NT Service\ReportServer" sddl=D:(A;;GX;;;S-1-5-80-1234567980-12346579-123456789-123456789-1234567890)  
  
    ```  
  
10. Na página **Status do Servidor de Relatório** do Gerenciador de Configuração do Reporting Services, clique em **Parar** e clique em **Iniciar** para reiniciar o servidor de relatório.  
  
## <a name="see-also"></a>Consulte também  
 [Arquivo de Configuração RsReportServer.config](../../reporting-services/report-server/rsreportserver-config-configuration-file.md)   
 [Reporting Services Configuration Manager &#40; Modo nativo &#41;](../../reporting-services/install-windows/reporting-services-configuration-manager-native-mode.md)   
 [Modificar um arquivo de configuração do Reporting Services &#40; Rsreportserver. config &#41;](../../reporting-services/report-server/modify-a-reporting-services-configuration-file-rsreportserver-config.md)   
 [Configurar URLs do servidor de relatório &#40; Gerenciador de configurações do SSRS &#41;](../../reporting-services/install-windows/configure-report-server-urls-ssrs-configuration-manager.md)  
  
  