---
title: Field2.FieldSize 属性 (DAO)
TOCTitle: FieldSize Property
ms:assetid: d609801d-7761-663f-2840-de5923bb120c
ms:mtpsurl: https://msdn.microsoft.com/library/Ff835039(v=office.15)
ms:contentKeyID: 48547976
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052870
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: a7dfeb33568664a6a75f9f43de64e0c24abeb09a
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28713574"
---
# <a name="field2fieldsize-property-dao"></a><span data-ttu-id="be674-102">Field2.FieldSize 属性 (DAO)</span><span class="sxs-lookup"><span data-stu-id="be674-102">Field2.FieldSize property (DAO)</span></span>


<span data-ttu-id="be674-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="be674-103">**Applies to**: Access 2013, Office 2013</span></span>


<span data-ttu-id="be674-104">返回 [**Recordset**](fields-collection-dao.md) 对象的 [**Fields**](recordset-object-dao.md) 集合中的"备注"或"长二进制"类型 **Field2** 对象的数据库（而不是内存）中使用的字节数。</span><span class="sxs-lookup"><span data-stu-id="be674-104">Returns the number of bytes used in the database (rather than in memory) of a Memo or Long Binary **Field2** object in the **[Fields](fields-collection-dao.md)** collection of a **[Recordset](recordset-object-dao.md)** object.</span></span>

## <a name="syntax"></a><span data-ttu-id="be674-105">语法</span><span class="sxs-lookup"><span data-stu-id="be674-105">Syntax</span></span>

<span data-ttu-id="be674-106">*表达式*。字段大小</span><span class="sxs-lookup"><span data-stu-id="be674-106">*expression* .FieldSize</span></span>

<span data-ttu-id="be674-107">*表达式*一个代表**Field2**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="be674-107">*expression* A variable that represents a **Field2** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="be674-108">注解</span><span class="sxs-lookup"><span data-stu-id="be674-108">Remarks</span></span>

<span data-ttu-id="be674-109">可以将 **FieldSize** 连同 **[AppendChunk](field-appendchunk-method-dao.md)** 和 **[GetChunk](field-getchunk-method-dao.md)** 方法一起使用，以处理较大的字段。</span><span class="sxs-lookup"><span data-stu-id="be674-109">You can use **FieldSize** with the **[AppendChunk](field-appendchunk-method-dao.md)** and **[GetChunk](field-getchunk-method-dao.md)** methods to manipulate large fields.</span></span>

<span data-ttu-id="be674-110">由于"长二进制"或"备注"字段的大小可能会超过 64K，因此，应该将 **FieldSize** 返回的值赋予给大小足以存储 **Long** 类型变量的变量。</span><span class="sxs-lookup"><span data-stu-id="be674-110">Because the size of a Long Binary or Memo field can exceed 64K, you should assign the value returned by **FieldSize** to a variable large enough to store a **Long** variable.</span></span>

<span data-ttu-id="be674-111">要确定除"备注"和"长二进制"类型以外的其他 **Field2** 对象的大小，请使用 **[Size](field-size-property-dao.md)** 属性。</span><span class="sxs-lookup"><span data-stu-id="be674-111">To determine the size of a **Field2** object other than Memo and Long Binary types, use the **[Size](field-size-property-dao.md)** property.</span></span>

  - <span data-ttu-id="be674-112">数据库服务器或 ODBC 驱动程序不支持服务器端游标。</span><span class="sxs-lookup"><span data-stu-id="be674-112">If the database server or ODBC driver does not support server-side cursors.</span></span>

  - <span data-ttu-id="be674-113">使用的是 ODBC 游标库（也就是说， **DefaultCursorDriver** 属性设置为 **dbUseODBC**，或者在服务器不支持服务器端游标的情况下设置为 **dbUseDefault**）。</span><span class="sxs-lookup"><span data-stu-id="be674-113">If you are using the ODBC cursor library (that is, the **DefaultCursorDriver** property is set to **dbUseODBC**, or to **dbUseDefault** when the server does not support server-side cursors).</span></span>

  - <span data-ttu-id="be674-114">使用的是无游标查询（也就是说， **DefaultCursorDriver** 属性设置为 **dbUseNoCursor**）。</span><span class="sxs-lookup"><span data-stu-id="be674-114">If you are using a cursorless query (that is, the **DefaultCursorDriver** property is set to **dbUseNoCursor**).</span></span>

<span data-ttu-id="be674-p101">**FieldSize** 属性和 VBA **Len()** 或 **LenB()** 函数可能返回不同的值作为同一字符串的长度。字符串以多字节字符集 (MBCS) 格式存储在 Microsoft Access 数据库中，但是通过 VBA 以 Unicode 格式显示。因此， **Len()** 函数始终返回字符数， **LenB** 始终返回字符数 X 2（Unicode 对每个字符使用两个字节），但如果字符串包含任何 MBCS 字符， **FieldSize** 将返回介于上述两者之间的某个值。例如，假设有一个字符串包括三个常规字符和两个 MBCS 字符，则 **Len()** 将返回 5， **LenB()** 将返回 10， **FieldSize** 将返回 7，即针对每个常规字符加 1，针对每个 MBCS 字符加 2。</span><span class="sxs-lookup"><span data-stu-id="be674-p101">The **FieldSize** property and the VBA **Len()** or **LenB()** functions may return different values as the length of the same string. Strings are stored in a Microsoft Access database in multi-byte character set (MBCS) form, but exposed through VBA in Unicode format. As a result, the **Len()** function will always return the number of characters, **LenB** will always return the number of characters X 2 (Unicode uses two bytes for each character), but **FieldSize** will return some value in between if the string has any MBCS characters. For example, given a string consisting of three normal characters and two MBCS characters, **Len()** will return 5, **LenB()** will return 10, and **FieldSize** will return 7, the sum of 1 for each normal character and 2 for each MBCS character.</span></span>

