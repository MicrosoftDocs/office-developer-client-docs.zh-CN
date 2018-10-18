---
<span data-ttu-id="b9c82-101"><<<<<<< 标头标题： 属性和 Name 属性示例 （VJ + +） TOCTitle: Attributes 和 Name 属性示例 （VJ + +） === 标题： 属性和 Name 属性示例 （VJ + +） TOCTitle： 属性和 Name 属性示例 （VJ++)</span><span class="sxs-lookup"><span data-stu-id="b9c82-101"><<<<<<< HEAD title: Attributes and Name Properties Example (VJ++) TOCTitle: Attributes and Name Properties Example (VJ++) ======= title: Attributes and Name properties example (VJ++) TOCTitle: Attributes and Name properties example (VJ++)</span></span>
>>>>>>> <span data-ttu-id="b9c82-102">母版页 ms:assetid: ad3fe113-ad14-2df3-ec41-c24e6d2b1b21 ms:mtpsurl: https://msdn.microsoft.com/library/JJ249812(v=office.15) ms:contentKeyID: 48547035 ms.date: 09/18/2015 mtps_version: office.15.aspx</span><span class="sxs-lookup"><span data-stu-id="b9c82-102">master ms:assetid: ad3fe113-ad14-2df3-ec41-c24e6d2b1b21 ms:mtpsurl: https://msdn.microsoft.com/library/JJ249812(v=office.15) ms:contentKeyID: 48547035 ms.date: 09/18/2015 mtps_version: v=office.15</span></span>
---

<span data-ttu-id="b9c82-103"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="b9c82-103"><<<<<<< HEAD</span></span>
# <a name="attributes-and-name-properties-example-vj"></a><span data-ttu-id="b9c82-104">Attributes 和 Name 属性示例 (VJ++)</span><span class="sxs-lookup"><span data-stu-id="b9c82-104">Attributes and Name Properties Example (VJ++)</span></span>
=======
# <a name="attributes-and-name-properties-example-vj"></a><span data-ttu-id="b9c82-105">Attributes 和 Name 属性示例 （VJ + +）</span><span class="sxs-lookup"><span data-stu-id="b9c82-105">Attributes and Name properties example (VJ++)</span></span>
>>>>>>> <span data-ttu-id="b9c82-106">master</span><span class="sxs-lookup"><span data-stu-id="b9c82-106">master</span></span>


<span data-ttu-id="b9c82-107">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="b9c82-107">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="b9c82-p101">此示例显示 [Connection](attributes-property-ado.md)、[Field](connection-object-ado.md) 和 [Property](field-object-ado.md) 对象的 [Attributes](property-object-ado.md) 属性的值。它使用 [Name](name-property-ado.md) 属性来显示每个 **Field** 和 **Property** 对象的名称。</span><span class="sxs-lookup"><span data-stu-id="b9c82-p101">This example displays the value of the [Attributes](attributes-property-ado.md) property for [Connection](connection-object-ado.md), [Field](field-object-ado.md), and [Property](property-object-ado.md) objects. It uses the [Name](name-property-ado.md) property to display the name of each **Field** and **Property** object.</span></span>

```java 
 
// BeginAttributesJ 
import com.ms.wfc.data.*; 
import java.io.*; 
 
public class AttributesX 
{ 
 // The main entry point for the application 
 public static void main (String[] args) 
 { 
 AttributesX(); 
 System.exit(0); 
 } 
 
 // AttributeX Function 
 
 static void AttributesX() 
 { 
 // Define ADO Objects. 
 Connection cnConn1 = null; 
 Recordset rstEmployees = null; 
 Fields listOfFields = null; 
 AdoProperties listOfProperties = null; 
 
 //Declarations. 
 BufferedReader in = 
 new BufferedReader (new InputStreamReader(System.in)); 
 String line = null; 
 String strCnn = "Provider='sqloledb';Data Source='MySqlServer';" 
 + "Initial Catalog='Pubs';Integrated Security='SSPI';"; 
 int recordDisplaySize = 15; 
 int propertyCount = 0; 
 try 
 { 
 // Open connection and recordset. 
 cnConn1 = new Connection(); 
 cnConn1.open(strCnn); 
 
 rstEmployees = new Recordset (); 
 rstEmployees.open("employee", 
 cnConn1,AdoEnums.CursorType.FORWARDONLY, 
 AdoEnums.LockType.READONLY, AdoEnums.CommandType.TABLE); 
 
 // Display the attributes of the connection. 
 System.out.println("Connection attributes = " 
 + cnConn1.getAttributes()); 
 // Display the attributes of the Employees table's fields. 
 System.out.println("\n\nField attributes : " + "\n"); 
 
 listOfFields = rstEmployees.getFields(); 
 
 for ( int i=0; i < listOfFields.getCount();i++) 
 { 
 System.out.println("\t\t" + listOfFields.getItem(i).getName() 
 + " = " + listOfFields.getItem(i).getAttributes()); 
 } 
 
 // Display fields of the Employees table which are NULLABLE. 
 System.out.println("\n\nNULLABLE Fields : " + "\n"); 
 for ( int i=0; i < listOfFields.getCount();i++) 
 { 
 if ((listOfFields.getItem(i).getAttributes() & 
 AdoEnums.FieldAttribute.ISNULLABLE) > 0) 
 System.out.println("\t\t" + 
 listOfFields.getItem(i).getName()); 
 
 } 
 
 System.out.println ("\n\nPress <Enter> key to continue.."); 
 line = in.readLine(); 
 
 // Display the attributes of the Employees table's properties. 
 System.out.println("\n\nProperty attributes : " ); 
 listOfProperties = rstEmployees.getProperties(); 
 for ( int i=0; i < listOfProperties.getCount() ;i++) 
 { 
 System.out.println("\t\t" + 
 listOfProperties.getItem(i).getName() 
 + " = " + listOfProperties.getItem(i).getAttributes()); 
 
 if (propertyCount == recordDisplaySize) 
 { 
 System.out.println ("\n\nPress <Enter> key to continue."); 
 line = in.readLine(); 
 propertyCount = 0; 
 } 
 propertyCount++; 
 } 
 
 System.out.println ("\n\nPress <Enter> key to continue."); 
 line = in.readLine(); 
 } 
 catch( AdoException ae ) 
 { 
 // Notify user of any errors that result from ADO. 
 
 // Check for null pointer for connection object. 
 if (rstEmployees.getActiveConnection()==null) 
 System.out.println("Exception: " + ae.getMessage()); 
 
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
 
 //.PrintIOError Function 
 
 static void PrintIOError( java.io.IOException je) 
 { 
 System.out.println("Error \n"); 
 System.out.println("\tSource = " + je.getClass() + "\n"); 
 System.out.println("\tDescription = " + je.getMessage() + "\n"); 
 } 
} 
 
// EndAttributesJ 
```

