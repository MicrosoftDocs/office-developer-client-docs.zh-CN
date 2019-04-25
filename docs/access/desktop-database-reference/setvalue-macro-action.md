---
title: SetValue 宏操作
TOCTitle: SetValue macro action
ms:assetid: a08be0c1-a053-45f9-b4ae-709fedc58e8b
ms:mtpsurl: https://msdn.microsoft.com/library/Ff820771(v=office.15)
ms:contentKeyID: 48546712
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Priority
ms.openlocfilehash: 6b6f16c22e9265159c73279cfa1b2644adbc0277
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32306816"
---
# <a name="setvalue-macro-action"></a><span data-ttu-id="bb607-102">SetValue 宏操作</span><span class="sxs-lookup"><span data-stu-id="bb607-102">SetValue macro action</span></span>

<span data-ttu-id="bb607-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="bb607-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="bb607-104">可以使用**SetValue**操作来设置 Microsoft Access 字段、 控件的值，或表单、表单数据表或报表属性。</span><span class="sxs-lookup"><span data-stu-id="bb607-104">You can use the **SetValue** action to set the value of a Microsoft Access field, control, or property on a form, a form datasheet, or a report.</span></span>

> [!NOTE]
> - <span data-ttu-id="bb607-105">不能使用**SetValue**操作来设置可返回一个对象的 Access 属性值。</span><span class="sxs-lookup"><span data-stu-id="bb607-105">You cannot use the **SetValue** action to set the value of an Access property that returns an object.</span></span>
> - <span data-ttu-id="bb607-106">如果数据库不受信任，则不允许执行此操作。</span><span class="sxs-lookup"><span data-stu-id="bb607-106">This action will not be allowed if the database is not trusted.</span></span> 

## <a name="setting"></a><span data-ttu-id="bb607-107">Setting</span><span class="sxs-lookup"><span data-stu-id="bb607-107">Setting</span></span>

