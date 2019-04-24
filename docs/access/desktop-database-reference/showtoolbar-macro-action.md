---
title: ShowToolbar 宏操作
TOCTitle: ShowToolbar macro action
ms:assetid: 9e53009b-1e5e-1bee-3bcc-f82dc1b0dc48
ms:mtpsurl: https://msdn.microsoft.com/library/Ff198288(v=office.15)
ms:contentKeyID: 48546649
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm27417
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 01ba59ce0898068788adb9269b3203794d1f31d4
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32306473"
---
# <a name="showtoolbar-macro-action"></a>ShowToolbar 宏操作

**适用于**：Access 2013、Office 2013

可以使用 **ShowToolbar** 操作显示或隐藏 **“加载项”** 选项卡上的一组命令。

> [!NOTE]
> - [!注释] **ShowToolbar** 操作不影响快捷菜单。
> - [!注释] 如果数据库不受信任，将不允许此操作。 

## <a name="setting"></a>设置

**ShowToolbar** 操作具有下列参数。

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
<td><p><strong>工具栏名称</strong></p></td>
<td><p>在<strong>“加载项”</strong>选项卡上要显示或隐藏的命令组的名称。 “宏生成器”窗格<strong>“操作参数”</strong>部分的<strong>“工具栏名称”</strong>框会显示此操作可以影响到的所有可用的组。 这是一个必选参数。 如果在类库数据库中运行包含 <strong>ShowToolbar</strong> 操作的宏，Access 将先在该类库数据库中查找具有此名称的组，然后再在当前数据库中查找。</p></td>
</tr>
<tr class="even">
<td><p><strong>Show</strong></p></td>
<td><p>指定是显示还是隐藏组以及在哪些视图中显示或隐藏组。 默认值为<strong>"是"</strong> (在所有时间都显示组)。 您可以选择<strong>"是"</strong>以始终显示组, 在<strong>适当</strong>的窗体或报表处于活动状态时仅显示组, 或 "<strong>否</strong>" 则始终隐藏组。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

可以在包含条件表达式的宏中使用此操作，以便根据某些条件来显示或隐藏组。

If you want to show a particular group on just one form or report, you can set the **OnActivate** property of the form or report to the name of a macro that contains a **ShowToolbar** action to show the group. Then set the **OnDeactivate** property of the form or report to the name of a macro that contains a **ShowToolbar** action to hide the group.

The built-in toolbars are not available to display or hide by using this action if you set the **AllowBuiltInToolbars** property to **False** (0) in a Visual Basic for Applications (VBA) module, or if you set the **Allow Built-in Toolbars** option to **False** in VBA by using the **SetOption** method.

要在 VBA 模块中运行 **ShowToolbar** 操作，请使用 **DoCmd** 对象的 **ShowToolbar** 方法。

