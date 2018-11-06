---
title: 回声宏操作 （访问桌面数据库参考 （英文）
TOCTitle: Echo macro action
ms:assetid: 38dfb2cf-8db5-44b3-91fa-e490932b940b
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192516(v=office.15)
ms:contentKeyID: 48544227
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 03eeab3884e093b7c22f8fd23d5471d1dc620bc8
ms.sourcegitcommit: 1dd744993ecb4bed241ace874ad26edaef1778b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2018
ms.locfileid: "25997453"
---
# <a name="echo-macro-action"></a><span data-ttu-id="19ae7-102">Echo 宏操作</span><span class="sxs-lookup"><span data-stu-id="19ae7-102">Echo macro action</span></span>

<span data-ttu-id="19ae7-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="19ae7-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="19ae7-104">**Echo**操作可用于指定是否打开回响。</span><span class="sxs-lookup"><span data-stu-id="19ae7-104">You can use the **Echo** action to specify whether echo is turned on.</span></span> <span data-ttu-id="19ae7-105">例如，您可以使用此操作可隐藏或运行时显示的宏的结果。</span><span class="sxs-lookup"><span data-stu-id="19ae7-105">For example, you can use this action to hide or show the results of a macro while it runs.</span></span>

## <a name="setting"></a><span data-ttu-id="19ae7-106">设置</span><span class="sxs-lookup"><span data-stu-id="19ae7-106">Setting</span></span>

> [!NOTE]
> <span data-ttu-id="19ae7-107">[!注释] 如果数据库不受信任，将不允许此操作。</span><span class="sxs-lookup"><span data-stu-id="19ae7-107">This action will not be allowed if the database is not trusted.</span></span>

<span data-ttu-id="19ae7-108">**Echo**操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="19ae7-108">The **Echo** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="19ae7-109">操作参数</span><span class="sxs-lookup"><span data-stu-id="19ae7-109">Action argument</span></span></p></th>
<th><p><span data-ttu-id="19ae7-110">说明</span><span class="sxs-lookup"><span data-stu-id="19ae7-110">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="19ae7-111"><strong>打开回响</strong></span><span class="sxs-lookup"><span data-stu-id="19ae7-111"><strong>Echo On</strong></span></span></p></td>
<td><p><span data-ttu-id="19ae7-112">单击<strong>是</strong>（打开回响） 或<strong>无</strong>（关闭回响） 的<strong>回声</strong>框中的<strong>操作参数</strong>部分的宏生成器窗格中。</span><span class="sxs-lookup"><span data-stu-id="19ae7-112">Click <strong>Yes</strong> (turn echo on) or <strong>No</strong> (turn echo off) in the <strong>Echo On</strong> box in the <strong>Action Arguments</strong> section of the Macro Builder pane.</span></span> <span data-ttu-id="19ae7-113">默认值为 <strong>"是"</strong>。</span><span class="sxs-lookup"><span data-stu-id="19ae7-113">The default is <strong>Yes</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19ae7-114"><strong>状态栏文字</strong></span><span class="sxs-lookup"><span data-stu-id="19ae7-114"><strong>Status Bar Text</strong></span></span></p></td>
<td><p><span data-ttu-id="19ae7-115">要关闭回声时在状态栏中显示的文本。</span><span class="sxs-lookup"><span data-stu-id="19ae7-115">The text to display in the status bar when echo is turned off.</span></span> <span data-ttu-id="19ae7-116">例如，当回声处于关闭状态，可以显示状态栏&quot;会在运行宏。&quot;</span><span class="sxs-lookup"><span data-stu-id="19ae7-116">For example, when echo is turned off, the status bar can display &quot;The macro is running.&quot;</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="19ae7-117">当宏运行时，屏幕更新通常会显示信息不为宏的功能必需。</span><span class="sxs-lookup"><span data-stu-id="19ae7-117">When a macro runs, screen updating often shows information not essential to the functioning of the macro.</span></span> <span data-ttu-id="19ae7-118">时将**打开回响**参数设置为**No**，宏将运行但没有更新屏幕。</span><span class="sxs-lookup"><span data-stu-id="19ae7-118">When you set the **Echo On** argument to **No**, the macro runs without updating the screen.</span></span> <span data-ttu-id="19ae7-119">宏执行完，Access 将自动打开回声和重画窗口。</span><span class="sxs-lookup"><span data-stu-id="19ae7-119">When the macro finishes, Access automatically turns echo back on and repaints the window.</span></span> <span data-ttu-id="19ae7-120">**打开回响**参数的**无**设置不会影响宏或其结果的功能。</span><span class="sxs-lookup"><span data-stu-id="19ae7-120">The **No** setting for the **Echo On** argument doesn't affect the functionality of the macro or its results.</span></span>

