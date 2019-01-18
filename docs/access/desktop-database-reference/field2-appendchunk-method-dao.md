---
title: Field2.AppendChunk 方法 (DAO)
TOCTitle: AppendChunk Method
ms:assetid: 540cd02d-1fc6-81d1-ac08-1e3df72a7208
ms:mtpsurl: https://msdn.microsoft.com/library/Ff194088(v=office.15)
ms:contentKeyID: 48544886
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052867
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: fda1ab5a3e339d951225f4f43ab4275cce2cdb80
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28705433"
---
# <a name="field2appendchunk-method-dao"></a>Field2.AppendChunk 方法 (DAO)

**适用于**： Access 2013、 Office 2013

将字符串表达式中的数据追加到 [**Recordset**](recordset-object-dao.md) 中的"备注"或"长二进制"型 **Field2** 对象。

## <a name="syntax"></a>语法

*表达式*。AppendChunk (***Val***)

*表达式*一个代表**Field2**对象的变量。

## <a name="parameters"></a>Parameters

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Name</p></th>
<th><p>必需/可选</p></th>
<th><p>数据类型</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>Val</em></p></td>
<td><p>必需</p></td>
<td><p><strong>Variant</strong></p></td>
<td><p>一个 Variant（String 子类型）类型的表达式或变量，其中包含要追加到 <strong>Field2</strong> 对象的数据。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

可以使用 **AppendChunk** 和 **GetChunk** 方法访问"备注"或"长二进制"型字段中的数据的子集。

在处理"备注"和"长二进制"型字段时，还可以使用这些方法来节省字符串空间。某些操作（如复制）涉及到临时字符串。如果字符串空间有限，可能需要处理字段的某些块而不是整个字段。

在使用 **AppendChunk** 时如果不存在当前记录，则会发生错误。

> [!NOTE]
> 初始的 **AppendChunk** 操作（ **[Edit](recordset-edit-method-dao.md)** 或 **[AddNew](recordset-addnew-method-dao.md)** 调用之后）只是将数据置于字段内，并覆盖任何现有的数据。然后同一 **Edit** 或 **AddNew** 会话中的后续 **AppendChunk** 调用将其添加到现有数据。

## <a name="example"></a>示例

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
