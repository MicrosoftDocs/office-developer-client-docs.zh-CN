---
title: MessageBox 宏操作
TOCTitle: MessageBox Macro Action
ms:assetid: 326a0e68-38fb-4f81-b319-5a70caa5aec4
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192304(v=office.15)
ms:contentKeyID: 48544077
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 6654d2994b472ff2d495b60fffd5fcdbd6e58089
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25885232"
---
# <a name="messagebox-macro-action"></a><span data-ttu-id="efe2a-102">MessageBox 宏操作</span><span class="sxs-lookup"><span data-stu-id="efe2a-102">MessageBox Macro Action</span></span>


<span data-ttu-id="efe2a-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="efe2a-103">**Applies to**: Access 2013, Office 2013</span></span>




<span data-ttu-id="efe2a-104">您可以使用**MessageBox**操作显示包含警告或信息性消息一个消息框。</span><span class="sxs-lookup"><span data-stu-id="efe2a-104">You can use the **MessageBox** action to display a message box containing a warning or an informational message.</span></span> <span data-ttu-id="efe2a-105">例如，您可以使用验证宏使用**MessageBox**操作。</span><span class="sxs-lookup"><span data-stu-id="efe2a-105">For example, you can use the **MessageBox** action with validation macros.</span></span> <span data-ttu-id="efe2a-106">当控件或记录失败时在宏中的有效性验证条件时，一个消息框可以显示一条错误消息，并提供有关应输入的数据类型的说明。</span><span class="sxs-lookup"><span data-stu-id="efe2a-106">When a control or record fails a validation condition in the macro, a message box can display an error message and provide instructions about the kind of data that should be entered.</span></span>

## <a name="setting"></a><span data-ttu-id="efe2a-107">设置</span><span class="sxs-lookup"><span data-stu-id="efe2a-107">Setting</span></span>

