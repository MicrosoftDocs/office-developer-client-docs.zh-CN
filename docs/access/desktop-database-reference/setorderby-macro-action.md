---
title: SetOrderBy 宏操作
TOCTitle: SetOrderBy Macro Action
ms:assetid: 78f65ce9-b56f-f476-3bd6-f3307bc22a08
ms:mtpsurl: https://msdn.microsoft.com/library/Ff196152(v=office.15)
ms:contentKeyID: 48545765
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm98639
f1_categories:
- Office.Version=v15
ms.openlocfilehash: ac911110d313243879d6dff993061d58c208cd34
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25876216"
---
# <a name="setorderby-macro-action"></a>SetOrderBy 宏操作


**适用于**： Access 2013、 Office 2013

您可以使用 **SetOrderBy** 操作指定希望如何筛选窗体、报表、表或查询结果中的记录。

## <a name="setting"></a>设置

**SetOrderBy** 操作具有下列参数。

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>操作参数</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Order By</strong></p></td>
<td><p>一个字符串表达式，包含作为记录排序依据的一个或多个字段的名称或可选的 ASC 或 DESC 关键字。</p></td>
</tr>
<tr class="even">
<td><p><strong>控件名称</strong></p></td>
<td><p>如果提供该参数并且活动对象是窗体或报表，则为与将要排序的子窗体或子报表对应的控件的名称。如果为空并且活动对象是窗体或报表，则对父窗体或报表进行排序。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注释

在运行该宏操作时，将对处于活动状态且具有焦点的表、窗体、报表或数据表（如查询结果）进行排序。

Order By 参数是作为记录排序依据的一个或多个字段的名称。如果使用多个字段名称，需用逗号 (,) 分隔每个名称。活动对象的 **OrderBy** 属性用于保存排序值并在以后应用该值。OrderBy 值与在其中创建这些值的对象一起保存。在打开对象时将自动加载这些值，但不会自动应用它们。

在输入一个或多个字段名称以设置 Order By 参数然后运行该宏时，默认情况下将按升序排列记录。

若要按降序排列记录，请在 Order By 参数表达式的末尾键入 DESC。例如，若要按联系人姓名的降序对客户记录进行排序，请将 Order By 参数设置为"ContactName DESC"。若要按"LastName"的降序和"FirstName"的升序对姓名进行排序，请将 Order By 参数设置为"LastName DESC, FirstName ASC"。

