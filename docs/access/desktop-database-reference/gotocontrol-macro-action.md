---
title: GoToControl Macro Action
TOCTitle: GoToControl Macro Action
ms:assetid: caff76dc-7ca8-4f87-8144-89445ed4600d
ms:mtpsurl: https://msdn.microsoft.com/library/Ff834370(v=office.15)
ms:contentKeyID: 48547705
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 2617544bf04aa0b26ccbb9d7ce8d7329d42ed1e9
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467042"
---
# <a name="gotocontrol-macro-action"></a><span data-ttu-id="4494a-102">GoToControl Macro Action</span><span class="sxs-lookup"><span data-stu-id="4494a-102">GoToControl Macro Action</span></span>


<span data-ttu-id="4494a-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="4494a-103">**Applies to**: Access 2013 | Office 2013</span></span>



<span data-ttu-id="4494a-104">您可以使用**GoToControl**操作将焦点移到指定的域或打开的窗体、 窗体数据表、 表数据表的当前记录中的控件或查询数据表。</span><span class="sxs-lookup"><span data-stu-id="4494a-104">You can use the **GoToControl** action to move the focus to the specified field or control in the current record of the open form, form datasheet, table datasheet, or query datasheet.</span></span> <span data-ttu-id="4494a-105">当你希望特定字段或控件获得焦点时，可以使用此操作。</span><span class="sxs-lookup"><span data-stu-id="4494a-105">You can use this action when you want a particular field or control to have the focus.</span></span> <span data-ttu-id="4494a-106">然后比较或 **FindRecord** 操作可以使用该字段或控件。</span><span class="sxs-lookup"><span data-stu-id="4494a-106">This field or control can then be used for comparisons or **FindRecord** actions.</span></span> <span data-ttu-id="4494a-107">你可以使用此操作以根据特定的条件在表单中导航。</span><span class="sxs-lookup"><span data-stu-id="4494a-107">You can also use this action to navigate in a form according to certain conditions.</span></span> <span data-ttu-id="4494a-108">例如，如果用户输入婚姻控件不能在健康保险窗体，焦点可以自动跳过配偶姓名控件并移动到下一个控件。</span><span class="sxs-lookup"><span data-stu-id="4494a-108">For example, if the user enters No in a Married control on a health insurance form, the focus can automatically skip the Spouse/partner Name control and move to the next control.</span></span>

## <a name="setting"></a><span data-ttu-id="4494a-109">设置</span><span class="sxs-lookup"><span data-stu-id="4494a-109">Setting</span></span>


> [!NOTE]
> <P><span data-ttu-id="4494a-110">此操作不适用于数据访问页。</span><span class="sxs-lookup"><span data-stu-id="4494a-110">This action is not available for use with data access pages.</span></span></P>



<span data-ttu-id="4494a-111">**GoToControl** 操作具有以下参数。</span><span class="sxs-lookup"><span data-stu-id="4494a-111">The **GoToControl** action has the following argument.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="4494a-112">操作参数</span><span class="sxs-lookup"><span data-stu-id="4494a-112">Action argument</span></span></p></th>
<th><p><span data-ttu-id="4494a-113">说明</span><span class="sxs-lookup"><span data-stu-id="4494a-113">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4494a-114"><strong>控件名称</strong></span><span class="sxs-lookup"><span data-stu-id="4494a-114"><strong>Control Name</strong></span></span></p></td>
<td><p><span data-ttu-id="4494a-115">希望获得焦点的字段或控件的名称。</span><span class="sxs-lookup"><span data-stu-id="4494a-115">The name of the field or control where you want the focus.</span></span> <span data-ttu-id="4494a-116">在<strong>操作参数</strong>部分的宏生成器窗格中的<strong>控件名称</strong>框中输入字段或控件的名称。</span><span class="sxs-lookup"><span data-stu-id="4494a-116">Enter the field or control name in the <strong>Control Name</strong> box in the <strong>Action Arguments</strong> section of the Macro Builder pane.</span></span> <span data-ttu-id="4494a-117">这是必需参数。</span><span class="sxs-lookup"><span data-stu-id="4494a-117">This is a required argument.</span></span></p>

> [!NOTE]
> <P><span data-ttu-id="4494a-118"><STRONG>控件名称</STRONG>参数，而不是完全限定标识符，如表单中输入仅字段或控件的名称 ！产品 ！[Product ID]。</span><span class="sxs-lookup"><span data-stu-id="4494a-118">Enter only the name of the field or control in the <STRONG>Control Name</STRONG> argument, not the fully qualified identifier, such as Forms!Products![Product ID].</span></span></P>


