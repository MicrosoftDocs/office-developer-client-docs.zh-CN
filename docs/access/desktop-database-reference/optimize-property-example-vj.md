---
<span data-ttu-id="1bb02-101"><<<<<<< 标头标题： 优化属性示例 （VJ + +） TOCTitle： 优化属性示例 （VJ + +） === 标题： Optimize 属性示例 （VJ + +） TOCTitle: Optimize 属性示例 （VJ + +）</span><span class="sxs-lookup"><span data-stu-id="1bb02-101"><<<<<<< HEAD title: Optimize Property Example (VJ++) TOCTitle: Optimize Property Example (VJ++) ======= title: Optimize property example (VJ++) TOCTitle: Optimize property example (VJ++)</span></span>
>>>>>>> <span data-ttu-id="1bb02-102">母版页 ms:assetid: d4ac9ae3-3304-addf-0292-7af4ed4fdbc2 ms:mtpsurl: https://msdn.microsoft.com/library/JJ250067(v=office.15) ms:contentKeyID: 48547949 ms.date: 09/18/2015 mtps_version: office.15.aspx</span><span class="sxs-lookup"><span data-stu-id="1bb02-102">master ms:assetid: d4ac9ae3-3304-addf-0292-7af4ed4fdbc2 ms:mtpsurl: https://msdn.microsoft.com/library/JJ250067(v=office.15) ms:contentKeyID: 48547949 ms.date: 09/18/2015 mtps_version: v=office.15</span></span>
---

<span data-ttu-id="1bb02-103"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="1bb02-103"><<<<<<< HEAD</span></span>
# <a name="optimize-property-example-vj"></a><span data-ttu-id="1bb02-104">Optimize 属性示例 (VJ++)</span><span class="sxs-lookup"><span data-stu-id="1bb02-104">Optimize Property Example (VJ++)</span></span>
=======
# <a name="optimize-property-example-vj"></a><span data-ttu-id="1bb02-105">Optimize 属性示例 （VJ + +）</span><span class="sxs-lookup"><span data-stu-id="1bb02-105">Optimize property example (VJ++)</span></span>
>>>>>>> <span data-ttu-id="1bb02-106">master</span><span class="sxs-lookup"><span data-stu-id="1bb02-106">master</span></span>


<span data-ttu-id="1bb02-107">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="1bb02-107">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="1bb02-108">本示例演示 [Field](field-object-ado.md) 对象动态 Optimize 属性。</span><span class="sxs-lookup"><span data-stu-id="1bb02-108">This example demonstrates the [Field](field-object-ado.md) object dynamic Optimize property.</span></span> <span data-ttu-id="1bb02-109">***Pubs***数据库中的***作者***表的***zip***字段不编制索引。</span><span class="sxs-lookup"><span data-stu-id="1bb02-109">The ***zip*** field of the ***Authors*** table in the ***Pubs*** database is not indexed.</span></span> <span data-ttu-id="1bb02-110">对***zip***字段[Optimize](optimize-property-dynamic-ado.md)属性设置为**True**授权 ADO 建立索引的提高性能的[Find](find-method-ado.md)方法。</span><span class="sxs-lookup"><span data-stu-id="1bb02-110">Setting the [Optimize](optimize-property-dynamic-ado.md) property to **True** on the ***zip*** field authorizes ADO to build an index that improves the performance of the [Find](find-method-ado.md) method.</span></span>

```java 
 
// BeginOptimizeJ 
import com.ms.wfc.data.*; 
import java.io.* ; 
 
public class OptimizeX 
{ 
 // The main entry point for the application. 
 
 public static void main (String[] args) 
 { 
 OptimizeX(); 
 System.exit(0); 
 } 
 
 // OptimizeX function 
 
 static void OptimizeX() 
 { 
 
 // Define ADO Objects. 
 Recordset rstAuthors = null; 
 
 // Declarations. 
 BufferedReader in = 
 new BufferedReader (new InputStreamReader(System.in)); 
 String strCnn = "Provider='sqloledb';Data Source='MySqlServer';" 
 + "Initial Catalog='Pubs';Integrated Security='SSPI';"; 
 
 try 
 { 
 rstAuthors = new Recordset(); 
 rstAuthors.setCursorLocation(AdoEnums.CursorLocation.CLIENT); 
 // Enable index creation. 
 rstAuthors.open("SELECT * FROM Authors", 
 strCnn, 
 AdoEnums.CursorType.STATIC, 
 AdoEnums.LockType.READONLY, 
 AdoEnums.CommandType.TEXT); 
 rstAuthors.getField("zip").getProperties(). 
 getItem("Optimize").setBoolean(true); // Create the index. 
 rstAuthors.find("zip = '94595'"); // Find Akiko Yokomoto. 
 System.out.println(rstAuthors.getField("au_fname").getString() + 
 " " + rstAuthors.getField("au_lname").getString() + " " + 
 rstAuthors.getField("address").getString() + " " + 
 rstAuthors.getField("city").getString() + " " + 
 rstAuthors.getField("state").getString() + " "); 
 rstAuthors.getField("zip").getProperties(). 
 getItem("Optimize").setBoolean(false); // Delete the index. 
 
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
// EndOptimizeJ 
```

