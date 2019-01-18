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
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28698307"
---
# <a name="quitaccess-macro-action"></a>QuitAccess 宏操作

**适用于**： Access 2013、 Office 2013

可以使用 **QuitAccess** 操作退出 Microsoft Access。 **QuitAccess** 操作还可以指定在退出 Access 之前用于保存数据库对象的若干选项之一。

> [!NOTE]
> [!注释] 如果数据库不受信任，将不允许此操作。 

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


## <a name="remarks"></a>说明

Access 不运行宏的 **QuitAccess** 操作后的任何操作。

您可以使用此操作退出 Access 不提示**保存**对话框通过使用窗体上的自定义菜单命令或按钮。 例如，您可能必须使用您的自定义工作区中显示的对象的主窗体。 此窗体无法有运行的宏的**QuitAccess**操作包含**选项**参数设置为**全部保存****退出**按钮。

此操作具有相同的效果，然后单击**退出**打开**文件**选项卡。 如果您有任何未保存的对象，当您单击此命令时，显示对话框是显示使用**提示**的**QuitAccess**操作在**Options**参数时的相同。

可以使用宏中的 **SaveObject** 操作保存指定的对象，而不必退出 Access 或者关闭该对象。

若要在 Visual Basic for Applications (VBA) 模块中运行 **QuitAccess** 操作，请使用 **DoCmd** 对象的 **Quit** 方法。

