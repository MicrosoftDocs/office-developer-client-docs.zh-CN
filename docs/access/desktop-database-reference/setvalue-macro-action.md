---
title: SetValue 宏操作
TOCTitle: SetValue macro action
ms:assetid: a08be0c1-a053-45f9-b4ae-709fedc58e8b
ms:mtpsurl: https://msdn.microsoft.com/library/Ff820771(v=office.15)
ms:contentKeyID: 48546712
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 6f407c5da2ca669025d5aec47685e6eb9732c72c
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25927100"
---
# <a name="setvalue-macro-action"></a><span data-ttu-id="02384-102">SetValue 宏操作</span><span class="sxs-lookup"><span data-stu-id="02384-102">SetValue macro action</span></span>


<span data-ttu-id="02384-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="02384-103">**Applies to**: Access 2013, Office 2013</span></span>


<span data-ttu-id="02384-104">您可以使用**SetValue**操作设置窗体、 窗体数据表或报表上的 Microsoft Access 字段、 控件或属性的值。</span><span class="sxs-lookup"><span data-stu-id="02384-104">You can use the **SetValue** action to set the value of a Microsoft Access field, control, or property on a form, a form datasheet, or a report.</span></span>


> [!NOTE]
> <P><span data-ttu-id="02384-105">您不能使用<STRONG>SetValue</STRONG>操作设置返回一个 object 访问属性的值。</span><span class="sxs-lookup"><span data-stu-id="02384-105">You cannot use the <STRONG>SetValue</STRONG> action to set the value of an Access property that returns an object.</span></span></P>




> [!NOTE]
> <P><span data-ttu-id="02384-p101">[!注释] 如果数据库不受信任，将不允许此操作。有关启用宏的详细信息，请参阅本文 See Also 一节中的链接。</span><span class="sxs-lookup"><span data-stu-id="02384-p101">This action will not be allowed if the database is not trusted. For more information about enabling macros, see the links in the See Also section of this article.</span></span></P>



## <a name="setting"></a><span data-ttu-id="02384-108">设置</span><span class="sxs-lookup"><span data-stu-id="02384-108">Setting</span></span>

<span data-ttu-id="02384-109">**SetValue**操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="02384-109">The **SetValue** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="02384-110">操作参数</span><span class="sxs-lookup"><span data-stu-id="02384-110">Action argument</span></span></p></th>
<th><p><span data-ttu-id="02384-111">说明</span><span class="sxs-lookup"><span data-stu-id="02384-111">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="02384-112"><strong>Item</strong></span><span class="sxs-lookup"><span data-stu-id="02384-112"><strong>Item</strong></span></span></p></td>
<td><p><span data-ttu-id="02384-113">字段、 控件或想要设置其值属性的名称。</span><span class="sxs-lookup"><span data-stu-id="02384-113">The name of the field, control, or property whose value you want to set.</span></span> <span data-ttu-id="02384-114">在宏生成器窗格的<strong>操作参数</strong>部分的<strong>项目</strong>框中输入字段、 控件或属性名称。</span><span class="sxs-lookup"><span data-stu-id="02384-114">Enter the field, control, or property name in the <strong>Item</strong> box in the <strong>Action Arguments</strong> section of the Macro Builder pane.</span></span> <span data-ttu-id="02384-115">您必须使用完整的语法引用此项目，如<em>controlname</em> （对于控件在窗体或报表从中调用宏） 或<strong>表单</strong>！<em>formname</em>！<em>控件名称</em>。</span><span class="sxs-lookup"><span data-stu-id="02384-115">You must use the full syntax to refer to this item, such as <em>controlname</em> (for a control on the form or report from which the macro was called) or <strong>Forms</strong>!<em>formname</em>!<em>controlname</em>.</span></span> <span data-ttu-id="02384-116">这是必需参数。</span><span class="sxs-lookup"><span data-stu-id="02384-116">This is a required argument.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02384-117"><strong>Expression</strong></span><span class="sxs-lookup"><span data-stu-id="02384-117"><strong>Expression</strong></span></span></p></td>
<td><p><span data-ttu-id="02384-118">Access 使用设置此项的值的表达式。</span><span class="sxs-lookup"><span data-stu-id="02384-118">The expression Access uses to set the value for this item.</span></span> <span data-ttu-id="02384-119">始终必须使用完整的语法来引用该表达式中的任何对象。</span><span class="sxs-lookup"><span data-stu-id="02384-119">You must always use the full syntax to refer to any objects in the expression.</span></span> <span data-ttu-id="02384-120">例如，若要增加 10 %employees 窗体上的薪金控件中的值，请使用表单 ！员工 ！Salary \* 1.1。</span><span class="sxs-lookup"><span data-stu-id="02384-120">For example, to increase the value in a Salary control on an Employees form by 10 percent, use Forms!Employees!Salary\*1.1.</span></span> <span data-ttu-id="02384-121">这是必需参数。</span><span class="sxs-lookup"><span data-stu-id="02384-121">This is a required argument.</span></span></p>