<span data-ttu-id="19ae7-121">**Echo**操作不会禁止显示模式对话框，例如错误消息或弹出式窗体，如属性表。</span><span class="sxs-lookup"><span data-stu-id="19ae7-121">The **Echo** action doesn't suppress the display of modal dialog boxes, such as error messages, or pop-up forms, such as property sheets.</span></span> <span data-ttu-id="19ae7-122">您可以使用对话框和弹出式窗体来收集或显示的信息，即使关闭回响。</span><span class="sxs-lookup"><span data-stu-id="19ae7-122">You can use dialog boxes and pop-up forms to gather or display information, even if echo is turned off.</span></span> <span data-ttu-id="19ae7-123">若要取消所有邮件或对话框框除的错误消息框和要求用户输入信息的对话框，请使用**SetWarnings**操作。</span><span class="sxs-lookup"><span data-stu-id="19ae7-123">To suppress all message or dialog boxes except error message boxes and dialog boxes that require the user to enter information, use the **SetWarnings** action.</span></span>

<span data-ttu-id="19ae7-124">您可以在宏中多次运行**Echo**操作。</span><span class="sxs-lookup"><span data-stu-id="19ae7-124">You can run the **Echo** action more than once in a macro.</span></span> <span data-ttu-id="19ae7-125">这样，您可以在宏运行时更改状态栏文本。</span><span class="sxs-lookup"><span data-stu-id="19ae7-125">This allows you to change the status bar text while the macro runs.</span></span>

