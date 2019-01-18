---
title: Execute、Requery 和 Clear 方法示例 (VJ++)
TOCTitle: Execute, Requery, and Clear methods example (VJ++)
ms:assetid: 00210f2e-7454-25c7-a035-68344868fe11
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248774(v=office.15)
ms:contentKeyID: 48542897
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: c2d8af2ac4dc49d8ff2236ac49f372864d0d21f6
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28718243"
---
# <a name="execute-requery-and-clear-methods-example-vj"></a><span data-ttu-id="ea871-102">Execute、Requery 和 Clear 方法示例 (VJ++)</span><span class="sxs-lookup"><span data-stu-id="ea871-102">Execute, Requery, and Clear methods example (VJ++)</span></span>


<span data-ttu-id="ea871-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="ea871-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="ea871-p101">本示例演示同时从 **Command** 对象和 [Connection](command-object-ado.md) 对象运行时的 [Execute](connection-object-ado.md) 方法。本示例还使用 [Requery](requery-method-ado.md) 方法来检索记录集中的当前数据，并使用 [Clear](clear-method-ado.md) 方法来清除 [Errors](errors-collection-ado.md) 集合的内容。若要使该过程运行，需要 ExecuteCommand 和 PrintOutput 过程。</span><span class="sxs-lookup"><span data-stu-id="ea871-p101">This example demonstrates the **Execute** method when run from both a [Command](command-object-ado.md) object and a [Connection](connection-object-ado.md) object. It also uses the [Requery](requery-method-ado.md) method to retrieve current data in a recordset, and the [Clear](clear-method-ado.md) method to clear the contents of the [Errors](errors-collection-ado.md) collection. The ExecuteCommand and PrintOutput procedures are required for this procedure to run.</span></span>

