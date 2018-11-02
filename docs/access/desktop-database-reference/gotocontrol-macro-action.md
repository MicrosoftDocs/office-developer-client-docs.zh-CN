---
title: GoToControl 宏操作
TOCTitle: GoToControl macro action
ms:assetid: caff76dc-7ca8-4f87-8144-89445ed4600d
ms:mtpsurl: https://msdn.microsoft.com/library/Ff834370(v=office.15)
ms:contentKeyID: 48547705
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 9fafa3ea40b492baf8b49dd240c6f7767ffad655
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25926652"
---
# <a name="gotocontrol-macro-action"></a>GoToControl 宏操作


**适用于**： Access 2013、 Office 2013



您可以使用**GoToControl**操作将焦点移到指定的域或打开的窗体、 窗体数据表、 表数据表的当前记录中的控件或查询数据表。 当你希望特定字段或控件获得焦点时，可以使用此操作。 然后比较或 **FindRecord** 操作可以使用该字段或控件。 你可以使用此操作以根据特定的条件在表单中导航。 例如，如果用户输入婚姻控件不能在健康保险窗体，焦点可以自动跳过配偶姓名控件并移动到下一个控件。

## <a name="setting"></a>设置


> [!NOTE]
> <P>此操作不适用于数据访问页。</P>



**GoToControl** 操作具有以下参数。

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
<td><p><strong>控件名称</strong></p></td>
<td><p>希望获得焦点的字段或控件的名称。 在<strong>操作参数</strong>部分的宏生成器窗格中的<strong>控件名称</strong>框中输入字段或控件的名称。 这是必需参数。</p>

> [!NOTE]
> <P><STRONG>控件名称</STRONG>参数，而不是完全限定标识符，如表单中输入仅字段或控件的名称 ！产品 ！[Product ID]。</P>


<p></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>说明

不能使用**GoToControl**操作将焦点移到隐藏窗体上的控件。


> [!TIP]
> <P><STRONG>GoToControl</STRONG>操作可用于将移动到子窗体，这是一类控件。 然后，您可以使用<STRONG>GoToRecord</STRONG>操作将移到子窗体中的特定记录。 您也可以通过使用<STRONG>GoToControl</STRONG>操作移到子窗体和子窗体上的控件移到子窗体上的控件。</P>



若要在 Visual Basic for Applications (VBA) 模块中运行**GoToControl**操作，请使用**DoCmd**对象的**GoToControl**方法。 您还可以使用 **SetFocus** 方法将焦点移到窗体或其任何子窗体上的控件或打开的表、 查询或窗体数据表中的字段。

## <a name="examples"></a>示例

**通过使用宏设置控件的值**

下面的宏 Suppliers 窗体上的按钮打开添加产品窗体。 它演示如何使用**回声**、 **CloseWindow**、 **OpenForm**、 **SetValue**和**GoToControl**操作。 **SetValue**操作供应商窗体上将产品窗体上的供应商 ID 控件设置为当前供应商。 然后， **GoToControl**操作将焦点移到类别 ID 字段中，您可以开始新产品的输入数据。 这个宏应附加到 Suppliers 窗体上的添加产品按钮。

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>操作</p></th>
<th><p>参数：设置</p></th>
<th><p>注释</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Echo</strong></p></td>
<td><p><strong>打开回响</strong>：<strong>否</strong></p></td>
<td><p>停止屏幕更新时运行宏。</p></td>
</tr>
<tr class="even">
<td><p><strong>CloseWindow</strong></p></td>
<td><p><strong>对象类型</strong>： <strong>FormObject 名称</strong>： 产品列表<strong>保存</strong>：<strong>否</strong></p></td>
<td><p>关闭产品列表窗体。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OpenForm</strong></p></td>
<td><p><strong>窗体名称</strong>： 产品<strong>视图</strong>： <strong>FormData 模式</strong>： <strong>AddWindow 模式</strong>：<strong>普通</strong></p></td>
<td><p>打开产品窗体。</p></td>
</tr>
<tr class="even">
<td><p><strong>SetValue</strong></p></td>
<td><p><strong>项目</strong>: [窗体] ！[产品] ！[SupplierID]<strong>表达式</strong>： 供应商 Id</p></td>
<td><p>在 Suppliers 窗体上将供应商 ID 控件设置为当前供应商。</p></td>
</tr>
<tr class="odd">
<td><p><strong>GoToControl</strong></p></td>
<td><p><strong>控件名称</strong>： CategoryID</p></td>
<td><p>转到类别 ID 控件。</p></td>
</tr>
</tbody>
</table>


