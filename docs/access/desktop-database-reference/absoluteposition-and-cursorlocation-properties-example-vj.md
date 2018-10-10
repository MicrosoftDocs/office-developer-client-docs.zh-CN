---
title: AbsolutePosition 和 CursorLocation 属性示例 (VJ++)
TOCTitle: AbsolutePosition and CursorLocation Properties Example (VJ++)
ms:assetid: 38872022-8a65-680f-20af-086e4d9d7b6a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249137(v=office.15)
ms:contentKeyID: 48544223
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: e864745821dd8d251740bfa816112a0a701c4784
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468813"
---
# <a name="absoluteposition-and-cursorlocation-properties-example-vj"></a><span data-ttu-id="c5034-102">AbsolutePosition 和 CursorLocation 属性示例 (VJ++)</span><span class="sxs-lookup"><span data-stu-id="c5034-102">AbsolutePosition and CursorLocation Properties Example (VJ++)</span></span>


<span data-ttu-id="c5034-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="c5034-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="c5034-p101">此示例演示 [AbsolutePosition](absoluteposition-property-ado.md) 属性如何跟踪枚举 [Recordset](recordset-object-ado.md) 的所有记录的循环的进度。它使用 [CursorLocation](cursorlocation-property-ado.md) 属性通过将游标设置为客户端游标来启用 **AbsolutePosition** 属性。</span><span class="sxs-lookup"><span data-stu-id="c5034-p101">This example demonstrates how the [AbsolutePosition](absoluteposition-property-ado.md) property can track the progress of a loop that enumerates all the records of a [Recordset](recordset-object-ado.md). It uses the [CursorLocation](cursorlocation-property-ado.md) property to enable the **AbsolutePosition** property by setting the cursor to a client cursor.</span></span>

```java 
 
// BeginAboslutePositionJ 
import com.ms.wfc.data.*; 
import java.io.*; 
 
public class AbsolutePositionX 
{ 
 // The main entry point for the application. 
 
 public static void main (String[] args) 
 { 
 AbsolutePositionX(); 
 System.exit(0); 
 } 
 
 //.AbsolutePositionX function 
 
 static void AbsolutePositionX() 
 { 
 
 // define ADO Objects. 
 Recordset rstEmployees = null; 
 
 // Declarations. 
 BufferedReader in = 
 new BufferedReader(new InputStreamReader(System.in)); 
 String line = null; 
 String strCnn = "Provider='sqloledb';Data Source='MySqlServer';" + 
 "Initial Catalog='Pubs';Integrated Security='SSPI';"; 
 
 String strLName; 
 String strMessage; 
 String strAbsolutePosition,strRecordCount; 
 int intAbsolutePosition; 
 int intRecordCount; 
 int intChoice; 
 
 try 
 { 
 
 rstEmployees = new Recordset(); 
 
 // Use client cursor to enable AbsolutePosition property. 
 rstEmployees.setCursorLocation( AdoEnums.CursorLocation.CLIENT); 
 
 // Open a recordset for Employees table using a client cursor. 
 rstEmployees.open("employee", strCnn, 
 AdoEnums.CursorType.FORWARDONLY , 
 AdoEnums.LockType.READONLY, 
 AdoEnums.CommandType.TABLE); 
 
 // Enumerate Recordset. 
 while ( !rstEmployees.getEOF()) // continuous loop 
 { 
 intRecordCount = rstEmployees.getRecordCount(); 
 strRecordCount = Integer.toString(intRecordCount); 
 
 // Read data field in the variables. 
 strLName = rstEmployees.getField("lname").getString(); 
 intAbsolutePosition = rstEmployees.getAbsolutePosition(); 
 strAbsolutePosition = Integer.toString(intAbsolutePosition); 
 
 // Display current record information. 
 strMessage = "\nEmployee: " + strLName + "\n" + "(Record " + 
 strAbsolutePosition + " of " +strRecordCount + " )"; 
 System.out.println(strMessage); 
 System.out.println( 
 "\nDo you want to continue (1 -> Yes / 2 -> No)?"); 
 //user types a number followed by enter (cr-lf). 
 line = in.readLine().trim(); 
 intChoice = Integer.parseInt(line); 
 if ( intChoice != 1) 
 break; 
 rstEmployees.moveNext(); 
 } 
 } 
 
 catch( NumberFormatException ne) 
 { 
 System.out.println("\nException : Integer Input required."); 
 System.exit(0); 
 } 
 
 catch( AdoException ae ) 
 { 
 // Notify user of any errors that result from ADO. 
 
 // Check for null pointer for connection object. 
 if (rstEmployees.getActiveConnection()== null) 
 System.out.println("Exception: " + ae.getMessage()); 
 // As passing a Recordset, check for null pointer first. 
 if (rstEmployees != null) 
 { 
 PrintProviderError(rstEmployees.getActiveConnection()); 
 } 
 else 
 { 
 System.out.println("Exception: " + ae.getMessage()); 
 } 
 } 
 
 // System read requires this catch. 
 catch( java.io.IOException je) 
 { 
 PrintIOError(je); 
 } 
 
 finally 
 { 
 // Cleanup objects before exit. 
 if (rstEmployees != null) 
 if (rstEmployees.getState() == 1) 
 rstEmployees.close(); 
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
 
 //.PrintIOError Function 
 
 static void PrintIOError( java.io.IOException je) 
 { 
 System.out.println("Error \n"); 
 System.out.println("\tSource = " + je.getClass() + "\n"); 
 System.out.println("\tDescription = " + je.getMessage() + "\n"); 
 } 
} 
 
// EndAbsolutePositionJ 
```

