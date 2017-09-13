---
title: "Configurar e gerenciar chaves de criptografia (Gerenciador de configuração do SSRS) | Microsoft Docs"
ms.custom: 
ms.date: 05/31/2016
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- encryption keys [Reporting Services]
- private keys [Reporting Services]
- cryptography [Reporting Services]
- symmetric keys [Reporting Services]
- encryption [Reporting Services]
- public keys [Reporting Services]
ms.assetid: 58e61636-88a2-4338-ae5f-3dd210aee887
caps.latest.revision: 8
author: guyinacube
ms.author: asaxton
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: 0eb007a5207ceb0b023952d5d9ef6d95986092ac
ms.openlocfilehash: 1433e2532fc1deeb8abe5ac0ca71de69956730e0
ms.contentlocale: pt-br
ms.lasthandoff: 08/09/2017

---
# <a name="ssrs-encryption-keys---manage-encryption-keys"></a>Chaves de criptografia do SSRS - gerenciar chaves de criptografia
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]usa chaves de criptografia para proteger credenciais e informações de conexão que são armazenadas em um banco de dados do servidor de relatório. No [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], o suporte à criptografia é dado por meio de uma combinação de chaves públicas, privadas e simétricas, usadas para proteger dados confidenciais. A chave simétrica é criada durante a inicialização do servidor de relatório quando você instala ou configura o servidor de relatório, sendo usada pelo servidor de relatório para criptografar dados confidenciais que estão armazenados no servidor de relatório. As chaves públicas e privadas são criadas pelo sistema operacional e são usadas para proteger a chave simétrica. Um par de chaves pública e privada é criado para cada instância do servidor de relatório, que armazena dados confidenciais em um banco de dados de servidor de relatório.  
  
 O gerenciamento das chaves de criptografia consiste na criação de uma cópia de backup da chave simétrica, além de saber quando e como restaurar, excluir ou alterar as chaves. Se você migrar a instalação de um servidor de relatório ou configurar uma implantação de expansão, deverá ter uma cópia de backup da chave simétrica, de maneira que seja possível aplicá-la à nova instalação.  
  
> [!IMPORTANT]  
>  Alterar periodicamente a chave de criptografia do Reporting Services é uma prática recomendada de segurança. Um momento indicado para alterar a chave é imediatamente após uma atualização de versão principal do Reporting Services. Alterar a chave depois de uma atualização minimiza a interrupção de serviço adicional causada pela alteração da chave de criptografia do Reporting Services fora do ciclo de atualização.  
  
 Para gerenciar chaves simétricas, você pode usar a ferramenta Configuração do Reporting Services ou o utilitário **rskeymgmt** . As ferramentas incluídas no [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] são usadas para gerenciar somente a chave simétrica (as chaves pública e privada são gerenciadas pelo sistema operacional). A ferramenta Configuração do Reporting Services e o utilitário **rskeymgmt** dão suporte às seguintes tarefas:  
  
-   Fazer o backup de uma cópia da chave simétrica, para que você possa usá-la para recuperar a instalação de um servidor de relatório ou como parte de uma migração planejada.  
  
-   Restaurar uma chave simétrica salva anteriormente para um banco de dados de servidor de relatório, permitindo que uma nova instância do servidor de relatório acesse dados existentes que ele não criptografou originalmente.  
  
-   Excluir os dados criptografados em um banco de dados de servidor de relatório no caso improvável de que você não mais possa acessar os dados criptografados.  
  
-   Recriar chaves simétricas e criptografar novamente os dados no caso improvável de que a chave simétrica seja comprometida. Como prática recomendável de segurança, você deve recriar a chave simétrica periodicamente (por exemplo, a cada tantos meses) a fim de proteger o banco de dados do servidor de relatório contra ataques cibernéticos que tentem decifrar a chave.  
  
-   Adicionar ou remover uma instância do servidor de relatório de uma implantação de expansão do servidor de relatório em que vários servidores de relatório compartilham um único banco de dados de servidor de relatório e a chave simétrica que fornece criptografia reversível para esse banco de dados.  
  
## <a name="in-this-section"></a>Nesta seção  
 [Inicializar um servidor de relatório &#40; Gerenciador de configurações do SSRS &#41;](../../reporting-services/install-windows/ssrs-encryption-keys-initialize-a-report-server.md)  
 Explica como as chaves de criptografia são criadas.  
  
 [Fazer backup e restaurar as chave de criptografia do Reporting Services](../../reporting-services/install-windows/ssrs-encryption-keys-back-up-and-restore-encryption-keys.md)  
 Explica como fazer o backup de chaves de criptografia e restaurá-las para recuperar ou migrar uma instalação de servidor de relatório.  
  
 [Criptografados de armazenamento de dados do servidor de relatório &#40; Gerenciador de configurações do SSRS &#41;](../../reporting-services/install-windows/ssrs-encryption-keys-store-encrypted-report-server-data.md)  
 Descreve criptografia em um servidor de relatório.  
  
 [Excluir e recriar chaves de criptografia &#40; Gerenciador de configurações do SSRS &#41;](../../reporting-services/install-windows/ssrs-encryption-keys-delete-and-re-create-encryption-keys.md)  
 Explica como é possível substituir uma chave simétrica por uma nova versão e como iniciar do princípio se as chaves simétricas não puderem ser validadas.  
  
 [Adicionar e remover chaves de criptografia para implantação em expansão &#40; Gerenciador de configurações do SSRS &#41;](../../reporting-services/install-windows/add-and-remove-encryption-keys-for-scale-out-deployment.md)  
 Explica como adicionar e remover chaves de criptografia para controlar quais servidores de relatório fazem parte de uma implantação de expansão.  
  
## <a name="see-also"></a>Consulte também  
[Gerenciador de Configurações do Reporting Services (Modo Nativo).](../../reporting-services/install-windows/reporting-services-configuration-manager-native-mode.md)