> [!NOTE]
> <P><span data-ttu-id="02384-122">不应使用等号 (<STRONG>=</STRONG>) 之前在该参数中的表达式。</span><span class="sxs-lookup"><span data-stu-id="02384-122">You shouldn't use an equal sign (<STRONG>=</STRONG>) before the expression in this argument.</span></span> <span data-ttu-id="02384-123">否则，Access 计算了表达式，然后使用此值作为此参数中的表达式。</span><span class="sxs-lookup"><span data-stu-id="02384-123">If you do, Access evaluates the expression and then uses this value as the expression in this argument.</span></span> <span data-ttu-id="02384-124">如果表达式是一个字符串，这可能会产生意外的结果。</span><span class="sxs-lookup"><span data-stu-id="02384-124">This can produce unexpected results if the expression is a string.</span></span></P>


<p><span data-ttu-id="02384-125">例如，如果您键入<strong>= &quot;String1&quot;</strong>用于此参数，Access 将首先计算表达式作为 String1。</span><span class="sxs-lookup"><span data-stu-id="02384-125">For example, if you type <strong>=&quot;String1&quot;</strong> for this argument, Access first evaluates the expression as String1.</span></span> <span data-ttu-id="02384-126">然后使用 String1 为此参数，应找到控件或窗体或报表调用宏上的名为 String1 属性中的表达式。</span><span class="sxs-lookup"><span data-stu-id="02384-126">Then it uses String1 as the expression in this argument, expecting to find a control or property named String1 on the form or report that called the macro.</span></span></p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> <P><span data-ttu-id="02384-127">在 Access 数据库 （.mdb 或.accdb），单击<STRONG>生成</STRONG>按钮以使用表达式生成器创建的上述参数的表达式。</span><span class="sxs-lookup"><span data-stu-id="02384-127">In an Access database (.mdb or .accdb), click the <STRONG>Build</STRONG> button to use the Expression Builder to create an expression for either of these arguments.</span></span></P>



## <a name="remarks"></a><span data-ttu-id="02384-128">说明</span><span class="sxs-lookup"><span data-stu-id="02384-128">Remarks</span></span>

<span data-ttu-id="02384-129">您可以使用此操作设置字段或窗体、 窗体数据表或报表上的控件的值。</span><span class="sxs-lookup"><span data-stu-id="02384-129">You can use this action to set a value for a field or control on a form, a form datasheet, or a report.</span></span> <span data-ttu-id="02384-130">您还可以在任何视图中设置几乎所有控件、 窗体和报表属性的值。</span><span class="sxs-lookup"><span data-stu-id="02384-130">You can also set the value for almost all control, form, and report properties in any view.</span></span> <span data-ttu-id="02384-131">了解特定属性是否可通过使用宏设置和哪些视图它可以是在设置，请参阅在 Visual Basic 编辑器中的属性的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="02384-131">To find out whether a particular property can be set by using a macro and which views it can be set in, see the Help topic for that property in the Visual Basic Editor.</span></span>

