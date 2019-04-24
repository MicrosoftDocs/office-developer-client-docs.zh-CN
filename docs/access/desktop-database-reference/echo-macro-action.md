---
title: Echo 宏操作 (Access desktop database reference)
TOCTitle: Echo macro action
ms:assetid: 38dfb2cf-8db5-44b3-91fa-e490932b940b
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192516(v=office.15)
ms:contentKeyID: 48544227
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 7d536ed47c780b7f9f1675a9879e86aeff80b67f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32293621"
---
# <a name="echo-macro-action"></a><span data-ttu-id="dd80c-102">Echo 宏操作</span><span class="sxs-lookup"><span data-stu-id="dd80c-102">Echo macro action</span></span>

<span data-ttu-id="dd80c-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="dd80c-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="dd80c-104">可以使用**echo**操作指定是否打开回响。</span><span class="sxs-lookup"><span data-stu-id="dd80c-104">You can use the **Echo** action to specify whether echo is turned on.</span></span> <span data-ttu-id="dd80c-105">例如, 可以使用此操作在宏运行时隐藏或显示其结果。</span><span class="sxs-lookup"><span data-stu-id="dd80c-105">For example, you can use this action to hide or show the results of a macro while it runs.</span></span>

## <a name="setting"></a><span data-ttu-id="dd80c-106">Setting</span><span class="sxs-lookup"><span data-stu-id="dd80c-106">Setting</span></span>

> [!NOTE]
> <span data-ttu-id="dd80c-107">[!注释] 如果数据库不受信任，将不允许此操作。</span><span class="sxs-lookup"><span data-stu-id="dd80c-107">This action will not be allowed if the database is not trusted.</span></span>

<span data-ttu-id="dd80c-108">**Echo**操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="dd80c-108">The **Echo** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="dd80c-109">操作参数</span><span class="sxs-lookup"><span data-stu-id="dd80c-109">Action argument</span></span></p></th>
<th><p><span data-ttu-id="dd80c-110">说明</span><span class="sxs-lookup"><span data-stu-id="dd80c-110">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dd80c-111"><strong>打开回响</strong></span><span class="sxs-lookup"><span data-stu-id="dd80c-111"><strong>Echo On</strong></span></span></p></td>
<td><p><span data-ttu-id="dd80c-112">在 "宏生成器" 窗格的 "<strong>操作参数</strong>" 部分的 "<strong>回响</strong>" 框中, 单击<strong>"是</strong>(打开回响)" 或 "否 (关闭回响)" 框中的 "<strong>否</strong>"。</span><span class="sxs-lookup"><span data-stu-id="dd80c-112">Click <strong>Yes</strong> (turn echo on) or <strong>No</strong> (turn echo off) in the <strong>Echo On</strong> box in the <strong>Action Arguments</strong> section of the Macro Builder pane.</span></span> <span data-ttu-id="dd80c-113">默认值为 <strong>"是"</strong>。</span><span class="sxs-lookup"><span data-stu-id="dd80c-113">The default is <strong>Yes</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dd80c-114"><strong>状态栏文字</strong></span><span class="sxs-lookup"><span data-stu-id="dd80c-114"><strong>Status Bar Text</strong></span></span></p></td>
<td><p><span data-ttu-id="dd80c-115">关闭回响时显示在状态栏中的文本。</span><span class="sxs-lookup"><span data-stu-id="dd80c-115">The text to display in the status bar when echo is turned off.</span></span> <span data-ttu-id="dd80c-116">例如, 当回响关闭时, 状态栏可以显示&quot;宏正在运行。&quot;</span><span class="sxs-lookup"><span data-stu-id="dd80c-116">For example, when echo is turned off, the status bar can display &quot;The macro is running.&quot;</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="dd80c-117">当宏运行时, 屏幕更新通常会显示不重要的有关宏功能的信息。</span><span class="sxs-lookup"><span data-stu-id="dd80c-117">When a macro runs, screen updating often shows information not essential to the functioning of the macro.</span></span> <span data-ttu-id="dd80c-118">当您将 "**打开回响**" 参数设置为 "**否**" 时, 宏将运行, 而不更新屏幕。</span><span class="sxs-lookup"><span data-stu-id="dd80c-118">When you set the **Echo On** argument to **No**, the macro runs without updating the screen.</span></span> <span data-ttu-id="dd80c-119">当宏完成时, Access 会自动打开回响, 并重新绘制窗口。</span><span class="sxs-lookup"><span data-stu-id="dd80c-119">When the macro finishes, Access automatically turns echo back on and repaints the window.</span></span> <span data-ttu-id="dd80c-120">"打开**回响**" 参数的 "**无**" 设置不会影响宏或其结果的功能。</span><span class="sxs-lookup"><span data-stu-id="dd80c-120">The **No** setting for the **Echo On** argument doesn't affect the functionality of the macro or its results.</span></span>