<span data-ttu-id="bb607-108">**SetValue** 操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="bb607-108">The **OpenVisualBasicModule** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="bb607-109">操作参数</span><span class="sxs-lookup"><span data-stu-id="bb607-109">Action argument</span></span></p></th>
<th><p><span data-ttu-id="bb607-110">说明</span><span class="sxs-lookup"><span data-stu-id="bb607-110">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bb607-111"><strong>Item</strong></span><span class="sxs-lookup"><span data-stu-id="bb607-111"><strong>Item</strong></span></span></p></td>
<td><p><span data-ttu-id="bb607-112">字段、 控件或想要设置其值的属性名称。</span><span class="sxs-lookup"><span data-stu-id="bb607-112">The name of the field, control, or property whose value you want to set.</span></span> <span data-ttu-id="bb607-113">请在“宏生成器”窗格<strong>“操作参数”</strong>部分的<strong>“项目”</strong>框中输入字段、控件或属性名称。</span><span class="sxs-lookup"><span data-stu-id="bb607-113">Enter the control name in the <strong>Control Name</strong> box in the <strong>Action Arguments</strong> section of the Macro Builder pane.</span></span> <span data-ttu-id="bb607-114">必须使用完整的语法来引用此项目，例如<em>controlname</em>（适用于表单上的控件或从其调用宏的报表）或<strong>Forms</strong>!<em>formname</em>!<em>controlname</em>。</span><span class="sxs-lookup"><span data-stu-id="bb607-114">You must use the full syntax to refer to this item, such as <em>controlname</em> (for a control on the form or report from which the macro was called) or <strong>Forms</strong>!<em>formname</em>!<em>controlname</em>.</span></span> <span data-ttu-id="bb607-115">这是必需参数。</span><span class="sxs-lookup"><span data-stu-id="bb607-115">This is a required argument.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb607-116"><strong>Expression</strong></span><span class="sxs-lookup"><span data-stu-id="bb607-116"><strong>Expression</strong></span></span></p></td>
<td><p><span data-ttu-id="bb607-117">表达式 Access 用于设置此项目的值。</span><span class="sxs-lookup"><span data-stu-id="bb607-117">The expression Access uses to set the value for this item.</span></span> <span data-ttu-id="bb607-118">必须始终使用完整的语法来引用表达式中任何对象。</span><span class="sxs-lookup"><span data-stu-id="bb607-118">You must always use the full syntax to refer to any objects in the expression.</span></span> <span data-ttu-id="bb607-119">例如，要增加“员工”表单上某个“工资”控件中的值 10%，请使用 Forms!Employees!Salary\*1.1。</span><span class="sxs-lookup"><span data-stu-id="bb607-119">For example, to increase the value in a Salary control on an Employees form by 10 percent, use Forms!Employees!Salary\*1.1.</span></span> <span data-ttu-id="bb607-120">这是必需参数。</span><span class="sxs-lookup"><span data-stu-id="bb607-120">This is a required argument.</span></span></p><p><span data-ttu-id="bb607-121"><strong>注释</strong>：不得在此参数表达式前使用等号 （=）。</span><span class="sxs-lookup"><span data-stu-id="bb607-121"><strong>NOTE</strong>: You shouldn't use an equal sign (=) before the expression in this argument.</span></span> <span data-ttu-id="bb607-122">若使用等号，则 Access 会对表达式求值，然后使用此值作为此参数中的表达式。</span><span class="sxs-lookup"><span data-stu-id="bb607-122">If you do, Access evaluates the expression and then uses this value as the expression in this argument.</span></span> <span data-ttu-id="bb607-123">如果表达式为一个字符串，将会产生意外结果。</span><span class="sxs-lookup"><span data-stu-id="bb607-123">This can produce unexpected results if the expression is a string.</span></span></p>
<p><span data-ttu-id="bb607-124">例如，如果此参数键入<strong> = &quot;String1&quot; </strong>，则 Access 首先计算表达式为 String1。</span><span class="sxs-lookup"><span data-stu-id="bb607-124">For example, if you type <strong>=&quot;String1&quot;</strong> for this argument, Access first evaluates the expression as String1.</span></span> <span data-ttu-id="bb607-125">然后使用 String1 作为此参数的表达式，期望在调用宏的表单或报表上找到名为 String1 的控件或属性。</span><span class="sxs-lookup"><span data-stu-id="bb607-125">Then it uses String1 as the expression in this argument, expecting to find a control or property named String1 on the form or report that called the macro.</span></span></p></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="bb607-126">在 Access 数据库（.mdb 或 .accdb）中，单击 **“生成”** 按钮，以便使用“表达式生成器”为这些参数中的任意一个选择一个表达式。</span><span class="sxs-lookup"><span data-stu-id="bb607-126">In an Access database (.mdb or .accdb), click the **Build** button to use the Expression Builder to select a function for this argument.</span></span>

## <a name="remarks"></a><span data-ttu-id="bb607-127">说明</span><span class="sxs-lookup"><span data-stu-id="bb607-127">Remarks</span></span>

<span data-ttu-id="bb607-128">此操作可用于设置表单、表单数据表或报表上的字段或控件的值。</span><span class="sxs-lookup"><span data-stu-id="bb607-128">You can use this action to set a value for a field or control on a form, a form datasheet, or a report.</span></span> <span data-ttu-id="bb607-129">此外可以在任意视图中设置几乎所有控件、表单和报表属性值。</span><span class="sxs-lookup"><span data-stu-id="bb607-129">You can also set the value for almost all control, form, and report properties in any view.</span></span> <span data-ttu-id="bb607-130">若要找出是否可通过使用宏来设置特定属性，以及可以在哪些视图中设置，请参阅在 Visual Basic 编辑器中有关该属性的“帮助”主题。</span><span class="sxs-lookup"><span data-stu-id="bb607-130">To find out whether a particular property can be set by using a macro and which views it can be set in, see the Help topic for that property in the Visual Basic Editor.</span></span>