<span data-ttu-id="02384-132">即使窗体不包含控件绑定到的字段，还可以在窗体基础表中设置字段的值。</span><span class="sxs-lookup"><span data-stu-id="02384-132">You can also set the value for a field in a form's underlying table even if the form doesn't contain a control bound to the field.</span></span> <span data-ttu-id="02384-133">使用语法**Forms**\!*formname*\!*fieldname*在**项**中设置此类的字段的值。</span><span class="sxs-lookup"><span data-stu-id="02384-133">Use the syntax **Forms**\!*formname*\!*fieldname* in the **Item** box to set the value for such a field.</span></span> <span data-ttu-id="02384-134">您还可以参考到报表的基础表中的字段通过使用**报告**的语法\!*reportname*\!*fieldname*，但必须绑定到此字段中，在报表上的控件或字段必须引用到在报表上的计算的控件。</span><span class="sxs-lookup"><span data-stu-id="02384-134">You can also refer to a field in a report's underlying table by using the syntax **Reports**\!*reportname*\!*fieldname*, but there must be a control on the report bound to this field, or the field must be referred to in a calculated control on the report.</span></span>

<span data-ttu-id="02384-135">如果设置窗体上控件的值， **SetValue**操作不会触发该控件的窗体级有效性规则，但如果控件绑定的控件，它会触发基础字段的表级有效性规则。</span><span class="sxs-lookup"><span data-stu-id="02384-135">If you set the value of a control on a form, the **SetValue** action doesn't trigger the control's form-level validation rules, but it does trigger the underlying field's table-level validation rules if the control is a bound control.</span></span> <span data-ttu-id="02384-136">**SetValue**操作还将触发重新计算，但重新计算不会立即发生。</span><span class="sxs-lookup"><span data-stu-id="02384-136">The **SetValue** action also triggers recalculation, but the recalculation may not happen immediately.</span></span> <span data-ttu-id="02384-137">若要触发立即重画并强制结束重新计算，请使用**RepaintObject**操作。</span><span class="sxs-lookup"><span data-stu-id="02384-137">To trigger immediate repainting and force the recalculation to completion, use the **RepaintObject** action.</span></span> <span data-ttu-id="02384-138">可以使用**SetValue**操作设置控件中的值还不受输入掩码在控件的设置或基础字段的**InputMask**属性。</span><span class="sxs-lookup"><span data-stu-id="02384-138">The value you set in a control by using the **SetValue** action is also not affected by an input mask set in the control's or underlying field's **InputMask** property.</span></span>

<span data-ttu-id="02384-139">若要更改控件的值，可以在宏中指定控件的**AfterUpdate**事件属性使用**SetValue**操作。</span><span class="sxs-lookup"><span data-stu-id="02384-139">To change the value of a control, you can use the **SetValue** action in a macro specified by the control's **AfterUpdate** event property.</span></span> <span data-ttu-id="02384-140">但是，不能在宏中指定控件的**BeforeUpdate**事件属性使用**SetValue**操作，更改控件的值 （尽管可以使用**SetValue**操作来更改其他控件的值）。</span><span class="sxs-lookup"><span data-stu-id="02384-140">However, you can't use the **SetValue** action in a macro specified by a control's **BeforeUpdate** event property to change the value of the control (although you can use the **SetValue** action to change the value of other controls).</span></span> <span data-ttu-id="02384-141">您可以在宏中指定窗体的**BeforeUpdate**或**AfterUpdate**属性使用**SetValue**操作更改当前记录中任何控件的值。</span><span class="sxs-lookup"><span data-stu-id="02384-141">You can also use the **SetValue** action in a macro specified by the **BeforeUpdate** or **AfterUpdate** property of a form to change the value of any controls in the current record.</span></span>


> [!NOTE]
> <P><span data-ttu-id="02384-142">不能使用<STRONG>SetValue</STRONG>操作设置以下控件的值：</span><span class="sxs-lookup"><span data-stu-id="02384-142">You can't use the <STRONG>SetValue</STRONG> action to set the value of the following controls:</span></span></P>
> <UL>
> <LI>
> <P><span data-ttu-id="02384-143">绑定控件和报表上的计算的控件。</span><span class="sxs-lookup"><span data-stu-id="02384-143">Bound controls and calculated controls on reports.</span></span></P>
> <LI>
> <P><span data-ttu-id="02384-144">在窗体上的计算的控件。</span><span class="sxs-lookup"><span data-stu-id="02384-144">Calculated controls on forms.</span></span></P></LI></UL>




