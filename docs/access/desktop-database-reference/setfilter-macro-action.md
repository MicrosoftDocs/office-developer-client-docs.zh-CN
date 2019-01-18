---
title: SetFilter 宏操作
TOCTitle: SetFilter macro action
ms:assetid: dee699e2-0840-1612-23ce-199ef8d30566
ms:mtpsurl: https://msdn.microsoft.com/library/Ff835438(v=office.15)
ms:contentKeyID: 48548203
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm122943
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: ac1a2c8a603fb74b56d71f73605455ecdbc87035
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28698678"
---
# <a name="setfilter-macro-action"></a>SetFilter 宏操作

**适用于**： Access 2013、 Office 2013

可以使用 **SetFilter** 操作向活动数据表、窗体、报表或表中的记录应用筛选器。

## <a name="setting"></a>设置

**SetFilter** 操作具有下列参数。

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
<td><p>Filter Name</p></td>
<td><p>如果提供该参数，则会将查询或筛选器的名称另存为查询。 客户端数据库中需要此参数或 WhereCondition 参数。 在 web 数据库中，此参数不可用。</p></td>
</tr>
<tr class="even">
<td><p>Where Condition</p></td>
<td><p>如果提供该参数，则为可限制数据表、窗体、报表或表中记录的 SQL WHERE 子句。 在 web 数据库中，此参数是必需的。</p></td>
</tr>
<tr class="odd">
<td><p>控件名称</p></td>
<td><p>如果提供该参数，则为与要筛选的子窗体或子报表相对应的控件的名称。如果为空，则筛选当前对象。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注释

在 Web 数据库中，"Where Condition"参数不能以等号 (=) 开头。

在运行该操作时，将对处于活动状态且具有焦点的表、窗体、报表或数据表（如查询结果）应用筛选器。

活动对象的 **Filter** 属性用于保存 WhereCondition 参数并在以后应用该参数。筛选器与在其中创建筛选器的对象一起保存。在打开对象时会自动加载筛选器，但不会自动应用筛选器。

在客户端数据库中，若要在打开对象时自动应用筛选器，请将 **FilterOnLoad** 属性设置为 True。

在 Web 数据库中，若要在打开对象时自动应用筛选器，请将 **SetFilter** 操作设置为宏，并将该宏添加到对象的 **OnLoad** 事件中。

## <a name="example"></a>示例

下面的示例演示如何使用 SetFilter 操作筛选在其中定义为宏的窗体。

**示例代码提供者** [Microsoft Access 2010 Programmer's Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。

```vb
    OpenForm
        Form Name sfrmFoods
        View Form
        Filter Name
        Where Condition
        Data Mode
        Window Mode Normal
    
    SetFilter
        Filter Name
        Where Condtion =[display_name] Like "*cheese*"
        Control Name
```
