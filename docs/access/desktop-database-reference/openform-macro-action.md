---
title: OpenForm 宏操作
TOCTitle: OpenForm macro action
ms:assetid: c519a9d7-99d4-4765-ad96-59c3fe1be9e3
ms:mtpsurl: https://msdn.microsoft.com/library/Ff823095(v=office.15)
ms:contentKeyID: 48547604
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: cf89b61a65c11f09d5a07e52caeee5ad416c118a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288369"
---
# <a name="openform-macro-action"></a><span data-ttu-id="e0db1-102">OpenForm 宏操作</span><span class="sxs-lookup"><span data-stu-id="e0db1-102">OpenForm macro action</span></span>

<span data-ttu-id="e0db1-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="e0db1-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="e0db1-104">可以使用**OpenForm**操作在 "窗体" 视图、"设计" 视图、"打印预览" 或 "数据表" 视图中打开窗体。</span><span class="sxs-lookup"><span data-stu-id="e0db1-104">You can use the **OpenForm** action to open a form in Form view, Design view, Print Preview, or Datasheet view.</span></span> <span data-ttu-id="e0db1-105">可以选择窗体的数据输入模式和窗口模式，并限制窗体显示的记录。</span><span class="sxs-lookup"><span data-stu-id="e0db1-105">You can select data entry and window modes for the form and restrict the records that the form displays.</span></span>

## <a name="setting"></a><span data-ttu-id="e0db1-106">Setting</span><span class="sxs-lookup"><span data-stu-id="e0db1-106">Setting</span></span>