> [!TIP]
> <P><span data-ttu-id="02384-145">您可以使用<STRONG>SetValue</STRONG>操作隐藏或显示窗体中窗体视图。</span><span class="sxs-lookup"><span data-stu-id="02384-145">You can use the <STRONG>SetValue</STRONG> action to hide or show a form in Form view.</span></span> <span data-ttu-id="02384-146">输入<STRONG>表单</STRONG>！<EM>formname</EM><STRONG>.可见</STRONG>中<STRONG>项</STRONG>框和<STRONG>无</STRONG>或<STRONG></STRONG><STRONG>表达式</STRONG>框中。</span><span class="sxs-lookup"><span data-stu-id="02384-146">Enter <STRONG>Forms</STRONG>!<EM>formname</EM><STRONG>.Visible</STRONG> in the <STRONG>Item</STRONG> box and <STRONG>No</STRONG> or <STRONG>Yes</STRONG> in the <STRONG>Expression</STRONG> box.</span></span> <span data-ttu-id="02384-147">模式窗体的<STRONG>Visible</STRONG>属性设置为<STRONG>否</STRONG>将隐藏窗体，并使其无模式。</span><span class="sxs-lookup"><span data-stu-id="02384-147">Setting a modal form's <STRONG>Visible</STRONG> property to <STRONG>No</STRONG> hides the form and makes it modeless.</span></span> <span data-ttu-id="02384-148">将属性设置为<STRONG>是</STRONG>的形式显示，并使其在再次时模式。</span><span class="sxs-lookup"><span data-stu-id="02384-148">Setting the property to <STRONG>Yes</STRONG> displays the form and makes it modal again.</span></span></P>



<span data-ttu-id="02384-149">更改的值或控件中添加新数据，在宏中使用**SetValue**操作不会触发如**BeforeUpdate**、 **BeforeInsert**，或**更改**时更改或输入数据，这些控件中所发生的事件用户界面。</span><span class="sxs-lookup"><span data-stu-id="02384-149">Changing the value of or adding new data in a control by using the **SetValue** action in a macro doesn't trigger events such as **BeforeUpdate**, **BeforeInsert**, or **Change** that occur when you change or enter data in these controls in the user interface.</span></span> <span data-ttu-id="02384-150">如果您通过使用 Visual Basic for Applications (VBA) 模块中设置控件的值还不发生这些事件。</span><span class="sxs-lookup"><span data-stu-id="02384-150">These events also don't occur if you set the value of the control by using a Visual Basic for Applications (VBA) module.</span></span>

<span data-ttu-id="02384-151">此操作不能在 VBA 模块中使用。</span><span class="sxs-lookup"><span data-stu-id="02384-151">This action isn't available in a VBA module.</span></span> <span data-ttu-id="02384-152">直接在 VBA 中设置的值。</span><span class="sxs-lookup"><span data-stu-id="02384-152">Set the value directly in VBA.</span></span>

## <a name="example"></a><span data-ttu-id="02384-153">示例</span><span class="sxs-lookup"><span data-stu-id="02384-153">Example</span></span>

<span data-ttu-id="02384-154">**通过使用宏设置控件的值**</span><span class="sxs-lookup"><span data-stu-id="02384-154">**Set the value of a control by using a macro**</span></span>

