---
title: Recordset.Move 方法 (DAO)
TOCTitle: Move Method
ms:assetid: 21ca5ab5-ff71-1ae8-21b3-8991d5f795cf
ms:mtpsurl: https://msdn.microsoft.com/library/Ff191697(v=office.15)
ms:contentKeyID: 48543689
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052941
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 02eb8d5e85356cd8a2f7744c057371f0ec901a20
ms.sourcegitcommit: 1dd744993ecb4bed241ace874ad26edaef1778b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2018
ms.locfileid: "25997502"
---
# <a name="recordsetmove-method-dao"></a>Recordset.Move 方法 (DAO)

**适用于**： Access 2013、 Office 2013

移动 **[Recordset](recordset-object-dao.md)** 对象中的当前记录的位置。

## <a name="syntax"></a>语法

*表达式*。移动 （***行***、 ***StartBookmark***）

*表达式*一个表示**Recordset**对象的变量。

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
<td><p><em>Rows</em></p></td>
<td><p>必需</p></td>
<td><p><strong>Long</strong></p></td>
<td><p>位置移动的行数。如果 rows 大于 0，则位置向前移（向文件的末尾处移动）。如果 rows 小于 0，则位置向后移（向文件的开头处移动）。</p></td>
</tr>
<tr class="even">
<td><p><em>StartBookmark</em></p></td>
<td><p>可选</p></td>
<td><p><strong>Variant</strong></p></td>
<td><p>一个标识书签的值。如果指定了 startbookmark，则相对于此书签开始移动。否则，从当前记录开始移动。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

如果使用 **Move** 将当前记录指针定位在第一条记录之前，当前记录指针将移到文件的开头。如果 **Recordset** 不包含记录，并且它的 **[BOF](recordset-bof-property-dao.md)** 属性为 **True**，则使用此方法后移会导致错误。

如果使用 **Move** 将当前记录指针定位在最后一条记录之后，当前记录指针将移到文件的末尾。如果 **Recordset** 不包含记录，并且它的 **[EOF](recordset-eof-property-dao.md)** 属性为 **True**，则使用此方法前移会导致错误。

如果 **BOF** 和 **EOF** 属性中的一个为 **True**，并且您试图在不使用有效书签的情况下使用 **Move** 方法，将会发生运行时错误。

> [!NOTE]
> - 如果对仅向前类型的 **Recordset** 对象使用 **Move**，则行参数必须是正整数，并且不允许使用书签。这意识着您只能前移。
> - 若要使 **Recordset** 中的第一条、最后一条、下一条或上一条记录成为当前记录，请使用 **MoveFirst**、 **MoveLast**、 **MoveNext** 和 **MovePrevious** 方法之一。
> - 在行等于 0 的情况下使用 **Move** 是检索当前记录的基础数据的简易方法。如果要确保当前记录具有基表中的最新数据，使用此方法十分有用。它还会取消任何待定的 **[Edit](recordset2-edit-method-dao.md)** 或 **[AddNew](recordset-addnew-method-dao.md)** 调用。


## <a name="example"></a>示例

以下示例使用 **Move** 方法基于用户输入来定位记录指针。

```vb
    Sub MoveX() 
     
       Dim dbsNorthwind As Database 
       Dim rstSuppliers As Recordset 
       Dim varBookmark As Variant 
       Dim strCommand As String 
       Dim lngMove As Long 
     
       Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
       Set rstSuppliers = _ 
          dbsNorthwind.OpenRecordset("SELECT CompanyName, " & _ 
          "City, Country FROM Suppliers ORDER BY CompanyName", _ 
          dbOpenDynaset) 
     
       With rstSuppliers 
          ' Populate recordset. 
          .MoveLast 
          .MoveFirst 
     
          Do While True 
             ' Display information about current record and ask  
             ' how many records to move. 
             strCommand = InputBox( _ 
                "Record " & (.AbsolutePosition + 1) & " of " & _ 
                .RecordCount & vbCr & "Company: " & _ 
                !CompanyName & vbCr & "Location: " & !City & _ 
                ", " & !Country & vbCr & vbCr & _ 
                "Enter number of records to Move " & _ 
                "(positive or negative).") 
     
             If strCommand = "" Then Exit Do 
     
             ' Store bookmark in case the Move doesn't work. 
             varBookmark = .Bookmark 
     
             ' Move method requires parameter of data type Long. 
             lngMove = CLng(strCommand) 
             .Move lngMove 
     
             ' Trap for BOF or EOF. 
             If .BOF Then 
                MsgBox "Too far backward! " & _ 
                   "Returning to current record." 
                .Bookmark = varBookmark 
             End If 
             If .EOF Then 
                MsgBox "Too far forward! " & _ 
                   "Returning to current record." 
                .Bookmark = varBookmark 
             End If 
          Loop 
          .Close 
       End With 
     
       dbsNorthwind.Close 
     
    End Sub
```
