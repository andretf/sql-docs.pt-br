---
title: "Criar um Gerenciador de Conexão personalizado | Microsoft Docs"
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- custom connection managers [Integration Services], creating
ms.assetid: e83f8e02-ace4-42e0-b979-2f6be1460985
caps.latest.revision: 25
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: 2c617741134c19c012f487bc00263c2e4b071810
ms.contentlocale: pt-br
ms.lasthandoff: 08/03/2017

---
# <a name="creating-a-custom-connection-manager"></a>Criando um gerenciador de conexões personalizado
  As etapas a seguir para criar um gerenciador de conexões personalizado são semelhantes às etapas de criação de qualquer outro objeto personalizado do [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)]:  
  
-   Crie uma classe nova herdada da classe base. Para um gerenciador de conexões, a classe base é <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase>.  
  
-   Aplique o atributo que identifica o tipo de objeto para a classe. Para um gerenciador de conexões, o atributo é <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute>.  
  
-   Substitua a implementação dos métodos e propriedades da classe base. Para um gerenciador de conexões, eles incluem a propriedade <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ConnectionString%2A> e os métodos <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.AcquireConnection%2A> e <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase.ReleaseConnection%2A>.  
  
-   Opcionalmente, desenvolva uma interface de usuário personalizada. Para um gerenciador de conexões, isso requer uma classe que implemente a interface <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsConnectionManagerUI>.  
  
> [!NOTE]  
>  A maioria das tarefas, fontes e destinos incluídos no [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] funcionam somente com tipos específicos de gerenciadores de conexões internos. Portanto, esses exemplos não podem ser testados com as tarefas e componentes internos.  
  
## <a name="getting-started-with-a-custom-connection-manager"></a>Guia de Introdução com um gerenciador de conexões personalizado  
  
### <a name="creating-projects-and-classes"></a>Criando projetos e classes  
 Como todos os gerenciadores de conexões gerenciados derivam da classe base <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManagerBase>, o primeiro passo para criar um gerenciador de conexões personalizado é criar um projeto de biblioteca de classes na linguagem de programação gerenciada de sua preferência e criar uma classe herdada da classe base. Esta classe derivada, você substituirá os métodos e propriedades da classe base para implementar sua funcionalidade personalizada.  
  
 Na mesma solução, crie um segundo projeto de biblioteca de classe para a interface de usuário personalizada. Recomenda-se um assembly separado para a interface do usuário para facilitar a implantação, pois ela permite que você atualize e implemente de novo o gerenciador de conexões ou sua interface do usuário de forma independente.  
  
 Configure ambos os projetos para atribuir os assemblies que serão gerados no momento de compilação usando um arquivo de chave de nome forte.  
  
### <a name="applying-the-dtsconnection-attribute"></a>Aplicando o atributo DtsConnection  
 Aplique o atributo <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute> à classe que você criou para identificá-la como um gerenciador de conexões. Esse atributo fornece informações de tempo de design como o nome, a descrição e o tipo de conexão do gerenciador de conexões. O <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute.ConnectionType%2A> e **descrição** propriedades correspondem ao **tipo** e **descrição** colunas exibidas no **adicionar Gerenciador de Conexão SSIS** caixa de diálogo que é exibida ao configurar as conexões de um pacote de [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].  
  
 Use a propriedade <xref:Microsoft.SqlServer.Dts.Runtime.DtsConnectionAttribute.UITypeName%2A> para vincular o gerenciador de conexões à sua interface do usuário personalizada. Para obter o token de chave pública é necessário para essa propriedade, você pode usar **sn.exe -t** para exibir o token de chave pública do arquivo de par de chaves (. snk) que você pretende usar para assinar o assembly de interface do usuário.  
  
```vb  
<DtsConnection(ConnectionType:="SQLVB", _  
  DisplayName:="SqlConnectionManager (VB)", _  
  Description:="Connection manager for Sql Server", _  
  UITypeName:="SqlConnMgrUIVB.SqlConnMgrUIVB,SqlConnMgrUIVB,Version=1.0.0.0,Culture=neutral,PublicKeyToken=<insert public key token here>")> _  
Public Class SqlConnMgrVB  
  Inherits ConnectionManagerBase  
  . . .  
End Class  
```  
  
```csharp  
[DtsConnection(ConnectionType = "SQLCS",  
  DisplayName = "SqlConnectionManager (CS)",  
  Description = "Connection manager for Sql Server",  
  UITypeName = "SqlConnMgrUICS.SqlConnMgrUICS,SqlConnMgrUICS,Version=1.0.0.0,Culture=neutral,PublicKeyToken=<insert public key token here>")]  
public class SqlConnMgrCS :  
ConnectionManagerBase  
{  
  . . .  
}  
```  
  
## <a name="building-deploying-and-debugging-a-custom-connection-manager"></a>Compilando, implantando e depurando um gerenciador de conexões personalizado  
 As etapas para compilar, implantar e depurar um gerenciador de conexões personalizado no [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] são semelhantes às etapas para outros tipos de objetos personalizados. Para obter mais informações, consulte [compilando, implantando e Debugging Custom Objects](../../../integration-services/extending-packages-custom-objects/building-deploying-and-debugging-custom-objects.md).    
  
## <a name="see-also"></a>Consulte também  
 [Codificando um Gerenciador de Conexão personalizado](../../../integration-services/extending-packages-custom-objects/connection-manager/coding-a-custom-connection-manager.md)   
 [Desenvolvendo uma Interface de usuário para um Gerenciador de Conexão personalizada](../../../integration-services/extending-packages-custom-objects/connection-manager/developing-a-user-interface-for-a-custom-connection-manager.md)  
  
  