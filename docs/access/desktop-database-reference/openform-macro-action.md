---
title: OpenForm Macro Action
TOCTitle: OpenForm Macro Action
ms:assetid: c519a9d7-99d4-4765-ad96-59c3fe1be9e3
ms:mtpsurl: https://msdn.microsoft.com/library/Ff823095(v=office.15)
ms:contentKeyID: 48547604
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: ba0314fff63014b36565b178f97950660ffec14f
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468545"
---
# <a name="openform-macro-action"></a><span data-ttu-id="abac9-102">OpenForm Macro Action</span><span class="sxs-lookup"><span data-stu-id="abac9-102">OpenForm Macro Action</span></span>


<span data-ttu-id="abac9-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="abac9-103">**Applies to**: Access 2013 | Office 2013</span></span>


<span data-ttu-id="abac9-104">您可以使用**OpenForm**操作窗体视图、 设计视图、 打印预览或数据表视图中打开窗体。</span><span class="sxs-lookup"><span data-stu-id="abac9-104">You can use the **OpenForm** action to open a form in Form view, Design view, Print Preview, or Datasheet view.</span></span> <span data-ttu-id="abac9-105">可以选择窗体的数据输入模式和窗口模式，并限制窗体显示的记录。</span><span class="sxs-lookup"><span data-stu-id="abac9-105">You can select data entry and window modes for the form and restrict the records that the form displays.</span></span>

## <a name="setting"></a><span data-ttu-id="abac9-106">设置</span><span class="sxs-lookup"><span data-stu-id="abac9-106">Setting</span></span>

<span data-ttu-id="abac9-107">**OpenForm**操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="abac9-107">The **OpenForm** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="abac9-108">操作参数</span><span class="sxs-lookup"><span data-stu-id="abac9-108">Action argument</span></span></p></th>
<th><p><span data-ttu-id="abac9-109">说明</span><span class="sxs-lookup"><span data-stu-id="abac9-109">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="abac9-110"><strong>表单名称</strong></span><span class="sxs-lookup"><span data-stu-id="abac9-110"><strong>Form Name</strong></span></span></p></td>
<td><p><span data-ttu-id="abac9-111">要打开的窗体名称。</span><span class="sxs-lookup"><span data-stu-id="abac9-111">The name of the form to open.</span></span> <span data-ttu-id="abac9-112">宏生成器窗格的<strong>窗体名称</strong>框在<strong>操作参数</strong>部分中显示当前数据库中的所有窗体。</span><span class="sxs-lookup"><span data-stu-id="abac9-112">The <strong>Form Name</strong> box in the <strong>Action Arguments</strong> section of the Macro Builder pane shows all forms in the current database.</span></span> <span data-ttu-id="abac9-113">这是必需参数。</span><span class="sxs-lookup"><span data-stu-id="abac9-113">This is a required argument.</span></span> <span data-ttu-id="abac9-114">如果您运行包含类库数据库中的<strong>OpenForm</strong>操作的宏，Microsoft Access 首先查找具有此名称在类库数据库，然后在当前数据库的窗体。</span><span class="sxs-lookup"><span data-stu-id="abac9-114">If you run a macro containing the <strong>OpenForm</strong> action in a library database, Microsoft Access first looks for the form with this name in the library database, and then in the current database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abac9-115"><strong>View</strong></span><span class="sxs-lookup"><span data-stu-id="abac9-115"><strong>View</strong></span></span></p></td>
<td><p><span data-ttu-id="abac9-116">将在其中打开窗体视图。</span><span class="sxs-lookup"><span data-stu-id="abac9-116">The view in which the form will open.</span></span> <span data-ttu-id="abac9-117">单击<strong>窗体</strong>、<strong>设计</strong>、<strong>打印预览</strong>、<strong>数据表</strong>、<strong>数据透视表</strong>，或<strong>数据透视图</strong><strong>视图</strong>框中。</span><span class="sxs-lookup"><span data-stu-id="abac9-117">Click <strong>Form</strong>, <strong>Design</strong>, <strong>Print Preview</strong>, <strong>Datasheet</strong>, <strong>PivotTable</strong>, or <strong>PivotChart</strong> in the <strong>View</strong> box.</span></span> <span data-ttu-id="abac9-118">默认值为<strong>窗体</strong>。</span><span class="sxs-lookup"><span data-stu-id="abac9-118">The default is <strong>Form</strong>.</span></span></p>

