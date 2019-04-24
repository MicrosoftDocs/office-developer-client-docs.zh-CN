---
title: Recordset 属性 (DAO)
TOCTitle: RecordsetType Property
ms:assetid: a66d4043-08cc-ead1-f9ff-efc7d7ea21bf
ms:mtpsurl: https://msdn.microsoft.com/library/Ff821178(v=office.15)
ms:contentKeyID: 48546853
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm13361
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 64f7dda8bec7806ef510d265deab350dc3cdad6b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32307628"
---
# <a name="recordsetrecordsettype-property-dao"></a>Recordset 属性 (DAO)

**适用于**：Access 2013、Office 2013

使用 **RecordsetType** 属性可以指定何种类型的记录集可以在窗体中使用。 **Byte** 型，可读写。

## <a name="syntax"></a>语法

*表达式*。设

*expression*：表示 **Form** 对象的变量。

## <a name="remarks"></a>注解

**RecordsetType** 属性在 Microsoft Access 数据库 中使用以下设置：

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Setting</p></th>
<th><p>记录集类型</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>0</p></td>
<td><p>可见</p></td>
<td><p>（默认值）可以对基于单个表或基于具有一对一关系的多个表的绑定控件进行编辑。 对于基于具有一对多关系的表绑定到字段的控件, 不能编辑关系&quot;一&quot;方的联接字段中的数据, 除非在表之间启用了级联更新。</p></td>
</tr>
<tr class="even">
<td><p>1</p></td>
<td><p>动态集（不一致的更新）</p></td>
<td><p>所有绑定到其字段的表和控件都可以编辑。</p></td>
</tr>
<tr class="odd">
<td><p>双面</p></td>
<td><p>概述</p></td>
<td><p>绑定到其字段的表和控件都不能编辑。</p></td>
</tr>
</tbody>
</table>

> [!NOTE]
> [!注释] 如果不希望在窗体位于窗体视图或数据表视图中时编辑绑定控件中的数据，可将 **RecordsetType** 属性设置为 2。

**RecordsetType** 属性在 Microsoft Access 项目 (.adp) 中使用以下设置：

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Setting</p></th>
<th><p>记录集类型</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>第三章</p></td>
<td><p>概述</p></td>
<td><p>绑定到其字段的表和控件都不能编辑。</p></td>
</tr>
<tr class="even">
<td><p>4</p></td>
<td><p>可更新快照</p></td>
<td><p>（默认值）所有绑定到其字段的表和控件都可以编辑。</p></td>
</tr>
</tbody>
</table>

> [!NOTE]
> [!注释] 更改打开的窗体或报表的 **RecordsetType** 属性时，将会引起自动重新创建记录集。

可以基于其字段绑定到窗体控件的多个基础表创建窗体。根据 **RecordsetType** 属性设置的不同，可以设置能够编辑哪些绑定控件。

除了由数据集提供的编辑控件**** 之外, 窗体上的每个控件都有一个**锁定**属性, 您可以设置该属性来指定是否可以编辑控件及其基础数据。 如果 **Locked** 属性设为"是"，则不能编辑数据。

## <a name="example"></a>示例

在下面的示例中，只有当用户 ID 为 ADMIN 时，才允许更新记录。 如果公共变量的值不是 ADMIN，则该代码示例会将 gstrUserID**RecordsetType** 属性设置为“快照”。

```vb
    Sub Form_Open(Cancel As Integer) 
     Const conSnapshot = 2 
     If gstrUserID <> "ADMIN" Then 
     Forms!Employees.RecordsetType = conSnapshot 
     End If 
    End Sub
```

## <a name="see-also"></a>另请参阅

- [Form 对象](https://docs.microsoft.com/office/vba/api/Access.Form)


