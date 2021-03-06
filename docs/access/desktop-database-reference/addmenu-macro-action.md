---
title: AddMenu 宏操作
TOCTitle: AddMenu macro action
ms:assetid: 4eb2afa0-ed1f-41b1-d27f-b3ce7a73d2bb
ms:mtpsurl: https://msdn.microsoft.com/library/Ff193760(v=office.15)
ms:contentKeyID: 48544762
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm37891
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 119e824cae71d54bb398aa68f476a667f14a6888
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32280271"
---
# <a name="addmenu-macro-action"></a>AddMenu 宏操作


**适用于**：Access 2013、Office 2013

本文介绍 **AddMenu** 宏操作的基本操作。

可以使用 **AddMenu** 操作创建：

- 特定窗体或报表的 **"加载项"** 选项卡上的自定义菜单。

- 窗体、报表或控件的自定义快捷菜单。自定义快捷菜单会替换窗体、报表或控件的内置快捷菜单。

- 全局快捷菜单。全局快捷菜单会替换表数据表、查询数据表、窗体和报表中各字段的内置快捷菜单，但为窗体、报表或控件添加的自定义快捷菜单除外。

## <a name="setting"></a>Setting

**AddMenu** 操作具有下列参数。

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
<td><p><strong>菜单名称</strong></p></td>
<td><p>菜单的&quot;名称, 例如, 报表命令&quot;或&quot;工具。&quot; 若要创建访问键以便可以使用键盘选择菜单, 请在要用作访问键的字母前面<strong>&amp;</strong>键入 "and" 符 ()。 在<strong>“加载项”</strong>选项卡上的菜单名称中，此字母将带有下划线。</p></td>
</tr>
<tr class="even">
<td><p><strong>菜单宏名称</strong></p></td>
<td><p>包含与菜单命令相对应的宏的宏组的名称。 这是一个必选参数。</p>
<p><strong>注意</strong>: 如果在类库数据库中运行包含<strong>AddMenu</strong>操作的宏, Microsoft Office Access 2007 将仅在当前数据库中查找具有此名称的宏组。</p></td>
</tr>
<tr class="odd">
<td><p><strong>状态栏文字</strong></p></td>
<td><p>选中菜单时在状态栏中显示的文字。 对于快捷菜单，将忽略此参数。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

要在 Visual Basic for Applications (VBA) 模块中运行 **AddMenu** 操作，请使用 **DoCmd** 对象的 **AddMenu** 方法。在 VBA 中，还可以设置 **MenuBar** 或 **ShortcutMenuBar** 属性，以便在 **"加载项"** 选项卡上创建自定义菜单，或在窗体、报表或控件上附加自定义快捷菜单。可以设置 **Application** 对象的 **ShortcutMenuBar** 属性，以便创建全局快捷菜单。