<span data-ttu-id="efe2a-108">**MessageBox**操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="efe2a-108">The **MessageBox** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="efe2a-109">操作参数</span><span class="sxs-lookup"><span data-stu-id="efe2a-109">Action argument</span></span></p></th>
<th><p><span data-ttu-id="efe2a-110">说明</span><span class="sxs-lookup"><span data-stu-id="efe2a-110">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="efe2a-111"><strong>Message</strong></span><span class="sxs-lookup"><span data-stu-id="efe2a-111"><strong>Message</strong></span></span></p></td>
<td><p><span data-ttu-id="efe2a-112">邮件框中的文本。</span><span class="sxs-lookup"><span data-stu-id="efe2a-112">The text in the message box.</span></span> <span data-ttu-id="efe2a-113">在宏生成器窗格的<strong>操作参数</strong>部分的<strong>消息</strong>框中输入消息文本。</span><span class="sxs-lookup"><span data-stu-id="efe2a-113">Enter the message text in the <strong>Message</strong> box in the <strong>Action Arguments</strong> section of the Macro Builder pane.</span></span> <span data-ttu-id="efe2a-114">您可以键入最多 255 个字符，或输入一个表达式 （前面带有等号）。</span><span class="sxs-lookup"><span data-stu-id="efe2a-114">You can type up to 255 characters or enter an expression (preceded by an equal sign).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efe2a-115"><strong>Beep</strong></span><span class="sxs-lookup"><span data-stu-id="efe2a-115"><strong>Beep</strong></span></span></p></td>
<td><p><span data-ttu-id="efe2a-116">指定是否计算机的扬声器发出嘟嘟声显示消息时。</span><span class="sxs-lookup"><span data-stu-id="efe2a-116">Specifies whether your computer's speaker sounds a beep tone when the message displays.</span></span> <span data-ttu-id="efe2a-117">单击<strong>是</strong>（发出嘟嘟声） 或<strong>否</strong>（不发出嘟嘟声）。</span><span class="sxs-lookup"><span data-stu-id="efe2a-117">Click <strong>Yes</strong> (sound the beep tone) or <strong>No</strong> (don't sound the beep tone).</span></span> <span data-ttu-id="efe2a-118">默认值为 <strong>"是"</strong>。</span><span class="sxs-lookup"><span data-stu-id="efe2a-118">The default is <strong>Yes</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="efe2a-119"><strong>类型</strong></span><span class="sxs-lookup"><span data-stu-id="efe2a-119"><strong>Type</strong></span></span></p></td>
<td><p><span data-ttu-id="efe2a-120">消息框中的类型。</span><span class="sxs-lookup"><span data-stu-id="efe2a-120">The type of message box.</span></span> <span data-ttu-id="efe2a-121">每种类型有不同的图标。</span><span class="sxs-lookup"><span data-stu-id="efe2a-121">Each type has a different icon.</span></span> <span data-ttu-id="efe2a-122">单击<strong>无</strong><strong>关键</strong><strong>警告？</strong>，<strong>警告 ！</strong>，或<strong>信息</strong>。</span><span class="sxs-lookup"><span data-stu-id="efe2a-122">Click <strong>None</strong>, <strong>Critical</strong>, <strong>Warning?</strong>, <strong>Warning!</strong>, or <strong>Information</strong>.</span></span> <span data-ttu-id="efe2a-123">默认值为<strong>None</strong>。</span><span class="sxs-lookup"><span data-stu-id="efe2a-123">The default is <strong>None</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efe2a-124"><strong>标题</strong></span><span class="sxs-lookup"><span data-stu-id="efe2a-124"><strong>Title</strong></span></span></p></td>
<td><p><span data-ttu-id="efe2a-125">在消息框标题栏中显示的文本。</span><span class="sxs-lookup"><span data-stu-id="efe2a-125">The text displayed in the message box title bar.</span></span> <span data-ttu-id="efe2a-126">例如，您可以标题栏中显示&quot;客户 ID 验证&quot;。</span><span class="sxs-lookup"><span data-stu-id="efe2a-126">For example, you can have the title bar display &quot;Customer ID Validation&quot;.</span></span> <span data-ttu-id="efe2a-127">如果您将此参数留空， &quot;Microsoft Access&quot;显示。</span><span class="sxs-lookup"><span data-stu-id="efe2a-127">If you leave this argument blank, &quot;Microsoft Access&quot; is displayed.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="efe2a-128">说明</span><span class="sxs-lookup"><span data-stu-id="efe2a-128">Remarks</span></span>

<span data-ttu-id="efe2a-129">**MessageBox**操作可用于创建带格式的错误消息类似于由 Microsoft Access 显示内置的错误消息。</span><span class="sxs-lookup"><span data-stu-id="efe2a-129">You can use the **MessageBox** action to create a formatted error message similar to built-in error messages displayed by Microsoft Access.</span></span> <span data-ttu-id="efe2a-130">**MessageBox**操作允许您提供三个部分的消息参数中的邮件。</span><span class="sxs-lookup"><span data-stu-id="efe2a-130">The **MessageBox** action permits you to supply a message in three sections for the Message argument.</span></span> <span data-ttu-id="efe2a-131">分隔各节与"@"字符。</span><span class="sxs-lookup"><span data-stu-id="efe2a-131">You separate the sections with the "@" character.</span></span>

<span data-ttu-id="efe2a-132">下面的示例显示一个带有分段消息的格式化的消息框。</span><span class="sxs-lookup"><span data-stu-id="efe2a-132">The following example displays a formatted message box with a sectioned message.</span></span> <span data-ttu-id="efe2a-133">第一节的消息中的文本显示为加粗的标题。</span><span class="sxs-lookup"><span data-stu-id="efe2a-133">The first section of text in the message is displayed as a bold heading.</span></span> <span data-ttu-id="efe2a-134">第二部分显示为纯文本标题的下面。</span><span class="sxs-lookup"><span data-stu-id="efe2a-134">The second section is displayed as plain text beneath that heading.</span></span> <span data-ttu-id="efe2a-135">第三部分显示为纯文本下方第二部分，使用它们之间的一个空行。</span><span class="sxs-lookup"><span data-stu-id="efe2a-135">The third section is displayed as plain text beneath the second section, with a blank line between them.</span></span>

