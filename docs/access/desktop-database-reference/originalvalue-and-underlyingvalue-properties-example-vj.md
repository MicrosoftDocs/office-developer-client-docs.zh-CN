---
title: OriginalValue 和 UnderlyingValue 属性示例 (VJ++)
TOCTitle: OriginalValue and UnderlyingValue properties example (VJ++)
ms:assetid: 622d0356-e33d-4378-df5e-8f15fa91d260
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249368(v=office.15)
ms:contentKeyID: 48545233
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: b2e7c70979b5bc5d791350e13fba744a34ee2e82
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288159"
---
# <a name="originalvalue-and-underlyingvalue-properties-example-vj"></a><span data-ttu-id="f59c3-102">OriginalValue 和 UnderlyingValue 属性示例 (VJ++)</span><span class="sxs-lookup"><span data-stu-id="f59c3-102">OriginalValue and UnderlyingValue properties example (VJ++)</span></span>


<span data-ttu-id="f59c3-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="f59c3-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="f59c3-104">本示例演示 [OriginalValue](originalvalue-property-ado.md) 和 [UnderlyingValue](underlyingvalue-property-ado.md) 属性，如果记录的基础数据在 [Recordset](recordset-object-ado.md) 批更新期间发生更改，则显示一条消息。</span><span class="sxs-lookup"><span data-stu-id="f59c3-104">This example demonstrates the [OriginalValue](originalvalue-property-ado.md) and [UnderlyingValue](underlyingvalue-property-ado.md) properties by displaying a message if a record's underlying data has changed during a [Recordset](recordset-object-ado.md) batch update.</span></span>

```java 
 
// BeginOriginalValueJ 
import com.ms.wfc.data.*; 
import java.io.* ; 
 
public class OriginalValueX 
{ 
 // The main entry point for the application. 
 
 public static void main (String[] args) 
 { 
 OriginalValueX(); 
 System.exit(0); 
 } 
 
 // OriginalValueX function 
 
 static void OriginalValueX() 
 { 
 // Define ADO Objects. 
 Connection cnConn1 = null; 
 Recordset rstTitles = null; 
 Field fldType = null; 
 
 // Declarations. 
 String strCnn = "Provider='sqloledb';Data Source='MySqlServer';" 
 + "Initial Catalog='Pubs';Integrated Security='SSPI';"; 
 BufferedReader in = 
 new BufferedReader (new InputStreamReader(System.in)); 
 
 try 
 { 
 // Open a connection. 
 cnConn1 = new Connection(); 
 cnConn1.open(strCnn); 
 
 // Open recordset for batch update. 
 rstTitles = new Recordset(); 
 rstTitles.setActiveConnection(cnConn1); 
 rstTitles.setCursorType(AdoEnums.CursorType.KEYSET); 
 rstTitles.setLockType(AdoEnums.LockType.BATCHOPTIMISTIC); 
 rstTitles.open("Titles",cnConn1, 
 AdoEnums.CursorType.KEYSET, 
 AdoEnums.LockType.BATCHOPTIMISTIC, 
 AdoEnums.CommandType.TABLE); 
 
 // Set field object variable for Type field. 
 fldType = rstTitles.getField("type"); 
 
 // Change the type of psychology titles. 
 while(!rstTitles.getEOF()) 
 { 
 if(rstTitles.getField("type").getString(). 
 trim().equals("psychology")) 
 fldType.setString("self_help"); 
 rstTitles.moveNext(); 
 } 
 
 // Similate a change by another user by updating 
 // data using a command string. 
 cnConn1.execute("UPDATE Titles SET type = 'sociology' " 
 + "WHERE type = 'psychology'"); 
 
 // Check for changes. 
 rstTitles.moveFirst(); 
 
 while(!rstTitles.getEOF()) 
 { 
 String strOriginalValue = 
 fldType.getOriginalValue().toString().trim(); 
 String strUnderlyingValue = 
 fldType.getUnderlyingValue().toString().trim(); 
 if(!(strOriginalValue.equals(strUnderlyingValue))) 
 { 
 System.out.println("Data has changed!" + "\n\n"); 
 System.out.println("\tTitle ID: " 
 + rstTitles.getField("title_id").getString().trim() + 
 "\n"); 
 System.out.println("\tCurrent value: " 
 + fldType.getString()+ "\n"); 
 System.out.println("\tOriginal value: " 
 + fldType.getOriginalValue().toString()+ "\n"); 
 System.out.println("\tUnderlying value: " 
 + fldType.getUnderlyingValue().toString()+ "\n"); 
 System.out.println("\n\nPress <Enter> to continue.."); 
 in.readLine(); 
 } 
 rstTitles.moveNext(); 
 } 
 // Cancel the update because this is a demonstration. 
 
 rstTitles.cancelBatch(); 
 
 // Restore original values. 
 cnConn1.execute("UPDATE Titles SET type = 'psychology' " 
 + "WHERE type = 'sociology'"); 
 } 
 catch( AdoException ae ) 
 { 
 // Notify user of any errors that result from ADO. 
 
 // As passing a Recordset, check for null pointer first. 
 if (rstTitles!= null) 
 { 
 PrintProviderError(rstTitles.getActiveConnection()); 
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
 if (rstTitles != null) 
 if (rstTitles.getState() == 1) 
 rstTitles.close(); 
 if (cnConn1 != null) 
 if (cnConn1.getState() == 1) 
 cnConn1.close(); 
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
// EndOriginalValueJ 
```

