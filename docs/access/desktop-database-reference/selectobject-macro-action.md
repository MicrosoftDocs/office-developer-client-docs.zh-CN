---
title: SelectObject 宏操作
TOCTitle: SelectObject macro action
ms:assetid: a90539a0-c5a0-e997-9c25-e0972d28f2a6
ms:mtpsurl: https://msdn.microsoft.com/library/Ff821420(v=office.15)
ms:contentKeyID: 48546914
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm41840
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 6287bc8a66858d51d65c37477eed7a86cd7839af
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32308727"
---
# <a name="selectobject-macro-action"></a>SelectObject 宏操作

**适用于**：Access 2013、Office 2013

可以使用 **SelectObject** 操作选择指定的数据库对象。

## <a name="setting"></a>Setting

**SelectObject** 操作具有下列参数。

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
<td><p><strong>对象类型</strong></p></td>
<td><p>要选择的数据库对象的类型。请在“宏生成器”窗格<strong>“操作参数”</strong>部分的<strong>“对象类型”</strong>框中单击<strong>“表”</strong>、<strong>“查询”</strong>、<strong>“窗体”</strong>、<strong>“报表”</strong>、<strong>“宏”</strong>、<strong>“模块”</strong>、<strong>“数据访问页”</strong>、<strong>“服务器视图”</strong>、<strong>“图表”</strong>、<strong>“存储过程”</strong>或<strong>“函数”</strong>。这是一个必选参数。</p></td>
</tr>
<tr class="even">
<td><p><strong>对象名称</strong></p></td>
<td><p>要选择的对象的名称。<strong>“对象名称”</strong>框会显示数据库中属于“对象类型”<strong></strong>参数所选的类型的所有对象。除非您将“在导航窗格中”参数设置为<strong>“是”</strong>，否则此参数是必选参数。</p><p><strong>注意</strong>:<STRONG>服务器视图</STRONG>、<STRONG>图表</STRONG>或<STRONG>存储过程</STRONG>对象的对象名称不会显示在 Access 项目 (.adp) 的 "<STRONG>对象名称</STRONG>" 框中。</p></td>
</tr>
<tr class="odd">
<td><p><strong>在导航窗格中</strong></p></td>
<td><p>指定 Microsoft Access 是否选择导航窗格中的对象。请单击<strong>“是”</strong>（选择导航窗格中的对象）或<strong>“否”</strong>（不选择导航窗格中的对象）。默认值为<strong>“否”</strong>。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注解

**SelectObject** 操作适用于可以接收焦点的任何 Access 对象。此操作将焦点移到指定的对象上，如果对象是隐藏的，还将显示该对象。如果该对象为窗体，**SelectObject** 操作会将窗体的“可见”**** 属性设置为“是”****，并将窗体返回到通过其窗体属性设置的模式（例如，模式或弹出式窗体）。

If the object isn't open in one of the other Access windows, you can select it in the Navigation Pane by setting the **In Navigation Pane** argument to **Yes**. If you set the **In Navigation Pane** argument to **No**, an error message appears when you try to select an object that isn't open.

通常，您可能会使用此操作来选择要对其执行其他操作的对象。例如，如果您将 Access 配置为使用重叠窗口，而不是使用选项卡式文档，您可能需要还原已经最小化的对象（使用 **RestoreWindow** 操作）或最大化包含您要使用的对象的窗口（使用 **MaximizeWindow** 操作）。

如果您选择了窗体，则可以使用 **GoToControl** 、 **GoToRecord** 和 **GoToPage** 操作移动至窗体上的特定区域。 **GoToRecord** 操作也适用于数据表。

要在 Visual Basic for Applications (VBA) 模块中运行 **SelectObject** 操作，请使用 **DoCmd** 对象的 **SelectObject** 方法。

