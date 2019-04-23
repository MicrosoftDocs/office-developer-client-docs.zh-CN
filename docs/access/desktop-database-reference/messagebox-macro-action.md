---
title: MessageBox 宏操作
TOCTitle: MessageBox macro action
ms:assetid: 326a0e68-38fb-4f81-b319-5a70caa5aec4
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192304(v=office.15)
ms:contentKeyID: 48544077
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 1175e3903e54fd3420be43dfd9e3652d9990468b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289154"
---
# <a name="messagebox-macro-action"></a><span data-ttu-id="379e0-102">MessageBox 宏操作</span><span class="sxs-lookup"><span data-stu-id="379e0-102">MessageBox macro action</span></span>

<span data-ttu-id="379e0-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="379e0-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="379e0-104">可以使用**MessageBox**操作显示包含警告或信息性消息的消息框。</span><span class="sxs-lookup"><span data-stu-id="379e0-104">You can use the **MessageBox** action to display a message box containing a warning or an informational message.</span></span> <span data-ttu-id="379e0-105">例如, 可以将**MessageBox**操作与验证宏一起使用。</span><span class="sxs-lookup"><span data-stu-id="379e0-105">For example, you can use the **MessageBox** action with validation macros.</span></span> <span data-ttu-id="379e0-106">当控件或记录未通过宏的有效性验证条件时, 消息框会显示一条错误消息, 并提供有关应输入的数据类型的说明。</span><span class="sxs-lookup"><span data-stu-id="379e0-106">When a control or record fails a validation condition in the macro, a message box can display an error message and provide instructions about the kind of data that should be entered.</span></span>

## <a name="setting"></a><span data-ttu-id="379e0-107">Setting</span><span class="sxs-lookup"><span data-stu-id="379e0-107">Setting</span></span>

<span data-ttu-id="379e0-108">**MessageBox**操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="379e0-108">The **MessageBox** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="379e0-109">操作参数</span><span class="sxs-lookup"><span data-stu-id="379e0-109">Action argument</span></span></p></th>
<th><p><span data-ttu-id="379e0-110">说明</span><span class="sxs-lookup"><span data-stu-id="379e0-110">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="379e0-111"><strong>Message</strong></span><span class="sxs-lookup"><span data-stu-id="379e0-111"><strong>Message</strong></span></span></p></td>
<td><p><span data-ttu-id="379e0-112">消息框中的文本。</span><span class="sxs-lookup"><span data-stu-id="379e0-112">The text in the message box.</span></span> <span data-ttu-id="379e0-113">在 "宏生成器" 窗格的 "<strong>操作参数</strong>" 部分的 "<strong>消息</strong>" 框中输入消息文本。</span><span class="sxs-lookup"><span data-stu-id="379e0-113">Enter the message text in the <strong>Message</strong> box in the <strong>Action Arguments</strong> section of the Macro Builder pane.</span></span> <span data-ttu-id="379e0-114">最长可键入255个字符或输入一个表达式 (前面加上等号)。</span><span class="sxs-lookup"><span data-stu-id="379e0-114">You can type up to 255 characters or enter an expression (preceded by an equal sign).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="379e0-115"><strong>Beep</strong></span><span class="sxs-lookup"><span data-stu-id="379e0-115"><strong>Beep</strong></span></span></p></td>
<td><p><span data-ttu-id="379e0-116">指定在显示消息时, 计算机的扬声器是否发出嘟嘟声。</span><span class="sxs-lookup"><span data-stu-id="379e0-116">Specifies whether your computer's speaker sounds a beep tone when the message displays.</span></span> <span data-ttu-id="379e0-117">单击<strong>"是"</strong> (发出蜂鸣音) 或 "<strong>否</strong>" (不发出嘟嘟声)。</span><span class="sxs-lookup"><span data-stu-id="379e0-117">Click <strong>Yes</strong> (sound the beep tone) or <strong>No</strong> (don't sound the beep tone).</span></span> <span data-ttu-id="379e0-118">默认值为 <strong>"是"</strong>。</span><span class="sxs-lookup"><span data-stu-id="379e0-118">The default is <strong>Yes</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="379e0-119"><strong>Type</strong></span><span class="sxs-lookup"><span data-stu-id="379e0-119"><strong>Type</strong></span></span></p></td>
<td><p><span data-ttu-id="379e0-120">消息框的类型。</span><span class="sxs-lookup"><span data-stu-id="379e0-120">The type of message box.</span></span> <span data-ttu-id="379e0-121">每种类型都有一个不同的图标。</span><span class="sxs-lookup"><span data-stu-id="379e0-121">Each type has a different icon.</span></span> <span data-ttu-id="379e0-122">单击 "<strong>无</strong>、<strong>紧急</strong>、<strong>警告？</strong>、<strong>警告!</strong>" 或 "<strong>信息</strong>"。</span><span class="sxs-lookup"><span data-stu-id="379e0-122">Click <strong>None</strong>, <strong>Critical</strong>, <strong>Warning?</strong>, <strong>Warning!</strong>, or <strong>Information</strong>.</span></span> <span data-ttu-id="379e0-123">默认值为 "<strong>无</strong>"。</span><span class="sxs-lookup"><span data-stu-id="379e0-123">The default is <strong>None</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="379e0-124"><strong>Title</strong></span><span class="sxs-lookup"><span data-stu-id="379e0-124"><strong>Title</strong></span></span></p></td>
<td><p><span data-ttu-id="379e0-125">消息框标题栏中显示的文本。</span><span class="sxs-lookup"><span data-stu-id="379e0-125">The text displayed in the message box title bar.</span></span> <span data-ttu-id="379e0-126">例如, 您可以让标题栏显示&quot;"客户 ID" 验证&quot;。</span><span class="sxs-lookup"><span data-stu-id="379e0-126">For example, you can have the title bar display &quot;Customer ID Validation&quot;.</span></span> <span data-ttu-id="379e0-127">如果将此参数留空, &quot;则会&quot;显示 Microsoft Access。</span><span class="sxs-lookup"><span data-stu-id="379e0-127">If you leave this argument blank, &quot;Microsoft Access&quot; is displayed.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="379e0-128">注解</span><span class="sxs-lookup"><span data-stu-id="379e0-128">Remarks</span></span>

