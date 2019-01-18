---
title: Recordset.RecordsetType 属性 (DAO)
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
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28709654"
---
# <a name="recordsetrecordsettype-property-dao"></a>Recordset.RecordsetType 属性 (DAO)

**适用于**： Access 2013、 Office 2013

使用 **RecordsetType** 属性可以指定何种类型的记录集可以在窗体中使用。 **Byte** 型，可读写。

## <a name="syntax"></a>语法

*表达式*。RecordsetType

*expression* 一个代表 **表单** 对象的变量。

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
<th><p>设置</p></th>
<th><p>记录集类型</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>0</p></td>
<td><p>动态集</p></td>
<td><p>（默认值）您可以编辑基于单个表或具有一对一关系的表绑定的控件。 对于基于具有-一对多关系的表的字段绑定控件，您不能编辑的联接字段中的数据，在&quot;一个&quot;除非级联更新启用表之间的关系侧。</p></td>
</tr>
<tr class="even">
<td><p>1</p></td>
<td><p>动态集（不一致的更新）</p></td>
<td><p>所有绑定到其字段的表和控件都可以编辑。</p></td>
</tr>
<tr class="odd">
<td><p>2</p></td>
<td><p>快照</p></td>
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
<th><p>设置</p></th>
<th><p>记录集类型</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>3</p></td>
<td><p>快照</p></td>
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

除了由**RecordsetType**提供的编辑控件，窗体上的每个控件具有**Locked**属性可设置来指定是否可编辑控件和其基础数据。 如果 **Locked** 属性设为"是"，则不能编辑数据。

## <a name="example"></a>示例

在下面的示例中，只有当用户 ID 为 ADMIN 时，才允许更新记录。如果公共变量的值不是 ADMIN，则该代码示例会将 gstrUserID**RecordsetType** 属性设置为“快照”。

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


