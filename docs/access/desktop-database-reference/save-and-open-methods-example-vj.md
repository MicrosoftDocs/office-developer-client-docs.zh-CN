---
title: Save 和 Open 方法示例 (VJ++)
TOCTitle: Save and Open methods example (VJ++)
ms:assetid: 15ad340a-2d32-3656-25d1-5c3927b9fed2
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248920(v=office.15)
ms:contentKeyID: 48543414
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 2536dd76c6080590852cba00eef9adca0e18d2cb
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32308958"
---
# <a name="save-and-open-methods-example-vj"></a>Save 和 Open 方法示例 (VJ++)


**适用于**：Access 2013、Office 2013

以下三个示例演示了如何将 [Save](save-method-ado.md) 和 **Open** 方法结合起来使用。

假设您正准备出差并希望携带数据库中的某个表。在出发前，您以 [Recordset](recordset-object-ado.md) 的形式访问数据并将其保存在便携表单中。到达目的地后，您将 **Recordset** 作为本地的已断开 **Recordset** 进行访问。您对 **Recordset** 进行更改，然后再次保存它。最后，您回家之后再次连接到数据库，并用出差时所做的更改更新该数据库。

```java 
 
// BeginSaveJ 
import com.ms.wfc.data.*; 
import java.io.* ; 
 
public class SaveX 
{ 
 // The main entry point for the application. 
 
 public static void main (String[] args) 
 { 
 SaveX1(); 
 SaveX2(); 
 SaveX3(); 
 System.exit(0); 
 } 
 
 // First, access and save the Authors table. 
 
 // SaveX1 function 
 
 static void SaveX1() 
 { 
 // Define ADO Objects. 
 Recordset rstAuthors = null; 
 
 // Declarations. 
 String strCnn = "Provider='sqloledb';Data Source='MySqlServer';" + 
 "Initial Catalog='Pubs';Integrated Security='SSPI';"; 
 BufferedReader in = 
 new BufferedReader(new InputStreamReader(System.in)); 
 File file; 
 
 try 
 { 
 rstAuthors = new Recordset(); 
 rstAuthors.setCursorLocation(AdoEnums.CursorLocation.CLIENT); 
 rstAuthors.open("SELECT * FROM Authors", 
 strCnn, 
 AdoEnums.CursorType.DYNAMIC, 
 AdoEnums.LockType.OPTIMISTIC, 
 AdoEnums.CommandType.TEXT); 
 
 // For the sake of illustration, save the recordset to a 
 //diskette in XML format. 
 file = new File("c:\\Pubs.xml"); 
 if(!file.exists()) 
 rstAuthors.save("c:\\Pubs.xml",AdoEnums.PersistFormat.XML); 
 else 
 { 
 System.out.println("\nFile already exists."); 
 System.out.println("\nPress <Enter> to continue.."); 
 in.readLine(); 
 System.exit(0); 
 } 
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
 
 // At this point, you have arrived at your destination. You will 
 // access the Authors table as a local, disconnected Recordset. 
 // Don't forget you must have the MSPersist provider on the machine 
 // you are using in order to access the saved file, a:\Pubs.xml. 
 
 // SaveX2 function 
 
 static void SaveX2() 
 { 
 // Define ADO Objects. 
 Recordset rstAuthors = null; 
 
 // Declarations. 
 BufferedReader in = 
 new BufferedReader(new InputStreamReader(System.in)); 
 
 try 
 { 
 rstAuthors = new Recordset(); 
 
 // For sake of illustration, we specify all parameters. 
 rstAuthors.open("c:\\Pubs.xml", 
 "Provider=MSPersist;", 
 AdoEnums.CursorType.FORWARDONLY, 
 AdoEnums.LockType.BATCHOPTIMISTIC, 
 AdoEnums.CommandType.FILE); 
 
 // Now you have a local, disconnected recordset. 
 // Edit it as you desire. 
 // (In this example, the change makes no difference). 
 rstAuthors.find("au_lname = 'Carson'"); 
 if(rstAuthors.getEOF()) 
 { 
 System.out.println("Name not found."); 
 System.out.println("\nPress <Enter> to continue.."); 
 in.readLine(); 
 return; 
 } 
 rstAuthors.getField("city").setString("Berkeley"); 
 rstAuthors.update(); 
 
 // Save changes in ADTG format this time, for illustration. 
 // Note that previous version on the diskette, as a:\Pubs.xml. 
 rstAuthors.save("c:\\Pubs.adtg",AdoEnums.PersistFormat.ADTG); 
 
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
 
 // Finally, update the database with your changes. 
 
 // SaveX3 function 
 
 static void SaveX3() 
 { 
 // Define ADO Objects. 
 Connection cnConn1 = null; 
 Recordset rstAuthors = null; 
 
 // Declarations. 
 String strCnn = "Provider='sqloledb';Data Source='MySqlServer';" + 
 "Initial Catalog='Pubs';Integrated Security='SSPI';"; 
 
 try 
 { 
 // If there is no ActiveConnection, you can open with defaults. 
 rstAuthors = new Recordset(); 
 rstAuthors.open("c:\\Pubs.adtg"); 
 
 // Connect to the database, associate the Recordset with 
 // connection, then update the database table with the changed 
 // Recordset. 
 cnConn1 = new Connection(); 
 cnConn1.open(strCnn); 
 rstAuthors.setActiveConnection(cnConn1); 
 rstAuthors.updateBatch(); 
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
// EndSaveJ 
```