<span data-ttu-id="efe2a-136">在**消息**参数中键入以下字符串：</span><span class="sxs-lookup"><span data-stu-id="efe2a-136">Type the following string in the **Message** argument:</span></span>

<span data-ttu-id="efe2a-137">**错误按钮\!@This 按钮不 work.@Try 另一个。**</span><span class="sxs-lookup"><span data-stu-id="efe2a-137">**Wrong button\!@This button doesn't work.@Try another.**</span></span>

<span data-ttu-id="efe2a-138">不能在 Visual Basic for Applications (VBA) 模块中运行的**MessageBox**操作。</span><span class="sxs-lookup"><span data-stu-id="efe2a-138">You can't run the **MessageBox** action in a Visual Basic for Applications (VBA) module.</span></span> <span data-ttu-id="efe2a-139">请改用**MsgBox**函数。</span><span class="sxs-lookup"><span data-stu-id="efe2a-139">Use the **MsgBox** function instead.</span></span>

## <a name="examples"></a><span data-ttu-id="efe2a-140">示例</span><span class="sxs-lookup"><span data-stu-id="efe2a-140">Examples</span></span>

<span data-ttu-id="efe2a-141">**通过使用宏同步处理窗体**</span><span class="sxs-lookup"><span data-stu-id="efe2a-141">**Synchronize forms by using a macro**</span></span>