<span data-ttu-id="dd80c-121">**Echo**操作不会禁止显示模式对话框 (如错误消息) 或弹出式窗体 (如属性表)。</span><span class="sxs-lookup"><span data-stu-id="dd80c-121">The **Echo** action doesn't suppress the display of modal dialog boxes, such as error messages, or pop-up forms, such as property sheets.</span></span> <span data-ttu-id="dd80c-122">您可以使用对话框和弹出窗体来收集或显示信息, 即使关闭了回响也是如此。</span><span class="sxs-lookup"><span data-stu-id="dd80c-122">You can use dialog boxes and pop-up forms to gather or display information, even if echo is turned off.</span></span> <span data-ttu-id="dd80c-123">若要禁止显示除错误消息框和要求用户输入信息的对话框以外的所有消息或对话框, 请使用**SetWarnings**操作。</span><span class="sxs-lookup"><span data-stu-id="dd80c-123">To suppress all message or dialog boxes except error message boxes and dialog boxes that require the user to enter information, use the **SetWarnings** action.</span></span>

<span data-ttu-id="dd80c-124">您可以在宏中多次运行**Echo**操作。</span><span class="sxs-lookup"><span data-stu-id="dd80c-124">You can run the **Echo** action more than once in a macro.</span></span> <span data-ttu-id="dd80c-125">这使您可以在宏运行时更改状态栏文本。</span><span class="sxs-lookup"><span data-stu-id="dd80c-125">This allows you to change the status bar text while the macro runs.</span></span>

