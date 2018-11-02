---
title: MoveAndSizeWindow 宏操作
TOCTitle: MoveAndSizeWindow macro action
ms:assetid: 86bcf45f-90ce-4ca2-a7fb-efbe5347d137
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197001(v=office.15)
ms:contentKeyID: 48546090
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: fd5bbe18af823e2b36772ef209db18ba6cb4b1d4
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25925266"
---
# <a name="moveandsizewindow-macro-action"></a>MoveAndSizeWindow 宏操作


**适用于**： Access 2013、 Office 2013


如果已将文档设置为使用重叠窗口而不是选项卡式文档的窗口选项，您可以使用**MoveAndSizeWindow**操作移动或调整活动窗口。 有关如何设置文档窗口选项的信息，请参阅备注部分。

## <a name="setting"></a>设置

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
<td><p>窗口左上角的新水平位置，从页所在窗口的左边缘开始算起。 在宏生成器窗格的<strong>操作参数</strong>部分中输入<strong>右</strong>框中的位置。</p></td>
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


如果参数为空，Microsoft Access 将使用窗口的当前设置。

您必须至少一个参数输入值。


> [!NOTE]
> <P>每个度量值是以英寸或厘米，具体取决于 Windows 控制面板中的区域设置。</P>



## <a name="remarks"></a>说明

若要设置应用程序使用重叠窗口而不是选项卡式文档，请使用以下过程：

1.  ，然后单击**选项**

2.  单击**当前数据库**。

3.  在 **“应用程序选项”** 部分中的 **“文档窗口选项”** 下，单击 **“重叠窗口”**。

4.  单击**确定**，然后关闭并重新打开数据库。

此操作类似于单击窗口**控件**菜单上的**移动**或**大小**。 与菜单命令中，您可以使用键盘的箭头键来移动或调整窗口大小。 如果使用**MoveAndSizeWindow**操作，您输入的位置和大小度量直接。 您还可以使用鼠标移动和调整窗口大小。

您可以在任何窗口中，在任何视图中使用此操作。

**提示**

  - 若要移动窗口而不调整其大小，**右边**和**向下**参数输入值，但将**Width**和**Height**参数留空。

  - 若要调整窗口大小而不移动的**宽度**和**高度**参数输入值，但将**右**和**关闭**参数留空。

若要在 Visual Basic for Applications (VBA) 模块中运行**MoveAndSizeWindow**操作，请使用**DoCmd**对象的**MoveSize**方法。

## <a name="example"></a>示例

**通过使用宏同步处理窗体**

下面的宏将在显示当前供应商的产品 Suppliers 窗体的右下角中打开产品列表窗体。 它演示如何使用**回声**、 **MessageBox**、 **GoToControl**、 **StopMacro**、 **OpenForm**，和**MoveAndSizeWindow**操作。 它还会显示具有**MessageBox**、 **GoToControl**和**StopMacro**操作的条件表达式使用。 这个宏应附加到 Suppliers 窗体上的查看产品按钮。

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
<th><p>注释</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p></p></td>
<td><p><strong>Echo</strong></p></td>
<td><p><strong>打开回响</strong>：<strong>否</strong></p></td>
<td><p>停止屏幕更新时运行宏。</p></td>
</tr>
<tr class="even">
<td><p>IsNull ([供应商 ID])</p></td>
<td><p><strong>MessageBox</strong></p></td>
<td><p><strong>消息</strong>： 移动到您要查看其的产品然后再次单击查看产品按钮的供应商记录。 <strong>发嘟嘟声</strong>： <strong>YesType</strong>: <strong>NoneTitle</strong>： 选择一个供应商</p></td>
<td><p>如果 Suppliers 窗体上没有当前供应商，显示一条消息。</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p><strong>GoToControl</strong></p></td>
<td><p><strong>控件名称</strong>： 公司名称</p></td>
<td><p>将焦点移到公司名称控件。</p></td>
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
<td><p><strong>窗体名称</strong>： 产品列表<strong>视图</strong>： <strong>DatasheetFilter 名称</strong>： <strong>Where 条件</strong>: [供应商 ID] = [窗体] ！[供应商] ！[SupplierID]<strong>数据模式</strong>：<strong>读取 OnlyWindow 模式</strong>：<strong>普通</strong></p></td>
<td><p>打开产品列表窗体并显示当前供应商的产品。</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p><strong>MoveAndSizeWindow</strong></p></td>
<td><p><strong>右</strong>： 0.7799&quot; <strong>下</strong>： 1.8&quot;</p></td>
<td><p>产品列表表单 Suppliers 窗体的右下角的位置。</p></td>
</tr>
</tbody>
</table>