<span data-ttu-id="efe2a-142">下面的宏将在显示当前供应商的产品 Suppliers 窗体的右下角中打开产品列表窗体。</span><span class="sxs-lookup"><span data-stu-id="efe2a-142">The following macro opens a Product List form in the lower-right corner of the Suppliers form, displaying the current supplier's products.</span></span> <span data-ttu-id="efe2a-143">它演示如何使用**回声**、 **MessageBox**、 **GoToControl**、 **StopMacro**、 **OpenForm**，和**MoveAndSizeWindow**操作。</span><span class="sxs-lookup"><span data-stu-id="efe2a-143">It shows the use of the **Echo**, **MessageBox**, **GoToControl**, **StopMacro**, **OpenForm**, and **MoveAndSizeWindow** actions.</span></span> <span data-ttu-id="efe2a-144">它还会显示具有**MessageBox**、 **GoToControl**和**StopMacro**操作的条件表达式使用。</span><span class="sxs-lookup"><span data-stu-id="efe2a-144">It also shows the use of a conditional expression with the **MessageBox**, **GoToControl**, and **StopMacro** actions.</span></span> <span data-ttu-id="efe2a-145">这个宏应附加到 Suppliers 窗体上的查看产品按钮。</span><span class="sxs-lookup"><span data-stu-id="efe2a-145">This macro should be attached to the Review Products button on the Suppliers form.</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="efe2a-146">条件</span><span class="sxs-lookup"><span data-stu-id="efe2a-146">Condition</span></span></p></th>
<th><p><span data-ttu-id="efe2a-147">操作</span><span class="sxs-lookup"><span data-stu-id="efe2a-147">Action</span></span></p></th>
<th><p><span data-ttu-id="efe2a-148">参数：设置</span><span class="sxs-lookup"><span data-stu-id="efe2a-148">Arguments: Setting</span></span></p></th>
<th><p><span data-ttu-id="efe2a-149">注释</span><span class="sxs-lookup"><span data-stu-id="efe2a-149">Comment</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p></p></td>
<td><p><span data-ttu-id="efe2a-150"><strong>Echo</strong></span><span class="sxs-lookup"><span data-stu-id="efe2a-150"><strong>Echo</strong></span></span></p></td>
<td><p><span data-ttu-id="efe2a-151"><strong>打开回响</strong>：<strong>否</strong></span><span class="sxs-lookup"><span data-stu-id="efe2a-151"><strong>Echo On</strong>: <strong>No</strong></span></span></p></td>
<td><p><span data-ttu-id="efe2a-152">停止屏幕更新时运行宏。</span><span class="sxs-lookup"><span data-stu-id="efe2a-152">Stop screen updating while the macro is running.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efe2a-153">IsNull([SupplierID])</span><span class="sxs-lookup"><span data-stu-id="efe2a-153">IsNull([SupplierID])</span></span></p></td>
<td><p><span data-ttu-id="efe2a-154"><strong>MessageBox</strong></span><span class="sxs-lookup"><span data-stu-id="efe2a-154"><strong>MessageBox</strong></span></span></p></td>
<td><p><span data-ttu-id="efe2a-155"><strong>消息</strong>： 移动到您要查看其的产品然后再次单击查看产品按钮的供应商记录。</span><span class="sxs-lookup"><span data-stu-id="efe2a-155"><strong>Message</strong>: Move to the supplier record whose products you want to see, then click the Review Products button again.</span></span> <span data-ttu-id="efe2a-156"><strong>发嘟嘟声</strong>： <strong>YesType</strong>: <strong>NoneTitle</strong>： 选择一个供应商</span><span class="sxs-lookup"><span data-stu-id="efe2a-156"><strong>Beep</strong>: <strong>YesType</strong>: <strong>NoneTitle</strong>: Select a Supplier</span></span></p></td>
<td><p><span data-ttu-id="efe2a-157">如果 Suppliers 窗体上没有当前供应商，显示一条消息。</span><span class="sxs-lookup"><span data-stu-id="efe2a-157">If there is no current supplier on the Suppliers form, display a message.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="efe2a-158">...</span><span class="sxs-lookup"><span data-stu-id="efe2a-158"></span></span></p></td>
<td><p><span data-ttu-id="efe2a-159"><strong>GoToControl</strong></span><span class="sxs-lookup"><span data-stu-id="efe2a-159"><strong>GoToControl</strong></span></span></p></td>
<td><p><span data-ttu-id="efe2a-160"><strong>控件名称</strong>： 公司名称</span><span class="sxs-lookup"><span data-stu-id="efe2a-160"><strong>Control Name</strong>: CompanyName</span></span></p></td>
<td><p><span data-ttu-id="efe2a-161">将焦点移到公司名称控件。</span><span class="sxs-lookup"><span data-stu-id="efe2a-161">Move focus to the CompanyName control.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efe2a-162">...</span><span class="sxs-lookup"><span data-stu-id="efe2a-162"></span></span></p></td>
<td><p><span data-ttu-id="efe2a-163"><strong>StopMacro</strong></span><span class="sxs-lookup"><span data-stu-id="efe2a-163"><strong>StopMacro</strong></span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="efe2a-164">停止宏。</span><span class="sxs-lookup"><span data-stu-id="efe2a-164">Stop the macro.</span></span></p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p><span data-ttu-id="efe2a-165"><strong>OpenForm</strong></span><span class="sxs-lookup"><span data-stu-id="efe2a-165"><strong>OpenForm</strong></span></span></p></td>
<td><p><span data-ttu-id="efe2a-166"><strong>窗体名称</strong>： 产品列表<strong>视图</strong>： <strong>DatasheetFilter 名称</strong>： <strong>Where 条件</strong>: [SupplierID] = [窗体] ！[供应商] ！[SupplierID]<strong>数据模式</strong>：<strong>读取 OnlyWindow 模式</strong>：<strong>普通</strong></span><span class="sxs-lookup"><span data-stu-id="efe2a-166"><strong>Form Name</strong>: Product List <strong>View</strong>: <strong>DatasheetFilter Name</strong>: <strong>Where Condition</strong>: [SupplierID] = [Forms]![Suppliers]![SupplierID] <strong>Data Mode</strong>: <strong>Read OnlyWindow Mode</strong>: <strong>Normal</strong></span></span></p></td>
<td><p><span data-ttu-id="efe2a-167">打开产品列表窗体并显示当前供应商的产品。</span><span class="sxs-lookup"><span data-stu-id="efe2a-167">Open the Product List form and show the current supplier's products.</span></span></p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p><span data-ttu-id="efe2a-168"><strong>MoveAndSizeWindow</strong></span><span class="sxs-lookup"><span data-stu-id="efe2a-168"><strong>MoveAndSizeWindow</strong></span></span></p></td>
<td><p><span data-ttu-id="efe2a-169"><strong>右</strong>： 0.7799&quot; <strong>下</strong>： 1.8&quot;</span><span class="sxs-lookup"><span data-stu-id="efe2a-169"><strong>Right</strong>: 0.7799&quot; <strong>Down</strong>: 1.8&quot;</span></span></p></td>
<td><p><span data-ttu-id="efe2a-170">产品列表表单 Suppliers 窗体的右下角的位置。</span><span class="sxs-lookup"><span data-stu-id="efe2a-170">Position the Product List form in the lower right of the Suppliers form.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="efe2a-171">**通过使用宏验证数据**</span><span class="sxs-lookup"><span data-stu-id="efe2a-171">**Validate data by using a macro**</span></span>