<span data-ttu-id="379e0-129">可以使用**MessageBox**操作创建类似于 Microsoft Access 所显示的内置错误消息的格式化错误消息。</span><span class="sxs-lookup"><span data-stu-id="379e0-129">You can use the **MessageBox** action to create a formatted error message similar to built-in error messages displayed by Microsoft Access.</span></span> <span data-ttu-id="379e0-130">**MessageBox**操作允许您在三个部分中为 message 参数提供一条消息。</span><span class="sxs-lookup"><span data-stu-id="379e0-130">The **MessageBox** action permits you to supply a message in three sections for the Message argument.</span></span> <span data-ttu-id="379e0-131">使用 "@" 字符分隔各部分。</span><span class="sxs-lookup"><span data-stu-id="379e0-131">You separate the sections with the "@" character.</span></span>

<span data-ttu-id="379e0-132">下面的示例显示一个带有分节消息的格式化消息框。</span><span class="sxs-lookup"><span data-stu-id="379e0-132">The following example displays a formatted message box with a sectioned message.</span></span> <span data-ttu-id="379e0-133">邮件中文本的第一部分显示为加粗标题。</span><span class="sxs-lookup"><span data-stu-id="379e0-133">The first section of text in the message is displayed as a bold heading.</span></span> <span data-ttu-id="379e0-134">第二部分在标题下方显示为纯文本。</span><span class="sxs-lookup"><span data-stu-id="379e0-134">The second section is displayed as plain text beneath that heading.</span></span> <span data-ttu-id="379e0-135">第三部分以纯文本的形式显示在第二部分的下方, 中间有一个空行。</span><span class="sxs-lookup"><span data-stu-id="379e0-135">The third section is displayed as plain text beneath the second section, with a blank line between them.</span></span>

<span data-ttu-id="379e0-136">在**Message**参数中键入以下字符串:</span><span class="sxs-lookup"><span data-stu-id="379e0-136">Type the following string in the **Message** argument:</span></span>

<span data-ttu-id="379e0-137">**错误按钮\!@This 按钮不起作用。 @Try 其他按钮。**</span><span class="sxs-lookup"><span data-stu-id="379e0-137">**Wrong button\!@This button doesn't work.@Try another.**</span></span>

<span data-ttu-id="379e0-138">不能在 Visual Basic for Applications (VBA) 模块中运行**MessageBox**操作。</span><span class="sxs-lookup"><span data-stu-id="379e0-138">You can't run the **MessageBox** action in a Visual Basic for Applications (VBA) module.</span></span> <span data-ttu-id="379e0-139">改为使用**MsgBox**函数。</span><span class="sxs-lookup"><span data-stu-id="379e0-139">Use the **MsgBox** function instead.</span></span>

