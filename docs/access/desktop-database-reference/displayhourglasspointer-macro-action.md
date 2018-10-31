---
title: DisplayHourglassPointer 宏操作
TOCTitle: DisplayHourglassPointer Macro Action
ms:assetid: 2c93039a-f75c-abeb-1dfa-e632a5bdf6f2
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192103(v=office.15)
ms:contentKeyID: 48543957
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm117200
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 725bb4530bffe9aeead327caa74cdba0798c181d
ms.sourcegitcommit: 801b1b54786f7b0e5b0d35466e7ae8d1e840b26f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25862652"
---
# <a name="displayhourglasspointer-macro-action"></a>DisplayHourglassPointer 宏操作


**适用于**： Access 2013 |Office 2013

可以使用 **DisplayHourglassPointer** 操作在宏运行时将鼠标指针更改为沙漏图像（或选择的其他图标）。此操作可直观地指示宏正在运行。当宏操作或宏本身需要较长的运行时间时，这会特别有用。

## <a name="setting"></a>设置

**DisplayHourglassPointer** 操作具有以下参数。

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
<td><p><strong>显示沙漏</strong></p></td>
<td><p>请在“宏生成器”窗格<strong>“操作参数”</strong>部分的<strong>“显示沙漏”</strong>框中单击<strong>“是”</strong>（显示图标）或<strong>“否”</strong>（显示正常的鼠标指针）。默认值为<strong>“是”</strong>。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>说明

如果已使用 **Echo** 操作关闭回响，则通常要使用此操作。 回声关闭时，Access 将挂起屏幕更新，直到完成宏。

当宏运行完毕时，access 会将**显示沙漏**参数自动重置为**否**。

> [!NOTE]
> - 在 Microsoft Windows 中，这是在 Windows 控制面板的 **"鼠标属性"** 对话框中为 **"忙"** 设置的图标。所有 Windows 操作系统的默认设置都是一个具有动画效果的沙漏图标。
> - 您可以根据需要选择其他图标。

若要在 Visual Basic for Applications (VBA) 模块中运行 **DisplayHourglassPointer** 操作，请使用 **DoCmd** 对象的 **Hourglass** 方法。

