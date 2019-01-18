---
title: NextRecordset 方法示例 (VJ++)
TOCTitle: NextRecordset method example (VJ++)
ms:assetid: 1803ce0e-43a6-0571-5703-525f1d2e29ea
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248930(v=office.15)
ms:contentKeyID: 48543457
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 0a520ae6a2480bec2220cc590c90058739737339
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28705636"
---
# <a name="nextrecordset-method-example-vj"></a><span data-ttu-id="4d4ec-102">NextRecordset 方法示例 (VJ++)</span><span class="sxs-lookup"><span data-stu-id="4d4ec-102">NextRecordset method example (VJ++)</span></span>


<span data-ttu-id="4d4ec-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="4d4ec-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="4d4ec-104">本示例使用 [NextRecordset](nextrecordset-method-ado.md) 方法来查看记录集中的数据，该方法使用由三个单独的 **SELECT** 语句构成的复合命令语句。</span><span class="sxs-lookup"><span data-stu-id="4d4ec-104">This example uses the [NextRecordset](nextrecordset-method-ado.md) method to view the data in a recordset that uses a compound command statement made up of three separate **SELECT** statements.</span></span>

```java 
 
// BeginNextRecordsetJ 
import java.io.*; 
import com.ms.wfc.data.*; 
 
public class NextRecordsetX 
{ 
 // The main entry point for the application. 
 
 public static void main (String[] args) 
 { 
 NextRecordsetX(); 
 System.exit(0); 
 } 
 // NextRecordsetX Function 
 static void NextRecordsetX() 
 { 
 // Define ADO Object 
 Recordset rstCompound = null; 
 
 // Declarations 
 BufferedReader in = 
 new BufferedReader(new InputStreamReader(System.in)); 
 String strCnn; 
 int intCount; 
 int intDisplayRecords = 15; 
 int intRecordCount; 
 
 try 
 { 
 // Open compound recordset. 
 strCnn = "Provider='sqloledb';Data Source='MySqlServer';" + 
 "Initial Catalog='Pubs';Integrated Security='SSPI';"; 
 
 rstCompound = new Recordset(); 
 rstCompound.open("select * from Authors;" + 
 "select * from stores;" + 
 "select * from jobs", strCnn, AdoEnums.CursorType.FORWARDONLY, 
 AdoEnums.LockType.READONLY,AdoEnums.CommandType.TEXT); 
 
 // Display results from each select statement. 
 intCount=1; 
 
 while (rstCompound != null) 
 { 
 System.out.println( 
 "Contents of recordset #" + intCount + "\n"); 
 intRecordCount = 0; 
 
 while(!rstCompound.getEOF()) 
 { 
 System.out.println( 
 rstCompound.getField(0).getString()+" " + 
 rstCompound.getField(1).getString()); 
 intRecordCount++; 
 
 rstCompound.moveNext(); 
 if ( intRecordCount == intDisplayRecords) 
 { 
 System.out.println("\nPress <Enter> to continue.."); 
 in.readLine(); 
 intRecordCount = 0; 
 } 
 } 
 System.out.println("\nPress <Enter> to continue.."); 
 in.readLine(); 
 
 rstCompound = rstCompound.nextRecordset(); 
 
 intCount++; 
 } 
 } 
 // System read requires this catch. 
 catch(java.io.IOException je) 
 { 
 PrintIOError(je); 
 } 
 catch(AdoException ae) 
 { 
 // Notify the user of any errors that result from ADO. 
 
 // As passing a recordset. check for the null pointer first 
 if(rstCompound!=null) 
 { 
 PrintProviderError(rstCompound.getActiveConnection()); 
 } 
 else 
 { 
 System.out.println("Exception: " + ae.getMessage()); 
 } 
 } 
 catch(java.lang.NullPointerException ne) 
 { 
 System.out.println("Error Description: " + ne.getMessage()); 
 } 
 
 finally 
 { 
 // Cleanup objects before exit. 
 if (rstCompound != null) 
 if (rstCompound.getState() == 1) 
 rstCompound.close(); 
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
// EndNextRecordsetJ 
```

