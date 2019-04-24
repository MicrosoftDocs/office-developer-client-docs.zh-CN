---
title: CancelUpdate 方法 (DAO)
TOCTitle: CancelUpdate method
ms:assetid: efc4f60b-876f-5e11-37fd-0fbbf225b15b
ms:mtpsurl: https://msdn.microsoft.com/library/Ff836421(v=office.15)
ms:contentKeyID: 48548590
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1053072
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 5950154d8896678889af01254104a2ac0dfef4cc
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32300677"
---
# <a name="recordsetcancelupdate-method-dao"></a>CancelUpdate 方法 (DAO)

**适用于**：Access 2013、Office 2013

取消 **[Recordset](recordset-object-dao.md)** 对象的任何待定更新。

## <a name="syntax"></a>语法

*表达式*。CancelUpdate (***UpdateType***)

*表达式*一个代表**Recordset**对象的变量。

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
<td><p>设置为<strong><a href="updatetypeenum-enumeration-dao.md">UpdateTypeEnum</a></strong>值之一。</p><p><strong>注意</strong>: <EM>dbUpdateRegular</EM>和<EM>dbUpdateBatch</EM>值仅在启用批更新时有效。</p>
</td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

可以使用 **CancelUpdate** 方法取消执行 **[Edit](recordset-edit-method-dao.md)** 或 **[AddNew](recordset-addnew-method-dao.md)** 操作后得到的任何待定更新。例如，如果用户调用了 **Edit** 或 **AddNew** 方法，但尚未调用 **Update** 方法， **CancelUpdate** 将取消 **Edit** 或 **AddNew** 被调用之后所做的任何更改。

检查**Recordset**的**[EditMode](recordset-editmode-property-dao.md)** 属性, 以确定是否存在可以取消的挂起操作。

> [!NOTE]
> [!注释] 使用 **CancelUpdate** 方法的效果与在不使用 **[Update](recordset-update-method-dao.md)** 方法的情况下移到另一条记录的效果相同，但是当前记录不发生更改，且不更新各个属性（例如 **[BOF](recordset-bof-property-dao.md)** 和 **[EOF](recordset-eof-property-dao.md)** ）。


## <a name="example"></a>示例

以下示例演示如何将 **CancelUpdate** 方法与 **AddNew** 方法一起使用。

```vb
    Sub CancelUpdateX() 
     
       Dim dbsNorthwind As Database 
       Dim rstEmployees As Recordset 
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

