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
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28712370"
---
# <a name="gotopage-macro-action"></a>GoToPage 宏操作

**适用于**： Access 2013、 Office 2013

可以使用 **GoToPage** 操作将焦点从活动窗体中移至指定页上的第一个控件上。如果您创建了一个包含若干组相关信息的分页窗体，则可以使用此操作。例如，您可能有一个"员工"窗体，第一页上是个人信息，第二页上是办公室信息，第三页上是销售信息。您可以使用 **GoToPage** 操作移到所需的页。也可以使用选项卡控件将多页信息呈现在单个窗体上。

## <a name="setting"></a>设置

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
<td><p>您想要将焦点移到的页的页码。 在宏生成器窗格的<strong>操作参数</strong>部分的<strong>页码</strong>框中输入的页号。 如果将此参数留空，焦点将停留在当前页上。 <strong>右</strong>和<strong>关闭</strong>参数可用于显示您想要查看页上的一部分。</p></td>
</tr>
<tr class="even">
<td><p><strong>Right</strong></p></td>
<td><p>在页上，从页所在窗口，显示在窗口的左边缘的左边缘开始算起的点的水平位置。 如果指定的<strong>向下</strong>参数，这是必需的。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Down</strong></p></td>
<td><p>在页上，从页所在窗口，要显示在窗口的上边缘的上边缘开始算起的点的垂直位置。 如果指定<strong>右</strong>参数，这是必需的。</p></td>
</tr>
</tbody>
</table>

> [!NOTE]
> **右**和**关闭**参数的测量以英寸或厘米，具体取决于 Windows 控制面板中的区域设置。

## <a name="remarks"></a>说明

可以使用此操作选择指定页上的第一个控件（由窗体的 Tab 键次序定义）。使用 **GoToControl** 操作可移至窗体上的特定控件。

可以在页面大于在 Access 窗口中使用窗体**右**和**关闭**的参数。 **页码**参数用于将移动到所需的页，然后使用**右**和**关闭**参数以显示您想要查看页上的一部分。 Access 将显示其左上角存在一定偏移的指定页面的左上角距离页上的一部分。

在以下情况下，不能使用 **GoToPage** 操作：

- 将焦点移到隐藏窗体上的页上。

- 在选项卡控件中将焦点从某一页移到另一页上。

要在 Visual Basic for Applications (VBA) 模块中运行 **GoToPage** 操作，请使用 **DoCmd** 对象的 **GoToPage** 方法。