## <a name="examples"></a><span data-ttu-id="379e0-140">示例</span><span class="sxs-lookup"><span data-stu-id="379e0-140">Examples</span></span>

<span data-ttu-id="379e0-141">**使用宏同步窗体**</span><span class="sxs-lookup"><span data-stu-id="379e0-141">**Synchronize forms by using a macro**</span></span>

<span data-ttu-id="379e0-142">以下宏将打开 "供应商" 窗体右下角的 "产品列表" 窗体, 显示当前供应商的产品。</span><span class="sxs-lookup"><span data-stu-id="379e0-142">The following macro opens a Product List form in the lower-right corner of the Suppliers form, displaying the current supplier's products.</span></span> <span data-ttu-id="379e0-143">它演示了如何使用**Echo**、 **MessageBox**、 **GoToControl**、 **StopMacro**、 **OpenForm**和**MoveAndSizeWindow**操作。</span><span class="sxs-lookup"><span data-stu-id="379e0-143">It shows the use of the **Echo**, **MessageBox**, **GoToControl**, **StopMacro**, **OpenForm**, and **MoveAndSizeWindow** actions.</span></span> <span data-ttu-id="379e0-144">它还演示了如何使用带有**MessageBox**、 **GoToControl**和**StopMacro**操作的条件表达式。</span><span class="sxs-lookup"><span data-stu-id="379e0-144">It also shows the use of a conditional expression with the **MessageBox**, **GoToControl**, and **StopMacro** actions.</span></span> <span data-ttu-id="379e0-145">此宏应附加到 "供应商" 窗体上的 "查看产品" 按钮。</span><span class="sxs-lookup"><span data-stu-id="379e0-145">This macro should be attached to the Review Products button on the Suppliers form.</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="379e0-146">条件</span><span class="sxs-lookup"><span data-stu-id="379e0-146">Condition</span></span></p></th>
<th><p><span data-ttu-id="379e0-147">操作</span><span class="sxs-lookup"><span data-stu-id="379e0-147">Action</span></span></p></th>
<th><p><span data-ttu-id="379e0-148">参数：设置</span><span class="sxs-lookup"><span data-stu-id="379e0-148">Arguments: Setting</span></span></p></th>
<th><p><span data-ttu-id="379e0-149">Comment</span><span class="sxs-lookup"><span data-stu-id="379e0-149">Comment</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p></p></td>
<td><p><span data-ttu-id="379e0-150"><strong>Echo</strong></span><span class="sxs-lookup"><span data-stu-id="379e0-150"><strong>Echo</strong></span></span></p></td>
<td><p><span data-ttu-id="379e0-151"><strong>打开回响</strong>:<strong>否</strong></span><span class="sxs-lookup"><span data-stu-id="379e0-151"><strong>Echo On</strong>: <strong>No</strong></span></span></p></td>
<td><p><span data-ttu-id="379e0-152">在宏运行时停止屏幕更新。</span><span class="sxs-lookup"><span data-stu-id="379e0-152">Stop screen updating while the macro is running.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="379e0-153">IsNull ([供应商 id])</span><span class="sxs-lookup"><span data-stu-id="379e0-153">IsNull([SupplierID])</span></span></p></td>
<td><p><span data-ttu-id="379e0-154"><strong>MessageBox</strong></span><span class="sxs-lookup"><span data-stu-id="379e0-154"><strong>MessageBox</strong></span></span></p></td>
<td><p><span data-ttu-id="379e0-155"><strong>消息</strong>: 移动到要查看其产品的供应商记录, 然后再次单击 "查看产品" 按钮。</span><span class="sxs-lookup"><span data-stu-id="379e0-155"><strong>Message</strong>: Move to the supplier record whose products you want to see, then click the Review Products button again.</span></span> <span data-ttu-id="379e0-156"><strong>嘟嘟声</strong>: <strong>YesType</strong>: <strong>NoneTitle</strong>: 选择供应商</span><span class="sxs-lookup"><span data-stu-id="379e0-156"><strong>Beep</strong>: <strong>YesType</strong>: <strong>NoneTitle</strong>: Select a Supplier</span></span></p></td>
<td><p><span data-ttu-id="379e0-157">如果 "供应商" 窗体上没有当前供应商, 则显示一条消息。</span><span class="sxs-lookup"><span data-stu-id="379e0-157">If there is no current supplier on the Suppliers form, display a message.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="379e0-158">...</span><span class="sxs-lookup"><span data-stu-id="379e0-158"></span></span></p></td>
<td><p><span data-ttu-id="379e0-159"><strong>GoToControl</strong></span><span class="sxs-lookup"><span data-stu-id="379e0-159"><strong>GoToControl</strong></span></span></p></td>
<td><p><span data-ttu-id="379e0-160"><strong>控件名称</strong>: 公司名称</span><span class="sxs-lookup"><span data-stu-id="379e0-160"><strong>Control Name</strong>: CompanyName</span></span></p></td>
<td><p><span data-ttu-id="379e0-161">将焦点移到 "公司名称" 控件。</span><span class="sxs-lookup"><span data-stu-id="379e0-161">Move focus to the CompanyName control.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="379e0-162">...</span><span class="sxs-lookup"><span data-stu-id="379e0-162"></span></span></p></td>
<td><p><span data-ttu-id="379e0-163"><strong>StopMacro</strong></span><span class="sxs-lookup"><span data-stu-id="379e0-163"><strong>StopMacro</strong></span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="379e0-164">停止宏。</span><span class="sxs-lookup"><span data-stu-id="379e0-164">Stop the macro.</span></span></p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p><span data-ttu-id="379e0-165"><strong>OpenForm</strong></span><span class="sxs-lookup"><span data-stu-id="379e0-165"><strong>OpenForm</strong></span></span></p></td>
<td><p><span data-ttu-id="379e0-166"><strong>表单名称</strong>: 产品列表<strong>视图</strong>: <strong>DatasheetFilter Name</strong>: <strong>Where 条件</strong>: [供应商 id] = [Forms]![供应商]!id<strong>数据模式</strong>:<strong>读取 OnlyWindow 模式</strong>:<strong>普通</strong></span><span class="sxs-lookup"><span data-stu-id="379e0-166"><strong>Form Name</strong>: Product List <strong>View</strong>: <strong>DatasheetFilter Name</strong>: <strong>Where Condition</strong>: [SupplierID] = [Forms]![Suppliers]![SupplierID] <strong>Data Mode</strong>: <strong>Read OnlyWindow Mode</strong>: <strong>Normal</strong></span></span></p></td>
<td><p><span data-ttu-id="379e0-167">打开 "产品列表" 表单并显示当前供应商的产品。</span><span class="sxs-lookup"><span data-stu-id="379e0-167">Open the Product List form and show the current supplier's products.</span></span></p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p><span data-ttu-id="379e0-168"><strong>MoveAndSizeWindow</strong></span><span class="sxs-lookup"><span data-stu-id="379e0-168"><strong>MoveAndSizeWindow</strong></span></span></p></td>
<td><p><span data-ttu-id="379e0-169"><strong>右侧</strong>: 0.7799&quot; <strong></strong>: 1。8&quot;</span><span class="sxs-lookup"><span data-stu-id="379e0-169"><strong>Right</strong>: 0.7799&quot; <strong>Down</strong>: 1.8&quot;</span></span></p></td>
<td><p><span data-ttu-id="379e0-170">将 "产品列表" 窗体放置在 "供应商" 窗体的右下角。</span><span class="sxs-lookup"><span data-stu-id="379e0-170">Position the Product List form in the lower right of the Suppliers form.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="379e0-171">**使用宏验证数据**</span><span class="sxs-lookup"><span data-stu-id="379e0-171">**Validate data by using a macro**</span></span>

