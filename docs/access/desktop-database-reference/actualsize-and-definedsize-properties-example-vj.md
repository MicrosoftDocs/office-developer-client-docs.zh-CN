---
<span data-ttu-id="9091a-101"><<<<<<< 标头标题： ActualSize 和 DefinedSize 属性示例 （VJ + +） TOCTitle: ActualSize 和 DefinedSize 属性示例 （VJ + +） ms:assetid: 3a25d3b7-df53-66c1-6141-d51cd57aca96 ms:mtpsurl: https://msdn.microsoft.com/library/JJ249145(v=office.15) ms:contentKeyID:48544261 ms.date: 09/18/2015 mtps_version: office.15.aspx</span><span class="sxs-lookup"><span data-stu-id="9091a-101"><<<<<<< HEAD title: ActualSize and DefinedSize Properties Example (VJ++) TOCTitle: ActualSize and DefinedSize Properties Example (VJ++) ms:assetid: 3a25d3b7-df53-66c1-6141-d51cd57aca96 ms:mtpsurl: https://msdn.microsoft.com/library/JJ249145(v=office.15) ms:contentKeyID: 48544261 ms.date: 09/18/2015 mtps_version: v=office.15</span></span>
---

# <a name="actualsize-and-definedsize-properties-example-vj"></a><span data-ttu-id="9091a-102">ActualSize 和 DefinedSize 属性示例 (VJ++)</span><span class="sxs-lookup"><span data-stu-id="9091a-102">ActualSize and DefinedSize Properties Example (VJ++)</span></span>

<span data-ttu-id="9091a-103">=== 标题： ActualSize 和 DefinedSize 属性示例 （VJ + +） TOCTitle: ActualSize 和 DefinedSize 属性示例 （VJ + +） ms:assetid: 3a25d3b7-df53-66c1-6141-d51cd57aca96 ms:mtpsurl: https://msdn.microsoft.com/library/JJ249145(v=office.15) ms:contentKeyID: 48544261 ms.date: 10/17/2018mtps_version: office.15.aspx</span><span class="sxs-lookup"><span data-stu-id="9091a-103">======= title: ActualSize and DefinedSize properties example (VJ++) TOCTitle: ActualSize and DefinedSize properties example (VJ++) ms:assetid: 3a25d3b7-df53-66c1-6141-d51cd57aca96 ms:mtpsurl: https://msdn.microsoft.com/library/JJ249145(v=office.15) ms:contentKeyID: 48544261 ms.date: 10/17/2018 mtps_version: v=office.15</span></span>
---

# <a name="actualsize-and-definedsize-properties-example-vj"></a><span data-ttu-id="9091a-104">ActualSize 和 DefinedSize 属性示例 （VJ + +）</span><span class="sxs-lookup"><span data-stu-id="9091a-104">ActualSize and DefinedSize properties example (VJ++)</span></span>
>>>>>>> <span data-ttu-id="9091a-105">master</span><span class="sxs-lookup"><span data-stu-id="9091a-105">master</span></span>

<span data-ttu-id="9091a-106">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="9091a-106">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="9091a-107">此示例使用 [ActualSize](actualsize-property-ado.md) 和 [DefinedSize](definedsize-property-ado.md) 属性来显示字段的定义大小和实际大小。</span><span class="sxs-lookup"><span data-stu-id="9091a-107">This example uses the [ActualSize](actualsize-property-ado.md) and [DefinedSize](definedsize-property-ado.md) properties to display the defined size and actual size of a field.</span></span>

```java 
 
// BeginActualSizeJ 
import com.ms.wfc.data.*; 
import java.io.*; 
 
public class ActualSizeX 
{ 
 // The main entry point for the application. 
 
 public static void main (String[] args) 
 { 
 ActualSizeX(); 
 System.exit(0); 
 } 
 
 // ActualSizeX function 
 
 static void ActualSizeX() 
 { 
 
 // Define ADO Objects. 
 Recordset rstStores = null; 
 
 // Declarations. 
 BufferedReader in = new 
 BufferedReader(new InputStreamReader(System.in)); 
 String line = null; 
 String strCnn = "Provider='sqloledb';Data Source='MySqlServer';" 
 + "Initial Catalog='Pubs';Integrated Security='SSPI';"; 
 
 String strStoreName; 
 String strMessage; 
 String strDSize,strASize; 
 int intDefinedSize; 
 int intActualSize; 
 int intChoice = 0; 
 
 try 
 { 
 // Open recordset with Stores table. 
 rstStores = new Recordset(); 
 rstStores.open("stores", strCnn, 
 AdoEnums.CursorType.FORWARDONLY , 
 AdoEnums.LockType.READONLY , 
 AdoEnums.CommandType.TABLE); 
 
 // Loop through the Recordset displaying the contents 
 // of the stor_name field, the field's defined size 
 // and it's actual size. 
 
 while ( !(rstStores.getEOF( ))) // continuous loop 
 { 
 // Read data field in the variables. 
 strStoreName = rstStores.getField("stor_name").getString(); 
 intDefinedSize = 
 rstStores.getField("stor_name").getDefinedSize(); 
 strDSize = Integer.toString(intDefinedSize); 
 intActualSize = rstStores.getField 
 ("stor_name").getActualSize (); 
 strASize = Integer.toString(intActualSize); 
 
 // Display current record information. 
 strMessage = "\nStore name: " + strStoreName + "\n" 
 + "Defined Size : " + strDSize + "\n" 
 + "Actual Size : " + strASize; 
 
 System.out.println(strMessage); 
 System.out.println("\nPress <Enter> key to continue."); 
 in.readLine(); 
 rstStores.moveNext(); 
 } 
 } 
 catch( AdoException ae ) 
 { 
 // Notify user of any errors that result from ADO. 
 
 // Check for null pointer for connection object. 
 if (rstStores.getActiveConnection()==null) 
 System.out.println("Exception: " + ae.getMessage()); 
 // As passing a Recordset, check for null pointer first. 
 if (rstStores != null) 
 { 
 PrintProviderError(rstStores.getActiveConnection()); 
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
 if (rstStores != null) 
 if (rstStores.getState() == 1) 
 rstStores.close(); 
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
// EndActualSizeJ 
```