```java 
 
// BeginExecuteJ 
// The WFC class includes the ADO objects. 
import com.ms.wfc.data.*; 
import java.io.*; 
 
public class ExecuteX 
{ 
 // Main Function 
 
 public static void main (String[] args) 
 { 
 ExecuteX(); 
 } 
 
 // ExecuteX Function 
 
 static void ExecuteX() 
 { 
 // Define string variables. 
 String strSQLChange = "UPDATE Titles SET Type = " 
 + "'self_help' WHERE Type = 'psychology'"; 
 String strSQLRestore = "UPDATE Titles SET Type = " 
 + "'psychology' WHERE Type = 'self_help'"; 
 String strCnn = "Provider='sqloledb';Data Source='MySqlServer';" 
 + "Initial Catalog='Pubs';Integrated Security='SSPI';"; 
 
 // Define ADO objects. 
 Connection cnConn1 = null; 
 Command cmdChange = null; 
 Recordset rsTitles = null; 
 
 try 
 { 
 // Open connection. 
 cnConn1 = new Connection (); 
 cnConn1.open(strCnn, "", "", AdoEnums.CommandType.UNSPECIFIED); 
 
 // Create command object. 
 cmdChange = new Command(); 
 cmdChange.setActiveConnection (cnConn1); 
 cmdChange.setCommandText (strSQLChange); 
 
 // Open recordset with Titles table. 
 rsTitles = new Recordset(); 
 rsTitles.open("Titles", cnConn1, 
 AdoEnums.CursorType.STATIC, 
 AdoEnums.LockType.OPTIMISTIC, 
 AdoEnums.CommandType.TABLE); 
 
 // Print report of original data. 
 System.out.println("\n\n\tData in Titles table " 
 + "before executing the query: \n"); 
 PrintOutput(rsTitles); 
 
 // Clear extraneous errors from the Errors collection. 
 cnConn1.getErrors().clear(); 
 
 // Call the ExecuteCommand subroutine to 
 // execute cmdChange command. 
 ExecuteCommand(cmdChange, rsTitles); 
 
 // Print report of new data. 
 System.out.println("\n\n\tData in Titles table after " 
 + "executing the query: \n"); 
 PrintOutput(rsTitles); 
 
 // Use the Connection object's execute method to 
 // execute SQL statement to restore data. 
 cnConn1.execute(strSQLRestore); 
 
 // Print report of restored data. 
 System.out.println("\n\n\tData after executing the query " 
 + "to restore the original information: \n"); 
 PrintOutput(rsTitles); 
 } // End Try statement. 
 catch( AdoException ae ) 
 { 
 // Notify user of any errors that result from ADO. 
 
 // As passing a Recordset, check for null pointer first. 
 if (rsTitles != null) 
 { 
 PrintProviderError(rsTitles.getActiveConnection()); 
 } 
 else 
 { 
 System.out.println("Exception: " + ae.getMessage()); 
 } 
 } 
 
 finally 
 { 
 // Cleanup objects before exit. 
 if (rsTitles != null) 
 if (rsTitles.getState() == 1) 
 rsTitles.close(); 
 if (cnConn1 != null) 
 if (cnConn1.getState() == 1) 
 cnConn1.close(); 
 } 
 } 
 
 // ExecuteCommand Function 
 
 static void ExecuteCommand(Command cmdTemp, Recordset rstTemp) 
 { 
 try 
 { 
 // CommandText property already set before function was called. 
 cmdTemp.setCommandType(AdoEnums.CommandType.TEXT); 
 cmdTemp.execute(); 
 
 // Retrieve the current data by requerying the recordset. 
 rstTemp.requery(AdoEnums.CommandType.UNKNOWN); 
 } 
 catch( AdoException ae ) 
 { 
 // Notify user of any errors that result from ADO. 
 PrintProviderError(rstTemp.getActiveConnection()); 
 } 
 } 
 
 // PrintOutput Function 
 
 static void PrintOutput(Recordset rstTemp) 
 { 
 // Declarations. 
 BufferedReader in = new 
 BufferedReader(new InputStreamReader(System.in)); 
 
 // Ensure at top of recordset. 
 rstTemp.moveFirst(); 
 
 // If EOF is true, then no data and skip print loop. 
 if( rstTemp.getEOF() ) 
 { 
 System.out.println("\tRecordset empty\n"); 
 } 
 else 
 { 
 // Enumerate Recordset and print data from each. 
 while( !(rstTemp.getEOF()) ) 
 { 
 // Convert variant string to convertable string type. 
 System.out.println("\t" 
 + rstTemp.getFields().getItem("Title").getValue() + " " 
 + rstTemp.getFields().getItem("Type").getValue() + "\n"); 
 rstTemp.moveNext(); 
 } 
 } 
 try 
 { 
 System.out.println("\nPress <Enter> key to continue."); 
 in.readLine(); 
 } 
 // System read requires this catch. 
 catch( java.io.IOException je) 
 { 
 PrintIOError(je); 
 } 
 } 
 
 // PrintProviderError Function 
 
 static void PrintProviderError( Connection Cnn1 ) 
 { 
 // Print Provider errors from Connection object. 
 // ErrItem is an item object in the Connections Errors collection. 
 com.ms.wfc.data.Error ErrItem = null; 
 long nCount = 0; 
 int i = 0; 
 
 nCount = Cnn1.getErrors().getCount(); 
 
 // If there are any errors in the collection, print them. 
 if( nCount > 0); 
 { 
 // Collection ranges from 0 to nCount - 1 
 for (i = 0; i< nCount; i++) 
 { 
 ErrItem = Cnn1.getErrors().getItem(i); 
 System.out.println("\t Error number: " + ErrItem.getNumber() 
 + "\t" + ErrItem.getDescription() ); 
 } 
 } 
 
 } 
 
 // PrintIOError Function 
 
 static void PrintIOError( java.io.IOException je) 
 { 
 System.out.println("Error \n"); 
 System.out.println("\tSource = " + je.getClass() + "\n"); 
 System.out.println("\tDescription = " + je.getMessage() + "\n"); 
 } 
} 
// EndExecuteJ 
```

