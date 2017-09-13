---
title: Trabalhando com os arquivos de Script do Console de exemplo (SybaseToSQL) | Microsoft Docs
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- sql-ssma
ms.tgt_pltfrm: 
ms.topic: article
applies_to:
- Azure SQL Database
- SQL Server
helpviewer_keywords:
- Sybase Console,Sample Console Script Files
ms.assetid: ef221118-b442-4ca6-9409-6ee1d9f8d948
caps.latest.revision: 9
author: Shamikg
ms.author: Shamikg
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: 3cb3c0f4f2e9f57b10527b9e524eae10563efebe
ms.contentlocale: pt-br
ms.lasthandoff: 08/02/2017

---
# <a name="working-with-the-sample-console-script-files-sybasetosql"></a>Trabalhando com os arquivos de Script do Console de exemplo (SybaseToSQL)
Alguns arquivos de exemplo foram fornecidos junto com o produto para a referência de usuário e uso. Esta seção descreve a maneira de personalizar facilmente esses scripts para se adequar às necessidades do usuário final.  
  
## <a name="sample-console-script-files"></a>Arquivos de Script do Console de exemplo  
Os seguintes arquivos de script de console de exemplo que abrangem cenários diferentes foi fornecidos para referência do usuário:  
  
-   ServersConnectionFileSample.xml  
  
-   VariableValueFileSample.xml  
  
-   AssessmentReportGenerationSample.xml  
  
-   SqlStatementConversionSample.xml  
  
-   ConversionAndDataMigrationSample.xml  
  