<span data-ttu-id="e0db1-107">**OpenForm**操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="e0db1-107">The **OpenForm** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="e0db1-108">操作参数</span><span class="sxs-lookup"><span data-stu-id="e0db1-108">Action argument</span></span></p></th>
<th><p><span data-ttu-id="e0db1-109">说明</span><span class="sxs-lookup"><span data-stu-id="e0db1-109">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e0db1-110"><strong>表单名称</strong></span><span class="sxs-lookup"><span data-stu-id="e0db1-110"><strong>Form Name</strong></span></span></p></td>
<td><p><span data-ttu-id="e0db1-111">要打开的窗体的名称。</span><span class="sxs-lookup"><span data-stu-id="e0db1-111">The name of the form to open.</span></span> <span data-ttu-id="e0db1-112">"宏生成器" 窗格的 "<strong>操作参数</strong>" 部分的 "<strong>窗体名称</strong>" 框中显示了当前数据库中的所有窗体。</span><span class="sxs-lookup"><span data-stu-id="e0db1-112">The <strong>Form Name</strong> box in the <strong>Action Arguments</strong> section of the Macro Builder pane shows all forms in the current database.</span></span> <span data-ttu-id="e0db1-113">这是必需参数。</span><span class="sxs-lookup"><span data-stu-id="e0db1-113">This is a required argument.</span></span> <span data-ttu-id="e0db1-114">如果在类库数据库中运行包含<strong>OpenForm</strong>操作的宏, Microsoft Access 将先在该类库数据库中查找具有此名称的窗体, 然后再在当前数据库中查找。</span><span class="sxs-lookup"><span data-stu-id="e0db1-114">If you run a macro containing the <strong>OpenForm</strong> action in a library database, Microsoft Access first looks for the form with this name in the library database, and then in the current database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0db1-115"><strong>View</strong></span><span class="sxs-lookup"><span data-stu-id="e0db1-115"><strong>View</strong></span></span></p></td>
<td><p><span data-ttu-id="e0db1-116">将在其中打开表单的视图。</span><span class="sxs-lookup"><span data-stu-id="e0db1-116">The view in which the form will open.</span></span> <span data-ttu-id="e0db1-117">单击 "<strong>视图</strong>" 框中的 "<strong>窗体</strong>、<strong>设计</strong>、<strong>打印预览</strong>、<strong>数据表</strong>、<strong>数据透视表</strong>" 或 "数据<strong>透视图</strong>"。</span><span class="sxs-lookup"><span data-stu-id="e0db1-117">Click <strong>Form</strong>, <strong>Design</strong>, <strong>Print Preview</strong>, <strong>Datasheet</strong>, <strong>PivotTable</strong>, or <strong>PivotChart</strong> in the <strong>View</strong> box.</span></span> <span data-ttu-id="e0db1-118">默认值为<strong>Form</strong>。</span><span class="sxs-lookup"><span data-stu-id="e0db1-118">The default is <strong>Form</strong>.</span></span></p><p><span data-ttu-id="e0db1-119"><strong>注意</strong>: "<STRONG>查看</STRONG>" 参数设置将覆盖窗体的 "<STRONG>默认</STRONG>视图<STRONG></STRONG> " 和 "已视图" 属性的设置。</span><span class="sxs-lookup"><span data-stu-id="e0db1-119"><strong>NOTE</strong>: The <STRONG>View</STRONG> argument setting overrides the settings of the form's <STRONG>DefaultView</STRONG> and <STRONG>ViewsAllowed</STRONG> properties.</span></span> <span data-ttu-id="e0db1-120">例如, 如果将窗体的 "可<STRONG>视图</STRONG>" 属性设置为<STRONG>"数据表</STRONG>", 仍可以使用<STRONG>OpenForm</STRONG>操作在 "窗体" 视图中打开窗体。</span><span class="sxs-lookup"><span data-stu-id="e0db1-120">For example, if a form's <STRONG>ViewsAllowed</STRONG> property is set to <STRONG>Datasheet</STRONG>, you can still use the <STRONG>OpenForm</STRONG> action to open the form in Form view.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0db1-121"><strong>Filter Name</strong></span><span class="sxs-lookup"><span data-stu-id="e0db1-121"><strong>Filter Name</strong></span></span></p></td>
<td><p><span data-ttu-id="e0db1-122">限制或对窗体的记录进行排序的筛选器。</span><span class="sxs-lookup"><span data-stu-id="e0db1-122">A filter that restricts or sorts the form's records.</span></span> <span data-ttu-id="e0db1-123">您可以输入现有查询的名称，也可以输入另存为查询的筛选的名称。</span><span class="sxs-lookup"><span data-stu-id="e0db1-123">You can enter the name of either an existing query or a filter that was saved as a query.</span></span> <span data-ttu-id="e0db1-124">但是, 查询必须包含要打开的窗体中的所有字段, 或者将其<strong>输出</strong>所有字段设置为<strong>"是"</strong>。</span><span class="sxs-lookup"><span data-stu-id="e0db1-124">However, the query must include all the fields in the form you are opening or have its <strong>OutputAllFields</strong> property set to <strong>Yes</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0db1-125"><strong>Where 条件</strong></span><span class="sxs-lookup"><span data-stu-id="e0db1-125"><strong>Where Condition</strong></span></span></p></td>
<td><p><span data-ttu-id="e0db1-126">Access 用于从窗体的基础表或查询中选择记录的有效 SQL WHERE 子句 (不含 word WHERE) 或表达式。</span><span class="sxs-lookup"><span data-stu-id="e0db1-126">A valid SQL WHERE clause (without the word WHERE) or expression that Access uses to select records from the form's underlying table or query.</span></span> <span data-ttu-id="e0db1-127">如果您通过“筛选名称”<strong></strong>参数选择筛选，Access 会将此 WHERE 子句应用于筛选的结果。</span><span class="sxs-lookup"><span data-stu-id="e0db1-127">If you select a filter with the <strong>Filter Name</strong> argument, Access applies this WHERE clause to the results of the filter.</span></span> <span data-ttu-id="e0db1-128">若要打开一个窗体并将其记录限制为由另一个窗体上的某个控件的值指定的记录, 请使用以下表达式: <strong>[</strong><em>fieldname</em><strong>] = Forms! [</strong><em>formname</em><strong>]![</strong><em>controlname 在其他窗体上</em>使用<strong>]</strong>将<em>fieldname</em>替换为要打开的窗体的基础表或查询中的字段的名称。</span><span class="sxs-lookup"><span data-stu-id="e0db1-128">To open a form and restrict its records to those specified by the value of a control on another form, use the following expression: <strong>[</strong><em>fieldname</em><strong>] = Forms![</strong><em>formname</em><strong>]![</strong><em>controlname on other form</em><strong>]</strong> Replace <em>fieldname</em> with the name of a field in the underlying table or query of the form you want to open.</span></span> <span data-ttu-id="e0db1-129">将其他表单<em>上</em>的<em>formname</em>和 controlname 替换为其他窗体的名称, 并将另一个窗体上的控件替换为您希望第一个窗体中的记录与之匹配的值。</span><span class="sxs-lookup"><span data-stu-id="e0db1-129">Replace <em>formname</em> and <em>controlname on other form</em> with the name of the other form and the control on the other form that contains the value you want records in the first form to match.</span></span></p><p><span data-ttu-id="e0db1-130"><strong>注意</strong>: <STRONG>Where Condition</STRONG>参数的最大长度为255个字符。</span><span class="sxs-lookup"><span data-stu-id="e0db1-130"><strong>NOTE</strong>: The maximum length of the <STRONG>Where Condition</STRONG> argument is 255 characters.</span></span> <span data-ttu-id="e0db1-131">如果需要输入更复杂的 SQL WHERE 子句, 请改用 Visual Basic for Applications (VBA) 模块中<STRONG>DoCmd</STRONG>对象的<STRONG>OpenForm</STRONG>方法。</span><span class="sxs-lookup"><span data-stu-id="e0db1-131">If you need to enter a more complex SQL WHERE clause longer than this, use the <STRONG>OpenForm</STRONG> method of the <STRONG>DoCmd</STRONG> object in a Visual Basic for Applications (VBA) module instead.</span></span> <span data-ttu-id="e0db1-132">在 VBA 中，可输入长达 32,768 个字符的 SQL WHERE 子句语句。</span><span class="sxs-lookup"><span data-stu-id="e0db1-132">You can enter SQL WHERE clause statements of up to 32,768 characters in VBA.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0db1-133"><strong>数据模式</strong></span><span class="sxs-lookup"><span data-stu-id="e0db1-133"><strong>Data Mode</strong></span></span></p></td>
<td><p><span data-ttu-id="e0db1-134">表单的数据输入模式。</span><span class="sxs-lookup"><span data-stu-id="e0db1-134">The data entry mode for the form.</span></span> <span data-ttu-id="e0db1-135">这仅适用于在窗体视图或数据表视图中打开的窗体。</span><span class="sxs-lookup"><span data-stu-id="e0db1-135">This applies only to forms opened in Form view or Datasheet view.</span></span> <span data-ttu-id="e0db1-136">请单击<strong>“添加”</strong>（用户可添加新记录，但不能编辑现有记录）、<strong>“编辑”</strong>（用户可编辑现有记录和添加新记录）或<strong>“只读”</strong>（用户只能查看记录）。</span><span class="sxs-lookup"><span data-stu-id="e0db1-136">Click <strong>Add</strong> (the user can add new records but can't edit existing records), <strong>Edit</strong> (the user can edit existing records and add new records), or <strong>Read Only</strong> (the user can only view records).</span></span> <span data-ttu-id="e0db1-137">默认值为<strong>“编辑”</strong>。</span><span class="sxs-lookup"><span data-stu-id="e0db1-137">The default is <strong>Edit</strong>.</span></span> <span data-ttu-id="e0db1-138"><strong>Notes</strong></span><span class="sxs-lookup"><span data-stu-id="e0db1-138"><strong>Notes</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="e0db1-139">"<strong>数据模式</strong>" 参数设置将替代表单的 "<strong>允许编辑</strong>"、" <strong></strong>允许删除" <strong></strong> 、"允许添加" 和 "输入" 属性的设置。 <strong></strong></span><span class="sxs-lookup"><span data-stu-id="e0db1-139">The <strong>Data Mode</strong> argument setting overrides the settings of the form's <strong>AllowEdits</strong>, <strong>AllowDeletions</strong>, <strong>AllowAdditions</strong>, and <strong>DataEntry</strong> properties.</span></span> <span data-ttu-id="e0db1-140">例如, 如果窗体的<strong>允许</strong>编辑属性设置为 "<strong>否</strong>", 仍可以使用<strong>OpenForm</strong>操作在编辑模式下打开该窗体。</span><span class="sxs-lookup"><span data-stu-id="e0db1-140">For example, if a form's <strong>AllowEdits</strong> property is set to <strong>No</strong>, you can still use the <strong>OpenForm</strong> action to open the form in Edit mode.</span></span></p></li>
<li><p><span data-ttu-id="e0db1-141">如果将此参数留空, Access 将打开 "数据输入" 模式中由窗体的<strong>允许编辑、允许</strong>删除<strong></strong>、允许添加<strong></strong>和添加属性设置的窗体。 <strong></strong></span><span class="sxs-lookup"><span data-stu-id="e0db1-141">If you leave this argument blank, Access opens the form in the data entry mode set by the form's <strong>AllowEdits</strong>, <strong>AllowDeletions</strong>, <strong>AllowAdditions</strong>, and <strong>DataEntry</strong> properties.</span></span></p></li>
</ul>
<p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0db1-142"><strong>窗口模式</strong></span><span class="sxs-lookup"><span data-stu-id="e0db1-142"><strong>Window Mode</strong></span></span></p></td>
<td><p><span data-ttu-id="e0db1-143">打开窗体时所用的窗口模式。</span><span class="sxs-lookup"><span data-stu-id="e0db1-143">The window mode in which the form opens.</span></span> <span data-ttu-id="e0db1-144">单击 "<strong>普通</strong>" (窗体将在由其属性设置的模式中打开)、"<strong>隐藏</strong>(隐藏窗体)"、"<strong>图标</strong>" (窗体打开时最小化为屏幕底部的小标题栏) 或<strong>对话框</strong>(窗体的<strong>模式</strong>和<strong>弹出菜单)</strong>属性设置为<strong>"是"</strong>)。</span><span class="sxs-lookup"><span data-stu-id="e0db1-144">Click <strong>Normal</strong> (the form opens in the mode set by its properties), <strong>Hidden</strong> (the form is hidden), <strong>Icon</strong> (the form opens minimized as a small title bar at the bottom of the screen), or <strong>Dialog</strong> (the form's <strong>Modal</strong> and <strong>PopUp</strong> properties are set to <strong>Yes</strong>).</span></span> <span data-ttu-id="e0db1-145">默认值为<strong>“普通”</strong>。</span><span class="sxs-lookup"><span data-stu-id="e0db1-145">The default is <strong>Normal</strong>.</span></span></p><p><span data-ttu-id="e0db1-146"><strong>注意</strong>: 使用选项卡式文档时, 某些<STRONG>窗口模式</STRONG>参数设置不适用。</span><span class="sxs-lookup"><span data-stu-id="e0db1-146"><strong>NOTE</strong>: Some <STRONG>Window Mode</STRONG> argument settings do not apply when using tabbed documents.</span></span> <span data-ttu-id="e0db1-147">要切换到重叠窗口，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="e0db1-147">To switch to overlapping windows:</span></span></p>
<ol>
<li><p><span data-ttu-id="e0db1-148">单击 "文件" 选项卡, 然后单击 "<strong>选项</strong>"。</span><span class="sxs-lookup"><span data-stu-id="e0db1-148">Click the File tab and then click <strong>Options</strong>.</span></span></p></li>
<li><p><span data-ttu-id="e0db1-149">在<strong>“Access 选项”</strong>对话框中，单击<strong>“当前数据库”</strong>。</span><span class="sxs-lookup"><span data-stu-id="e0db1-149">In the <strong>Access Options</strong> dialog box, click <strong>Current Database</strong>.</span></span></p></li>
<li><p><span data-ttu-id="e0db1-150">在 "<strong>应用程序选项</strong>" 部分的 "<strong>文档窗口选项</strong>" 下, 单击 "<strong>重叠窗口</strong>"。</span><span class="sxs-lookup"><span data-stu-id="e0db1-150">In the <strong>Application Options</strong>section, under <strong>Document Window Options</strong>, click <strong>Overlapping Windows</strong>.</span></span></p></li>
<li><p><span data-ttu-id="e0db1-151">单击<strong>“确定”</strong>，然后关闭并重新打开数据库。</span><span class="sxs-lookup"><span data-stu-id="e0db1-151">Click <strong>OK</strong>, then close and reopen the database.</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="e0db1-152">注解</span><span class="sxs-lookup"><span data-stu-id="e0db1-152">Remarks</span></span>

<span data-ttu-id="e0db1-153">此操作类似于在导航窗格中双击窗体, 或者右键单击导航窗格中的窗体, 然后选择视图。</span><span class="sxs-lookup"><span data-stu-id="e0db1-153">This action is similar to double-clicking a form in the Navigation Pane, or right-clicking the form in the Navigation Pane and then selecting a view.</span></span>

<span data-ttu-id="e0db1-154">窗体可以是模式的 (在用户可以执行任何其他操作之前, 必须将其关闭或隐藏) 或无模式 (用户可以在窗体处于打开状态时移动到其他窗口)。</span><span class="sxs-lookup"><span data-stu-id="e0db1-154">A form can be modal (it must be closed or hidden before the user can perform any other action) or modeless (the user can move to other windows while the form is open).</span></span> <span data-ttu-id="e0db1-155">它还可以是弹出式窗体 (用于收集或显示在所有其他 Access 窗口顶部的信息的窗体)。</span><span class="sxs-lookup"><span data-stu-id="e0db1-155">It can also be a pop-up form (a form used to collect or display information that remains on top of all other Access windows).</span></span> <span data-ttu-id="e0db1-156">您在设计窗体时设置了**Modal**和**PopUp**属性。</span><span class="sxs-lookup"><span data-stu-id="e0db1-156">You set the **Modal** and **PopUp** properties when you design the form.</span></span> <span data-ttu-id="e0db1-157">如果对 "**窗口模式**" 参数使用 "**常规**", 则该窗体将以这些属性设置指定的模式打开。</span><span class="sxs-lookup"><span data-stu-id="e0db1-157">If you use **Normal** for the **Window Mode** argument, the form opens in the mode specified by these property settings.</span></span> <span data-ttu-id="e0db1-158">如果将**对话框**用于**窗口模式**参数, 则这些属性都设置为 **"是"**。</span><span class="sxs-lookup"><span data-stu-id="e0db1-158">If you use **Dialog** for the **Window Mode** argument, these properties are both set to **Yes**.</span></span> <span data-ttu-id="e0db1-159">作为隐藏或图标打开的窗体将返回到显示或还原时其属性设置所指定的模式。</span><span class="sxs-lookup"><span data-stu-id="e0db1-159">A form opened as hidden or as an icon returns to the mode specified by its property settings when you show or restore it.</span></span>

<span data-ttu-id="e0db1-160">打开 "**窗口模式**" 参数设置为 "**对话框**" 的窗体时, Access 将挂起宏, 直到窗体关闭或隐藏。</span><span class="sxs-lookup"><span data-stu-id="e0db1-160">When you open a form with the **Window Mode** argument set to **Dialog**, Access suspends the macro until the form is closed or hidden.</span></span> <span data-ttu-id="e0db1-161">您可以通过使用**SetValue**操作将窗体的**Visible**属性设置为 "**否**" 来隐藏窗体。</span><span class="sxs-lookup"><span data-stu-id="e0db1-161">You can hide a form by setting its **Visible** property to **No** by using the **SetValue** action.</span></span>

> [!TIP]
> <span data-ttu-id="e0db1-162">您可以在导航窗格中选择窗体并将其拖动到宏操作行。</span><span class="sxs-lookup"><span data-stu-id="e0db1-162">You can select a form in the Navigation Pane and drag it to a macro action row.</span></span> <span data-ttu-id="e0db1-163">这会自动创建一个在 "窗体" 视图中打开窗体的**OpenForm**操作。</span><span class="sxs-lookup"><span data-stu-id="e0db1-163">This automatically creates an **OpenForm** action that opens the form in Form view.</span></span>

<span data-ttu-id="e0db1-164">应用的筛选和 WHERE 条件将成为窗体的**filter**属性的设置。</span><span class="sxs-lookup"><span data-stu-id="e0db1-164">The filter and WHERE condition you apply become the setting of the form's **Filter** property.</span></span>

## <a name="examples"></a><span data-ttu-id="e0db1-165">示例</span><span class="sxs-lookup"><span data-stu-id="e0db1-165">Examples</span></span>

<span data-ttu-id="e0db1-166">**使用宏设置控件的值**</span><span class="sxs-lookup"><span data-stu-id="e0db1-166">**Set the value of a control by using a macro**</span></span>

<span data-ttu-id="e0db1-167">以下宏将从 "供应商" 窗体上的按钮中打开 "添加产品" 窗体。</span><span class="sxs-lookup"><span data-stu-id="e0db1-167">The following macro opens the Add Products form from a button on the Suppliers form.</span></span> <span data-ttu-id="e0db1-168">它显示了**Echo**、 **CloseWindow**、 **OpenForm**、 **SetValue**和**GoToControl**操作的使用。</span><span class="sxs-lookup"><span data-stu-id="e0db1-168">It shows the use of the **Echo**, **CloseWindow**, **OpenForm**, **SetValue**, and **GoToControl** actions.</span></span> <span data-ttu-id="e0db1-169">**SetValue**操作将 "产品" 窗体上的 "供应商 ID" 控件设置为 "供应商" 窗体上的当前供应商。</span><span class="sxs-lookup"><span data-stu-id="e0db1-169">The **SetValue** action sets the Supplier ID control on the Products form to the current supplier on the Suppliers form.</span></span> <span data-ttu-id="e0db1-170">然后, **GoToControl**操作将焦点移到 "类别 ID" 字段, 在其中可以开始为新产品输入数据。</span><span class="sxs-lookup"><span data-stu-id="e0db1-170">The **GoToControl** action then moves the focus to the Category ID field, where you can begin to enter data for the new product.</span></span> <span data-ttu-id="e0db1-171">此宏应附加到 "供应商" 窗体上的 "添加产品" 按钮。</span><span class="sxs-lookup"><span data-stu-id="e0db1-171">This macro should be attached to the Add Products button on the Suppliers form.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="e0db1-172">操作</span><span class="sxs-lookup"><span data-stu-id="e0db1-172">Action</span></span></p></th>
<th><p><span data-ttu-id="e0db1-173">参数：设置</span><span class="sxs-lookup"><span data-stu-id="e0db1-173">Arguments: Setting</span></span></p></th>
<th><p><span data-ttu-id="e0db1-174">Comment</span><span class="sxs-lookup"><span data-stu-id="e0db1-174">Comment</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e0db1-175"><strong>Echo</strong></span><span class="sxs-lookup"><span data-stu-id="e0db1-175"><strong>Echo</strong></span></span></p></td>
<td><p><span data-ttu-id="e0db1-176"><strong>打开回响</strong>:<strong>否</strong></span><span class="sxs-lookup"><span data-stu-id="e0db1-176"><strong>Echo On</strong>: <strong>No</strong></span></span></p></td>
<td><p><span data-ttu-id="e0db1-177">在宏运行时停止屏幕更新。</span><span class="sxs-lookup"><span data-stu-id="e0db1-177">Stop screen updating while the macro is running.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0db1-178"><strong>CloseWindow</strong></span><span class="sxs-lookup"><span data-stu-id="e0db1-178"><strong>CloseWindow</strong></span></span></p></td>
<td><p><span data-ttu-id="e0db1-179"><strong>对象类型</strong>: <strong>FormObject 名称</strong>: 产品列表是否<strong>保存</strong>:<strong>否</strong></span><span class="sxs-lookup"><span data-stu-id="e0db1-179"><strong>Object Type</strong>: <strong>FormObject Name</strong>: Product List <strong>Save</strong>: <strong>No</strong></span></span></p></td>
<td><p><span data-ttu-id="e0db1-180">关闭 "产品列表" 表单。</span><span class="sxs-lookup"><span data-stu-id="e0db1-180">Close the Product List form.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0db1-181"><strong>OpenForm</strong></span><span class="sxs-lookup"><span data-stu-id="e0db1-181"><strong>OpenForm</strong></span></span></p></td>
<td><p><span data-ttu-id="e0db1-182"><strong>表单名称</strong>: 产品<strong>视图</strong>: <strong>FormData 模式</strong>: <strong>AddWindow 模式</strong>: <strong>Normal</strong></span><span class="sxs-lookup"><span data-stu-id="e0db1-182"><strong>Form Name</strong>: Products <strong>View</strong>: <strong>FormData Mode</strong>: <strong>AddWindow Mode</strong>: <strong>Normal</strong></span></span></p></td>
<td><p><span data-ttu-id="e0db1-183">打开 "产品" 窗体。</span><span class="sxs-lookup"><span data-stu-id="e0db1-183">Open the Products form.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0db1-184"><strong>SetValue</strong></span><span class="sxs-lookup"><span data-stu-id="e0db1-184"><strong>SetValue</strong></span></span></p></td>
<td><p><span data-ttu-id="e0db1-185"><strong>项</strong>: [Forms]![Products]!id<strong>表达式</strong>: 供应商 id</span><span class="sxs-lookup"><span data-stu-id="e0db1-185"><strong>Item</strong>: [Forms]![Products]![SupplierID] <strong>Expression</strong>: SupplierID</span></span></p></td>
<td><p><span data-ttu-id="e0db1-186">将 "供应商 ID" 控件设置为 "供应商" 窗体上的当前供应商。</span><span class="sxs-lookup"><span data-stu-id="e0db1-186">Set the Supplier ID control to the current supplier on the Suppliers form.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0db1-187"><strong>GoToControl</strong></span><span class="sxs-lookup"><span data-stu-id="e0db1-187"><strong>GoToControl</strong></span></span></p></td>
<td><p><span data-ttu-id="e0db1-188"><strong>控件名称</strong>: 类别 id</span><span class="sxs-lookup"><span data-stu-id="e0db1-188"><strong>Control Name</strong>: CategoryID</span></span></p></td>
<td><p><span data-ttu-id="e0db1-189">转到 "类别 ID" 控件。</span><span class="sxs-lookup"><span data-stu-id="e0db1-189">Go to the Category ID control.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e0db1-190">以下宏将打开 "供应商" 窗体右下角的 "产品列表" 窗体, 显示当前供应商的产品。</span><span class="sxs-lookup"><span data-stu-id="e0db1-190">The following macro opens a Product List form in the lower-right corner of the Suppliers form, displaying the current supplier's products.</span></span> <span data-ttu-id="e0db1-191">它演示了如何使用**Echo**、 **MessageBox**、 **GoToControl**、 **StopMacro**、 **OpenForm**和**MoveAndSizeWindow**操作。</span><span class="sxs-lookup"><span data-stu-id="e0db1-191">It shows the use of the **Echo**, **MessageBox**, **GoToControl**, **StopMacro**, **OpenForm**, and **MoveAndSizeWindow** actions.</span></span> <span data-ttu-id="e0db1-192">它还演示了如何使用带有**MessageBox**、 **GoToControl**和**StopMacro**操作的条件表达式。</span><span class="sxs-lookup"><span data-stu-id="e0db1-192">It also shows the use of a conditional expression with the **MessageBox**, **GoToControl**, and **StopMacro** actions.</span></span> <span data-ttu-id="e0db1-193">此宏应附加到 "供应商" 窗体上的 "查看产品" 按钮。</span><span class="sxs-lookup"><span data-stu-id="e0db1-193">This macro should be attached to the Review Products button on the Suppliers form.</span></span>

<span data-ttu-id="e0db1-194">**使用宏同步窗体**</span><span class="sxs-lookup"><span data-stu-id="e0db1-194">**Synchronize forms by using a macro**</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="e0db1-195">条件</span><span class="sxs-lookup"><span data-stu-id="e0db1-195">Condition</span></span></p></th>
<th><p><span data-ttu-id="e0db1-196">操作</span><span class="sxs-lookup"><span data-stu-id="e0db1-196">Action</span></span></p></th>
<th><p><span data-ttu-id="e0db1-197">参数：设置</span><span class="sxs-lookup"><span data-stu-id="e0db1-197">Arguments: Setting</span></span></p></th>
<th><p><span data-ttu-id="e0db1-198">Comment</span><span class="sxs-lookup"><span data-stu-id="e0db1-198">Comment</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p></p></td>
<td><p><span data-ttu-id="e0db1-199"><strong>Echo</strong></span><span class="sxs-lookup"><span data-stu-id="e0db1-199"><strong>Echo</strong></span></span></p></td>
<td><p><span data-ttu-id="e0db1-200"><strong>打开回响</strong>:<strong>否</strong></span><span class="sxs-lookup"><span data-stu-id="e0db1-200"><strong>Echo On</strong>: <strong>No</strong></span></span></p></td>
<td><p><span data-ttu-id="e0db1-201">在宏运行时停止屏幕更新。</span><span class="sxs-lookup"><span data-stu-id="e0db1-201">Stop screen updating while the macro is running.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0db1-202">IsNull ([供应商 id])</span><span class="sxs-lookup"><span data-stu-id="e0db1-202">IsNull([SupplierID])</span></span></p></td>
<td><p><span data-ttu-id="e0db1-203"><strong>MessageBox</strong></span><span class="sxs-lookup"><span data-stu-id="e0db1-203"><strong>MessageBox</strong></span></span></p></td>
<td><p><span data-ttu-id="e0db1-204"><strong>消息</strong>: 移动到要查看其产品的供应商记录, 然后再次单击 "查看产品" 按钮。</span><span class="sxs-lookup"><span data-stu-id="e0db1-204"><strong>Message</strong>: Move to the supplier record whose products you want to see, then click the Review Products button again.</span></span> <span data-ttu-id="e0db1-205"><strong>嘟嘟声</strong>: <strong>YesType</strong>: <strong>NoneTitle</strong>: 选择供应商</span><span class="sxs-lookup"><span data-stu-id="e0db1-205"><strong>Beep</strong>: <strong>YesType</strong>: <strong>NoneTitle</strong>: Select a Supplier</span></span></p></td>
<td><p><span data-ttu-id="e0db1-206">如果 "供应商" 窗体上没有当前供应商, 则显示一条消息。</span><span class="sxs-lookup"><span data-stu-id="e0db1-206">If there is no current supplier on the Suppliers form, display a message.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0db1-207">...</span><span class="sxs-lookup"><span data-stu-id="e0db1-207"></span></span></p></td>
<td><p><span data-ttu-id="e0db1-208"><strong>GoToControl</strong></span><span class="sxs-lookup"><span data-stu-id="e0db1-208"><strong>GoToControl</strong></span></span></p></td>
<td><p><span data-ttu-id="e0db1-209"><strong>控件名称</strong>: 公司名称</span><span class="sxs-lookup"><span data-stu-id="e0db1-209"><strong>Control Name</strong>: CompanyName</span></span></p></td>
<td><p><span data-ttu-id="e0db1-210">将焦点移到 "公司名称" 控件。</span><span class="sxs-lookup"><span data-stu-id="e0db1-210">Move focus to the CompanyName control.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0db1-211">...</span><span class="sxs-lookup"><span data-stu-id="e0db1-211"></span></span></p></td>
<td><p><span data-ttu-id="e0db1-212"><strong>StopMacro</strong></span><span class="sxs-lookup"><span data-stu-id="e0db1-212"><strong>StopMacro</strong></span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="e0db1-213">停止宏。</span><span class="sxs-lookup"><span data-stu-id="e0db1-213">Stop the macro.</span></span></p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p><span data-ttu-id="e0db1-214"><strong>OpenForm</strong></span><span class="sxs-lookup"><span data-stu-id="e0db1-214"><strong>OpenForm</strong></span></span></p></td>
<td><p><span data-ttu-id="e0db1-215"><strong>表单名称</strong>: 产品列表<strong>视图</strong>: <strong>DatasheetFilter Name</strong>: <strong>Where 条件</strong>: [供应商 id] = [Forms]![供应商]!id<strong>数据模式</strong>:<strong>读取 OnlyWindow 模式</strong>:<strong>普通</strong></span><span class="sxs-lookup"><span data-stu-id="e0db1-215"><strong>Form Name</strong>: Product List <strong>View</strong>: <strong>DatasheetFilter Name</strong>: <strong>Where Condition</strong>: [SupplierID] = [Forms]![Suppliers]![SupplierID] <strong>Data Mode</strong>: <strong>Read OnlyWindow Mode</strong>: <strong>Normal</strong></span></span></p></td>
<td><p><span data-ttu-id="e0db1-216">打开 "产品列表" 表单并显示当前供应商的产品。</span><span class="sxs-lookup"><span data-stu-id="e0db1-216">Open the Product List form and show the current supplier's products.</span></span></p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p><span data-ttu-id="e0db1-217"><strong>MoveAndSizeWindow</strong></span><span class="sxs-lookup"><span data-stu-id="e0db1-217"><strong>MoveAndSizeWindow</strong></span></span></p></td>
<td><p><span data-ttu-id="e0db1-218"><strong>右侧</strong>: 0.7799&quot; <strong></strong>: 1。8&quot;</span><span class="sxs-lookup"><span data-stu-id="e0db1-218"><strong>Right</strong>: 0.7799&quot; <strong>Down</strong>: 1.8&quot;</span></span></p></td>
<td><p><span data-ttu-id="e0db1-219">将 "产品列表" 窗体放置在 "供应商" 窗体的右下角。</span><span class="sxs-lookup"><span data-stu-id="e0db1-219">Position the Product List form in the lower right of the Suppliers form.</span></span></p></td>
</tr>
</tbody>
</table>

