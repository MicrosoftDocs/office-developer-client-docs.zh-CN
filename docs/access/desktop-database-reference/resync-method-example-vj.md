---
title: Resync 方法示例 (VJ++)
TOCTitle: Resync method example (VJ++)
ms:assetid: f8394f26-7a56-a342-ef99-9b32a3f8ebf5
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250261(v=office.15)
ms:contentKeyID: 48548780
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 1cd3d1bec0848255179d37af481e57685ff5322c
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28720868"
---
# <a name="resync-method-example-vj"></a><span data-ttu-id="2a0bd-102">Resync 方法示例 (VJ++)</span><span class="sxs-lookup"><span data-stu-id="2a0bd-102">Resync method example (VJ++)</span></span>


<span data-ttu-id="2a0bd-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="2a0bd-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="2a0bd-104">以下示例演示了如何使用 [Resync](resync-method-ado.md) 方法刷新静态记录集中的数据。</span><span class="sxs-lookup"><span data-stu-id="2a0bd-104">This example demonstrates using the [Resync](resync-method-ado.md) method to refresh data in a static recordset.</span></span>

```java 
 
// BeginResyncJ 
import java.io.*; 
import com.ms.wfc.data.*; 
 
public class ResyncX 
{ 
 // The main entry point of the application. 
 public static void main (String[] args) 
 { 
 ResyncX(); 
 System.exit(0); 
 } 
 static void ResyncX() 
 { 
 // Define ADO Objects. 
 Recordset rstTitles = null; 
 
 // Declarations. 
 BufferedReader in = 
 new BufferedReader(new InputStreamReader(System.in)); 
 String strCnn = "Provider='sqloledb';Data Source='MySqlServer';" + 
 "Initial Catalog='Pubs';Integrated Security='SSPI';"; 
 
 try 
 { 
 // Open recordset for Titles table. 
 rstTitles = new Recordset(); 
 rstTitles.setCursorLocation(AdoEnums.CursorLocation.CLIENT); 
 rstTitles.setCursorType(AdoEnums.CursorType.STATIC); 
 rstTitles.setLockType(AdoEnums.LockType.BATCHOPTIMISTIC); 
 rstTitles.open("Titles", strCnn, AdoEnums.CursorType.STATIC, 
 AdoEnums.LockType.BATCHOPTIMISTIC, 
 AdoEnums.CommandType.TABLE); 
 
 // Change the type of the first title in the recordset. 
 rstTitles.getField("type").setString("database"); 
 
 // Display the results of the change. 
 System.out.println("\n\n\tBefore resync:\n" + "\tTitle - " + 
 rstTitles.getField("title").getString() + 
 "\n\tType - " + rstTitles.getField("type").getString()); 
 
 // Resync with database and redisplay the results. 
 rstTitles.resync(); 
 System.out.println("\n\n\tAfter resync:\n" + "\tTitle - " + 
 rstTitles.getField("title").getString() + 
 "\n\tType - " + 
 rstTitles.getField("type").getString()+"\n"); 
 rstTitles.cancelBatch(); 
 
 System.out.println("\tPress <Enter> to continue.."); 
 in.readLine(); 
 
 } 
 catch(AdoException ae) 
 { 
 // Notify user of any errors that result from ADO. 
 
 // As passing a recordset, check for null pointer first. 
 if(rstTitles != null) 
 { 
 PrintProviderError(rstTitles.getActiveConnection()); 
 } 
 else 
 { 
 System.out.println("Exception: " + ae.getMessage()); 
 } 
 } 
 // System read requires this catch. 
 catch(java.io.IOException je) 
 { 
 PrintIOError(je); 
 } 
 
 finally 
 { 
 // Cleanup objects before exit. 
 if (rstTitles != null) 
 if (rstTitles.getState() == 1) 
 rstTitles.close(); 
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
// EndResyncJ 
```