<span data-ttu-id="379e0-172">下面的验证宏会检查在"供应商"窗体中输入的邮政编码。</span><span class="sxs-lookup"><span data-stu-id="379e0-172">The following validation macro checks the postal codes entered in a Suppliers form.</span></span> <span data-ttu-id="379e0-173">它演示如何使用 **StopMacro** 、 **MessageBox** 、 **CancelEvent** 和 **GoToControl** 操作。</span><span class="sxs-lookup"><span data-stu-id="379e0-173">It shows the use of the **StopMacro**, **MessageBox**, **CancelEvent**, and **GoToControl** actions.</span></span> <span data-ttu-id="379e0-174">其条件表达式检查在窗体的记录中输入的国家/地区和邮政编码。</span><span class="sxs-lookup"><span data-stu-id="379e0-174">A conditional expression checks the country/region and postal code entered in a record on the form.</span></span> <span data-ttu-id="379e0-175">如果邮政编码的格式不是正确的国家/地区, 宏将显示一个消息框, 并取消保存该记录。</span><span class="sxs-lookup"><span data-stu-id="379e0-175">If the postal code isn't in the right format for the country/region, the macro displays a message box and cancels saving the record.</span></span> <span data-ttu-id="379e0-176">然后, 它将返回到 "邮政编码" 控件, 您可以在其中更正错误。</span><span class="sxs-lookup"><span data-stu-id="379e0-176">It then returns you to the PostalCode control, where you can correct the error.</span></span> <span data-ttu-id="379e0-177">此宏应附加到“供应商”窗体的 **BeforeUpdate** 属性。</span><span class="sxs-lookup"><span data-stu-id="379e0-177">This macro should be attached to the **BeforeUpdate** property of the Suppliers form.</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="379e0-178">条件</span><span class="sxs-lookup"><span data-stu-id="379e0-178">Condition</span></span></p></th>
<th><p><span data-ttu-id="379e0-179">操作</span><span class="sxs-lookup"><span data-stu-id="379e0-179">Action</span></span></p></th>
<th><p><span data-ttu-id="379e0-180">参数：设置</span><span class="sxs-lookup"><span data-stu-id="379e0-180">Arguments: Setting</span></span></p></th>
<th><p><span data-ttu-id="379e0-181">Comment</span><span class="sxs-lookup"><span data-stu-id="379e0-181">Comment</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="379e0-182">IsNull ([国家/地区])</span><span class="sxs-lookup"><span data-stu-id="379e0-182">IsNull([CountryRegion])</span></span></p></td>
<td><p><span data-ttu-id="379e0-183"><strong>StopMacro</strong></span><span class="sxs-lookup"><span data-stu-id="379e0-183"><strong>StopMacro</strong></span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="379e0-184">如果 "国家/地区" 为<strong>Null</strong>, 则无法验证邮政编码。</span><span class="sxs-lookup"><span data-stu-id="379e0-184">If CountryRegion is <strong>Null</strong>, the postal code can't be validated.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="379e0-185">国家/地区In (&quot;法国&quot;,&quot;意大利&quot;,&quot;西班牙&quot;) 和 Len ([邮政编码]) &lt; &gt; 5</span><span class="sxs-lookup"><span data-stu-id="379e0-185">[CountryRegion] In (&quot;France&quot;,&quot;Italy&quot;,&quot;Spain&quot;) And Len([PostalCode]) &lt;&gt; 5</span></span></p></td>
<td><p><span data-ttu-id="379e0-186"><strong>MessageBox</strong></span><span class="sxs-lookup"><span data-stu-id="379e0-186"><strong>MessageBox</strong></span></span></p></td>
<td><p><span data-ttu-id="379e0-187"><strong>消息</strong>: 邮政编码必须为5个字符。</span><span class="sxs-lookup"><span data-stu-id="379e0-187"><strong>Message</strong>: The postal code must be 5 characters.</span></span> <span data-ttu-id="379e0-188"><strong>嘟嘟声</strong>: <strong>YesType</strong>: <strong>InformationTitle</strong>: 邮政编码错误</span><span class="sxs-lookup"><span data-stu-id="379e0-188"><strong>Beep</strong>: <strong>YesType</strong>: <strong>InformationTitle</strong>: Postal Code Error</span></span></p></td>
<td><p><span data-ttu-id="379e0-189">如果邮政编码不是 5 个字符，则显示一条消息。</span><span class="sxs-lookup"><span data-stu-id="379e0-189">If the postal code isn't 5 characters, display a message.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="379e0-190">...</span><span class="sxs-lookup"><span data-stu-id="379e0-190"></span></span></p></td>
<td><p><span data-ttu-id="379e0-191"><strong>CancelEvent</strong></span><span class="sxs-lookup"><span data-stu-id="379e0-191"><strong>CancelEvent</strong></span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="379e0-192">取消事件。</span><span class="sxs-lookup"><span data-stu-id="379e0-192">Cancel the event.</span></span></p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p><span data-ttu-id="379e0-193"><strong>GoToControl</strong></span><span class="sxs-lookup"><span data-stu-id="379e0-193"><strong>GoToControl</strong></span></span></p></td>
<td><p><span data-ttu-id="379e0-194"><strong>控件名称</strong>: 邮政编码</span><span class="sxs-lookup"><span data-stu-id="379e0-194"><strong>Control Name</strong>: PostalCode</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="379e0-195">国家/地区In (&quot;澳大利亚&quot;,&quot;新加坡&quot;) 和 Len ([邮政编码]) &lt; &gt; 4</span><span class="sxs-lookup"><span data-stu-id="379e0-195">[CountryRegion] In (&quot;Australia&quot;,&quot;Singapore&quot;) And Len([PostalCode]) &lt;&gt; 4</span></span></p></td>
<td><p><span data-ttu-id="379e0-196"><strong>MessageBox</strong></span><span class="sxs-lookup"><span data-stu-id="379e0-196"><strong>MessageBox</strong></span></span></p></td>
<td><p><span data-ttu-id="379e0-197"><strong>消息</strong>: 邮政编码必须为4个字符。</span><span class="sxs-lookup"><span data-stu-id="379e0-197"><strong>Message</strong>: The postal code must be 4 characters.</span></span> <span data-ttu-id="379e0-198"><strong>嘟嘟声</strong>: <strong>YesType</strong>: <strong>InformationTitle</strong>: 邮政编码错误</span><span class="sxs-lookup"><span data-stu-id="379e0-198"><strong>Beep</strong>: <strong>YesType</strong>: <strong>InformationTitle</strong>: Postal Code Error</span></span></p></td>
<td><p><span data-ttu-id="379e0-199">如果邮政编码不是 4 个字符，则显示一条消息。</span><span class="sxs-lookup"><span data-stu-id="379e0-199">If the postal code isn't 4 characters, display a message.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="379e0-200">...</span><span class="sxs-lookup"><span data-stu-id="379e0-200"></span></span></p></td>
<td><p><span data-ttu-id="379e0-201"><strong>CancelEvent</strong></span><span class="sxs-lookup"><span data-stu-id="379e0-201"><strong>CancelEvent</strong></span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="379e0-202">取消事件。</span><span class="sxs-lookup"><span data-stu-id="379e0-202">Cancel the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p><span data-ttu-id="379e0-203"><strong>GoToControl</strong></span><span class="sxs-lookup"><span data-stu-id="379e0-203"><strong>GoToControl</strong></span></span></p></td>
<td><p><span data-ttu-id="379e0-204"><strong>控件名称</strong>: 邮政编码</span><span class="sxs-lookup"><span data-stu-id="379e0-204"><strong>Control Name</strong>: PostalCode</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="379e0-205">([国家/地区&quot;]&quot;= 加拿大)和 ([邮政编码] 不喜欢&quot;[a-z] [0-9] [a-z] [0-9] [a-z] [0-9]&quot;)</span><span class="sxs-lookup"><span data-stu-id="379e0-205">([CountryRegion] = &quot;Canada&quot;) And ([PostalCode] Not Like&quot;[A-Z][0-9][A-Z] [0-9][A-Z][0-9]&quot;)</span></span></p></td>
<td><p><span data-ttu-id="379e0-206"><strong>MessageBox</strong></span><span class="sxs-lookup"><span data-stu-id="379e0-206"><strong>MessageBox</strong></span></span></p></td>
<td><p><span data-ttu-id="379e0-207"><strong>消息</strong>: 邮政编码无效。</span><span class="sxs-lookup"><span data-stu-id="379e0-207"><strong>Message</strong>: The postal code is not valid.</span></span> <span data-ttu-id="379e0-208">加拿大代码示例: H1J 1C3<strong>嘟嘟声</strong>: <strong>YesType</strong>: <strong>InformationTitle</strong>: 邮政编码错误</span><span class="sxs-lookup"><span data-stu-id="379e0-208">Example of Canadian code: H1J 1C3 <strong>Beep</strong>: <strong>YesType</strong>: <strong>InformationTitle</strong>: Postal Code Error</span></span></p></td>
<td><p><span data-ttu-id="379e0-209">如果邮政编码不符合加拿大格式，则显示一条消息。</span><span class="sxs-lookup"><span data-stu-id="379e0-209">If the postal code isn't correct for Canada, display a message.</span></span> <span data-ttu-id="379e0-210">（加拿大邮政编码示例：H1J 1C3）</span><span class="sxs-lookup"><span data-stu-id="379e0-210">(Example of Canadian code: H1J 1C3)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="379e0-211">...</span><span class="sxs-lookup"><span data-stu-id="379e0-211"></span></span></p></td>
<td><p><span data-ttu-id="379e0-212"><strong>CancelEvent</strong></span><span class="sxs-lookup"><span data-stu-id="379e0-212"><strong>CancelEvent</strong></span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="379e0-213">取消事件。</span><span class="sxs-lookup"><span data-stu-id="379e0-213">Cancel the event.</span></span></p></td>
</tr>
</tbody>
</table>