<span data-ttu-id="dd80c-126">如果关闭了回响, 则可以使用**DisplayHourglassPointer**操作将鼠标指针更改为沙漏图标 (或为 "忙碌" 设置的任何鼠标指针图标), 以提供宏运行的可视指示。</span><span class="sxs-lookup"><span data-stu-id="dd80c-126">If you turn echo off, you can use the **DisplayHourglassPointer** action to change the mouse pointer into an hourglass icon (or whatever mouse pointer icon you've set for "Busy") to provide a visual indication that the macro is running.</span></span>

<span data-ttu-id="dd80c-127">若要在 Visual Basic for Applications (VBA) 模块中运行**echo**操作, 请使用**DoCmd**对象的**echo**方法。</span><span class="sxs-lookup"><span data-stu-id="dd80c-127">To run the **Echo** action in a Visual Basic for Applications (VBA) module, use the **Echo** method of the **DoCmd** object.</span></span>

## <a name="examples"></a><span data-ttu-id="dd80c-128">示例</span><span class="sxs-lookup"><span data-stu-id="dd80c-128">Examples</span></span>

### <a name="set-the-value-of-a-control-by-using-a-macro"></a><span data-ttu-id="dd80c-129">使用宏设置控件的值</span><span class="sxs-lookup"><span data-stu-id="dd80c-129">Set the value of a control by using a macro</span></span>

<span data-ttu-id="dd80c-130">以下宏将从 "供应商" 窗体上的按钮中打开 "添加产品" 窗体。</span><span class="sxs-lookup"><span data-stu-id="dd80c-130">The following macro opens the Add Products form from a button on the Suppliers form.</span></span> <span data-ttu-id="dd80c-131">它显示了**Echo**、 **CloseWindow**、 **OpenForm**、 **SetValue**和**GoToControl**操作的使用。</span><span class="sxs-lookup"><span data-stu-id="dd80c-131">It shows the use of the **Echo**, **CloseWindow**, **OpenForm**, **SetValue**, and **GoToControl** actions.</span></span> <span data-ttu-id="dd80c-132">**SetValue**操作将 "产品" 窗体上的 "供应商 ID" 控件设置为 "供应商" 窗体上的当前供应商。</span><span class="sxs-lookup"><span data-stu-id="dd80c-132">The **SetValue** action sets the Supplier ID control on the Products form to the current supplier on the Suppliers form.</span></span> <span data-ttu-id="dd80c-133">然后, **GoToControl**操作将焦点移到 "类别 ID" 字段, 在其中可以开始为新产品输入数据。</span><span class="sxs-lookup"><span data-stu-id="dd80c-133">The **GoToControl** action then moves the focus to the Category ID field, where you can begin to enter data for the new product.</span></span> <span data-ttu-id="dd80c-134">此宏应附加到 "供应商" 窗体上的 "添加产品" 按钮。</span><span class="sxs-lookup"><span data-stu-id="dd80c-134">This macro should be attached to the Add Products button on the Suppliers form.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="dd80c-135">操作</span><span class="sxs-lookup"><span data-stu-id="dd80c-135">Action</span></span></p></th>
<th><p><span data-ttu-id="dd80c-136">参数：设置</span><span class="sxs-lookup"><span data-stu-id="dd80c-136">Arguments: Setting</span></span></p></th>
<th><p><span data-ttu-id="dd80c-137">Comment</span><span class="sxs-lookup"><span data-stu-id="dd80c-137">Comment</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dd80c-138"><strong>Echo</strong></span><span class="sxs-lookup"><span data-stu-id="dd80c-138"><strong>Echo</strong></span></span></p></td>
<td><p><span data-ttu-id="dd80c-139"><strong>打开回响</strong>:<strong>否</strong></span><span class="sxs-lookup"><span data-stu-id="dd80c-139"><strong>Echo On</strong>: <strong>No</strong></span></span></p></td>
<td><p><span data-ttu-id="dd80c-140">在宏运行时停止屏幕更新。</span><span class="sxs-lookup"><span data-stu-id="dd80c-140">Stop screen updating while the macro is running.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dd80c-141"><strong>CloseWindow</strong></span><span class="sxs-lookup"><span data-stu-id="dd80c-141"><strong>CloseWindow</strong></span></span></p></td>
<td><p><span data-ttu-id="dd80c-142"><strong>对象类型</strong>: <strong>FormObject 名称</strong>: 产品列表是否<strong>保存</strong>:<strong>否</strong></span><span class="sxs-lookup"><span data-stu-id="dd80c-142"><strong>Object Type</strong>: <strong>FormObject Name</strong>: Product List <strong>Save</strong>: <strong>No</strong></span></span></p></td>
<td><p><span data-ttu-id="dd80c-143">关闭 "产品列表" 表单。</span><span class="sxs-lookup"><span data-stu-id="dd80c-143">Close the Product List form.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dd80c-144"><strong>OpenForm</strong></span><span class="sxs-lookup"><span data-stu-id="dd80c-144"><strong>OpenForm</strong></span></span></p></td>
<td><p><span data-ttu-id="dd80c-145"><strong>表单名称</strong>: 产品<strong>视图</strong>: <strong>FormData 模式</strong>: <strong>AddWindow 模式</strong>: <strong>Normal</strong></span><span class="sxs-lookup"><span data-stu-id="dd80c-145"><strong>Form Name</strong>: Products <strong>View</strong>: <strong>FormData Mode</strong>: <strong>AddWindow Mode</strong>: <strong>Normal</strong></span></span></p></td>
<td><p><span data-ttu-id="dd80c-146">打开 "产品" 窗体。</span><span class="sxs-lookup"><span data-stu-id="dd80c-146">Open the Products form.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dd80c-147"><strong>SetValue</strong></span><span class="sxs-lookup"><span data-stu-id="dd80c-147"><strong>SetValue</strong></span></span></p></td>
<td><p><span data-ttu-id="dd80c-148"><strong>项</strong>: [Forms]![Products]!id<strong>表达式</strong>: 供应商 id</span><span class="sxs-lookup"><span data-stu-id="dd80c-148"><strong>Item</strong>: [Forms]![Products]![SupplierID] <strong>Expression</strong>: SupplierID</span></span></p></td>
<td><p><span data-ttu-id="dd80c-149">将 "供应商 ID" 控件设置为 "供应商" 窗体上的当前供应商。</span><span class="sxs-lookup"><span data-stu-id="dd80c-149">Set the Supplier ID control to the current supplier on the Suppliers form.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dd80c-150"><strong>GoToControl</strong></span><span class="sxs-lookup"><span data-stu-id="dd80c-150"><strong>GoToControl</strong></span></span></p></td>
<td><p><span data-ttu-id="dd80c-151"><strong>控件名称</strong>: 类别 id</span><span class="sxs-lookup"><span data-stu-id="dd80c-151"><strong>Control Name</strong>: CategoryID</span></span></p></td>
<td><p><span data-ttu-id="dd80c-152">转到 "类别 ID" 控件。</span><span class="sxs-lookup"><span data-stu-id="dd80c-152">Go to the Category ID control.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="synchronize-forms-by-using-a-macro"></a><span data-ttu-id="dd80c-153">使用宏同步窗体</span><span class="sxs-lookup"><span data-stu-id="dd80c-153">Synchronize forms by using a macro</span></span>

<span data-ttu-id="dd80c-154">以下宏将打开 "供应商" 窗体右下角的 "产品列表" 窗体, 显示当前供应商的产品。</span><span class="sxs-lookup"><span data-stu-id="dd80c-154">The following macro opens the Product List form in the lower-right corner of the Suppliers form, displaying the current supplier's products.</span></span> <span data-ttu-id="dd80c-155">它演示了如何使用**Echo**、 **MessageBox**、 **GoToControl**、 **StopMacro**、 **OpenForm**和**MoveAndSizeWindow**操作。</span><span class="sxs-lookup"><span data-stu-id="dd80c-155">It shows the use of the **Echo**, **MessageBox**, **GoToControl**, **StopMacro**, **OpenForm**, and **MoveAndSizeWindow** actions.</span></span> <span data-ttu-id="dd80c-156">它还演示了如何使用带有**MessageBox**、 **GoToControl**和**StopMacro**操作的条件表达式。</span><span class="sxs-lookup"><span data-stu-id="dd80c-156">It also shows the use of a conditional expression with the **MessageBox**, **GoToControl**, and **StopMacro** actions.</span></span> <span data-ttu-id="dd80c-157">此宏应附加到 "供应商" 窗体上的 "查看产品" 按钮。</span><span class="sxs-lookup"><span data-stu-id="dd80c-157">This macro should be attached to the Review Products button on the Suppliers form.</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="dd80c-158">条件</span><span class="sxs-lookup"><span data-stu-id="dd80c-158">Condition</span></span></p></th>
<th><p><span data-ttu-id="dd80c-159">操作</span><span class="sxs-lookup"><span data-stu-id="dd80c-159">Action</span></span></p></th>
<th><p><span data-ttu-id="dd80c-160">参数：设置</span><span class="sxs-lookup"><span data-stu-id="dd80c-160">Arguments: Setting</span></span></p></th>
<th><p><span data-ttu-id="dd80c-161">Comment</span><span class="sxs-lookup"><span data-stu-id="dd80c-161">Comment</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p></p></td>
<td><p><span data-ttu-id="dd80c-162"><strong>Echo</strong></span><span class="sxs-lookup"><span data-stu-id="dd80c-162"><strong>Echo</strong></span></span></p></td>
<td><p><span data-ttu-id="dd80c-163"><strong>打开回响</strong>:<strong>否</strong></span><span class="sxs-lookup"><span data-stu-id="dd80c-163"><strong>Echo On</strong>: <strong>No</strong></span></span></p></td>
<td><p><span data-ttu-id="dd80c-164">在宏运行时停止屏幕更新。</span><span class="sxs-lookup"><span data-stu-id="dd80c-164">Stop screen updating while the macro is running.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dd80c-165">IsNull ([供应商 ID])</span><span class="sxs-lookup"><span data-stu-id="dd80c-165">IsNull([Supplier ID])</span></span></p></td>
<td><p><span data-ttu-id="dd80c-166"><strong>MessageBox</strong></span><span class="sxs-lookup"><span data-stu-id="dd80c-166"><strong>MessageBox</strong></span></span></p></td>
<td><p><span data-ttu-id="dd80c-167"><strong>消息</strong>: 移动到要查看其产品的供应商记录, 然后再次单击 "查看产品" 按钮。</span><span class="sxs-lookup"><span data-stu-id="dd80c-167"><strong>Message</strong>: Move to the supplier record whose products you want to see, then click the Review Products button again.</span></span> <span data-ttu-id="dd80c-168"><strong>嘟嘟声</strong>: <strong>YesType</strong>: <strong>NoneTitle</strong>: 选择供应商</span><span class="sxs-lookup"><span data-stu-id="dd80c-168"><strong>Beep</strong>: <strong>YesType</strong>: <strong>NoneTitle</strong>: Select a Supplier</span></span></p></td>
<td><p><span data-ttu-id="dd80c-169">如果 "供应商" 窗体上没有当前供应商, 则显示一条消息。</span><span class="sxs-lookup"><span data-stu-id="dd80c-169">If there is no current supplier on the Suppliers form, display a message.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dd80c-170">...</span><span class="sxs-lookup"><span data-stu-id="dd80c-170"></span></span></p></td>
<td><p><span data-ttu-id="dd80c-171"><strong>GoToControl</strong></span><span class="sxs-lookup"><span data-stu-id="dd80c-171"><strong>GoToControl</strong></span></span></p></td>
<td><p><span data-ttu-id="dd80c-172"><strong>控件名称</strong>: 公司名称</span><span class="sxs-lookup"><span data-stu-id="dd80c-172"><strong>Control Name</strong>: CompanyName</span></span></p></td>
<td><p><span data-ttu-id="dd80c-173">将焦点移到 "公司名称" 控件。</span><span class="sxs-lookup"><span data-stu-id="dd80c-173">Move focus to the CompanyName control.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dd80c-174">...</span><span class="sxs-lookup"><span data-stu-id="dd80c-174"></span></span></p></td>
<td><p><span data-ttu-id="dd80c-175"><strong>StopMacro</strong></span><span class="sxs-lookup"><span data-stu-id="dd80c-175"><strong>StopMacro</strong></span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="dd80c-176">停止宏。</span><span class="sxs-lookup"><span data-stu-id="dd80c-176">Stop the macro.</span></span></p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p><span data-ttu-id="dd80c-177"><strong>OpenForm</strong></span><span class="sxs-lookup"><span data-stu-id="dd80c-177"><strong>OpenForm</strong></span></span></p></td>
<td><p><span data-ttu-id="dd80c-178"><strong>表单名称</strong>: 产品列表<strong>视图</strong>: <strong>DatasheetFilter Name</strong>: <strong>Where 条件</strong>: [供应商 ID] = [Forms]![供应商]!id<strong>数据模式</strong>:<strong>读取 OnlyWindow 模式</strong>:<strong>普通</strong></span><span class="sxs-lookup"><span data-stu-id="dd80c-178"><strong>Form Name</strong>: Product List <strong>View</strong>: <strong>DatasheetFilter Name</strong>: <strong>Where Condition</strong>: [Supplier ID] = [Forms]![Suppliers]![SupplierID] <strong>Data Mode</strong>: <strong>Read OnlyWindow Mode</strong>: <strong>Normal</strong></span></span></p></td>
<td><p><span data-ttu-id="dd80c-179">打开 "产品列表" 表单并显示当前供应商的产品。</span><span class="sxs-lookup"><span data-stu-id="dd80c-179">Open the Product List form and show the current supplier's products.</span></span></p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p><span data-ttu-id="dd80c-180"><strong>MoveAndSizeWindow</strong></span><span class="sxs-lookup"><span data-stu-id="dd80c-180"><strong>MoveAndSizeWindow</strong></span></span></p></td>
<td><p><span data-ttu-id="dd80c-181"><strong>右侧</strong>: 0.7799&quot; <strong></strong>: 1。8&quot;</span><span class="sxs-lookup"><span data-stu-id="dd80c-181"><strong>Right</strong>: 0.7799&quot; <strong>Down</strong>: 1.8&quot;</span></span></p></td>
<td><p><span data-ttu-id="dd80c-182">将 "产品列表" 窗体放置在 "供应商" 窗体的右下角。</span><span class="sxs-lookup"><span data-stu-id="dd80c-182">Position the Product List form in the lower right of the Suppliers form.</span></span></p></td>
</tr>
</tbody>
</table>