## <a name="example"></a><span data-ttu-id="be674-119">示例</span><span class="sxs-lookup"><span data-stu-id="be674-119">Example</span></span>

<span data-ttu-id="be674-120">以下示例使用 **FieldSize** 属性列出两个不同的表中"备注"和"长二进制"Field 对象使用的字节数。</span><span class="sxs-lookup"><span data-stu-id="be674-120">This example uses the **FieldSize** property to list the number of bytes used by the Memo and Long Binary Field objects in two different tables.</span></span>

```vb
    Sub FieldSizeX() 
     
     Dim dbsNorthwind As Database 
     Dim rstCategories As Recordset 
     Dim rstEmployees As Recordset 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     Set rstCategories = _ 
     dbsNorthwind.OpenRecordset("Categories", _ 
     dbOpenDynaset) 
     Set rstEmployees = _ 
     dbsNorthwind.OpenRecordset("Employees", _ 
     dbOpenDynaset) 
     
     Debug.Print _ 
     "Field sizes from records in Categories table" 
     
     With rstCategories 
     Debug.Print " CategoryName - " & _ 
     "Description (bytes) - Picture (bytes)" 
     
     ' Enumerate the Categories Recordset and print the size 
     ' in bytes of the picture field for each record. 
     Do While Not .EOF 
     Debug.Print " " & !CategoryName & " - " & _ 
     !Description.FieldSize & " - " & _ 
     !Picture.FieldSize 
     .MoveNext 
     Loop 
     
     .Close 
     End With 
     
     Debug.Print "Field sizes from records in Employees table" 
     
     With rstEmployees 
     Debug.Print " LastName - Notes (bytes) - " & _ 
     "Photo (bytes)" 
     
     ' Enumerate the Employees Recordset and print the size 
     ' in bytes of the picture field for each record. 
     Do While Not .EOF 
     Debug.Print " " & !LastName & " - " & _ 
     !Notes.FieldSize & " - " & !Photo.FieldSize 
     .MoveNext 
     Loop 
     
     .Close 
     End With 
     
     dbsNorthwind.Close 
     
    End Sub 
```

<br/>

<span data-ttu-id="be674-p102">以下示例使用 **AppendChunk** 和 **GetChunk** 方法，用来自其他记录的数据，以每次 32K 的形式填充 OLE 对象字段。在实际的应用程序中，用户可以使用与此类似的过程，将雇员记录（包括雇员的照片）从一个表复制到另一个表。在以下示例中，只是将记录复制回到同一个表。请注意，所有块操作将在单个 AddNew-Update 序列中发生。</span><span class="sxs-lookup"><span data-stu-id="be674-p102">This example uses the **AppendChunk** and **GetChunk** methods to fill an OLE object field with data from another record, 32K at a time. In a real application, one might use a procedure like this to copy an employee record (including the employee's photo) from one table to another. In this example, the record is simply being copied back to same table. Note that all the chunk manipulation takes place within a single AddNew-Update sequence.</span></span>

```vb
    Sub AppendChunkX() 
     
     Dim dbsNorthwind As Database 
     Dim rstEmployees As Recordset 
     Dim rstEmployees2 As Recordset 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     
     ' Open two recordsets from the Employees table. 
     Set rstEmployees = _ 
     dbsNorthwind.OpenRecordset("Employees", _ 
     dbOpenDynaset) 
     Set rstEmployees2 = rstEmployees.Clone 
     
     ' Add a new record to the first Recordset and copy the 
     ' data from a record in the second Recordset. 
     With rstEmployees 
     .AddNew 
     !FirstName = rstEmployees2!FirstName 
     !LastName = rstEmployees2!LastName 
     CopyLargeField rstEmployees2!Photo, !Photo 
     .Update 
     
     ' Delete new record because this is a demonstration. 
     .Bookmark = .LastModified 
     .Delete 
     .Close 
     End With 
     
     rstEmployees2.Close 
     dbsNorthwind.Close 
     
    End Sub 
     
    Function CopyLargeField(fldSource As Field2, _ 
     fldDestination As Field2) 
     
     ' Set size of chunk in bytes. 
     Const conChunkSize = 32768 
     
     Dim lngOffset As Long 
     Dim lngTotalSize As Long 
     Dim strChunk As String 
     
     ' Copy the photo from one Recordset to the other in 32K 
     ' chunks until the entire field is copied. 
     lngTotalSize = fldSource.FieldSize 
     Do While lngOffset < lngTotalSize 
     strChunk = fldSource.GetChunk(lngOffset, conChunkSize) 
     fldDestination.AppendChunk strChunk 
     lngOffset = lngOffset + conChunkSize 
     Loop 
     
    End Function
```
