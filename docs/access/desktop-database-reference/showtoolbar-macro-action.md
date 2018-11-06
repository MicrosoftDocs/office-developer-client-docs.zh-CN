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
ms.openlocfilehash: ed69a84f9b1774b7c33711a0bb8e80da54e656cc
ms.sourcegitcommit: 1dd744993ecb4bed241ace874ad26edaef1778b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2018
ms.locfileid: "25997928"
---
# <a name="showtoolbar-macro-action"></a>ShowToolbar 宏操作

**适用于**： Access 2013、 Office 2013

可以使用 **ShowToolbar** 操作显示或隐藏 **"加载项"** 选项卡上的一组命令。

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
<td><p>您想要显示或隐藏<strong>加载项</strong>选项卡上的命令组的名称。 宏生成器窗格中的<strong>操作参数</strong>部分的<strong>工具栏名称</strong>框显示此操作将影响的所有可用的组。 这是必需参数。 如果在类库数据库中运行包含 <strong>ShowToolbar</strong> 操作的宏，Access 将先在该类库数据库中查找具有此名称的组，然后再在当前数据库中查找。</p></td>
</tr>
<tr class="even">
<td><p><strong>Show</strong></p></td>
<td><p>指定是否显示还是隐藏组以及在何种视图中显示或隐藏它。 默认值为<strong>是</strong>（始终显示组）。 您可以选择<strong>是</strong>时间，<strong>其中适当</strong>显示组仅时的相应窗体或报表处于活动状态，或<strong>不</strong>隐藏组任何时候都在所有显示组。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>说明

可以在包含条件表达式的宏中使用此操作，以便根据某些条件来显示或隐藏组。

如果您想要显示在只有一个窗体或报表上的特定组，您可将窗体或报表的**OnActivate**属性设置包含**ShowToolbar**操作显示该组的宏的名称。 包含要隐藏组**ShowToolbar**操作的宏的名称，然后设置窗体或报表的**OnDeactivate**属性。

不可用来显示或隐藏如果**AllowBuiltInToolbars**属性设置为**False** (0) 在 Visual Basic for Applications (VBA) 模块中或将**允许内置工具栏**选项设置为使用此操作的内置工具栏**False**在 VBA 中使用**SetOption**方法。

要在 VBA 模块中运行 **ShowToolbar** 操作，请使用 **DoCmd** 对象的 **ShowToolbar** 方法。

