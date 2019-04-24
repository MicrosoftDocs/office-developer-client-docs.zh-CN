---
title: CompareBookmarks 方法示例 (VJ++)
TOCTitle: CompareBookmarks method example (VJ++)
ms:assetid: f36f77ec-e51a-41dc-961f-0ec3166155bd
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250236(v=office.15)
ms:contentKeyID: 48548671
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 7f9a5b0e31381d36d523c23290076e0d9b07a01c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32296085"
---
# <a name="comparebookmarks-method-example-vj"></a><span data-ttu-id="33e3d-102">CompareBookmarks 方法示例 (VJ++)</span><span class="sxs-lookup"><span data-stu-id="33e3d-102">CompareBookmarks method example (VJ++)</span></span>


<span data-ttu-id="33e3d-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="33e3d-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="33e3d-104">以下示例展示了 [CompareBookmarks](comparebookmarks-method-ado.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="33e3d-104">This example demonstrates the [CompareBookmarks](comparebookmarks-method-ado.md) method.</span></span> <span data-ttu-id="33e3d-105">除非书签存在某些特殊之处，一般很少需要书签的相对值。</span><span class="sxs-lookup"><span data-stu-id="33e3d-105">The relative value of bookmarks is seldom needed unless a particular bookmark is somehow special.</span></span>

<span data-ttu-id="33e3d-106">将派生自 ***Authors***（作者）表的 [Recordset](recordset-object-ado.md) 的随机行指定为搜索目标。</span><span class="sxs-lookup"><span data-stu-id="33e3d-106">Designate a random row of a [Recordset](recordset-object-ado.md) derived from the ***Authors*** table as the target of a search.</span></span> <span data-ttu-id="33e3d-107">然后显示每一行相对于该目标的位置。</span><span class="sxs-lookup"><span data-stu-id="33e3d-107">Then display the position of each row relative to that target.</span></span>

```java 
 
// BeginCompareBookmarksJ 
import com.ms.wfc.data.*; 
import java.io.* ; 
import com.ms.com.*; 
 
public class CompareBookmarksX // 
{ 
 // The main entry point for the application. 
 
 public static void main (String[] args) 
 { 
 CompareBookmarksX(); 
 System.exit(0); 
 } 
 
 // CompareBookmarksX function 
 
 static void CompareBookmarksX() 
 { 
 // Define ADO Objects. 
 Recordset rstAuthors = null; 
 
 // Declarations. 
 BufferedReader in = 
 new BufferedReader (new InputStreamReader(System.in)); 
 String strCnn = "Provider='sqloledb';Data Source='MySqlServer';" + 
 "Initial Catalog='Pubs';Integrated Security='SSPI';"; 
 int intCount; 
 Variant varTarget = null; 
 int intResult; 
 String strAns; 
 int intDisplaySize = 15; 
 
 try 
 { 
 rstAuthors = new Recordset(); 
 rstAuthors.open("SELECT * FROM authors", 
 strCnn, 
 AdoEnums.CursorType.STATIC, 
 AdoEnums.LockType.READONLY, 
 AdoEnums.CommandType.TEXT); 
 intCount = rstAuthors.getRecordCount(); 
 System.out.println("Rows in the Recordset = " + 
 Integer.toString(intCount)); 
 
 // Exit if an empty recordset. 
 if(intCount == 0) 
 System.exit(0); 
 
 // Randomize. 
 intCount = (int)(intCount * Math.random()); 
 // Get position between 0 and count-1. 
 System.out.println("\nRandomly chosen row position = " + 
 Integer.toString(intCount)+ "\n"); 
 rstAuthors.move(intCount,new Integer(AdoEnums.Bookmark.FIRST)); // Move row to random position. 
 varTarget = (Variant)rstAuthors.getBookmark(); 
 // Remember the mystery row. 
 intCount = 0; 
 rstAuthors.moveFirst(); 
 
 // Loop through recordset. 
 while(!rstAuthors.getEOF()) 
 { 
 intResult = rstAuthors.compareBookmarks 
 ((Variant)rstAuthors.getBookmark(), varTarget); 
 if(intResult == AdoEnums.Compare.NOTEQUAL) 
 System.out.println("Row " + 
 Integer.toString(intCount) + 
 ": Bookmarks are not equal."); 
 else if(intResult == AdoEnums.Compare.NOTCOMPARABLE) 
 System.out.println("Row " + 
 Integer.toString(intCount) + 
 ": Bookmarks are not comparable."); 
 else 
 { 
 switch(intResult) 
 { 
 case AdoEnums.Compare.LESSTHAN : 
 strAns = "less than"; 
 break; 
 case AdoEnums.Compare.EQUAL : 
 strAns = "equal to"; 
 break; 
 case AdoEnums.Compare.GREATERTHAN : 
 strAns = "greater than"; 
 break; 
 default : 
 strAns = "in error comparing to"; 
 break; 
 } 
 System.out.println("Row position " + 
 Integer.toString(intCount) + 
 " is " + strAns + " the target."); 
 } 
 if(intCount % intDisplaySize == 0 && intCount > 0) 
 { 
 System.out.println("\nPress <Enter> to continue.."); 
 in.readLine(); 
 } 
 intCount++; 
 rstAuthors.moveNext(); 
 } 
 
 System.out.println("\nPress <Enter> to continue.."); 
 in.readLine(); 
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
 
 // System read requires this catch. 
 catch( java.io.IOException je) 
 { 
 PrintIOError(je); 
 } 
 
 finally 
 { 
 // Cleanup objects before exit. 
 if (rstAuthors != null) 
 if (rstAuthors.getState() == 1) 
 rstAuthors.close(); 
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
 
// EndCompareBookmarksJ 
```

