---
title: OpenSchema 方法示例 (VJ++)
TOCTitle: OpenSchema method example (VJ++)
ms:assetid: a76f2c21-d535-a1f5-c541-adaab21c87d0
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249773(v=office.15)
ms:contentKeyID: 48546877
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 8c66c16e8e110fd9565b9417c70e98247f2abc24
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288327"
---
# <a name="openschema-method-example-vj"></a>OpenSchema 方法示例 (VJ++)


**适用于**：Access 2013、Office 2013

本示例使用 [OpenSchema](openschema-method-ado.md) 方法来显示 ***Pubs*** 数据库中每个表的名称和类型。

```java 
 
// BeginOpenSchemaJ 
import com.ms.wfc.data.*; 
import java.io.*; 
import com.ms.com.*; 
 
public class OpenSchemaX 
{ 
 // The main entry point of the application. 
 
public static void main (String[] args) 
{ 
 System.out.println("\nResults for OpenSchemaX:\n\n"); 
 OpenSchemaX(); 
 System.out.println("\nResults for OpenSchemaX2:\n\n"); 
 OpenSchemaX2(); 
 System.exit(0); 
} 
 
// OpenSchemaX Function 
 static void OpenSchemaX() 
 { 
 // Define ADO Objects 
 Connection cnn1 = null; 
 Recordset rstSchema = null; 
 
 // Declarations 
 String strCnn; 
 BufferedReader in = new BufferedReader(new InputStreamReader(System.in)); 
 int intDisplayRecords = 5; 
 int intRecordCount = 0; 
 
 try 
 { 
 
 cnn1 = new Connection(); 
 strCnn = "Provider = Microsoft.Jet.OLEDB.4.0;" + 
 "Data Source=C:\\Program Files\\Microsoft " + 
 "Office\\Office\\Samples\\Northwind.mdb;"; 
 cnn1.open(strCnn); 
 rstSchema = cnn1.openSchema(AdoEnums.Schema.TABLES); 
 
 while (!rstSchema.getEOF()) 
 { 
 
 System.out.println("Table Name: " + 
 rstSchema.getField("TABLE_NAME").getString()+"\n"+ 
 "Table Type: " + 
 rstSchema.getField("TABLE_TYPE").getString()+"\n"); 
 intRecordCount++; 
 if ( intRecordCount == intDisplayRecords) 
 { 
 System.out.println("Press <Enter> to continue.."); 
 in.readLine(); 
 intRecordCount = 0; 
 } 
 rstSchema.moveNext(); 
 
 } 
 System.out.println("Press <Enter> to continue.."); 
 in.readLine(); 
 
 } 
 catch(AdoException ae) 
 { 
 // Notify user of any errors that result from ADO. 
 
 // As passing a Recordset, check for null pointer first. 
 if(rstSchema != null) 
 { 
 PrintProviderError(rstSchema.getActiveConnection()); 
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
 if (rstSchema != null) 
 if (rstSchema.getState() == 1) 
 rstSchema.close(); 
 if (cnn1 != null) 
 if (cnn1.getState() == 1) 
 cnn1.close(); 
 } 
 } 
 
 // OpenSchemaX2 Function 
 
 static void OpenSchemaX2() 
 { 
 // Define ADO Objects 
 Connection cnn2 = null; 
 Recordset rstSchema = null; 
 
 // Declarations 
 String strCnn; 
 BufferedReader in = 
 new BufferedReader(new InputStreamReader(System.in)); 
 int intDisplayRecords = 5; 
 int intRecordCount = 0; 
 
 try 
 { 
 cnn2 = new Connection(); 
 strCnn = "Provider = Microsoft.Jet.OLEDB.4.0;" + 
 "Data Source=C:\\Program Files\\Microsoft " + 
 "Office\\Office\\Samples\\Northwind.mdb;"; 
 cnn2.open(strCnn); 
 
 Variant[] va = new Variant[4]; 
 va[0] = new Variant(); 
 va[1] = new Variant(); 
 va[2] = new Variant(); 
 va[3] = new Variant("VIEW"); 
 rstSchema = cnn2.openSchema(AdoEnums.Schema.TABLES,(Object[])va); 
 
 while (!rstSchema.getEOF()) 
 { 
 System.out.println("Table Name: " + 
 rstSchema.getField("TABLE_NAME").getString()+"\n"+ 
 "Table Type: " + 
 rstSchema.getField("TABLE_TYPE").getString()+"\n"); 
 intRecordCount++; 
 if ( intRecordCount == intDisplayRecords) 
 { 
 System.out.println("Press <Enter> to continue.."); 
 in.readLine(); 
 intRecordCount = 0; 
 } 
 rstSchema.moveNext(); 
 
 } 
 System.out.println("Press <Enter> to continue.."); 
 in.readLine(); 
 
 } 
 catch(AdoException ae) 
 { 
 // Notify user of any errors that result from ADO. 
 
 // As passing a Recordset, check for null pointer first. 
 if(rstSchema != null) 
 { 
 PrintProviderError(rstSchema.getActiveConnection()); 
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
 // Cleanup Objects before exit. 
 rstSchema.close(); 
 cnn2.close(); 
 // Cleanup objects before exit. 
 if (rstSchema != null) 
 if (rstSchema.getState() == 1) 
 rstSchema.close(); 
 if (cnn2 != null) 
 if (cnn2.getState() == 1) 
 cnn2.close(); 
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
// EndOpenSchemaJ 
```