<p></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="4494a-119">说明</span><span class="sxs-lookup"><span data-stu-id="4494a-119">Remarks</span></span>

<span data-ttu-id="4494a-120">不能使用**GoToControl**操作将焦点移到隐藏窗体上的控件。</span><span class="sxs-lookup"><span data-stu-id="4494a-120">You cannot use the **GoToControl** action to move the focus to a control on a hidden form.</span></span>


> [!TIP]
> <P><span data-ttu-id="4494a-121"><STRONG>GoToControl</STRONG>操作可用于将移动到子窗体，这是一类控件。</span><span class="sxs-lookup"><span data-stu-id="4494a-121">You can use the <STRONG>GoToControl</STRONG> action to move to a subform, which is a type of control.</span></span> <span data-ttu-id="4494a-122">然后，您可以使用<STRONG>GoToRecord</STRONG>操作将移到子窗体中的特定记录。</span><span class="sxs-lookup"><span data-stu-id="4494a-122">You can then use the <STRONG>GoToRecord</STRONG> action to move to a particular record in the subform.</span></span> <span data-ttu-id="4494a-123">您也可以通过使用<STRONG>GoToControl</STRONG>操作移到子窗体和子窗体上的控件移到子窗体上的控件。</span><span class="sxs-lookup"><span data-stu-id="4494a-123">You can also move to a control on a subform by using the <STRONG>GoToControl</STRONG> action to move first to the subform and then to the control on the subform.</span></span></P>



<span data-ttu-id="4494a-124">若要在 Visual Basic for Applications (VBA) 模块中运行**GoToControl**操作，请使用**DoCmd**对象的**GoToControl**方法。</span><span class="sxs-lookup"><span data-stu-id="4494a-124">To run the **GoToControl** action in a Visual Basic for Applications (VBA) module, use the **GoToControl** method of the **DoCmd** object.</span></span> <span data-ttu-id="4494a-125">您还可以使用 **SetFocus** 方法将焦点移到窗体或其任何子窗体上的控件或打开的表、 查询或窗体数据表中的字段。</span><span class="sxs-lookup"><span data-stu-id="4494a-125">You can also use the **SetFocus** method to move the focus to a control on a form or any of its subforms, or to a field in an open table, query, or form datasheet.</span></span>

## <a name="examples"></a><span data-ttu-id="4494a-126">示例</span><span class="sxs-lookup"><span data-stu-id="4494a-126">Examples</span></span>

<span data-ttu-id="4494a-127">**通过使用宏设置控件的值**</span><span class="sxs-lookup"><span data-stu-id="4494a-127">**Set the value of a control by using a macro**</span></span>

