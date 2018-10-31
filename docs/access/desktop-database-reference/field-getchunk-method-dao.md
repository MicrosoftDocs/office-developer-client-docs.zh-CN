---
title: Field.GetChunk Method (DAO)
TOCTitle: GetChunk Method
ms:assetid: b8984e79-54f7-8052-85a3-d12033daf7a1
ms:mtpsurl: https://msdn.microsoft.com/library/Ff822448(v=office.15)
ms:contentKeyID: 48547328
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052871
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 691b4d0b18b31c4c4a40f73e232a1829101913f1
ms.sourcegitcommit: 801b1b54786f7b0e5b0d35466e7ae8d1e840b26f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25863274"
---
# <a name="fieldgetchunk-method-dao"></a>Field.GetChunk Method (DAO)


**适用于**： Access 2013 |Office 2013

返回 ****Recordset**** 对象的 **[Fields](field-object-dao.md)** 集合中的 [Memo](fields-collection-dao.md) 或 **Long Binary** **[Field](recordset-object-dao.md)** 对象的全部或一部分内容。

## <a name="syntax"></a>语法

*表达式*。GetChunk***偏移***(***字节***）

*表达式*一个代表**Field**对象的变量。

### <a name="parameters"></a>参数

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
<td><p>Offset</p></td>
<td><p>必需</p></td>
<td><p><strong>Long</strong></p></td>
<td><p>开始复制前要跳过的字节数。</p></td>
</tr>
<tr class="even">
<td><p>字节数</p></td>
<td><p>必需</p></td>
<td><p><strong>Long</strong></p></td>
<td><p>要返回的字节数。</p></td>
</tr>
</tbody>
</table>


<<<<<<< 头
### <a name="return-value"></a>返回值
=======
### <a name="return-value"></a>返回值
>>>>>>> 母版

Variant

## <a name="remarks"></a>注解

将 **GetChunk** 返回的字节指定给变量。使用 **GetChunk** 每次返回总数据值的一部分。可以使用 **[AppendChunk](field-appendchunk-method-dao.md)** 方法重新组装片段。

如果 offset 为**0,getchunk**将从字段的第一个字节开始。

如果 numbytes 大于字段中的字节数， **GetChunk**将返回字段中的实际剩余的字节数。


> [!NOTE]
> [!注释] 对文本使用 **Memo** 字段，只能在 **Long Binary** 字段中放置二进制数据。否则会导致不合需要的结果。



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
