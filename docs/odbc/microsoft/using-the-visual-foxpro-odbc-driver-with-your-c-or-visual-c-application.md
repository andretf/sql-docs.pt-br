---
title: Usar o Driver ODBC do Visual FoxPro com C ou Visual C++ aplicativo | Microsoft Docs
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
- FoxPro ODBC driver [ODBC], C or C++ applications
- C++ applications [ODBC]
- Visual FoxPro ODBC driver [ODBC], C or C++ applications
- Visual FoxPro data [ODBC], C or C++ applications
- C applications [ODBC]
ms.assetid: beb11a68-849e-4fe0-b217-d3722b1b1389
caps.latest.revision: "9"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: eb3d94f0534d7c86dc4c0c8b54804d153281f29a
ms.sourcegitcommit: cc71f1027884462c359effb898390c8d97eaa414
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/21/2017
---
# <a name="use-the-visual-foxpro-odbc-driver-with-your-c-or-visual-c-application"></a>Usar o Driver ODBC do Visual FoxPro com o C ou Visual C++ de aplicativos
Seu aplicativo C ou C++ se comunica com os dados do Visual FoxPro, enviando um [SQLExecute](../../odbc/microsoft/sqlexecute-visual-foxpro-odbc-driver.md) ou [SQLExecDirect](../../odbc/microsoft/sqlexecdirect-visual-foxpro-odbc-driver.md) instrução do Visual FoxPro. Essa instrução pode conter o seguinte:  
  
-   Instruções SQL nativas para a linguagem do Visual FoxPro, como o [DROP TABLE](../../odbc/microsoft/drop-table-command.md) comando.  
  
-   [Suporte a gramática de SQL ODBC](../../odbc/microsoft/supported-odbc-sql-grammar-visual-foxpro-odbc-driver.md).  
  
-   A linguagem do Visual FoxPro não SQL, como [suporte para comandos SET](../../odbc/microsoft/supported-set-commands-visual-foxpro-odbc-driver.md).  
  
 Para obter mais informações sobre SQL nativo do Visual FoxPro, consulte a documentação do Visual FoxPro.  
  
## <a name="example-using-the-visual-foxpro-odbc-driver-with-your-c-or-c-application"></a>Exemplo: Usando o Driver ODBC do Visual FoxPro com seu aplicativo C ou C++  
 O exemplo a seguir usa a API de C do ODBC para recuperar dados armazenados no campo Sobrenome da tabela employee do banco de dados de exemplo do Microsoft® Visual FoxPro denominado TasTrade. Este banco de dados é fornecido com o Visual FoxPro e é instalado por padrão no seguinte local:  
  
 `c:\vfp\samples\mainsamp\data\tastrade.dbc`  
  
 O exemplo exibe um sobrenome ao mesmo tempo, permitindo que você clique Okey na caixa de mensagem para ver o nome do último próximo. Presume-se que uma fonte de dados denominada Tastrade configurada para usar o banco de dados Tastrade.dbc.  
  
> [!NOTE]  
>  Verificação de erros deve ser executada em todas as chamadas de API de ODBC; Este exemplo exclui as verificações de erro por questão de brevidade.  
  
