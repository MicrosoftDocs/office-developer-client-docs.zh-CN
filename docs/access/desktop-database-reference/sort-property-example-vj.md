---
title: Sort 属性示例 (VJ++)
TOCTitle: Sort property example (VJ++)
ms:assetid: 29f34b9d-a75a-baa3-2505-ebd70e71950f
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249051(v=office.15)
ms:contentKeyID: 48543896
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 138364f58024f20d547a898ef4c0c00d4bd7893d
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28709080"
---
# <a name="sort-property-example-vj"></a><span data-ttu-id="4d4f4-102">Sort 属性示例 (VJ++)</span><span class="sxs-lookup"><span data-stu-id="4d4f4-102">Sort property example (VJ++)</span></span>


<span data-ttu-id="4d4f4-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="4d4f4-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="4d4f4-104">此示例使用[Recordset](recordset-object-ado.md)对象的[Sort](sort-property-ado.md)属性重新排列**Recordset**派生自***Pubs***数据库的***Authors***表的行。</span><span class="sxs-lookup"><span data-stu-id="4d4f4-104">This example uses the [Recordset](recordset-object-ado.md) object's [Sort](sort-property-ado.md) property to reorder the rows of a **Recordset** derived from the ***Authors*** table of the ***Pubs*** database.</span></span> <span data-ttu-id="4d4f4-105">由辅助实用程序例程打印每行。</span><span class="sxs-lookup"><span data-stu-id="4d4f4-105">A secondary utility routine prints each row.</span></span>

```java 
 
// BeginSortJ 
import com.ms.wfc.data.*; 
import java.io.* ; 
 
public class SortX 
{ 
 // The main entry point for the application. 
 
 public static void main (String[] args) 
 { 
 SortX(); 
 System.exit(0); 
 } 
 
 // SortX function 
 
 static void SortX() 
 { 
 // Define ADO Objects. 
 Connection cnConn1 = null; 
 Recordset rstAuthors = null; 
 
 // Declarations. 
 String strCnn = "Provider='sqloledb';Data Source='MySqlServer';" + 
 "Initial Catalog='Pubs';Integrated Security='SSPI';"; 
 
 try 
 { 
 cnConn1 = new Connection(); 
 cnConn1.open(strCnn); 
 rstAuthors = new Recordset(); 
 rstAuthors.setCursorLocation(AdoEnums.CursorLocation.CLIENT); 
 rstAuthors.open("SELECT * FROM Authors", 
 cnConn1, 
 AdoEnums.CursorType.STATIC, 
 AdoEnums.LockType.READONLY, 
 AdoEnums.CommandType.TEXT); 
 SortXprint("Initial Order",rstAuthors); 
 
 rstAuthors.setSort("au_lname ASC, au_fname ASC"); 
 SortXprint("Last Name Ascending",rstAuthors); 
 
 rstAuthors.setSort("au_lname DESC, au_fname ASC"); 
 SortXprint("Last Name Descending",rstAuthors); 
 } 
 catch( AdoException ae ) 
 { 
 // Notify user of any errors that result from ADO. 
 
 // As passing a Recordset, check for null pointer first. 
 if (rstAuthors != null) 
 { 
 PrintProviderError(rstAuthors.getActiveConnection()); 
 } 
 else 
 { 
 System.out.println("Exception: " + ae.getMessage()); 
 } 
 } 
 
 finally 
 { 
 // Cleanup objects before exit. 
 if (rstAuthors != null) 
 if (rstAuthors.getState() == 1) 
 rstAuthors.close(); 
 if (cnConn1 != null) 
 if (cnConn1.getState() == 1) 
 cnConn1.close(); 
 } 
 
 } 
 
 // SortXprint function 
 
 static void SortXprint(String strTitle,Recordset rstp) 
 { 
 // Declarations. 
 BufferedReader in = 
 new BufferedReader (new InputStreamReader(System.in)); 
 int intDisplaysize = 15; 
 int intCount = 1; 
 try 
 { 
 System.out.println("---------------" + 
 strTitle + 
 "---------------"); 
 System.out.println("First Name Last Name" + "\n" + 
 "-------------------------" + 
 "-------------------------"); 
 rstp.moveFirst(); 
 while(!rstp.getEOF()) 
 { 
 System.out.println(rstp.getField("au_fname").getString() + 
 " " + 
 rstp.getField("au_lname").getString()); 
 if(intCount % intDisplaysize == 0) 
 { 
 System.out.println("\nPress <Enter> to continue.."); 
 in.readLine(); 
 intCount = 0; 
 } 
 intCount++; 
 rstp.moveNext(); 
 } 
 System.out.println("\nPress <Enter> to continue.."); 
 in.readLine(); 
 } 
 catch( AdoException ae ) 
 { 
 // Notify user of any errors that result from ADO. 
 
 // As passing a Recordset, check for null pointer first. 
 if (rstp != null) 
 { 
 PrintProviderError(rstp.getActiveConnection()); 
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
// EndSortJ 
```