<span data-ttu-id="19ae7-126">如果关闭回声，您可以使用**DisplayHourglassPointer**操作将鼠标指针更改为沙漏图标 （或已设置为"忙碌"的任何鼠标指针图标） 提供直观的指示运行宏。</span><span class="sxs-lookup"><span data-stu-id="19ae7-126">If you turn echo off, you can use the **DisplayHourglassPointer** action to change the mouse pointer into an hourglass icon (or whatever mouse pointer icon you've set for "Busy") to provide a visual indication that the macro is running.</span></span>

<span data-ttu-id="19ae7-127">若要在 Visual Basic for Applications (VBA) 模块中运行**Echo**操作，请使用**DoCmd**对象的**回声**方法。</span><span class="sxs-lookup"><span data-stu-id="19ae7-127">To run the **Echo** action in a Visual Basic for Applications (VBA) module, use the **Echo** method of the **DoCmd** object.</span></span>

## <a name="examples"></a><span data-ttu-id="19ae7-128">示例</span><span class="sxs-lookup"><span data-stu-id="19ae7-128">Examples</span></span>

### <a name="set-the-value-of-a-control-by-using-a-macro"></a><span data-ttu-id="19ae7-129">通过使用宏设置控件的值</span><span class="sxs-lookup"><span data-stu-id="19ae7-129">Set the value of a control by using a macro</span></span>

<span data-ttu-id="19ae7-130">下面的宏 Suppliers 窗体上的按钮打开添加产品窗体。</span><span class="sxs-lookup"><span data-stu-id="19ae7-130">The following macro opens the Add Products form from a button on the Suppliers form.</span></span> <span data-ttu-id="19ae7-131">它演示如何使用**回声**、 **CloseWindow**、 **OpenForm**、 **SetValue**和**GoToControl**操作。</span><span class="sxs-lookup"><span data-stu-id="19ae7-131">It shows the use of the **Echo**, **CloseWindow**, **OpenForm**, **SetValue**, and **GoToControl** actions.</span></span> <span data-ttu-id="19ae7-132">**SetValue**操作供应商窗体上将产品窗体上的供应商 ID 控件设置为当前供应商。</span><span class="sxs-lookup"><span data-stu-id="19ae7-132">The **SetValue** action sets the Supplier ID control on the Products form to the current supplier on the Suppliers form.</span></span> <span data-ttu-id="19ae7-133">然后， **GoToControl**操作将焦点移到类别 ID 字段中，您可以开始新产品的输入数据。</span><span class="sxs-lookup"><span data-stu-id="19ae7-133">The **GoToControl** action then moves the focus to the Category ID field, where you can begin to enter data for the new product.</span></span> <span data-ttu-id="19ae7-134">这个宏应附加到 Suppliers 窗体上的添加产品按钮。</span><span class="sxs-lookup"><span data-stu-id="19ae7-134">This macro should be attached to the Add Products button on the Suppliers form.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="19ae7-135">操作</span><span class="sxs-lookup"><span data-stu-id="19ae7-135">Action</span></span></p></th>
<th><p><span data-ttu-id="19ae7-136">参数：设置</span><span class="sxs-lookup"><span data-stu-id="19ae7-136">Arguments: Setting</span></span></p></th>
<th><p><span data-ttu-id="19ae7-137">注释</span><span class="sxs-lookup"><span data-stu-id="19ae7-137">Comment</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="19ae7-138"><strong>Echo</strong></span><span class="sxs-lookup"><span data-stu-id="19ae7-138"><strong>Echo</strong></span></span></p></td>
<td><p><span data-ttu-id="19ae7-139"><strong>打开回响</strong>：<strong>否</strong></span><span class="sxs-lookup"><span data-stu-id="19ae7-139"><strong>Echo On</strong>: <strong>No</strong></span></span></p></td>
<td><p><span data-ttu-id="19ae7-140">停止屏幕更新时运行宏。</span><span class="sxs-lookup"><span data-stu-id="19ae7-140">Stop screen updating while the macro is running.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19ae7-141"><strong>CloseWindow</strong></span><span class="sxs-lookup"><span data-stu-id="19ae7-141"><strong>CloseWindow</strong></span></span></p></td>
<td><p><span data-ttu-id="19ae7-142"><strong>对象类型</strong>： <strong>FormObject 名称</strong>： 产品列表<strong>保存</strong>：<strong>否</strong></span><span class="sxs-lookup"><span data-stu-id="19ae7-142"><strong>Object Type</strong>: <strong>FormObject Name</strong>: Product List <strong>Save</strong>: <strong>No</strong></span></span></p></td>
<td><p><span data-ttu-id="19ae7-143">关闭产品列表窗体。</span><span class="sxs-lookup"><span data-stu-id="19ae7-143">Close the Product List form.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19ae7-144"><strong>OpenForm</strong></span><span class="sxs-lookup"><span data-stu-id="19ae7-144"><strong>OpenForm</strong></span></span></p></td>
<td><p><span data-ttu-id="19ae7-145"><strong>窗体名称</strong>： 产品<strong>视图</strong>： <strong>FormData 模式</strong>： <strong>AddWindow 模式</strong>：<strong>普通</strong></span><span class="sxs-lookup"><span data-stu-id="19ae7-145"><strong>Form Name</strong>: Products <strong>View</strong>: <strong>FormData Mode</strong>: <strong>AddWindow Mode</strong>: <strong>Normal</strong></span></span></p></td>
<td><p><span data-ttu-id="19ae7-146">打开产品窗体。</span><span class="sxs-lookup"><span data-stu-id="19ae7-146">Open the Products form.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19ae7-147"><strong>SetValue</strong></span><span class="sxs-lookup"><span data-stu-id="19ae7-147"><strong>SetValue</strong></span></span></p></td>
<td><p><span data-ttu-id="19ae7-148"><strong>项目</strong>: [窗体] ！[产品] ！[SupplierID]<strong>表达式</strong>： 供应商 Id</span><span class="sxs-lookup"><span data-stu-id="19ae7-148"><strong>Item</strong>: [Forms]![Products]![SupplierID] <strong>Expression</strong>: SupplierID</span></span></p></td>
<td><p><span data-ttu-id="19ae7-149">在 Suppliers 窗体上将供应商 ID 控件设置为当前供应商。</span><span class="sxs-lookup"><span data-stu-id="19ae7-149">Set the Supplier ID control to the current supplier on the Suppliers form.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19ae7-150"><strong>GoToControl</strong></span><span class="sxs-lookup"><span data-stu-id="19ae7-150"><strong>GoToControl</strong></span></span></p></td>
<td><p><span data-ttu-id="19ae7-151"><strong>控件名称</strong>： CategoryID</span><span class="sxs-lookup"><span data-stu-id="19ae7-151"><strong>Control Name</strong>: CategoryID</span></span></p></td>
<td><p><span data-ttu-id="19ae7-152">转到类别 ID 控件。</span><span class="sxs-lookup"><span data-stu-id="19ae7-152">Go to the Category ID control.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="synchronize-forms-by-using-a-macro"></a><span data-ttu-id="19ae7-153">通过使用宏同步处理窗体</span><span class="sxs-lookup"><span data-stu-id="19ae7-153">Synchronize forms by using a macro</span></span>

<span data-ttu-id="19ae7-154">下面的宏将在显示当前供应商的产品 Suppliers 窗体的右下角中打开产品列表窗体。</span><span class="sxs-lookup"><span data-stu-id="19ae7-154">The following macro opens the Product List form in the lower-right corner of the Suppliers form, displaying the current supplier's products.</span></span> <span data-ttu-id="19ae7-155">它演示如何使用**回声**、 **MessageBox**、 **GoToControl**、 **StopMacro**、 **OpenForm**，和**MoveAndSizeWindow**操作。</span><span class="sxs-lookup"><span data-stu-id="19ae7-155">It shows the use of the **Echo**, **MessageBox**, **GoToControl**, **StopMacro**, **OpenForm**, and **MoveAndSizeWindow** actions.</span></span> <span data-ttu-id="19ae7-156">它还会显示具有**MessageBox**、 **GoToControl**和**StopMacro**操作的条件表达式使用。</span><span class="sxs-lookup"><span data-stu-id="19ae7-156">It also shows the use of a conditional expression with the **MessageBox**, **GoToControl**, and **StopMacro** actions.</span></span> <span data-ttu-id="19ae7-157">这个宏应附加到 Suppliers 窗体上的查看产品按钮。</span><span class="sxs-lookup"><span data-stu-id="19ae7-157">This macro should be attached to the Review Products button on the Suppliers form.</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="19ae7-158">条件</span><span class="sxs-lookup"><span data-stu-id="19ae7-158">Condition</span></span></p></th>
<th><p><span data-ttu-id="19ae7-159">操作</span><span class="sxs-lookup"><span data-stu-id="19ae7-159">Action</span></span></p></th>
<th><p><span data-ttu-id="19ae7-160">参数：设置</span><span class="sxs-lookup"><span data-stu-id="19ae7-160">Arguments: Setting</span></span></p></th>
<th><p><span data-ttu-id="19ae7-161">注释</span><span class="sxs-lookup"><span data-stu-id="19ae7-161">Comment</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p></p></td>
<td><p><span data-ttu-id="19ae7-162"><strong>Echo</strong></span><span class="sxs-lookup"><span data-stu-id="19ae7-162"><strong>Echo</strong></span></span></p></td>
<td><p><span data-ttu-id="19ae7-163"><strong>打开回响</strong>：<strong>否</strong></span><span class="sxs-lookup"><span data-stu-id="19ae7-163"><strong>Echo On</strong>: <strong>No</strong></span></span></p></td>
<td><p><span data-ttu-id="19ae7-164">停止屏幕更新时运行宏。</span><span class="sxs-lookup"><span data-stu-id="19ae7-164">Stop screen updating while the macro is running.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19ae7-165">IsNull ([供应商 ID])</span><span class="sxs-lookup"><span data-stu-id="19ae7-165">IsNull([Supplier ID])</span></span></p></td>
<td><p><span data-ttu-id="19ae7-166"><strong>MessageBox</strong></span><span class="sxs-lookup"><span data-stu-id="19ae7-166"><strong>MessageBox</strong></span></span></p></td>
<td><p><span data-ttu-id="19ae7-167"><strong>消息</strong>： 移动到您要查看其的产品然后再次单击查看产品按钮的供应商记录。</span><span class="sxs-lookup"><span data-stu-id="19ae7-167"><strong>Message</strong>: Move to the supplier record whose products you want to see, then click the Review Products button again.</span></span> <span data-ttu-id="19ae7-168"><strong>发嘟嘟声</strong>： <strong>YesType</strong>: <strong>NoneTitle</strong>： 选择一个供应商</span><span class="sxs-lookup"><span data-stu-id="19ae7-168"><strong>Beep</strong>: <strong>YesType</strong>: <strong>NoneTitle</strong>: Select a Supplier</span></span></p></td>
<td><p><span data-ttu-id="19ae7-169">如果 Suppliers 窗体上没有当前供应商，显示一条消息。</span><span class="sxs-lookup"><span data-stu-id="19ae7-169">If there is no current supplier on the Suppliers form, display a message.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19ae7-170">...</span><span class="sxs-lookup"><span data-stu-id="19ae7-170"></span></span></p></td>
<td><p><span data-ttu-id="19ae7-171"><strong>GoToControl</strong></span><span class="sxs-lookup"><span data-stu-id="19ae7-171"><strong>GoToControl</strong></span></span></p></td>
<td><p><span data-ttu-id="19ae7-172"><strong>控件名称</strong>： 公司名称</span><span class="sxs-lookup"><span data-stu-id="19ae7-172"><strong>Control Name</strong>: CompanyName</span></span></p></td>
<td><p><span data-ttu-id="19ae7-173">将焦点移到公司名称控件。</span><span class="sxs-lookup"><span data-stu-id="19ae7-173">Move focus to the CompanyName control.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19ae7-174">...</span><span class="sxs-lookup"><span data-stu-id="19ae7-174"></span></span></p></td>
<td><p><span data-ttu-id="19ae7-175"><strong>StopMacro</strong></span><span class="sxs-lookup"><span data-stu-id="19ae7-175"><strong>StopMacro</strong></span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="19ae7-176">停止宏。</span><span class="sxs-lookup"><span data-stu-id="19ae7-176">Stop the macro.</span></span></p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p><span data-ttu-id="19ae7-177"><strong>OpenForm</strong></span><span class="sxs-lookup"><span data-stu-id="19ae7-177"><strong>OpenForm</strong></span></span></p></td>
<td><p><span data-ttu-id="19ae7-178"><strong>窗体名称</strong>： 产品列表<strong>视图</strong>： <strong>DatasheetFilter 名称</strong>： <strong>Where 条件</strong>: [供应商 ID] = [窗体] ！[供应商] ！[SupplierID]<strong>数据模式</strong>：<strong>读取 OnlyWindow 模式</strong>：<strong>普通</strong></span><span class="sxs-lookup"><span data-stu-id="19ae7-178"><strong>Form Name</strong>: Product List <strong>View</strong>: <strong>DatasheetFilter Name</strong>: <strong>Where Condition</strong>: [Supplier ID] = [Forms]![Suppliers]![SupplierID] <strong>Data Mode</strong>: <strong>Read OnlyWindow Mode</strong>: <strong>Normal</strong></span></span></p></td>
<td><p><span data-ttu-id="19ae7-179">打开产品列表窗体并显示当前供应商的产品。</span><span class="sxs-lookup"><span data-stu-id="19ae7-179">Open the Product List form and show the current supplier's products.</span></span></p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p><span data-ttu-id="19ae7-180"><strong>MoveAndSizeWindow</strong></span><span class="sxs-lookup"><span data-stu-id="19ae7-180"><strong>MoveAndSizeWindow</strong></span></span></p></td>
<td><p><span data-ttu-id="19ae7-181"><strong>右</strong>： 0.7799&quot; <strong>下</strong>： 1.8&quot;</span><span class="sxs-lookup"><span data-stu-id="19ae7-181"><strong>Right</strong>: 0.7799&quot; <strong>Down</strong>: 1.8&quot;</span></span></p></td>
<td><p><span data-ttu-id="19ae7-182">产品列表表单 Suppliers 窗体的右下角的位置。</span><span class="sxs-lookup"><span data-stu-id="19ae7-182">Position the Product List form in the lower right of the Suppliers form.</span></span></p></td>
</tr>
</tbody>
</table>