-   **ServersConnectionFileSample.xml:**  
  
    -   Este exemplo fornece diferentes modos de conexão disponível para o banco de dados de origem e de destino e o usuário pode selecionar qualquer modo de acordo com a necessidade. Este exemplo contém as definições de servidor.  
  
    -   O usuário pode se conectar ao banco de dados necessário, simplesmente alterando os valores para a origem necessários e definições de servidor de destino. No exemplo fornecido todos os valores foram fornecidos valores de variáveis como que estão disponíveis no **VariableValueFileSample.xml**.  Todos os outros parâmetros de conexão podem ser removidos do arquivo de conexão de servidor de trabalho do usuário.  
  
    -   Para obter mais informações sobre a conexão com o servidor de origem e de destino, consulte [criar os arquivos de Conexão do servidor &#40; SybaseToSQL &#41; ](../../ssma/sybase/creating-the-server-connection-files-sybasetosql.md).  
  
-   **VariableValueFileSample.xml:**  
    Arquivos de script de todas as variáveis que foram usadas no console de exemplo e `ServersConnectionFileSample.xml` foram agrupadas nesse arquivo. Para executar os scripts de console de exemplo que o usuário tem para simplesmente substituir a variável de exemplo valores com usuário definido aqueles em passam esse arquivo como um argumento de linha de comando adicionais, juntamente com o arquivo de script.  
  
    Para obter mais informações sobre o arquivo de valor de variável, consulte [criando arquivos de valor variável &#40; SybaseToSQL &#41; ](../../ssma/sybase/creating-variable-value-files-sybasetosql.md).  
  
-   **AssessmentReportGenerationSample.xml:**  
    Este exemplo permite que o usuário gerar um relatório de avaliação de xml que pode ser usado pelo usuário para análise antes de ele começa a converter e migrar dados.  
  
    No `generate-assessment-report` o usuário tem para mandatorily alterar o valor da variável de comando (consulte **VariableValueFileSample.xml**) no `object-name` atributo a ser o nome de banco de dados em uso pelo usuário. Dependendo do tipo de objeto especificado, o `object-type` valor também precisa ser alterado.  
  
    Se o usuário tem que avaliar a vários objetos de bancos de dados pode especificar vários `metabase-object` nós, conforme ilustrado a `generate-assessment-report` exemplo 4 do comando do arquivo de script de console de exemplo.  
  
    Para obter mais informações sobre como gerar relatórios, consulte [gerando relatórios &#40; SybaseToSQL &#41; ](../../ssma/sybase/generating-reports-sybasetosql.md).  
  
    > [!NOTE]  
    > -   Certifique-se de que o argumento de linha de comando do arquivo de valor da variável é passado para o aplicativo de console e VariableValueFileSample.xml é atualizado com o usuário especificado valores.  
    > -   Certifique-se de que o argumento de linha de comando do arquivo de conexão do servidor é passado para o aplicativo de console e o ServersConnectionFileSample.xml é atualizado com os valores de parâmetro de servidor correto.  
  
-   **SqlStatementConversionSample.xml:**  
    Este exemplo permite que o usuário gerar correspondente `t-sql` script para o banco de dados de origem `sql` comando fornecido como entrada.  
  
    No `convert-sql-statement` o usuário tem para mandatorily alterar o valor da variável de comando (consulte **VariableValueFileSample.xml**) no `context` de atributo para o nome do banco de dados que está sendo utilizado pelo usuário. O usuário também precisará alterar o `sql` valor de atributo para o banco de dados de origem `sql` comando que ele precisa para ser convertido.  
  
    O usuário também pode fornecer arquivos de sql a ser convertido. Isso tem sido ilustrado no `convert-sql-statement` exemplo 4 do comando do arquivo de script de console de exemplo.  
  
    > [!NOTE]  
    > Certifique-se de que o argumento de linha de comando do arquivo de valor da variável é passado para o aplicativo de console e VariableValueFileSample.xml é atualizado com o usuário especificado valores.  
  
-   **ConversionAndDataMigrationSample.xml:**  
     Este exemplo permite que o usuário executar uma migração de ponta a ponta de conversão de migração de dados. A lista de valores de atributo obrigatório que eles terão de alterar esteja listada abaixo:  
  
    **Nome de comando**  
  
    `map-schema`  
  
    Mapeamento de esquema de banco de dados de origem para o esquema de destino.  
  
    **Atributo**  
  
    -   `source-schema:`Especifica o banco de dados de origem que requer a ser convertido.  
  
    -   `sql-server-schema`: Especifica o banco de dados de destino que deve ser migrada para  
  
    **Nome de comando**  
  
    `convert-schema`  
  
    -   Executa a conversão de esquema de origem para o esquema de destino.  
  
    -   Se o usuário tem que avaliar a vários objetos de bancos de dados pode especificar vários `metabase-object` nós, conforme ilustrado a `convert-schema` exemplo 4 do comando do arquivo de script de console de exemplo.  
  
    **Atributo**  
  
    `object-name`: Especifique o banco de dados de origem / object name que requer a ser convertido. Certifique-se de que o correspondente `object-type` é alterada com base no tipo de objeto que é especificado do`object-name`  
  
    **Nome de comando**  
  
    `synchronize-target`  
  
    -   Os objetos de destino será sincronizado com o banco de dados de destino.  
  
    -   Se o usuário tem que avaliar a vários objetos de bancos de dados pode especificar vários `metabase-object` nós, conforme ilustrado a `synchronize-target` exemplo 3 do comando do arquivo de script de console de exemplo.  
  
    **Atributo**  
  
    `object-name:`Especifique o banco de dados do sql server / nome que requer a criação do objeto. Certifique-se de que o correspondente `object-type` é alterada com base no tipo de objeto que é especificado do`object-name`  
  
    **Nome de comando**  
  
    `migrate-data`  
  
    -   Migra os dados de origem para o destino.  
  
    -   Se o usuário tem que avaliar a vários objetos de bancos de dados pode especificar vários `metabase-object` nós, conforme ilustrado a `migrate-data` exemplo 2 do comando do arquivo de script de console de exemplo.  
  
    **Atributo**  
  
    `object-name:`Especifica o banco de dados de origem / tabelas nome que requer a serem migradas. Certifique-se de que o correspondente `object-type` é alterada com base no tipo de objeto que é especificado do`object-name`  
  
## <a name="see-also"></a>Consulte também  
[Criando arquivos do valor da variável &#40; SybaseToSQL &#41;](../../ssma/sybase/creating-variable-value-files-sybasetosql.md)  
[Criar os arquivos de Conexão do servidor &#40; SybaseToSQL &#41;](../../ssma/sybase/creating-the-server-connection-files-sybasetosql.md)  
[Gerando relatórios &#40; SybaseToSQL &#41;](../../ssma/sybase/generating-reports-sybasetosql.md)  
  