> [!NOTE]
> <P><span data-ttu-id="abac9-119"><STRONG>视图</STRONG>参数设置将覆盖窗体的<STRONG>默认视图</STRONG>和<STRONG>ViewsAllowed</STRONG>属性的设置。</span><span class="sxs-lookup"><span data-stu-id="abac9-119">The <STRONG>View</STRONG> argument setting overrides the settings of the form's <STRONG>DefaultView</STRONG> and <STRONG>ViewsAllowed</STRONG> properties.</span></span> <span data-ttu-id="abac9-120">例如，如果窗体<STRONG>ViewsAllowed</STRONG>属性设置为<STRONG>数据表</STRONG>，您可以仍使用<STRONG>OpenForm</STRONG>操作在窗体视图中打开窗体。</span><span class="sxs-lookup"><span data-stu-id="abac9-120">For example, if a form's <STRONG>ViewsAllowed</STRONG> property is set to <STRONG>Datasheet</STRONG>, you can still use the <STRONG>OpenForm</STRONG> action to open the form in Form view.</span></span></P>


<p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abac9-121"><strong>Filter Name</strong></span><span class="sxs-lookup"><span data-stu-id="abac9-121"><strong>Filter Name</strong></span></span></p></td>
<td><p><span data-ttu-id="abac9-122">筛选器的限制或排序窗体的记录。</span><span class="sxs-lookup"><span data-stu-id="abac9-122">A filter that restricts or sorts the form's records.</span></span> <span data-ttu-id="abac9-123">您可以输入现有查询或筛选器已保存为查询的名称。</span><span class="sxs-lookup"><span data-stu-id="abac9-123">You can enter the name of either an existing query or a filter that was saved as a query.</span></span> <span data-ttu-id="abac9-124">但是，查询必须包含要打开的窗体中的所有字段，或将它<strong>OutputAllFields</strong>属性设置为<strong>是</strong>。</span><span class="sxs-lookup"><span data-stu-id="abac9-124">However, the query must include all the fields in the form you are opening or have its <strong>OutputAllFields</strong> property set to <strong>Yes</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abac9-125"><strong>Where Condition</strong></span><span class="sxs-lookup"><span data-stu-id="abac9-125"><strong>Where Condition</strong></span></span></p></td>
<td><p><span data-ttu-id="abac9-126">关键字的有效 SQL WHERE 子句 (不带有单词其中) 或 Access 使用记录选择的窗体中的表达式的基础表或查询。</span><span class="sxs-lookup"><span data-stu-id="abac9-126">A valid SQL WHERE clause (without the word WHERE) or expression that Access uses to select records from the form's underlying table or query.</span></span> <span data-ttu-id="abac9-127">如果选择<strong>筛选器名称</strong>参数的筛选器，Access 会将此 WHERE 子句于筛选结果。</span><span class="sxs-lookup"><span data-stu-id="abac9-127">If you select a filter with the <strong>Filter Name</strong> argument, Access applies this WHERE clause to the results of the filter.</span></span> <span data-ttu-id="abac9-128">打开窗体，并将其记录限制为所指定的另一个窗体上控件的值，请使用以下表达式： <strong>[</strong><em>fieldname</em><strong>] = 的表单 ！ [</strong><em>formname</em><strong>]![</strong><em>其他窗体上的控件名称</em><strong>]</strong> <em>fieldname</em>替换为基础表或查询的要打开的窗体中的字段的名称。</span><span class="sxs-lookup"><span data-stu-id="abac9-128">To open a form and restrict its records to those specified by the value of a control on another form, use the following expression: <strong>[</strong><em>fieldname</em><strong>] = Forms![</strong><em>formname</em><strong>]![</strong><em>controlname on other form</em><strong>]</strong> Replace <em>fieldname</em> with the name of a field in the underlying table or query of the form you want to open.</span></span> <span data-ttu-id="abac9-129"><em>Formname</em>和<em>其他窗体上的控件名称</em>替换为其他表单和包含所需中第一个窗体中，以匹配的记录的值的其他窗体上的控件的名称。</span><span class="sxs-lookup"><span data-stu-id="abac9-129">Replace <em>formname</em> and <em>controlname on other form</em> with the name of the other form and the control on the other form that contains the value you want records in the first form to match.</span></span></p>