<span data-ttu-id="bb607-131">即使表单不包含绑定字段的控件，也可以在表单基础表中设置字段值。</span><span class="sxs-lookup"><span data-stu-id="bb607-131">You can also set the value for a field in a form's underlying table even if the form doesn't contain a control bound to the field.</span></span> <span data-ttu-id="bb607-132">在**项目**框中使用语法**Forms**\!*formname*\!*fieldname*以设置此类字段的值。</span><span class="sxs-lookup"><span data-stu-id="bb607-132">Use the syntax **Forms**\!*formname*\!*fieldname* in the **Item** box to set the value for such a field.</span></span> <span data-ttu-id="bb607-133">你还可使用语法**Reports**\!*reportname*\!*fieldname*引用到报表基础表中的字段，但是绑定到此字段的报表上必须有一个控件，或者必须在报表上计算控件中引用字段。</span><span class="sxs-lookup"><span data-stu-id="bb607-133">You can also refer to a field in a report's underlying table by using the syntax **Reports**\!*reportname*\!*fieldname*, but there must be a control on the report bound to this field, or the field must be referred to in a calculated control on the report.</span></span>

<span data-ttu-id="bb607-134">如果在表单上设置控件值，**SetValue**操作不会触发控件的表单级别的验证规则，但如果控件是绑定的控件，则会触发基础字段的表级别验证规则。</span><span class="sxs-lookup"><span data-stu-id="bb607-134">If you set the value of a control on a form, the **SetValue** action doesn't trigger the control's form-level validation rules, but it does trigger the underlying field's table-level validation rules if the control is a bound control.</span></span> <span data-ttu-id="bb607-135">**SetValue**操作还会触发重新计算，但重新计算不会立即发生。</span><span class="sxs-lookup"><span data-stu-id="bb607-135">The **SetValue** action also triggers recalculation, but the recalculation may not happen immediately.</span></span> <span data-ttu-id="bb607-136">若触发立即重画并强制完成重新计算，使用**RepaintObject**操作。</span><span class="sxs-lookup"><span data-stu-id="bb607-136">To trigger immediate repainting and force the recalculation to completion, use the **RepaintObject** action.</span></span> <span data-ttu-id="bb607-137">使用**SetValue**操作在控件中设置的值还不受在控件或基础字段的**InputMask**属性中设置的输入掩码的影响。</span><span class="sxs-lookup"><span data-stu-id="bb607-137">The value you set in a control by using the **SetValue** action is also not affected by an input mask set in the control's or underlying field's **InputMask** property.</span></span>

<span data-ttu-id="bb607-138">若要更改控件值，可以在由控件的**AfterUpdate**事件属性指定的宏中使用**SetValue**操作。</span><span class="sxs-lookup"><span data-stu-id="bb607-138">To change the value of a control, you can use the **SetValue** action in a macro specified by the control's **AfterUpdate** event property.</span></span> <span data-ttu-id="bb607-139">但是，不能在控件的**BeforeUpdate**事件属性指定的宏中使用**SetValue**操作来变更控件值（虽然可使用**SetValue**操作来变更其他控件的值）。</span><span class="sxs-lookup"><span data-stu-id="bb607-139">However, you can't use the **SetValue** action in a macro specified by a control's **BeforeUpdate** event property to change the value of the control (although you can use the **SetValue** action to change the value of other controls).</span></span> <span data-ttu-id="bb607-140">也可以在表单的**BeforeUpdate**或**AfterUpdate**属性指定的宏中使用**SetValue**操作来变更在当前记录中任何控件的值。</span><span class="sxs-lookup"><span data-stu-id="bb607-140">You can also use the **SetValue** action in a macro specified by the **BeforeUpdate** or **AfterUpdate** property of a form to change the value of any controls in the current record.</span></span>

> [!NOTE]
> <span data-ttu-id="bb607-141">不能使用**SetValue**操作来设置以下控件的值：</span><span class="sxs-lookup"><span data-stu-id="bb607-141">You can't use the **SetValue** action to set the value of the following controls:</span></span>
> - <span data-ttu-id="bb607-142">报表上的绑定控件计算控件。</span><span class="sxs-lookup"><span data-stu-id="bb607-142">Bound controls and calculated controls on reports.</span></span>
> - <span data-ttu-id="bb607-143">表单上的计算控件。</span><span class="sxs-lookup"><span data-stu-id="bb607-143">Calculated controls on forms.</span></span>