<span data-ttu-id="02384-155">下面的宏 Suppliers 窗体上的按钮打开添加产品窗体。</span><span class="sxs-lookup"><span data-stu-id="02384-155">The following macro opens the Add Products form from a button on the Suppliers form.</span></span> <span data-ttu-id="02384-156">它演示如何使用**回声**、 **CloseWindow**、 **OpenForm**、 **SetValue**和**GoToControl**操作。</span><span class="sxs-lookup"><span data-stu-id="02384-156">It shows the use of the **Echo**, **CloseWindow**, **OpenForm**, **SetValue**, and **GoToControl** actions.</span></span> <span data-ttu-id="02384-157">**SetValue**操作供应商窗体上将产品窗体上的 SupplierID 控件设置为当前供应商。</span><span class="sxs-lookup"><span data-stu-id="02384-157">The **SetValue** action sets the SupplierID control on the Products form to the current supplier on the Suppliers form.</span></span> <span data-ttu-id="02384-158">然后， **GoToControl**操作将焦点移到 CategoryID 字段中，您可以开始新产品的输入数据。</span><span class="sxs-lookup"><span data-stu-id="02384-158">The **GoToControl** action then moves the focus to the CategoryID field, where you can begin to enter data for the new product.</span></span> <span data-ttu-id="02384-159">这个宏应附加到 Suppliers 窗体上的添加产品按钮。</span><span class="sxs-lookup"><span data-stu-id="02384-159">This macro should be attached to the Add Products button on the Suppliers form.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="02384-160">操作</span><span class="sxs-lookup"><span data-stu-id="02384-160">Action</span></span></p></th>
<th><p><span data-ttu-id="02384-161">参数：设置</span><span class="sxs-lookup"><span data-stu-id="02384-161">Arguments: Setting</span></span></p></th>
<th><p><span data-ttu-id="02384-162">注释</span><span class="sxs-lookup"><span data-stu-id="02384-162">Comment</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="02384-163"><strong>Echo</strong></span><span class="sxs-lookup"><span data-stu-id="02384-163"><strong>Echo</strong></span></span></p></td>
<td><p><span data-ttu-id="02384-164"><strong>打开回响</strong>：<strong>否</strong></span><span class="sxs-lookup"><span data-stu-id="02384-164"><strong>Echo On</strong>: <strong>No</strong></span></span></p></td>
<td><p><span data-ttu-id="02384-165">停止屏幕更新时运行宏。</span><span class="sxs-lookup"><span data-stu-id="02384-165">Stop screen updating while the macro is running.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02384-166"><strong>CloseWindow</strong></span><span class="sxs-lookup"><span data-stu-id="02384-166"><strong>CloseWindow</strong></span></span></p></td>
<td><p><span data-ttu-id="02384-167"><strong>对象类型</strong>： <strong>FormObject 名称</strong>： 产品列表<strong>保存</strong>：<strong>否</strong></span><span class="sxs-lookup"><span data-stu-id="02384-167"><strong>Object Type</strong>: <strong>FormObject Name</strong>: Product List <strong>Save</strong>: <strong>No</strong></span></span></p></td>
<td><p><span data-ttu-id="02384-168">关闭产品列表窗体。</span><span class="sxs-lookup"><span data-stu-id="02384-168">Close the Product List form.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02384-169"><strong>OpenForm</strong></span><span class="sxs-lookup"><span data-stu-id="02384-169"><strong>OpenForm</strong></span></span></p></td>
<td><p><span data-ttu-id="02384-170"><strong>窗体名称</strong>： 产品<strong>视图</strong>： <strong>FormData 模式</strong>： <strong>AddWindow 模式</strong>：<strong>普通</strong></span><span class="sxs-lookup"><span data-stu-id="02384-170"><strong>Form Name</strong>: Products <strong>View</strong>: <strong>FormData Mode</strong>: <strong>AddWindow Mode</strong>: <strong>Normal</strong></span></span></p></td>
<td><p><span data-ttu-id="02384-171">打开产品窗体。</span><span class="sxs-lookup"><span data-stu-id="02384-171">Open the Products form.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="02384-172"><strong>SetValue</strong></span><span class="sxs-lookup"><span data-stu-id="02384-172"><strong>SetValue</strong></span></span></p></td>
<td><p><span data-ttu-id="02384-173"><strong>项目</strong>: [窗体] ！[产品] ！[SupplierID]<strong>表达式</strong>： 供应商 Id</span><span class="sxs-lookup"><span data-stu-id="02384-173"><strong>Item</strong>: [Forms]![Products]![SupplierID] <strong>Expression</strong>: SupplierID</span></span></p></td>
<td><p><span data-ttu-id="02384-174">在 Suppliers 窗体上将 SupplierID 控件设置为当前供应商。</span><span class="sxs-lookup"><span data-stu-id="02384-174">Set the SupplierID control to the current supplier on the Suppliers form.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="02384-175"><strong>GoToControl</strong></span><span class="sxs-lookup"><span data-stu-id="02384-175"><strong>GoToControl</strong></span></span></p></td>
<td><p><span data-ttu-id="02384-176"><strong>控件名称</strong>： CategoryID</span><span class="sxs-lookup"><span data-stu-id="02384-176"><strong>Control Name</strong>: CategoryID</span></span></p></td>
<td><p><span data-ttu-id="02384-177">转到 CategoryID 控件。</span><span class="sxs-lookup"><span data-stu-id="02384-177">Go to the CategoryID control.</span></span></p></td>
</tr>
</tbody>
</table>

