---
title: Count 属性示例 (VJ++)
TOCTitle: Count property example (VJ++)
ms:assetid: 749de00a-7530-ea04-558c-34277c4d2f61
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249478(v=office.15)
ms:contentKeyID: 48545666
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 6b875e2b5dff6f3b6927e73105b6732dfaa6fd0b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32295441"
---
# <a name="count-property-example-vj"></a>Count 属性示例 (VJ++)


**适用于**：Access 2013、Office 2013

此示例使用 ***Employees***（雇员）数据库中的两个集合演示 [Count](count-property-ado.md) 属性。 该属性获得每个集合中的对象数，并设置枚举这两个集合的循环的上限。 另一种不使用 **Count** 属性枚举这些集合的方式是使用语句。

```java 
 
// BeginCountJ 
import com.ms.wfc.data.*; 
import java.io.* ; 
 
public class CountX 
{ 
 // The main entry point for the application. 
 
 public static void main (String[] args) 
 { 
 CountX(); 
 System.exit(0); 
 } 
 
 // CountX function 
 
 static void CountX() 
 { 
 
 // Define ADO Objects. 
 Recordset rstEmployees = null; 
 
 // Declarations. 
 BufferedReader in = 
 new BufferedReader (new InputStreamReader(System.in)); 
 String line = null; 
 String strCnn = "Provider='sqloledb';Data Source='MySqlServer';" 
 + "Initial Catalog='Pubs';Integrated Security='SSPI';"; 
 
 int intLoop; 
 int intDisplaySize = 20; 
 int recCount=0; 
 
 try 
 { 
 rstEmployees = new Recordset(); 
 
 // Open recordset with data from Employees table. 
 rstEmployees.open("employee", strCnn, 
 AdoEnums.CursorType.FORWARDONLY, 
 AdoEnums.LockType.READONLY, 
 AdoEnums.CommandType.TABLE); 
 
 // Print information about Fields collection. 
 System.out.println(rstEmployees.getFields().getCount() + 
 " Fields in Employees"); 
 for ( intLoop = 0; intLoop < 
 rstEmployees.getFields().getCount(); intLoop++) 
 { 
 System.out.println("\t" + 
 rstEmployees.getFields().getItem(intLoop).getName()); 
 } 
 System.out.println("\n\nPress <Enter> to continue.."); 
 in.readLine(); 
 
 // Print information about Properties collection. 
 System.out.println(rstEmployees.getProperties().getCount() + 
 " Properties in Employees"); 
 for ( intLoop = 0; intLoop < 
 rstEmployees.getProperties().getCount(); intLoop++) 
 { 
 System.out.println("\t" + 
 rstEmployees.getProperties().getItem(intLoop).getName()); 
 recCount++; 
 if ( recCount >= intDisplaySize) 
 { 
 System.out.println("\n\nPress <Enter> to continue.."); 
 in.readLine(); 
 recCount = 0; 
 } 
 } 
 System.out.println("\n\nPress <Enter> to continue.."); 
 in.readLine(); 
 
 } 
 catch( AdoException ae ) 
 { 
 // Notify user of any errors that result from ADO. 
 
 // Check for null pointer for connection object. 
 if (rstEmployees.getActiveConnection()==null) 
 { 
 System.out.println("Exception: " + ae.getMessage()); 
 } 
 else 
 { 
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
 
 // PrintIOError Function 
 
 static void PrintIOError( java.io.IOException je) 
 { 
 System.out.println("Error \n"); 
 System.out.println("\tSource = " + je.getClass() + "\n"); 
 System.out.println("\tDescription = " + je.getMessage() + "\n"); 
 } 
} 
 
// EndCountJ 
```