```  
// FoxPro_ODBC_Driver_with_C.cpp  
// compile with: odbc32.lib user32.lib /c  
#include <windows.h>  
#include <sql.h>  
#include <sqlext.h>  
#include <stdio.h>  
#include <mbstring.h>  
  
#define MAX_DATA 100  
#define MYSQLSUCCESS(rc) ((rc==SQL_SUCCESS)||(rc==SQL_SUCCESS_WITH_INFO))  
  
class direxec {  
   RETCODE rc;        // ODBC return code  
   HENV henv;         // Environment     
   HDBC hdbc;         // Connection handle  
   HSTMT hstmt;       // Statement handle  
   unsigned char szData[MAX_DATA];   // Returned data storage  
   SDWORD cbData;     // Output length of data  
   unsigned char chr_ds_name[SQL_MAX_DSN_LENGTH];   // Data source name  
  
public:  
   direxec();           // Constructor  
   void sqlconn();      // Allocate env, stat, and conn  
   void sqlexec(unsigned char *);   // Execute SQL statement  
   void sqldisconn();   // Free pointers to env, stat, conn, and disconnect  
   void error_out();    // Displays errors  
};  
  
// Constructor initializes the string chr_ds_name with the data source name.  
direxec::direxec() {  
   _mbscpy_s(chr_ds_name, (const unsigned char *)"tastrade");  
}  
  
// Allocate environment handle, allocate connection handle,  
// connect to data source, and allocate statement handle.  
void direxec::sqlconn() {  
   SQLAllocEnv(&henv);  
   SQLAllocConnect(henv, &hdbc);  
   rc=SQLConnect(hdbc, chr_ds_name, SQL_NTS, NULL, 0, NULL, 0);  
  
   // Deallocate handles, display error message, and exit.  
   if (!MYSQLSUCCESS(rc)) {  
      SQLFreeEnv(henv);  
      SQLFreeConnect(hdbc);  
      error_out();  
      exit(-1);  
   }  
  
   rc = SQLAllocStmt(hdbc, &hstmt);  
}  
  
// Execute SQL command with SQLExecDirect() ODBC API.  
void direxec::sqlexec(unsigned char * cmdstr) {  
   rc = SQLExecDirect(hstmt, cmdstr, SQL_NTS);  
   if (!MYSQLSUCCESS(rc)) {   // Error  
      error_out();  
      // Deallocate handles and disconnect.  
      SQLFreeStmt(hstmt, SQL_DROP);  
      SQLDisconnect(hdbc);  
      SQLFreeConnect(hdbc);  
      SQLFreeEnv(henv);  
      exit(-1);  
   }  
   else {  
      for (rc = SQLFetch(hstmt) ; rc == SQL_SUCCESS; rc=SQLFetch(hstmt)) {  
         SQLGetData(hstmt, 1, SQL_C_CHAR, szData, sizeof(szData), &cbData);  
         // In this example, the data is returned in a messagebox for  
         // simplicity. However, normally the SQLBindCol() ODBC API could  
         // be called to bind individual data rows and assign for a rowset.  
         MessageBox(NULL, (const char *)szData, "ODBC", MB_OK);  
      }  
   }  
}  
  
// Free the statement handle, disconnect, free the connection handle, and  
// free the environment handle.  
void direxec::sqldisconn() {  
   SQLFreeStmt(hstmt, SQL_DROP);  
   SQLDisconnect(hdbc);  
   SQLFreeConnect(hdbc);  
   SQLFreeEnv(henv);  
}  
  
// Display error message in a message box that has an OK button.  
void direxec::error_out() {  
   unsigned char szSQLSTATE[10];  
   SDWORD nErr;  
   unsigned char msg[SQL_MAX_MESSAGE_LENGTH + 1];  
   SWORD cbmsg;  
  
   while(SQLError(0, 0, hstmt, szSQLSTATE, &nErr, msg, sizeof(msg), &cbmsg) == SQL_SUCCESS) {  
      sprintf_s((char *)szData, MAX_DATA, "Error:\nSQLSTATE=%s, Native error=%ld, msg='%s'",   
         szSQLSTATE, nErr, msg);  
  
      MessageBox(NULL, (const char *)szData, "ODBC Error", MB_OK);  
   }  
}  
  
int main (){  
   // Declare an instance of the direxec object.  
   direxec x;  
  
   // Allocate handles and connect.  
   x.sqlconn();  
  
   // Execute SQL command "SELECT last_name FROM employee".  
   x.sqlexec((UCHAR FAR *)"SELECT last_name FROM employee");  
  
   // Free handles, and disconnect.  
   x.sqldisconn();  
  
   // Return success code; example executed successfully.  
   return (TRUE);  
}  
```