> [!TIP]
> <span data-ttu-id="bb607-144">可以使用**SetValue**操作来隐藏或显示“表单”视图中的表单。</span><span class="sxs-lookup"><span data-stu-id="bb607-144">You can use the **SetValue** action to hide or show a form in Form view.</span></span> <span data-ttu-id="bb607-145">在**Item**框中输入**Forms**!\*formname\***.Visible**，然后在**Expression**框中输入**No**或**Yes**。</span><span class="sxs-lookup"><span data-stu-id="bb607-145">Enter **Forms**!*formname\*\*\*.Visible*\* in the **Item** box, and **No** or **Yes** in the **Expression** box.</span></span> <span data-ttu-id="bb607-146">设置模式表单的**Visible**属性为**No**，以隐藏表单并使其成为无模式。</span><span class="sxs-lookup"><span data-stu-id="bb607-146">Setting a modal form's **Visible** property to **No** hides the form and makes it modeless.</span></span> <span data-ttu-id="bb607-147">将属性设置为**Yes**以显示表单并使其再次成为模式。</span><span class="sxs-lookup"><span data-stu-id="bb607-147">Setting the property to **Yes** displays the form and makes it modal again.</span></span>

<span data-ttu-id="bb607-148">在宏中使用**SetValue**操作来变更控件值或添加新数据不会触发**BeforeUpdate**、**BeforeInsert**或**Change**之类的事件，在用户界面的这些控件中更改或输入数据时通常发生此类事件。</span><span class="sxs-lookup"><span data-stu-id="bb607-148">Changing the value of or adding new data in a control by using the **SetValue** action in a macro doesn't trigger events such as **BeforeUpdate**, **BeforeInsert**, or **Change** that occur when you change or enter data in these controls in the user interface.</span></span> <span data-ttu-id="bb607-149">如果使用 Visual Basic for Applications (VBA) 模块来设置控件值，也不会发生这些事件。</span><span class="sxs-lookup"><span data-stu-id="bb607-149">These events also don't occur if you set the value of the control by using a Visual Basic for Applications (VBA) module.</span></span>

<span data-ttu-id="bb607-150">此操作在 VBA 模块中不可用。</span><span class="sxs-lookup"><span data-stu-id="bb607-150">This action isn't available in a VBA module.</span></span> <span data-ttu-id="bb607-151">直接在 VBA 中设置值。</span><span class="sxs-lookup"><span data-stu-id="bb607-151">Set the value directly in Visual Basic.</span></span>

## <a name="example"></a><span data-ttu-id="bb607-152">示例</span><span class="sxs-lookup"><span data-stu-id="bb607-152">Example</span></span>

<span data-ttu-id="bb607-153">**使用宏来设置控件值**</span><span class="sxs-lookup"><span data-stu-id="bb607-153">**Set the value of a control by using a macro**</span></span>

