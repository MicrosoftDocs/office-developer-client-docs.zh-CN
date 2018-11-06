---
title: Recordset2.CancelUpdate 方法 (DAO)
TOCTitle: CancelUpdate Method
ms:assetid: f741dec1-b9a4-506e-74ec-2bc309b0918e
ms:mtpsurl: https://msdn.microsoft.com/library/Ff836907(v=office.15)
ms:contentKeyID: 48548761
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: e9679a39a8509bb73e9d788e776e208f3c899d3c
ms.sourcegitcommit: 1dd744993ecb4bed241ace874ad26edaef1778b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2018
ms.locfileid: "25998404"
---
# <a name="recordset2cancelupdate-method-dao"></a>Recordset2.CancelUpdate 方法 (DAO)

**适用于**： Access 2013、 Office 2013

取消 **[Recordset](recordset-object-dao.md)** 对象的任何待定更新。

## <a name="syntax"></a>语法

*表达式*。CancelUpdate (***UpdateType***)

*表达式*一个表示**Recordset2**对象的变量。

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
<td><p><em>UpdateType</em></p></td>
<td><p>可选</p></td>
<td><p><strong>Long</strong></p></td>
<td><p>设置为<strong><a href="updatetypeenum-enumeration-dao.md">UpdateTypeEnum</a></strong>值之一。</p><p><strong>注意</strong>： <EM>dbUpdateRegular</EM>和<EM>dbUpdateBatch</EM>值是仅当批更新启用有效。</p>
</td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

可以使用 **CancelUpdate** 方法取消执行 **[Edit](recordset2-edit-method-dao.md)** 或 **[AddNew](recordset2-addnew-method-dao.md)** 操作后得到的任何待定更新。例如，如果用户调用了 **Edit** 或 **AddNew** 方法，但尚未调用 **Update** 方法， **CancelUpdate** 将取消 **Edit** 或 **AddNew** 被调用之后所做的任何更改。

检查 [Recordset](recordset2-editmode-property-dao.md) 的 ****EditMode**** 属性，以确定是否存在可以取消的待定操作。

> [!NOTE]
> [!注释] 使用 **CancelUpdate** 方法的效果与在不使用 **[Update](recordset2-update-method-dao.md)** 方法的情况下移到另一条记录的效果相同，但是当前记录不发生更改，且不更新各个属性（例如 **[BOF](recordset2-bof-property-dao.md)** 和 **[EOF](recordset2-eof-property-dao.md)** ）。

## <a name="example"></a>示例

以下示例演示如何将 **CancelUpdate** 方法与 **AddNew** 方法一起使用。

```vb
    Sub CancelUpdateX() 
     
       Dim dbsNorthwind As Database 
       Dim rstEmployees As Recordset2 
       Dim intCommand As Integer 
     
       Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
       Set rstEmployees = dbsNorthwind.OpenRecordset( _ 
          "Employees", dbOpenDynaset) 
     
       With rstEmployees 
          .AddNew 
          !FirstName = "Kimberly" 
          !LastName = "Bowen" 
          intCommand = MsgBox("Add new record for " & _ 
             !FirstName & " " & !LastName & "?", vbYesNo) 
          If intCommand = vbYes Then 
             .Update 
             MsgBox "Record added." 
             ' Delete new record because this is a  
             ' demonstration. 
             .Bookmark = .LastModified 
             .Delete 
          Else 
             .CancelUpdate 
             MsgBox "Record not added." 
          End If 
       End With 
     
       dbsNorthwind.Close 
     
    End Sub 
```

<br/>

以下示例演示如何将 **CancelUpdate** 方法与 **Edit** 方法一起使用。

```vb
Sub CancelUpdateX2() 
 
   Dim dbsNorthwind As Database 
   Dim rstEmployees As Recordset 
   Dim strFirst As String 
   Dim strLast As String 
   Dim intCommand As Integer 
 
   Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
   Set rstEmployees = dbsNorthwind.OpenRecordset( _ 
      "Employees", dbOpenDynaset) 
 
   With rstEmployees 
      strFirst = !FirstName 
      strLast = !LastName 
      .Edit 
      !FirstName = "Cora" 
      !LastName = "Edmonds" 
      intCommand = MsgBox("Replace current name with " & _ 
         !FirstName & " " & !LastName & "?", vbYesNo) 
      If intCommand = vbYes Then 
         .Update 
         MsgBox "Record modified." 
         ' Restore data because this is a demonstration. 
         .Bookmark = .LastModified 
         .Edit 
         !FirstName = strFirst 
         !LastName = strLast 
         .Update 
      Else 
         .CancelUpdate 
         MsgBox "Record not modified." 
      End If 
      .Close 
   End With 
 
   dbsNorthwind.Close 
 
End Sub 
 
```

