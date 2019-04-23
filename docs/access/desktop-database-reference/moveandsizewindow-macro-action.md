---
title: MoveAndSizeWindow 宏操作
TOCTitle: MoveAndSizeWindow macro action
ms:assetid: 86bcf45f-90ce-4ca2-a7fb-efbe5347d137
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197001(v=office.15)
ms:contentKeyID: 48546090
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: c1b127995a2f9a0af7da80e9df862259b570870e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288804"
---
# <a name="moveandsizewindow-macro-action"></a>MoveAndSizeWindow 宏操作

**适用于**：Access 2013、Office 2013

如果您已将文档窗口选项设置为使用重叠窗口而不是选项卡式文档, 则可以使用**MoveAndSizeWindow**操作移动或调整活动窗口的大小。 有关如何设置文档窗口选项的信息, 请参阅 "备注" 部分。

## <a name="setting"></a>Setting

**MoveAndSizeWindow**操作具有下列参数。

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
<td><p><strong>Right</strong></p></td>
<td><p>窗口左上角的新水平位置，从页所在窗口的左边缘开始算起。 在 "宏生成器" 窗格的 "<strong>操作参数</strong>" 部分的 "<strong>右</strong>" 框中输入位置。</p></td>
</tr>
<tr class="even">
<td><p><strong>Down</strong></p></td>
<td><p>活动窗口左上角的新垂直位置，从页所在窗口的上边缘开始算起。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Width</strong></p></td>
<td><p>活动窗口的新宽度。</p></td>
</tr>
<tr class="even">
<td><p><strong>Height</strong></p></td>
<td><p>活动窗口的新高度。</p></td>
</tr>
</tbody>
</table>


如果将参数留空, Microsoft Access 将使用窗口的当前设置。

必须至少输入一个参数的值。

> [!NOTE]
> 每个度量单位都以英寸或厘米为单位, 具体取决于 Windows "控制面板" 中的区域设置。

## <a name="remarks"></a>注解

若要将应用程序设置为使用重叠窗口而不是选项卡式文档, 请使用以下过程:

1.  单击 "**选项**"

2.  单击 "**当前数据库**"。

3.  在 **“应用程序选项”** 部分中的 **“文档窗口选项”** 下，单击 **“重叠窗口”**。

4.  单击 **"确定**", 然后关闭并重新打开数据库。

此操作类似于在窗口的 "**控制**" 菜单上单击 "**移动**" 或 "**大小**"。 使用菜单命令, 可以使用键盘的箭头键移动或调整窗口大小。 使用**MoveAndSizeWindow**操作, 可以直接输入位置和大小的度量值。 您还可以使用鼠标移动窗口和调整窗口大小。

您可以在任何视图中的任何窗口上使用此操作。

> [!TIP]
> - 若要在不调整窗口大小的情况下移动窗口, 请为**Right**和**Down**参数输入值, 但将**Width**和**Height**参数保留为空。
> - 若要调整窗口大小而不移动它, 请输入**Width**和**Height**参数的值, 但将**右侧**和**下方**参数留空。

若要在 Visual Basic for Applications (VBA) 模块中运行**MoveAndSizeWindow**操作, 请使用**DoCmd**对象的**MoveSize**方法。

## <a name="example"></a>示例

**使用宏同步窗体**

以下宏将打开 "供应商" 窗体右下角的 "产品列表" 窗体, 显示当前供应商的产品。 它演示了如何使用**Echo**、 **MessageBox**、 **GoToControl**、 **StopMacro**、 **OpenForm**和**MoveAndSizeWindow**操作。 它还演示了如何使用带有**MessageBox**、 **GoToControl**和**StopMacro**操作的条件表达式。 此宏应附加到 "供应商" 窗体上的 "查看产品" 按钮。

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>条件</p></th>
<th><p>操作</p></th>
<th><p>参数：设置</p></th>
<th><p>Comment</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p></p></td>
<td><p><strong>Echo</strong></p></td>
<td><p><strong>打开回响</strong>:<strong>否</strong></p></td>
<td><p>在宏运行时停止屏幕更新。</p></td>
</tr>
<tr class="even">
<td><p>IsNull ([供应商 ID])</p></td>
<td><p><strong>MessageBox</strong></p></td>
<td><p><strong>消息</strong>: 移动到要查看其产品的供应商记录, 然后再次单击 "查看产品" 按钮。 <strong>嘟嘟声</strong>: <strong>YesType</strong>: <strong>NoneTitle</strong>: 选择供应商</p></td>
<td><p>如果 "供应商" 窗体上没有当前供应商, 则显示一条消息。</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p><strong>GoToControl</strong></p></td>
<td><p><strong>控件名称</strong>: 公司名称</p></td>
<td><p>将焦点移到 "公司名称" 控件。</p></td>
</tr>
<tr class="even">
<td><p>...</p></td>
<td><p><strong>StopMacro</strong></p></td>
<td><p></p></td>
<td><p>停止宏。</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p><strong>OpenForm</strong></p></td>
<td><p><strong>表单名称</strong>: 产品列表<strong>视图</strong>: <strong>DatasheetFilter Name</strong>: <strong>Where 条件</strong>: [供应商 ID] = [Forms]![供应商]!id<strong>数据模式</strong>:<strong>读取 OnlyWindow 模式</strong>:<strong>普通</strong></p></td>
<td><p>打开 "产品列表" 表单并显示当前供应商的产品。</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p><strong>MoveAndSizeWindow</strong></p></td>
<td><p><strong>右侧</strong>: 0.7799&quot; <strong></strong>: 1。8&quot;</p></td>
<td><p>将 "产品列表" 窗体放置在 "供应商" 窗体的右下角。</p></td>
</tr>
</tbody>
</table>

