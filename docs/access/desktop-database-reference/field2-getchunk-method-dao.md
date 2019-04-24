---
title: GetChunk 方法 (DAO)
TOCTitle: GetChunk method
ms:assetid: 5d3a66c0-8216-d701-0a91-b79fbbc822b8
ms:mtpsurl: https://msdn.microsoft.com/library/Ff194600(v=office.15)
ms:contentKeyID: 48545101
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 6a4b850658ca4ab36b0d4f4cbed7266d39b4ff8d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32292774"
---
# <a name="field2getchunk-method-dao"></a>GetChunk 方法 (DAO)

**适用于**：Access 2013、Office 2013

返回**[Recordset](recordset-object-dao.md)** 对象的**[Fields](fields-collection-dao.md)** 集合中的**Memo**或**Long BinaryField2**对象的全部或部分内容。

## <a name="syntax"></a>语法

*表达式*。GetChunk (***偏移量***、***字节数***)

*表达式*一个代表**Field2**对象的变量。

## <a name="parameters"></a>参数

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>名称</p></th>
<th><p>必需/可选</p></th>
<th><p>数据类型</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>Offset</em></p></td>
<td><p>必需</p></td>
<td><p><strong>Long</strong></p></td>
<td><p>开始复制前要跳过的字节数。</p></td>
</tr>
<tr class="even">
<td><p><em>单位</em></p></td>
<td><p>必需</p></td>
<td><p><strong>Long</strong></p></td>
<td><p>要返回的字节数。</p></td>
</tr>
</tbody>
</table>


## <a name="return-value"></a>返回值

Variant

## <a name="remarks"></a>注解

将 **GetChunk** 返回的字节指定给变量。使用 **GetChunk** 每次返回总数据值的一部分。可以使用 **[AppendChunk](field-appendchunk-method-dao.md)** 方法重新组装片段。

如果 offset 为 0, **GetChunk**将从字段的第一个字节开始复制。

如果 numbytes 大于字段中的字节数, 则**GetChunk**将返回字段中剩余的实际字节数。

> [!NOTE]
> [!注释] 对文本使用 **Memo** 字段，只能在 **Long Binary** 字段中放置二进制数据。 否则会导致不合需要的结果。

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