<span data-ttu-id="bb607-154">下列宏从“供应商”表单上的按钮打开“添加产品”表单。</span><span class="sxs-lookup"><span data-stu-id="bb607-154">The following macro opens the Add Products form from a button on the Suppliers form.</span></span> <span data-ttu-id="bb607-155">显示如何使用**Echo**、**CloseWindow**、**OpenForm**、 **SetValue**和**GoToControl**操作。</span><span class="sxs-lookup"><span data-stu-id="bb607-155">It shows the use of the **Echo**, **CloseWindow**, **OpenForm**, **SetValue**, and **GoToControl** actions.</span></span> <span data-ttu-id="bb607-156">**SetValue**操作将“产品”表单上的 SupplierID 控件设置为“供应商”表单上的当前供应商。</span><span class="sxs-lookup"><span data-stu-id="bb607-156">The **SetValue** action sets the SupplierID control on the Products form to the current supplier on the Suppliers form.</span></span> <span data-ttu-id="bb607-157">然后**GoToControl**操作会将焦点移动至 CategoryID 字段，在这里开始输入新产品数据。</span><span class="sxs-lookup"><span data-stu-id="bb607-157">The **GoToControl** action then moves the focus to the CategoryID field, where you can begin to enter data for the new product.</span></span> <span data-ttu-id="bb607-158">此宏应附加到“供应商”表单上的“添加产品”按钮。</span><span class="sxs-lookup"><span data-stu-id="bb607-158">This macro should be attached to the Add Products button on the Suppliers form.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="bb607-159">操作</span><span class="sxs-lookup"><span data-stu-id="bb607-159">Action</span></span></p></th>
<th><p><span data-ttu-id="bb607-160">参数：设置</span><span class="sxs-lookup"><span data-stu-id="bb607-160">Arguments: Setting</span></span></p></th>
<th><p><span data-ttu-id="bb607-161">注释</span><span class="sxs-lookup"><span data-stu-id="bb607-161">Comment</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bb607-162"><strong>Echo</strong></span><span class="sxs-lookup"><span data-stu-id="bb607-162"><strong>Echo</strong></span></span></p></td>
<td><p><span data-ttu-id="bb607-163"><strong>Echo On</strong>: <strong>No</strong></span><span class="sxs-lookup"><span data-stu-id="bb607-163"><strong>Echo On</strong>: <strong>No</strong></span></span></p></td>
<td><p><span data-ttu-id="bb607-164">运行宏时停止屏幕更新。</span><span class="sxs-lookup"><span data-stu-id="bb607-164">Stop screen updating while the macro is running.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb607-165"><strong>CloseWindow</strong></span><span class="sxs-lookup"><span data-stu-id="bb607-165"><strong>CloseWindow</strong></span></span></p></td>
<td><p><span data-ttu-id="bb607-166"><strong>Object Type</strong>: <strong>FormObject Name</strong>: Product List <strong>Save</strong>: <strong>No</strong></span><span class="sxs-lookup"><span data-stu-id="bb607-166"><strong>Object Type</strong>: <strong>FormObject Name</strong>: Product List <strong>Save</strong>: <strong>No</strong></span></span></p></td>
<td><p><span data-ttu-id="bb607-167">关闭“产品列表”表单。</span><span class="sxs-lookup"><span data-stu-id="bb607-167">Close the Product List form.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb607-168"><strong>OpenForm</strong></span><span class="sxs-lookup"><span data-stu-id="bb607-168"><strong>OpenForm</strong></span></span></p></td>
<td><p><span data-ttu-id="bb607-169"><strong>Form Name</strong>: Products <strong>View</strong>: <strong>FormData Mode</strong>: <strong>AddWindow Mode</strong>: <strong>Normal</strong></span><span class="sxs-lookup"><span data-stu-id="bb607-169"><strong>Form Name</strong>: Products <strong>View</strong>: <strong>FormData Mode</strong>: <strong>AddWindow Mode</strong>: <strong>Normal</strong></span></span></p></td>
<td><p><span data-ttu-id="bb607-170">打开“产品”表单。</span><span class="sxs-lookup"><span data-stu-id="bb607-170">Open the form</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb607-171"><strong>SetValue</strong></span><span class="sxs-lookup"><span data-stu-id="bb607-171"><strong>SetValue</strong></span></span></p></td>
<td><p><span data-ttu-id="bb607-172"><strong>Item</strong>: [Forms]![Products]![SupplierID] <strong>Expression</strong>: SupplierID</span><span class="sxs-lookup"><span data-stu-id="bb607-172"><strong>Item</strong>: [Forms]![Products]![SupplierID] <strong>Expression</strong>: SupplierID</span></span></p></td>
<td><p><span data-ttu-id="bb607-173">在“供应商”表单上将 SupplierID 控件设置为当前供应商。</span><span class="sxs-lookup"><span data-stu-id="bb607-173">Set the SupplierID control to the current supplier on the Suppliers form.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb607-174"><strong>GoToControl</strong></span><span class="sxs-lookup"><span data-stu-id="bb607-174"><strong>GoToControl</strong></span></span></p></td>
<td><p><span data-ttu-id="bb607-175"><strong>Control Name</strong>: CategoryID</span><span class="sxs-lookup"><span data-stu-id="bb607-175"><strong>Control Name</strong>: CategoryID</span></span></p></td>
<td><p><span data-ttu-id="bb607-176">转到 CategoryID 控件。</span><span class="sxs-lookup"><span data-stu-id="bb607-176">Go to the CategoryID control.</span></span></p></td>
</tr>
</tbody>
</table>