<span data-ttu-id="4494a-128">下面的宏 Suppliers 窗体上的按钮打开添加产品窗体。</span><span class="sxs-lookup"><span data-stu-id="4494a-128">The following macro opens the Add Products form from a button on the Suppliers form.</span></span> <span data-ttu-id="4494a-129">它演示如何使用**回声**、 **CloseWindow**、 **OpenForm**、 **SetValue**和**GoToControl**操作。</span><span class="sxs-lookup"><span data-stu-id="4494a-129">It shows the use of the **Echo**, **CloseWindow**, **OpenForm**, **SetValue**, and **GoToControl** actions.</span></span> <span data-ttu-id="4494a-130">**SetValue**操作供应商窗体上将产品窗体上的供应商 ID 控件设置为当前供应商。</span><span class="sxs-lookup"><span data-stu-id="4494a-130">The **SetValue** action sets the Supplier ID control on the Products form to the current supplier on the Suppliers form.</span></span> <span data-ttu-id="4494a-131">然后， **GoToControl**操作将焦点移到类别 ID 字段中，您可以开始新产品的输入数据。</span><span class="sxs-lookup"><span data-stu-id="4494a-131">The **GoToControl** action then moves the focus to the Category ID field, where you can begin to enter data for the new product.</span></span> <span data-ttu-id="4494a-132">这个宏应附加到 Suppliers 窗体上的添加产品按钮。</span><span class="sxs-lookup"><span data-stu-id="4494a-132">This macro should be attached to the Add Products button on the Suppliers form.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="4494a-133">操作</span><span class="sxs-lookup"><span data-stu-id="4494a-133">Action</span></span></p></th>
<th><p><span data-ttu-id="4494a-134">参数：设置</span><span class="sxs-lookup"><span data-stu-id="4494a-134">Arguments: Setting</span></span></p></th>
<th><p><span data-ttu-id="4494a-135">注释</span><span class="sxs-lookup"><span data-stu-id="4494a-135">Comment</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4494a-136"><strong>Echo</strong></span><span class="sxs-lookup"><span data-stu-id="4494a-136"><strong>Echo</strong></span></span></p></td>
<td><p><span data-ttu-id="4494a-137"><strong>打开回响</strong>：<strong>否</strong></span><span class="sxs-lookup"><span data-stu-id="4494a-137"><strong>Echo On</strong>: <strong>No</strong></span></span></p></td>
<td><p><span data-ttu-id="4494a-138">停止屏幕更新时运行宏。</span><span class="sxs-lookup"><span data-stu-id="4494a-138">Stop screen updating while the macro is running.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4494a-139"><strong>CloseWindow</strong></span><span class="sxs-lookup"><span data-stu-id="4494a-139"><strong>CloseWindow</strong></span></span></p></td>
<td><p><span data-ttu-id="4494a-140"><strong>对象类型</strong>： <strong>FormObject 名称</strong>： 产品列表<strong>保存</strong>：<strong>否</strong></span><span class="sxs-lookup"><span data-stu-id="4494a-140"><strong>Object Type</strong>: <strong>FormObject Name</strong>: Product List <strong>Save</strong>: <strong>No</strong></span></span></p></td>
<td><p><span data-ttu-id="4494a-141">关闭产品列表窗体。</span><span class="sxs-lookup"><span data-stu-id="4494a-141">Close Product List form.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4494a-142"><strong>OpenForm</strong></span><span class="sxs-lookup"><span data-stu-id="4494a-142"><strong>OpenForm</strong></span></span></p></td>
<td><p><span data-ttu-id="4494a-143"><strong>窗体名称</strong>： 产品<strong>视图</strong>： <strong>FormData 模式</strong>： <strong>AddWindow 模式</strong>：<strong>普通</strong></span><span class="sxs-lookup"><span data-stu-id="4494a-143"><strong>Form Name</strong>: Products <strong>View</strong>: <strong>FormData Mode</strong>: <strong>AddWindow Mode</strong>: <strong>Normal</strong></span></span></p></td>
<td><p><span data-ttu-id="4494a-144">打开产品窗体。</span><span class="sxs-lookup"><span data-stu-id="4494a-144">Open the Products form.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4494a-145"><strong>SetValue</strong></span><span class="sxs-lookup"><span data-stu-id="4494a-145"><strong>SetValue</strong></span></span></p></td>
<td><p><span data-ttu-id="4494a-146"><strong>项目</strong>: [窗体] ！[产品] ！[SupplierID]<strong>表达式</strong>： 供应商 Id</span><span class="sxs-lookup"><span data-stu-id="4494a-146"><strong>Item</strong>: [Forms]![Products]![SupplierID] <strong>Expression</strong>: SupplierID</span></span></p></td>
<td><p><span data-ttu-id="4494a-147">在 Suppliers 窗体上将供应商 ID 控件设置为当前供应商。</span><span class="sxs-lookup"><span data-stu-id="4494a-147">Set the Supplier ID control to the current supplier on the Suppliers form.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4494a-148"><strong>GoToControl</strong></span><span class="sxs-lookup"><span data-stu-id="4494a-148"><strong>GoToControl</strong></span></span></p></td>
<td><p><span data-ttu-id="4494a-149"><strong>控件名称</strong>： CategoryID</span><span class="sxs-lookup"><span data-stu-id="4494a-149"><strong>Control Name</strong>: CategoryID</span></span></p></td>
<td><p><span data-ttu-id="4494a-150">转到类别 ID 控件。</span><span class="sxs-lookup"><span data-stu-id="4494a-150">Go to the Category ID control.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4494a-151">**通过使用宏验证数据**</span><span class="sxs-lookup"><span data-stu-id="4494a-151">**Validate data by using a macro**</span></span>

