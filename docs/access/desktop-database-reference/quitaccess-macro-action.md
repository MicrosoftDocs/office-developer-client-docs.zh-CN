---
title: QuitAccess 宏操作
TOCTitle: QuitAccess macro action
ms:assetid: af063f65-d3b1-fa9a-4bc1-04b0d21d62b9
ms:mtpsurl: https://msdn.microsoft.com/library/Ff821759(v=office.15)
ms:contentKeyID: 48547089
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm96777
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 424b2b2cab9bc4272052a201350a0cc2ab297b8c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32302812"
---
# <a name="quitaccess-macro-action"></a>QuitAccess 宏操作

**适用于**：Access 2013、Office 2013

可以使用 **QuitAccess** 操作退出 Microsoft Access。**QuitAccess** 操作还可以指定在退出 Access 之前用于保存数据库对象的若干选项之一。

> [!NOTE]
> 如果数据库不受信任，则不允许执行此操作。 

## <a name="setting"></a>设置

**QuitAccess** 操作具有以下参数。

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
<td><p><strong>选项</strong></p></td>
<td><p>指定在退出 Access 时未保存的对象会出现什么情况。请在“宏生成器”窗格<strong>“操作参数”</strong>部分的<strong>“选项”</strong>对话框中单击<strong>“提示”</strong>（显示询问是否保存每个对象的对话框）、<strong>“全部保存”</strong>（直接保存所有对象而不使用对话框提示）或<strong>“退出”</strong>（退出而不保存任何对象）。默认值为<strong>“全部保存”</strong>。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

Access 不运行宏的 **QuitAccess** 操作后的任何操作。

You can use this action to quit Access without prompts from **Save** dialog boxes by using a custom menu command or a button on a form. For example, you might have a master form that you use to display the objects in your custom workspace. This form could have a **Quit** button that runs a macro containing the **QuitAccess** action with the **Options** argument set to **Save All**.

This action has the same effect as clicking the **File** tab and then clicking **Exit**. If you have any unsaved objects when you click this command, the dialog boxes that appear are the same as those displayed when you use **Prompt** for the **Options** argument of the **QuitAccess** action.

可以使用宏中的 **SaveObject** 操作保存指定的对象，而不必退出 Access 或者关闭该对象。

若要在 Visual Basic for Applications (VBA) 模块中运行 **QuitAccess** 操作，请使用 **DoCmd** 对象的 **Quit** 方法。