<span data-ttu-id="efe2a-172">下面的验证宏会检查在"供应商"窗体中输入的邮政编码。</span><span class="sxs-lookup"><span data-stu-id="efe2a-172">The following validation macro checks the postal codes entered in a Suppliers form.</span></span> <span data-ttu-id="efe2a-173">它演示如何使用 **StopMacro** 、 **MessageBox** 、 **CancelEvent** 和 **GoToControl** 操作。</span><span class="sxs-lookup"><span data-stu-id="efe2a-173">It shows the use of the **StopMacro**, **MessageBox**, **CancelEvent**, and **GoToControl** actions.</span></span> <span data-ttu-id="efe2a-174">其条件表达式检查在窗体的记录中输入的国家/地区和邮政编码。</span><span class="sxs-lookup"><span data-stu-id="efe2a-174">A conditional expression checks the country/region and postal code entered in a record on the form.</span></span> <span data-ttu-id="efe2a-175">如果邮政编码不是以适当的国家/地区的格式，宏将显示一个消息框，并取消保存记录。</span><span class="sxs-lookup"><span data-stu-id="efe2a-175">If the postal code isn't in the right format for the country/region, the macro displays a message box and cancels saving the record.</span></span> <span data-ttu-id="efe2a-176">它然后返回到 PostalCode 控件中，您可以在其中更正错误。</span><span class="sxs-lookup"><span data-stu-id="efe2a-176">It then returns you to the PostalCode control, where you can correct the error.</span></span> <span data-ttu-id="efe2a-177">此宏应附加到"供应商"窗体的 **BeforeUpdate** 属性。</span><span class="sxs-lookup"><span data-stu-id="efe2a-177">This macro should be attached to the **BeforeUpdate** property of the Suppliers form.</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="efe2a-178">条件</span><span class="sxs-lookup"><span data-stu-id="efe2a-178">Condition</span></span></p></th>
<th><p><span data-ttu-id="efe2a-179">操作</span><span class="sxs-lookup"><span data-stu-id="efe2a-179">Action</span></span></p></th>
<th><p><span data-ttu-id="efe2a-180">参数：设置</span><span class="sxs-lookup"><span data-stu-id="efe2a-180">Arguments: Setting</span></span></p></th>
<th><p><span data-ttu-id="efe2a-181">注释</span><span class="sxs-lookup"><span data-stu-id="efe2a-181">Comment</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="efe2a-182">IsNull([CountryRegion])</span><span class="sxs-lookup"><span data-stu-id="efe2a-182">IsNull([CountryRegion])</span></span></p></td>
<td><p><span data-ttu-id="efe2a-183"><strong>StopMacro</strong></span><span class="sxs-lookup"><span data-stu-id="efe2a-183"><strong>StopMacro</strong></span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="efe2a-184">国家/地区为<strong>Null</strong>，如果无法验证邮政编码。</span><span class="sxs-lookup"><span data-stu-id="efe2a-184">If CountryRegion is <strong>Null</strong>, the postal code can't be validated.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efe2a-185">[国家/地区]中 (&quot;法国&quot;，&quot;意大利&quot;，&quot;西班牙&quot;) 和 Len([PostalCode]) &lt; &gt; 5</span><span class="sxs-lookup"><span data-stu-id="efe2a-185">[CountryRegion] In (&quot;France&quot;,&quot;Italy&quot;,&quot;Spain&quot;) And Len([PostalCode]) &lt;&gt; 5</span></span></p></td>
<td><p><span data-ttu-id="efe2a-186"><strong>MessageBox</strong></span><span class="sxs-lookup"><span data-stu-id="efe2a-186"><strong>MessageBox</strong></span></span></p></td>
<td><p><span data-ttu-id="efe2a-187"><strong>消息</strong>： 邮政编码必须为 5 个字符。</span><span class="sxs-lookup"><span data-stu-id="efe2a-187"><strong>Message</strong>: The postal code must be 5 characters.</span></span> <span data-ttu-id="efe2a-188"><strong>发嘟嘟声</strong>： <strong>YesType</strong>: <strong>InformationTitle</strong>： 邮政编码错误</span><span class="sxs-lookup"><span data-stu-id="efe2a-188"><strong>Beep</strong>: <strong>YesType</strong>: <strong>InformationTitle</strong>: Postal Code Error</span></span></p></td>
<td><p><span data-ttu-id="efe2a-189">如果邮政编码不是 5 个字符，则显示一条消息。</span><span class="sxs-lookup"><span data-stu-id="efe2a-189">If the postal code isn't 5 characters, display a message.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="efe2a-190">...</span><span class="sxs-lookup"><span data-stu-id="efe2a-190"></span></span></p></td>
<td><p><span data-ttu-id="efe2a-191"><strong>CancelEvent</strong></span><span class="sxs-lookup"><span data-stu-id="efe2a-191"><strong>CancelEvent</strong></span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="efe2a-192">取消事件。</span><span class="sxs-lookup"><span data-stu-id="efe2a-192">Cancel the event.</span></span></p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p><span data-ttu-id="efe2a-193"><strong>GoToControl</strong></span><span class="sxs-lookup"><span data-stu-id="efe2a-193"><strong>GoToControl</strong></span></span></p></td>
<td><p><span data-ttu-id="efe2a-194"><strong>控件名称</strong>： 邮政编码</span><span class="sxs-lookup"><span data-stu-id="efe2a-194"><strong>Control Name</strong>: PostalCode</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="efe2a-195">[国家/地区]中 (&quot;澳大利亚&quot;，&quot;新加坡&quot;) 和 Len([PostalCode]) &lt; &gt; 4</span><span class="sxs-lookup"><span data-stu-id="efe2a-195">[CountryRegion] In (&quot;Australia&quot;,&quot;Singapore&quot;) And Len([PostalCode]) &lt;&gt; 4</span></span></p></td>
<td><p><span data-ttu-id="efe2a-196"><strong>MessageBox</strong></span><span class="sxs-lookup"><span data-stu-id="efe2a-196"><strong>MessageBox</strong></span></span></p></td>
<td><p><span data-ttu-id="efe2a-197"><strong>消息</strong>： 邮政编码必须为 4 个字符。</span><span class="sxs-lookup"><span data-stu-id="efe2a-197"><strong>Message</strong>: The postal code must be 4 characters.</span></span> <span data-ttu-id="efe2a-198"><strong>发嘟嘟声</strong>： <strong>YesType</strong>: <strong>InformationTitle</strong>： 邮政编码错误</span><span class="sxs-lookup"><span data-stu-id="efe2a-198"><strong>Beep</strong>: <strong>YesType</strong>: <strong>InformationTitle</strong>: Postal Code Error</span></span></p></td>
<td><p><span data-ttu-id="efe2a-199">如果邮政编码不是 4 个字符，则显示一条消息。</span><span class="sxs-lookup"><span data-stu-id="efe2a-199">If the postal code isn't 4 characters, display a message.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efe2a-200">...</span><span class="sxs-lookup"><span data-stu-id="efe2a-200"></span></span></p></td>
<td><p><span data-ttu-id="efe2a-201"><strong>CancelEvent</strong></span><span class="sxs-lookup"><span data-stu-id="efe2a-201"><strong>CancelEvent</strong></span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="efe2a-202">取消事件。</span><span class="sxs-lookup"><span data-stu-id="efe2a-202">Cancel the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p><span data-ttu-id="efe2a-203"><strong>GoToControl</strong></span><span class="sxs-lookup"><span data-stu-id="efe2a-203"><strong>GoToControl</strong></span></span></p></td>
<td><p><span data-ttu-id="efe2a-204"><strong>控件名称</strong>： 邮政编码</span><span class="sxs-lookup"><span data-stu-id="efe2a-204"><strong>Control Name</strong>: PostalCode</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efe2a-205">([国家/地区] =&quot;加拿大&quot;)和 ([邮政编码] Not Like&quot;[A-Z] [0-9] [A-Z] [0-9] [A-Z] [0-9]&quot;)</span><span class="sxs-lookup"><span data-stu-id="efe2a-205">([CountryRegion] = &quot;Canada&quot;) And ([PostalCode] Not Like&quot;[A-Z][0-9][A-Z] [0-9][A-Z][0-9]&quot;)</span></span></p></td>
<td><p><span data-ttu-id="efe2a-206"><strong>MessageBox</strong></span><span class="sxs-lookup"><span data-stu-id="efe2a-206"><strong>MessageBox</strong></span></span></p></td>
<td><p><span data-ttu-id="efe2a-207"><strong>消息</strong>： 邮政编码无效。</span><span class="sxs-lookup"><span data-stu-id="efe2a-207"><strong>Message</strong>: The postal code is not valid.</span></span> <span data-ttu-id="efe2a-208">加拿大代码示例： H1J 1c3<strong>发嘟嘟声</strong>： <strong>YesType</strong>: <strong>InformationTitle</strong>： 邮政代码错误</span><span class="sxs-lookup"><span data-stu-id="efe2a-208">Example of Canadian code: H1J 1C3 <strong>Beep</strong>: <strong>YesType</strong>: <strong>InformationTitle</strong>: Postal Code Error</span></span></p></td>
<td><p><span data-ttu-id="efe2a-p115">如果邮政编码不符合加拿大格式，则显示一条消息。（加拿大邮政编码示例：H1J 1C3）</span><span class="sxs-lookup"><span data-stu-id="efe2a-p115">If the postal code isn't correct for Canada, display a message. (Example of Canadian code: H1J 1C3)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="efe2a-211">...</span><span class="sxs-lookup"><span data-stu-id="efe2a-211"></span></span></p></td>
<td><p><span data-ttu-id="efe2a-212"><strong>CancelEvent</strong></span><span class="sxs-lookup"><span data-stu-id="efe2a-212"><strong>CancelEvent</strong></span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="efe2a-213">取消事件。</span><span class="sxs-lookup"><span data-stu-id="efe2a-213">Cancel the event.</span></span></p></td>
</tr>
</tbody>
</table>