<span data-ttu-id="4494a-152">下面的验证宏会检查在"供应商"窗体中输入的邮政编码。</span><span class="sxs-lookup"><span data-stu-id="4494a-152">The following validation macro checks the postal codes entered in a Suppliers form.</span></span> <span data-ttu-id="4494a-153">它演示如何使用 **StopMacro** 、 **MessageBox** 、 **CancelEvent** 和 **GoToControl** 操作。</span><span class="sxs-lookup"><span data-stu-id="4494a-153">It shows the use of the **StopMacro**, **MessageBox**, **CancelEvent**, and **GoToControl** actions.</span></span> <span data-ttu-id="4494a-154">其条件表达式检查在窗体的记录中输入的国家/地区和邮政编码。</span><span class="sxs-lookup"><span data-stu-id="4494a-154">A conditional expression checks the country/region and postal code entered in a record on the form.</span></span> <span data-ttu-id="4494a-155">如果邮政编码的格式与国家/地区不符，该宏将显示一个消息框并取消对该记录的保存操作。</span><span class="sxs-lookup"><span data-stu-id="4494a-155">If the postal code is not in the right format for the country/region, the macro displays a message box and cancels saving the record.</span></span> <span data-ttu-id="4494a-156">宏然后您返回到邮政编码控件，您可以在其中更正错误。</span><span class="sxs-lookup"><span data-stu-id="4494a-156">The macro then returns you to the Postal Code control, where you can correct the error.</span></span> <span data-ttu-id="4494a-157">此宏应附加到"供应商"窗体的 **BeforeUpdate** 属性。</span><span class="sxs-lookup"><span data-stu-id="4494a-157">This macro should be attached to the **BeforeUpdate** property of the Suppliers form.</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="4494a-158">条件</span><span class="sxs-lookup"><span data-stu-id="4494a-158">Condition</span></span></p></th>
<th><p><span data-ttu-id="4494a-159">操作</span><span class="sxs-lookup"><span data-stu-id="4494a-159">Action</span></span></p></th>
<th><p><span data-ttu-id="4494a-160">参数：设置</span><span class="sxs-lookup"><span data-stu-id="4494a-160">Arguments: Setting</span></span></p></th>
<th><p><span data-ttu-id="4494a-161">注释</span><span class="sxs-lookup"><span data-stu-id="4494a-161">Comment</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4494a-162">IsNull([CountryRegion])</span><span class="sxs-lookup"><span data-stu-id="4494a-162">IsNull([CountryRegion])</span></span></p></td>
<td><p><span data-ttu-id="4494a-163"><strong>StopMacro</strong></span><span class="sxs-lookup"><span data-stu-id="4494a-163"><strong>StopMacro</strong></span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="4494a-164">国家/地区为<strong>Null</strong>，如果无法验证邮政编码。</span><span class="sxs-lookup"><span data-stu-id="4494a-164">If CountryRegion is <strong>Null</strong>, postal code cannot be validated.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4494a-165">[国家/地区]中 (&quot;法国&quot;，&quot;意大利&quot;，&quot;西班牙&quot;) And Len （[邮政编码]） &lt; &gt; 5</span><span class="sxs-lookup"><span data-stu-id="4494a-165">[CountryRegion] In (&quot;France&quot;,&quot;Italy&quot;,&quot;Spain&quot;) And Len([Postal Code]) &lt;&gt; 5</span></span></p></td>
<td><p><span data-ttu-id="4494a-166"><strong>MessageBox</strong></span><span class="sxs-lookup"><span data-stu-id="4494a-166"><strong>MessageBox</strong></span></span></p></td>
<td><p><span data-ttu-id="4494a-167"><strong>消息</strong>： 邮政编码必须为 5 个字符。</span><span class="sxs-lookup"><span data-stu-id="4494a-167"><strong>Message</strong>: The postal code must be 5 characters.</span></span> <span data-ttu-id="4494a-168"><strong>发嘟嘟声</strong>： <strong>YesType</strong>: <strong>InformationTitle</strong>： 邮政编码错误</span><span class="sxs-lookup"><span data-stu-id="4494a-168"><strong>Beep</strong>: <strong>YesType</strong>: <strong>InformationTitle</strong>: Postal Code Error</span></span></p></td>
<td><p><span data-ttu-id="4494a-169">如果邮政编码不是 5 个字符，则显示一条消息。</span><span class="sxs-lookup"><span data-stu-id="4494a-169">If the postal code is not 5 characters, display a message.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4494a-170">...</span><span class="sxs-lookup"><span data-stu-id="4494a-170"></span></span></p></td>
<td><p><span data-ttu-id="4494a-171"><strong>CancelEvent</strong></span><span class="sxs-lookup"><span data-stu-id="4494a-171"><strong>CancelEvent</strong></span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="4494a-172">取消事件。</span><span class="sxs-lookup"><span data-stu-id="4494a-172">Cancel the event.</span></span></p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p><span data-ttu-id="4494a-173"><strong>GoToControl</strong></span><span class="sxs-lookup"><span data-stu-id="4494a-173"><strong>GoToControl</strong></span></span></p></td>
<td><p><span data-ttu-id="4494a-174"><strong>控件名称</strong>： 邮政编码</span><span class="sxs-lookup"><span data-stu-id="4494a-174"><strong>Control Name</strong>: PostalCode</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4494a-175">[国家/地区]中 (&quot;澳大利亚&quot;，&quot;新加坡&quot;) And Len （[邮政编码]） &lt; &gt; 4</span><span class="sxs-lookup"><span data-stu-id="4494a-175">[CountryRegion] In (&quot;Australia&quot;,&quot;Singapore&quot;) And Len([Postal Code]) &lt;&gt; 4</span></span></p></td>
<td><p><span data-ttu-id="4494a-176"><strong>MessageBox</strong></span><span class="sxs-lookup"><span data-stu-id="4494a-176"><strong>MessageBox</strong></span></span></p></td>
<td><p><span data-ttu-id="4494a-177">消息：邮政编码必须为 4 个字符。 

