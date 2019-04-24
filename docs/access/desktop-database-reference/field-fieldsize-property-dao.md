---
title: Field 字段 FieldSize 属性 (DAO)
TOCTitle: FieldSize Property
ms:assetid: c81bd5cb-6b7c-5390-2d6b-049143f2f3b6
ms:mtpsurl: https://msdn.microsoft.com/library/Ff823165(v=office.15)
ms:contentKeyID: 48547645
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 68a1b354b27515dd855703b9bf6344e4a9e90d7b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32293110"
---
# <a name="fieldfieldsize-property-dao"></a>Field 字段 FieldSize 属性 (DAO)


**适用于**：Access 2013、Office 2013


返回 **[Recordset](field-object-dao.md)** 对象的 **[Fields](fields-collection-dao.md)** 集合中"备注"或"长二进制"类型 **[Field](recordset-object-dao.md)** 对象的数据库（而不是内存）中使用的字节数。

## <a name="syntax"></a>语法

*表达式*。FieldSize

*表达式*一个代表**Field**对象的变量。

## <a name="remarks"></a>注解

可以将 **FieldSize** 连同 **[AppendChunk](field-appendchunk-method-dao.md)** 和 **[GetChunk](field-getchunk-method-dao.md)** 方法一起使用，以处理较大的字段。

由于"长二进制"或"备注"字段的大小可能会超过 64K，因此，应该将 **FieldSize** 返回的值赋予给大小足以存储 **Long** 类型变量的变量。

要确定除"备注"和"长二进制"类型以外的其他 **Field** 对象的大小，请使用 **[Size](field-size-property-dao.md)** 属性。

  - 数据库服务器或 ODBC 驱动程序不支持服务器端游标。

  - 使用的是 ODBC 游标库（也就是说， **DefaultCursorDriver** 属性设置为 **dbUseODBC**，或者在服务器不支持服务器端游标的情况下设置为 **dbUseDefault**）。

  - 使用的是无游标查询（也就是说， **DefaultCursorDriver** 属性设置为 **dbUseNoCursor**）。

**FieldSize** 属性和 VBA **Len()** 或 **LenB()** 函数可能返回不同的值作为同一字符串的长度。字符串以多字节字符集 (MBCS) 格式存储在 Microsoft Access 数据库中，但是通过 VBA 以 Unicode 格式显示。因此， **Len()** 函数始终返回字符数， **LenB** 始终返回字符数 X 2（Unicode 对每个字符使用两个字节），但如果字符串包含任何 MBCS 字符， **FieldSize** 将返回介于上述两者之间的某个值。例如，假设有一个字符串包括三个常规字符和两个 MBCS 字符，则 **Len()** 将返回 5， **LenB()** 将返回 10， **FieldSize** 将返回 7，即针对每个常规字符加 1，针对每个 MBCS 字符加 2。

## <a name="example"></a>示例

以下示例使用 **FieldSize** 属性列出两个不同的表中"备注"和"长二进制"Field 对象使用的字节数。

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

以下示例使用 **AppendChunk** 和 **GetChunk** 方法，用来自其他记录的数据，以每次 32K 的形式填充 OLE 对象字段。在实际的应用程序中，用户可以使用与此类似的过程，将雇员记录（包括雇员的照片）从一个表复制到另一个表。在以下示例中，只是将记录复制回到同一个表。请注意，所有块操作将在单个 AddNew-Update 序列中发生。

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
     
    Function CopyLargeField(fldSource As Field, _ 
     fldDestination As Field) 
     
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
