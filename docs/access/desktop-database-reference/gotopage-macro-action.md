---
title: GoToPage 宏操作
TOCTitle: GoToPage macro action
ms:assetid: 611aadff-83b7-e74d-4093-93fb5ce6e3ab
ms:mtpsurl: https://msdn.microsoft.com/library/Ff194858(v=office.15)
ms:contentKeyID: 48545199
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm129285
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 10d55b435a59594eaf3e8380b6690ebbda63a258
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32292158"
---
# <a name="gotopage-macro-action"></a>GoToPage 宏操作

**适用于**：Access 2013、Office 2013

可以使用 **GoToPage** 操作将焦点从活动窗体中移至指定页上的第一个控件上。如果您创建了一个包含若干组相关信息的分页窗体，则可以使用此操作。例如，您可能有一个"员工"窗体，第一页上是个人信息，第二页上是办公室信息，第三页上是销售信息。您可以使用 **GoToPage** 操作移到所需的页。也可以使用选项卡控件将多页信息呈现在单个窗体上。

## <a name="setting"></a>Setting

**GoToPage** 操作具有下列参数。

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
<td><p><strong>页码</strong></p></td>
<td><p>要将焦点移到的页码。请在“宏生成器”窗格<strong>“操作参数”</strong>部分的<strong>“页码”</strong>框中输入页码。如果将此参数留空，焦点将留在当前页上。可以使用“右”<strong></strong>和“下”<strong></strong>参数显示要查看的页部分。</p></td>
</tr>
<tr class="even">
<td><p><strong>Right</strong></p></td>
<td><p>显示在窗口左边缘的页中的点的水平位置，此值从所在窗口的左边缘开始测量。如果指定了“下”<strong></strong>参数，则此参数为必选参数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Down</strong></p></td>
<td><p>显示在窗口上边缘的页中的点的垂直位置，此值从所在窗口的上边缘开始测量。如果指定了“右”<strong></strong>参数，则此参数为必选参数。</p></td>
</tr>
</tbody>
</table>

> [!NOTE]
> “右”**** 和“下”**** 参数的测量单位是英寸或厘米，具体取决于 Windows 控制面板中的区域设置。

## <a name="remarks"></a>注解

可以使用此操作选择指定页上的第一个控件（由窗体的 Tab 键次序定义）。使用 **GoToControl** 操作可移至窗体上的特定控件。

您可以对页面大小大于 Access 窗口的窗体使用**右**和**下**参数。 Use the **Page Number** argument to move to the desired page, and then use the **Right** and **Down** arguments to display the part of the page you want to see. Access displays the part of the page whose upper-left corner is offset the specified distance from the upper-left corner of the page.

在以下情况下，不能使用 **GoToPage** 操作：

- 将焦点移到隐藏窗体上的页上。

- 在选项卡控件中将焦点从某一页移到另一页上。

要在 Visual Basic for Applications (VBA) 模块中运行 **GoToPage** 操作，请使用 **DoCmd** 对象的 **GoToPage** 方法。