</span><span class="sxs-lookup"><span data-stu-id="4494a-177">Message: The postal code must be 4 characters.</span></span> <span data-ttu-id="4494a-178"><strong>发嘟嘟声</strong>： <strong>YesType</strong>: <strong>InformationTitle</strong>： 邮政编码错误</span><span class="sxs-lookup"><span data-stu-id="4494a-178"><strong>Beep</strong>: <strong>YesType</strong>: <strong>InformationTitle</strong>: Postal Code Error</span></span></p></td>
<td><p><span data-ttu-id="4494a-179">如果邮政编码不是 4 个字符，则显示一条消息。</span><span class="sxs-lookup"><span data-stu-id="4494a-179">If the postal code is not 4 characters, display a message.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4494a-180">...</span><span class="sxs-lookup"><span data-stu-id="4494a-180"></span></span></p></td>
<td><p><span data-ttu-id="4494a-181"><strong>CancelEvent</strong></span><span class="sxs-lookup"><span data-stu-id="4494a-181"><strong>CancelEvent</strong></span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="4494a-182">取消事件。</span><span class="sxs-lookup"><span data-stu-id="4494a-182">Cancel the event.</span></span></p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p><span data-ttu-id="4494a-183"><strong>GoToControl</strong></span><span class="sxs-lookup"><span data-stu-id="4494a-183"><strong>GoToControl</strong></span></span></p></td>
<td><p><span data-ttu-id="4494a-184"><strong>控件名称</strong>： 邮政编码</span><span class="sxs-lookup"><span data-stu-id="4494a-184"><strong>Control Name</strong>: PostalCode</span></span></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4494a-185">([国家/地区] =&quot;加拿大&quot;)和 ([邮政编码] Not Like&quot;[A-Z] [0-9] [A-Z] [0-9] [A-Z] [0-9]&quot;)</span><span class="sxs-lookup"><span data-stu-id="4494a-185">([CountryRegion] = &quot;Canada&quot;) And ([Postal Code] Not Like&quot;[A-Z][0-9][A-Z] [0-9][A-Z][0-9]&quot;)</span></span></p></td>
<td><p><span data-ttu-id="4494a-186"><strong>MessageBox</strong></span><span class="sxs-lookup"><span data-stu-id="4494a-186"><strong>MessageBox</strong></span></span></p></td>
<td><p><span data-ttu-id="4494a-187"><strong>消息</strong>： 邮政编码无效。</span><span class="sxs-lookup"><span data-stu-id="4494a-187"><strong>Message</strong>: The postal code is not valid.</span></span> <span data-ttu-id="4494a-188">加拿大代码示例： H1J 1c3<strong>发嘟嘟声</strong>： <strong>YesType</strong>: <strong>InformationTitle</strong>： 邮政代码错误</span><span class="sxs-lookup"><span data-stu-id="4494a-188">Example of Canadian code: H1J 1C3 <strong>Beep</strong>: <strong>YesType</strong>: <strong>InformationTitle</strong>: Postal Code Error</span></span></p></td>
<td><p><span data-ttu-id="4494a-189">如果邮政编码不正确的加拿大，显示一条消息。</span><span class="sxs-lookup"><span data-stu-id="4494a-189">If the postal code is not correct for Canada, display a message.</span></span> <span data-ttu-id="4494a-190">(加拿大代码示例： H1J 1c3)</span><span class="sxs-lookup"><span data-stu-id="4494a-190">(Example of Canadian code: H1J 1C3)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4494a-191">...</span><span class="sxs-lookup"><span data-stu-id="4494a-191"></span></span></p></td>
<td><p><span data-ttu-id="4494a-192"><strong>CancelEvent</strong></span><span class="sxs-lookup"><span data-stu-id="4494a-192"><strong>CancelEvent</strong></span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="4494a-193">取消事件。</span><span class="sxs-lookup"><span data-stu-id="4494a-193">Cancel the event.</span></span></p></td>
</tr>
</tbody>
</table>
