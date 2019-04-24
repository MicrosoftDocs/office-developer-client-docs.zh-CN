---
title: RunMenuCommand 宏操作
TOCTitle: RunMenuCommand macro action
ms:assetid: cc4a4f72-0c73-91b7-8cec-6cbcda7e5b1c
ms:mtpsurl: https://msdn.microsoft.com/library/Ff834420(v=office.15)
ms:contentKeyID: 48547735
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm6446
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: c2b5a19b7a92fb68dfb774afeec5cd6ba456f38d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32306501"
---
# <a name="runmenucommand-macro-action"></a>RunMenuCommand 宏操作

**适用于**：Access 2013、Office 2013

可以使用 **RunMenuCommand** 操作运行内置的 Microsoft Access 命令。

## <a name="setting"></a>Setting

**RunMenuCommand** 操作具有以下操作参数。

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
<td><p><strong>Command</strong></p></td>
<td><p>要运行的命令的名称。<strong>“命令”</strong>框按照字母顺序显示 Access 中可用的内置命令。这是一个必选参数。</p></td>
</tr>
</tbody>
</table>

## <a name="remarks"></a>注解

可以使用 **RunMenuCommand** 操作运行自定义菜单栏、全局菜单栏、自定义快捷菜单或全局快捷菜单中的 Access 命令。

可以在具有条件表达式的宏内使用 **RunMenuCommand** 操作，以便根据某些条件运行命令。

> [!NOTE]
> Clicking the **File** tab and then clicking **Recent** shows the most recently used databases. You can click one of these databases instead of clicking **Open**. These database items don't appear in the drop-down list box for the **Command** argument, and aren't available by using the **RunMenuCommand** action in a macro.

When you convert an Access database from a previous version of Access, some commands may no longer be available. A command may have been renamed, moved to a different menu, or may no longer be available in Access. The **DoMenuItem** actions for such commands can't be converted to **RunMenuCommand** actions. When you open the macro, Access will display a **RunMenuCommand** action with a blank **Command** argument for such commands. You must edit the macro and enter a valid command argument, or delete the **RunMenuCommand** action.

若要在 Visual Basic for Applications (VBA) 模块中运行 **RunMenuCommand** 操作，请使用 **Application** 对象的 **RunCommand** 方法。（此方法等效于 **DoCmd** 对象的 **RunCommand** 方法。）