**通过使用宏验证数据**

下面的验证宏会检查在"供应商"窗体中输入的邮政编码。 它演示如何使用 **StopMacro** 、 **MessageBox** 、 **CancelEvent** 和 **GoToControl** 操作。 其条件表达式检查在窗体的记录中输入的国家/地区和邮政编码。 如果邮政编码的格式与国家/地区不符，该宏将显示一个消息框并取消对该记录的保存操作。 宏然后您返回到邮政编码控件，您可以在其中更正错误。 此宏应附加到"供应商"窗体的 **BeforeUpdate** 属性。

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
<td><p>IsNull([CountryRegion])</p></td>
<td><p><strong>StopMacro</strong></p></td>
<td><p></p></td>
<td><p>国家/地区为<strong>Null</strong>，如果无法验证邮政编码。</p></td>
</tr>
<tr class="even">
<td><p>[国家/地区]中 (&quot;法国&quot;，&quot;意大利&quot;，&quot;西班牙&quot;) And Len （[邮政编码]） &lt; &gt; 5</p></td>
<td><p><strong>MessageBox</strong></p></td>
<td><p><strong>消息</strong>： 邮政编码必须为 5 个字符。 <strong>发嘟嘟声</strong>： <strong>YesType</strong>: <strong>InformationTitle</strong>： 邮政编码错误</p></td>
<td><p>如果邮政编码不是 5 个字符，则显示一条消息。</p></td>
</tr>
<tr class="odd">
<td><p>...</p></td>
<td><p><strong>CancelEvent</strong></p></td>
<td><p></p></td>
<td><p>取消事件。</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p><strong>GoToControl</strong></p></td>
<td><p><strong>控件名称</strong>： 邮政编码</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>[国家/地区]中 (&quot;澳大利亚&quot;，&quot;新加坡&quot;) And Len （[邮政编码]） &lt; &gt; 4</p></td>
<td><p><strong>MessageBox</strong></p></td>
<td><p>消息：邮政编码必须为 4 个字符。 

 <strong>发嘟嘟声</strong>： <strong>YesType</strong>: <strong>InformationTitle</strong>： 邮政编码错误</p></td>
<td><p>如果邮政编码不是 4 个字符，则显示一条消息。</p></td>
</tr>
<tr class="even">
<td><p>...</p></td>
<td><p><strong>CancelEvent</strong></p></td>
<td><p></p></td>
<td><p>取消事件。</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p><strong>GoToControl</strong></p></td>
<td><p><strong>控件名称</strong>： 邮政编码</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>([国家/地区] =&quot;加拿大&quot;)和 ([邮政编码] Not Like&quot;[A-Z] [0-9] [A-Z] [0-9] [A-Z] [0-9]&quot;)</p></td>
<td><p><strong>MessageBox</strong></p></td>
<td><p><strong>消息</strong>： 邮政编码无效。 加拿大代码示例： H1J 1c3<strong>发嘟嘟声</strong>： <strong>YesType</strong>: <strong>InformationTitle</strong>： 邮政代码错误</p></td>
<td><p>如果邮政编码不正确的加拿大，显示一条消息。 (加拿大代码示例： H1J 1c3)</p></td>
</tr>
<tr class="odd">
<td><p>...</p></td>
<td><p><strong>CancelEvent</strong></p></td>
<td><p></p></td>
<td><p>取消事件。</p></td>
</tr>
</tbody>
</table>