> [!NOTE]
> <P><span data-ttu-id="abac9-130"><STRONG>Where 条件</STRONG>参数的最大长度为 255 个字符。</span><span class="sxs-lookup"><span data-stu-id="abac9-130">The maximum length of the <STRONG>Where Condition</STRONG> argument is 255 characters.</span></span> <span data-ttu-id="abac9-131">如果您需要输入一个更复杂 SQL WHERE 子句多于此，请改用<STRONG>DoCmd</STRONG>对象的<STRONG>OpenForm</STRONG>方法在 Visual Basic for Applications (VBA) 模块。</span><span class="sxs-lookup"><span data-stu-id="abac9-131">If you need to enter a more complex SQL WHERE clause longer than this, use the <STRONG>OpenForm</STRONG> method of the <STRONG>DoCmd</STRONG> object in a Visual Basic for Applications (VBA) module instead.</span></span> <span data-ttu-id="abac9-132">您可以在 VBA 中输入 SQL WHERE 子句语句的最多为 32,768 个字符。</span><span class="sxs-lookup"><span data-stu-id="abac9-132">You can enter SQL WHERE clause statements of up to 32,768 characters in VBA.</span></span></P>


<p></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abac9-133"><strong>Data Mode</strong></span><span class="sxs-lookup"><span data-stu-id="abac9-133"><strong>Data Mode</strong></span></span></p></td>
<td><p><span data-ttu-id="abac9-134">窗体的数据输入模式。</span><span class="sxs-lookup"><span data-stu-id="abac9-134">The data entry mode for the form.</span></span> <span data-ttu-id="abac9-135">这仅适用于在窗体视图或数据表视图中打开的窗体。</span><span class="sxs-lookup"><span data-stu-id="abac9-135">This applies only to forms opened in Form view or Datasheet view.</span></span> <span data-ttu-id="abac9-136">单击<strong>添加</strong>（用户可以添加新记录，但不能编辑现有记录），<strong>编辑</strong>（用户可以编辑现有记录，并可以添加新记录） 或<strong>只读</strong>（用户只能查看记录）。</span><span class="sxs-lookup"><span data-stu-id="abac9-136">Click <strong>Add</strong> (the user can add new records but can't edit existing records), <strong>Edit</strong> (the user can edit existing records and add new records), or <strong>Read Only</strong> (the user can only view records).</span></span> <span data-ttu-id="abac9-137">默认值为<strong>编辑</strong>。</span><span class="sxs-lookup"><span data-stu-id="abac9-137">The default is <strong>Edit</strong>.</span></span> <span data-ttu-id="abac9-138"><strong>备注</strong></span><span class="sxs-lookup"><span data-stu-id="abac9-138"><strong>Notes</strong></span></span></p>
<ul>
<li><p><span data-ttu-id="abac9-139"><strong>数据模式</strong>参数设置将覆盖窗体的<strong>AllowEdits</strong>、 <strong>AllowDeletions</strong>、 <strong>AllowAdditions</strong>和<strong>DataEntry</strong>属性的设置。</span><span class="sxs-lookup"><span data-stu-id="abac9-139">The <strong>Data Mode</strong> argument setting overrides the settings of the form's <strong>AllowEdits</strong>, <strong>AllowDeletions</strong>, <strong>AllowAdditions</strong>, and <strong>DataEntry</strong> properties.</span></span> <span data-ttu-id="abac9-140">例如，如果窗体的<strong>AllowEdits</strong>属性设置为<strong>No</strong>，您可以仍使用<strong>OpenForm</strong>操作在编辑模式中打开窗体。</span><span class="sxs-lookup"><span data-stu-id="abac9-140">For example, if a form's <strong>AllowEdits</strong> property is set to <strong>No</strong>, you can still use the <strong>OpenForm</strong> action to open the form in Edit mode.</span></span></p></li>
<li><p><span data-ttu-id="abac9-141">如果将此参数留空，Access 将窗体的<strong>AllowEdits</strong>、 <strong>AllowDeletions</strong>、 <strong>AllowAdditions</strong>和<strong>DataEntry</strong>属性设置的数据输入模式中打开窗体。</span><span class="sxs-lookup"><span data-stu-id="abac9-141">If you leave this argument blank, Access opens the form in the data entry mode set by the form's <strong>AllowEdits</strong>, <strong>AllowDeletions</strong>, <strong>AllowAdditions</strong>, and <strong>DataEntry</strong> properties.</span></span></p></li>
</ul>
<p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abac9-142"><strong>窗口模式</strong></span><span class="sxs-lookup"><span data-stu-id="abac9-142"><strong>Window Mode</strong></span></span></p></td>
<td><p><span data-ttu-id="abac9-143">打开窗体窗口模式。</span><span class="sxs-lookup"><span data-stu-id="abac9-143">The window mode in which the form opens.</span></span> <span data-ttu-id="abac9-144">依次单击<strong>普通</strong>（由其属性设置模式中打开窗体）、<strong>隐藏</strong>（隐藏窗体）、<strong>图标</strong>（窗体打开最小化为小型的标题栏中，在屏幕底部），或<strong>对话框</strong>（窗体的<strong>模式</strong>和<strong>弹出窗口</strong>属性设置为<strong>是</strong>)。</span><span class="sxs-lookup"><span data-stu-id="abac9-144">Click <strong>Normal</strong> (the form opens in the mode set by its properties), <strong>Hidden</strong> (the form is hidden), <strong>Icon</strong> (the form opens minimized as a small title bar at the bottom of the screen), or <strong>Dialog</strong> (the form's <strong>Modal</strong> and <strong>PopUp</strong> properties are set to <strong>Yes</strong>).</span></span> <span data-ttu-id="abac9-145">默认值为<strong>Normal</strong>。</span><span class="sxs-lookup"><span data-stu-id="abac9-145">The default is <strong>Normal</strong>.</span></span></p>

> [!NOTE]
> <P><span data-ttu-id="abac9-146">有些<STRONG>窗口模式</STRONG>参数设置不适用于使用选项卡式的文档时。</span><span class="sxs-lookup"><span data-stu-id="abac9-146">Some <STRONG>Window Mode</STRONG> argument settings do not apply when using tabbed documents.</span></span> <span data-ttu-id="abac9-147">若要切换到重叠窗口：</span><span class="sxs-lookup"><span data-stu-id="abac9-147">To switch to overlapping windows:</span></span></P>


<p></p>
<ol>
<li><p><span data-ttu-id="abac9-148">单击文件选项卡，然后单击<strong>选项</strong>。</span><span class="sxs-lookup"><span data-stu-id="abac9-148">Click the File tab and then click <strong>Options</strong>.</span></span></p></li>
<li><p><span data-ttu-id="abac9-149">在<strong>“Access 选项”</strong>对话框中，单击<strong>“当前数据库”</strong>。</span><span class="sxs-lookup"><span data-stu-id="abac9-149">In the <strong>Access Options</strong> dialog box, click <strong>Current Database</strong>.</span></span></p></li>
<li><p><span data-ttu-id="abac9-150">在<strong>应用程序选项</strong>部分中，<strong>文档窗口选项</strong>下单击<strong>重叠窗口</strong>。</span><span class="sxs-lookup"><span data-stu-id="abac9-150">In the <strong>Application Options</strong>section, under <strong>Document Window Options</strong>, click <strong>Overlapping Windows</strong>.</span></span></p></li>
<li><p><span data-ttu-id="abac9-151">单击<strong>“确定”</strong>，然后关闭并重新打开数据库。</span><span class="sxs-lookup"><span data-stu-id="abac9-151">Click <strong>OK</strong>, then close and reopen the database.</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="abac9-152">说明</span><span class="sxs-lookup"><span data-stu-id="abac9-152">Remarks</span></span>

<span data-ttu-id="abac9-153">此操作类似于双击在导航窗格中，窗体或右键单击导航窗格中的窗体，然后选择视图。</span><span class="sxs-lookup"><span data-stu-id="abac9-153">This action is similar to double-clicking a form in the Navigation Pane, or right-clicking the form in the Navigation Pane and then selecting a view.</span></span>

<span data-ttu-id="abac9-154">窗体可以是的模式 （它必须关闭或隐藏然后用户可以执行任何其他操作） 或无模式 （用户可以在窗体打开时移动到其他 windows 中）。</span><span class="sxs-lookup"><span data-stu-id="abac9-154">A form can be modal (it must be closed or hidden before the user can perform any other action) or modeless (the user can move to other windows while the form is open).</span></span> <span data-ttu-id="abac9-155">也可以是弹出式窗体 （用于收集或显示信息的所有其他访问窗体之上的窗体）。</span><span class="sxs-lookup"><span data-stu-id="abac9-155">It can also be a pop-up form (a form used to collect or display information that remains on top of all other Access windows).</span></span> <span data-ttu-id="abac9-156">设计表单时，您可以设置的**Modal**和**PopUp**属性。</span><span class="sxs-lookup"><span data-stu-id="abac9-156">You set the **Modal** and **PopUp** properties when you design the form.</span></span> <span data-ttu-id="abac9-157">如果您使用**普通\*\*\*\*窗口模式**参数，通过这些属性设置指定的模式中打开窗体。</span><span class="sxs-lookup"><span data-stu-id="abac9-157">If you use **Normal** for the **Window Mode** argument, the form opens in the mode specified by these property settings.</span></span> <span data-ttu-id="abac9-158">如果您使用**窗口模式**参数**对话框**，这些属性都设置为**是**。</span><span class="sxs-lookup"><span data-stu-id="abac9-158">If you use **Dialog** for the **Window Mode** argument, these properties are both set to **Yes**.</span></span> <span data-ttu-id="abac9-159">打开作为隐藏或图标的窗体返回到显示或将其还原时，其属性设置所指定的模式。</span><span class="sxs-lookup"><span data-stu-id="abac9-159">A form opened as hidden or as an icon returns to the mode specified by its property settings when you show or restore it.</span></span>

<span data-ttu-id="abac9-160">当您打开窗体**窗口模式**参数设置为**对话框**时，Access 将挂起宏，直到窗体被关闭或隐藏。</span><span class="sxs-lookup"><span data-stu-id="abac9-160">When you open a form with the **Window Mode** argument set to **Dialog**, Access suspends the macro until the form is closed or hidden.</span></span> <span data-ttu-id="abac9-161">您可以通过使用**SetValue**操作将其**Visible**属性设置为**否**隐藏窗体。</span><span class="sxs-lookup"><span data-stu-id="abac9-161">You can hide a form by setting its **Visible** property to **No** by using the **SetValue** action.</span></span>


> [!TIP]
> <P><span data-ttu-id="abac9-162">您可以在导航窗格中选择一个窗体，并将它拖到宏操作行。</span><span class="sxs-lookup"><span data-stu-id="abac9-162">You can select a form in the Navigation Pane and drag it to a macro action row.</span></span> <span data-ttu-id="abac9-163">这会自动创建窗体视图中打开该窗体<STRONG>OpenForm</STRONG>操作。</span><span class="sxs-lookup"><span data-stu-id="abac9-163">This automatically creates an <STRONG>OpenForm</STRONG> action that opens the form in Form view.</span></span></P>



<span data-ttu-id="abac9-164">筛选和 WHERE 条件将成为窗体的**Filter**属性的设置。</span><span class="sxs-lookup"><span data-stu-id="abac9-164">The filter and WHERE condition you apply become the setting of the form's **Filter** property.</span></span>

## <a name="examples"></a><span data-ttu-id="abac9-165">示例</span><span class="sxs-lookup"><span data-stu-id="abac9-165">Examples</span></span>

<span data-ttu-id="abac9-166">**通过使用宏设置控件的值**</span><span class="sxs-lookup"><span data-stu-id="abac9-166">**Set the value of a control by using a macro**</span></span>

<span data-ttu-id="abac9-167">下面的宏 Suppliers 窗体上的按钮打开添加产品窗体。</span><span class="sxs-lookup"><span data-stu-id="abac9-167">The following macro opens the Add Products form from a button on the Suppliers form.</span></span> <span data-ttu-id="abac9-168">它演示如何使用**回声**、 **CloseWindow**、 **OpenForm**、 **SetValue**和**GoToControl**操作。</span><span class="sxs-lookup"><span data-stu-id="abac9-168">It shows the use of the **Echo**, **CloseWindow**, **OpenForm**, **SetValue**, and **GoToControl** actions.</span></span> <span data-ttu-id="abac9-169">**SetValue**操作供应商窗体上将产品窗体上的供应商 ID 控件设置为当前供应商。</span><span class="sxs-lookup"><span data-stu-id="abac9-169">The **SetValue** action sets the Supplier ID control on the Products form to the current supplier on the Suppliers form.</span></span> <span data-ttu-id="abac9-170">然后， **GoToControl**操作将焦点移到类别 ID 字段中，您可以开始新产品的输入数据。</span><span class="sxs-lookup"><span data-stu-id="abac9-170">The **GoToControl** action then moves the focus to the Category ID field, where you can begin to enter data for the new product.</span></span> <span data-ttu-id="abac9-171">这个宏应附加到 Suppliers 窗体上的添加产品按钮。</span><span class="sxs-lookup"><span data-stu-id="abac9-171">This macro should be attached to the Add Products button on the Suppliers form.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="abac9-172">操作</span><span class="sxs-lookup"><span data-stu-id="abac9-172">Action</span></span></p></th>
<th><p><span data-ttu-id="abac9-173">参数：设置</span><span class="sxs-lookup"><span data-stu-id="abac9-173">Arguments: Setting</span></span></p></th>
<th><p><span data-ttu-id="abac9-174">注释</span><span class="sxs-lookup"><span data-stu-id="abac9-174">Comment</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="abac9-175"><strong>Echo</strong></span><span class="sxs-lookup"><span data-stu-id="abac9-175"><strong>Echo</strong></span></span></p></td>
<td><p><span data-ttu-id="abac9-176"><strong>打开回响</strong>：<strong>否</strong></span><span class="sxs-lookup"><span data-stu-id="abac9-176"><strong>Echo On</strong>: <strong>No</strong></span></span></p></td>
<td><p><span data-ttu-id="abac9-177">停止屏幕更新时运行宏。</span><span class="sxs-lookup"><span data-stu-id="abac9-177">Stop screen updating while the macro is running.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abac9-178"><strong>CloseWindow</strong></span><span class="sxs-lookup"><span data-stu-id="abac9-178"><strong>CloseWindow</strong></span></span></p></td>
<td><p><span data-ttu-id="abac9-179"><strong>对象类型</strong>： <strong>FormObject 名称</strong>： 产品列表<strong>保存</strong>：<strong>否</strong></span><span class="sxs-lookup"><span data-stu-id="abac9-179"><strong>Object Type</strong>: <strong>FormObject Name</strong>: Product List <strong>Save</strong>: <strong>No</strong></span></span></p></td>
<td><p><span data-ttu-id="abac9-180">关闭产品列表窗体。</span><span class="sxs-lookup"><span data-stu-id="abac9-180">Close the Product List form.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abac9-181"><strong>OpenForm</strong></span><span class="sxs-lookup"><span data-stu-id="abac9-181"><strong>OpenForm</strong></span></span></p></td>
<td><p><span data-ttu-id="abac9-182"><strong>窗体名称</strong>： 产品<strong>视图</strong>： <strong>FormData 模式</strong>： <strong>AddWindow 模式</strong>：<strong>普通</strong></span><span class="sxs-lookup"><span data-stu-id="abac9-182"><strong>Form Name</strong>: Products <strong>View</strong>: <strong>FormData Mode</strong>: <strong>AddWindow Mode</strong>: <strong>Normal</strong></span></span></p></td>
<td><p><span data-ttu-id="abac9-183">打开产品窗体。</span><span class="sxs-lookup"><span data-stu-id="abac9-183">Open the Products form.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abac9-184"><strong>SetValue</strong></span><span class="sxs-lookup"><span data-stu-id="abac9-184"><strong>SetValue</strong></span></span></p></td>
<td><p><span data-ttu-id="abac9-185"><strong>项目</strong>: [窗体] ！[产品] ！[SupplierID]<strong>表达式</strong>： 供应商 Id</span><span class="sxs-lookup"><span data-stu-id="abac9-185"><strong>Item</strong>: [Forms]![Products]![SupplierID] <strong>Expression</strong>: SupplierID</span></span></p></td>
<td><p><span data-ttu-id="abac9-186">在 Suppliers 窗体上将供应商 ID 控件设置为当前供应商。</span><span class="sxs-lookup"><span data-stu-id="abac9-186">Set the Supplier ID control to the current supplier on the Suppliers form.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abac9-187"><strong>GoToControl</strong></span><span class="sxs-lookup"><span data-stu-id="abac9-187"><strong>GoToControl</strong></span></span></p></td>
<td><p><span data-ttu-id="abac9-188"><strong>控件名称</strong>： CategoryID</span><span class="sxs-lookup"><span data-stu-id="abac9-188"><strong>Control Name</strong>: CategoryID</span></span></p></td>
<td><p><span data-ttu-id="abac9-189">转到类别 ID 控件。</span><span class="sxs-lookup"><span data-stu-id="abac9-189">Go to the Category ID control.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="abac9-190">下面的宏将在显示当前供应商的产品 Suppliers 窗体的右下角中打开产品列表窗体。</span><span class="sxs-lookup"><span data-stu-id="abac9-190">The following macro opens a Product List form in the lower-right corner of the Suppliers form, displaying the current supplier's products.</span></span> <span data-ttu-id="abac9-191">它演示如何使用**回声**、 **MessageBox**、 **GoToControl**、 **StopMacro**、 **OpenForm**，和**MoveAndSizeWindow**操作。</span><span class="sxs-lookup"><span data-stu-id="abac9-191">It shows the use of the **Echo**, **MessageBox**, **GoToControl**, **StopMacro**, **OpenForm**, and **MoveAndSizeWindow** actions.</span></span> <span data-ttu-id="abac9-192">它还会显示具有**MessageBox**、 **GoToControl**和**StopMacro**操作的条件表达式使用。</span><span class="sxs-lookup"><span data-stu-id="abac9-192">It also shows the use of a conditional expression with the **MessageBox**, **GoToControl**, and **StopMacro** actions.</span></span> <span data-ttu-id="abac9-193">这个宏应附加到 Suppliers 窗体上的查看产品按钮。</span><span class="sxs-lookup"><span data-stu-id="abac9-193">This macro should be attached to the Review Products button on the Suppliers form.</span></span>

<span data-ttu-id="abac9-194">**通过使用宏同步处理窗体**</span><span class="sxs-lookup"><span data-stu-id="abac9-194">**Synchronize forms by using a macro**</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="abac9-195">条件</span><span class="sxs-lookup"><span data-stu-id="abac9-195">Condition</span></span></p></th>
<th><p><span data-ttu-id="abac9-196">操作</span><span class="sxs-lookup"><span data-stu-id="abac9-196">Action</span></span></p></th>
<th><p><span data-ttu-id="abac9-197">参数：设置</span><span class="sxs-lookup"><span data-stu-id="abac9-197">Arguments: Setting</span></span></p></th>
<th><p><span data-ttu-id="abac9-198">注释</span><span class="sxs-lookup"><span data-stu-id="abac9-198">Comment</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p></p></td>
<td><p><span data-ttu-id="abac9-199"><strong>Echo</strong></span><span class="sxs-lookup"><span data-stu-id="abac9-199"><strong>Echo</strong></span></span></p></td>
<td><p><span data-ttu-id="abac9-200"><strong>打开回响</strong>：<strong>否</strong></span><span class="sxs-lookup"><span data-stu-id="abac9-200"><strong>Echo On</strong>: <strong>No</strong></span></span></p></td>
<td><p><span data-ttu-id="abac9-201">停止屏幕更新时运行宏。</span><span class="sxs-lookup"><span data-stu-id="abac9-201">Stop screen updating while the macro is running.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abac9-202">IsNull([SupplierID])</span><span class="sxs-lookup"><span data-stu-id="abac9-202">IsNull([SupplierID])</span></span></p></td>
<td><p><span data-ttu-id="abac9-203"><strong>MessageBox</strong></span><span class="sxs-lookup"><span data-stu-id="abac9-203"><strong>MessageBox</strong></span></span></p></td>
<td><p><span data-ttu-id="abac9-204"><strong>消息</strong>： 移动到您要查看其的产品然后再次单击查看产品按钮的供应商记录。</span><span class="sxs-lookup"><span data-stu-id="abac9-204"><strong>Message</strong>: Move to the supplier record whose products you want to see, then click the Review Products button again.</span></span> <span data-ttu-id="abac9-205"><strong>发嘟嘟声</strong>： <strong>YesType</strong>: <strong>NoneTitle</strong>： 选择一个供应商</span><span class="sxs-lookup"><span data-stu-id="abac9-205"><strong>Beep</strong>: <strong>YesType</strong>: <strong>NoneTitle</strong>: Select a Supplier</span></span></p></td>
<td><p><span data-ttu-id="abac9-206">如果 Suppliers 窗体上没有当前供应商，显示一条消息。</span><span class="sxs-lookup"><span data-stu-id="abac9-206">If there is no current supplier on the Suppliers form, display a message.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abac9-207">...</span><span class="sxs-lookup"><span data-stu-id="abac9-207"></span></span></p></td>
<td><p><span data-ttu-id="abac9-208"><strong>GoToControl</strong></span><span class="sxs-lookup"><span data-stu-id="abac9-208"><strong>GoToControl</strong></span></span></p></td>
<td><p><span data-ttu-id="abac9-209"><strong>控件名称</strong>： 公司名称</span><span class="sxs-lookup"><span data-stu-id="abac9-209"><strong>Control Name</strong>: CompanyName</span></span></p></td>
<td><p><span data-ttu-id="abac9-210">将焦点移到公司名称控件。</span><span class="sxs-lookup"><span data-stu-id="abac9-210">Move focus to the CompanyName control.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abac9-211">...</span><span class="sxs-lookup"><span data-stu-id="abac9-211"></span></span></p></td>
<td><p><span data-ttu-id="abac9-212"><strong>StopMacro</strong></span><span class="sxs-lookup"><span data-stu-id="abac9-212"><strong>StopMacro</strong></span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="abac9-213">停止宏。</span><span class="sxs-lookup"><span data-stu-id="abac9-213">Stop the macro.</span></span></p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p><span data-ttu-id="abac9-214"><strong>OpenForm</strong></span><span class="sxs-lookup"><span data-stu-id="abac9-214"><strong>OpenForm</strong></span></span></p></td>
<td><p><span data-ttu-id="abac9-215"><strong>窗体名称</strong>： 产品列表<strong>视图</strong>： <strong>DatasheetFilter 名称</strong>： <strong>Where 条件</strong>: [SupplierID] = [窗体] ！[供应商] ！[SupplierID]<strong>数据模式</strong>：<strong>读取 OnlyWindow 模式</strong>：<strong>普通</strong></span><span class="sxs-lookup"><span data-stu-id="abac9-215"><strong>Form Name</strong>: Product List <strong>View</strong>: <strong>DatasheetFilter Name</strong>: <strong>Where Condition</strong>: [SupplierID] = [Forms]![Suppliers]![SupplierID] <strong>Data Mode</strong>: <strong>Read OnlyWindow Mode</strong>: <strong>Normal</strong></span></span></p></td>
<td><p><span data-ttu-id="abac9-216">打开产品列表窗体并显示当前供应商的产品。</span><span class="sxs-lookup"><span data-stu-id="abac9-216">Open the Product List form and show the current supplier's products.</span></span></p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p><span data-ttu-id="abac9-217"><strong>MoveAndSizeWindow</strong></span><span class="sxs-lookup"><span data-stu-id="abac9-217"><strong>MoveAndSizeWindow</strong></span></span></p></td>
<td><p><span data-ttu-id="abac9-218"><strong>右</strong>： 0.7799&quot; <strong>下</strong>： 1.8&quot;</span><span class="sxs-lookup"><span data-stu-id="abac9-218"><strong>Right</strong>: 0.7799&quot; <strong>Down</strong>: 1.8&quot;</span></span></p></td>
<td><p><span data-ttu-id="abac9-219">产品列表表单 Suppliers 窗体的右下角的位置。</span><span class="sxs-lookup"><span data-stu-id="abac9-219">Position the Product List form in the lower right of the Suppliers form.</span></span></p></td>
</tr>
</tbody>
</table>

