---
title: MoveAndSizeWindow 宏操作
TOCTitle: MoveAndSizeWindow macro action
ms:assetid: 86bcf45f-90ce-4ca2-a7fb-efbe5347d137
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197001(v=office.15)
ms:contentKeyID: 48546090
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 8737de80c38626b72933eb15a59e08ab0452ce74
ms.sourcegitcommit: 1dd744993ecb4bed241ace874ad26edaef1778b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2018
ms.locfileid: "25998810"
---
# <a name="moveandsizewindow-macro-action"></a><span data-ttu-id="8c63e-102">MoveAndSizeWindow 宏操作</span><span class="sxs-lookup"><span data-stu-id="8c63e-102">MoveAndSizeWindow macro action</span></span>

<span data-ttu-id="8c63e-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="8c63e-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="8c63e-104">如果已将文档设置为使用重叠窗口而不是选项卡式文档的窗口选项，您可以使用**MoveAndSizeWindow**操作移动或调整活动窗口。</span><span class="sxs-lookup"><span data-stu-id="8c63e-104">If you have set your document window options to use overlapping windows instead of tabbed documents, you can use the **MoveAndSizeWindow** action to move or resize the active window.</span></span> <span data-ttu-id="8c63e-105">有关如何设置文档窗口选项的信息，请参阅备注部分。</span><span class="sxs-lookup"><span data-stu-id="8c63e-105">For information on how to set document window options, see the Remarks section.</span></span>

## <a name="setting"></a><span data-ttu-id="8c63e-106">设置</span><span class="sxs-lookup"><span data-stu-id="8c63e-106">Setting</span></span>

<span data-ttu-id="8c63e-107">**MoveAndSizeWindow**操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="8c63e-107">The **MoveAndSizeWindow** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="8c63e-108">操作参数</span><span class="sxs-lookup"><span data-stu-id="8c63e-108">Action argument</span></span></p></th>
<th><p><span data-ttu-id="8c63e-109">说明</span><span class="sxs-lookup"><span data-stu-id="8c63e-109">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8c63e-110"><strong>Right</strong></span><span class="sxs-lookup"><span data-stu-id="8c63e-110"><strong>Right</strong></span></span></p></td>
<td><p><span data-ttu-id="8c63e-111">窗口左上角的新水平位置，从页所在窗口的左边缘开始算起。</span><span class="sxs-lookup"><span data-stu-id="8c63e-111">The new horizontal position of the window's upper-left corner, measured from the left edge of its containing window.</span></span> <span data-ttu-id="8c63e-112">在宏生成器窗格的<strong>操作参数</strong>部分中输入<strong>右</strong>框中的位置。</span><span class="sxs-lookup"><span data-stu-id="8c63e-112">Enter the position in the <strong>Right</strong> box in the <strong>Action Arguments</strong> section of the Macro Builder pane.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c63e-113"><strong>Down</strong></span><span class="sxs-lookup"><span data-stu-id="8c63e-113"><strong>Down</strong></span></span></p></td>
<td><p><span data-ttu-id="8c63e-114">活动窗口左上角的新垂直位置，从页所在窗口的上边缘开始算起。</span><span class="sxs-lookup"><span data-stu-id="8c63e-114">The new vertical position of the window's upper-left corner, measured from the top edge of its containing window.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8c63e-115"><strong>Width</strong></span><span class="sxs-lookup"><span data-stu-id="8c63e-115"><strong>Width</strong></span></span></p></td>
<td><p><span data-ttu-id="8c63e-116">活动窗口的新宽度。</span><span class="sxs-lookup"><span data-stu-id="8c63e-116">The window's new width.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c63e-117"><strong>Height</strong></span><span class="sxs-lookup"><span data-stu-id="8c63e-117"><strong>Height</strong></span></span></p></td>
<td><p><span data-ttu-id="8c63e-118">活动窗口的新高度。</span><span class="sxs-lookup"><span data-stu-id="8c63e-118">The window's new height.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8c63e-119">如果参数为空，Microsoft Access 将使用窗口的当前设置。</span><span class="sxs-lookup"><span data-stu-id="8c63e-119">If you leave an argument blank, Microsoft Access uses the window's current setting.</span></span>

<span data-ttu-id="8c63e-120">您必须至少一个参数输入值。</span><span class="sxs-lookup"><span data-stu-id="8c63e-120">You must enter a value for at least one argument.</span></span>

> [!NOTE]
> <span data-ttu-id="8c63e-121">每个度量值是以英寸或厘米，具体取决于 Windows 控制面板中的区域设置。</span><span class="sxs-lookup"><span data-stu-id="8c63e-121">Each measurement is in inches or centimeters, depending on the regional settings in Windows Control Panel.</span></span>

## <a name="remarks"></a><span data-ttu-id="8c63e-122">备注</span><span class="sxs-lookup"><span data-stu-id="8c63e-122">Remarks</span></span>

<span data-ttu-id="8c63e-123">若要设置应用程序使用重叠窗口而不是选项卡式文档，请使用以下过程：</span><span class="sxs-lookup"><span data-stu-id="8c63e-123">To set up an application to use overlapping windows instead of tabbed documents, use the following procedure:</span></span>

1.  <span data-ttu-id="8c63e-124">单击**选项**</span><span class="sxs-lookup"><span data-stu-id="8c63e-124">Click **Options**</span></span>

2.  <span data-ttu-id="8c63e-125">单击**当前数据库**。</span><span class="sxs-lookup"><span data-stu-id="8c63e-125">Click **Current Database**.</span></span>

3.  <span data-ttu-id="8c63e-126">在 **“应用程序选项”** 部分中的 **“文档窗口选项”** 下，单击 **“重叠窗口”**。</span><span class="sxs-lookup"><span data-stu-id="8c63e-126">In the **Application Options** section, under **Document Window Options**, click **Overlapping Windows**.</span></span>

4.  <span data-ttu-id="8c63e-127">单击**确定**，然后关闭并重新打开数据库。</span><span class="sxs-lookup"><span data-stu-id="8c63e-127">Click **OK**, and then close and reopen the database.</span></span>

<span data-ttu-id="8c63e-128">此操作类似于单击窗口**控件**菜单上的**移动**或**大小**。</span><span class="sxs-lookup"><span data-stu-id="8c63e-128">This action is similar to clicking **Move** or **Size** on the window's **Control** menu.</span></span> <span data-ttu-id="8c63e-129">与菜单命令中，您可以使用键盘的箭头键来移动或调整窗口大小。</span><span class="sxs-lookup"><span data-stu-id="8c63e-129">With the menu commands, you use the keyboard's arrow keys to move or resize the window.</span></span> <span data-ttu-id="8c63e-130">如果使用**MoveAndSizeWindow**操作，您输入的位置和大小度量直接。</span><span class="sxs-lookup"><span data-stu-id="8c63e-130">With the **MoveAndSizeWindow** action, you enter the position and size measurements directly.</span></span> <span data-ttu-id="8c63e-131">您还可以使用鼠标移动和调整窗口大小。</span><span class="sxs-lookup"><span data-stu-id="8c63e-131">You can also use the mouse to move and size windows.</span></span>

<span data-ttu-id="8c63e-132">您可以在任何窗口中，在任何视图中使用此操作。</span><span class="sxs-lookup"><span data-stu-id="8c63e-132">You can use this action on any window, in any view.</span></span>

> [!TIP]
> - <span data-ttu-id="8c63e-133">若要移动窗口而不调整其大小，**右边**和**向下**参数输入值，但将**Width**和**Height**参数留空。</span><span class="sxs-lookup"><span data-stu-id="8c63e-133">To move a window without resizing it, enter values for the **Right** and **Down** arguments but leave the **Width** and **Height** arguments blank.</span></span>
> - <span data-ttu-id="8c63e-134">若要调整窗口大小而不移动的**宽度**和**高度**参数输入值，但将**右**和**关闭**参数留空。</span><span class="sxs-lookup"><span data-stu-id="8c63e-134">To resize a window without moving it, enter values for the **Width** and **Height** arguments but leave the **Right** and **Down** arguments blank.</span></span>

<span data-ttu-id="8c63e-135">若要在 Visual Basic for Applications (VBA) 模块中运行**MoveAndSizeWindow**操作，请使用**DoCmd**对象的**MoveSize**方法。</span><span class="sxs-lookup"><span data-stu-id="8c63e-135">To run the **MoveAndSizeWindow** action in a Visual Basic for Applications (VBA) module, use the **MoveSize** method of the **DoCmd** object.</span></span>

## <a name="example"></a><span data-ttu-id="8c63e-136">示例</span><span class="sxs-lookup"><span data-stu-id="8c63e-136">Example</span></span>

<span data-ttu-id="8c63e-137">**通过使用宏同步处理窗体**</span><span class="sxs-lookup"><span data-stu-id="8c63e-137">**Synchronize forms by using a macro**</span></span>

<span data-ttu-id="8c63e-138">下面的宏将在显示当前供应商的产品 Suppliers 窗体的右下角中打开产品列表窗体。</span><span class="sxs-lookup"><span data-stu-id="8c63e-138">The following macro opens a Product List form in the lower-right corner of the Suppliers form, displaying the current supplier's products.</span></span> <span data-ttu-id="8c63e-139">它演示如何使用**回声**、 **MessageBox**、 **GoToControl**、 **StopMacro**、 **OpenForm**，和**MoveAndSizeWindow**操作。</span><span class="sxs-lookup"><span data-stu-id="8c63e-139">It shows the use of the **Echo**, **MessageBox**, **GoToControl**, **StopMacro**, **OpenForm**, and **MoveAndSizeWindow** actions.</span></span> <span data-ttu-id="8c63e-140">它还会显示具有**MessageBox**、 **GoToControl**和**StopMacro**操作的条件表达式使用。</span><span class="sxs-lookup"><span data-stu-id="8c63e-140">It also shows the use of a conditional expression with the **MessageBox**, **GoToControl**, and **StopMacro** actions.</span></span> <span data-ttu-id="8c63e-141">这个宏应附加到 Suppliers 窗体上的查看产品按钮。</span><span class="sxs-lookup"><span data-stu-id="8c63e-141">This macro should be attached to the Review Products button on the Suppliers form.</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="8c63e-142">条件</span><span class="sxs-lookup"><span data-stu-id="8c63e-142">Condition</span></span></p></th>
<th><p><span data-ttu-id="8c63e-143">操作</span><span class="sxs-lookup"><span data-stu-id="8c63e-143">Action</span></span></p></th>
<th><p><span data-ttu-id="8c63e-144">参数：设置</span><span class="sxs-lookup"><span data-stu-id="8c63e-144">Arguments: Setting</span></span></p></th>
<th><p><span data-ttu-id="8c63e-145">注释</span><span class="sxs-lookup"><span data-stu-id="8c63e-145">Comment</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p></p></td>
<td><p><span data-ttu-id="8c63e-146"><strong>Echo</strong></span><span class="sxs-lookup"><span data-stu-id="8c63e-146"><strong>Echo</strong></span></span></p></td>
<td><p><span data-ttu-id="8c63e-147"><strong>打开回响</strong>：<strong>否</strong></span><span class="sxs-lookup"><span data-stu-id="8c63e-147"><strong>Echo On</strong>: <strong>No</strong></span></span></p></td>
<td><p><span data-ttu-id="8c63e-148">停止屏幕更新时运行宏。</span><span class="sxs-lookup"><span data-stu-id="8c63e-148">Stop screen updating while the macro is running.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c63e-149">IsNull ([供应商 ID])</span><span class="sxs-lookup"><span data-stu-id="8c63e-149">IsNull([Supplier ID])</span></span></p></td>
<td><p><span data-ttu-id="8c63e-150"><strong>MessageBox</strong></span><span class="sxs-lookup"><span data-stu-id="8c63e-150"><strong>MessageBox</strong></span></span></p></td>
<td><p><span data-ttu-id="8c63e-151"><strong>消息</strong>： 移动到您要查看其的产品然后再次单击查看产品按钮的供应商记录。</span><span class="sxs-lookup"><span data-stu-id="8c63e-151"><strong>Message</strong>: Move to the supplier record whose products you want to see, then click the Review Products button again.</span></span> <span data-ttu-id="8c63e-152"><strong>发嘟嘟声</strong>： <strong>YesType</strong>: <strong>NoneTitle</strong>： 选择一个供应商</span><span class="sxs-lookup"><span data-stu-id="8c63e-152"><strong>Beep</strong>: <strong>YesType</strong>: <strong>NoneTitle</strong>: Select a Supplier</span></span></p></td>
<td><p><span data-ttu-id="8c63e-153">如果 Suppliers 窗体上没有当前供应商，显示一条消息。</span><span class="sxs-lookup"><span data-stu-id="8c63e-153">If there is no current supplier on the Suppliers form, display a message.</span></span></p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p><span data-ttu-id="8c63e-154"><strong>GoToControl</strong></span><span class="sxs-lookup"><span data-stu-id="8c63e-154"><strong>GoToControl</strong></span></span></p></td>
<td><p><span data-ttu-id="8c63e-155"><strong>控件名称</strong>： 公司名称</span><span class="sxs-lookup"><span data-stu-id="8c63e-155"><strong>Control Name</strong>: CompanyName</span></span></p></td>
<td><p><span data-ttu-id="8c63e-156">将焦点移到公司名称控件。</span><span class="sxs-lookup"><span data-stu-id="8c63e-156">Move focus to the CompanyName control.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c63e-157">...</span><span class="sxs-lookup"><span data-stu-id="8c63e-157"></span></span></p></td>
<td><p><span data-ttu-id="8c63e-158"><strong>StopMacro</strong></span><span class="sxs-lookup"><span data-stu-id="8c63e-158"><strong>StopMacro</strong></span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="8c63e-159">停止宏。</span><span class="sxs-lookup"><span data-stu-id="8c63e-159">Stop the macro.</span></span></p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p><span data-ttu-id="8c63e-160"><strong>OpenForm</strong></span><span class="sxs-lookup"><span data-stu-id="8c63e-160"><strong>OpenForm</strong></span></span></p></td>
<td><p><span data-ttu-id="8c63e-161"><strong>窗体名称</strong>： 产品列表<strong>视图</strong>： <strong>DatasheetFilter 名称</strong>： <strong>Where 条件</strong>: [供应商 ID] = [窗体] ！[供应商] ！[SupplierID]<strong>数据模式</strong>：<strong>读取 OnlyWindow 模式</strong>：<strong>普通</strong></span><span class="sxs-lookup"><span data-stu-id="8c63e-161"><strong>Form Name</strong>: Product List <strong>View</strong>: <strong>DatasheetFilter Name</strong>: <strong>Where Condition</strong>: [Supplier ID] = [Forms]![Suppliers]![SupplierID] <strong>Data Mode</strong>: <strong>Read OnlyWindow Mode</strong>: <strong>Normal</strong></span></span></p></td>
<td><p><span data-ttu-id="8c63e-162">打开产品列表窗体并显示当前供应商的产品。</span><span class="sxs-lookup"><span data-stu-id="8c63e-162">Open the Product List form and show the current supplier's products.</span></span></p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p><span data-ttu-id="8c63e-163"><strong>MoveAndSizeWindow</strong></span><span class="sxs-lookup"><span data-stu-id="8c63e-163"><strong>MoveAndSizeWindow</strong></span></span></p></td>
<td><p><span data-ttu-id="8c63e-164"><strong>右</strong>： 0.7799&quot; <strong>下</strong>： 1.8&quot;</span><span class="sxs-lookup"><span data-stu-id="8c63e-164"><strong>Right</strong>: 0.7799&quot; <strong>Down</strong>: 1.8&quot;</span></span></p></td>
<td><p><span data-ttu-id="8c63e-165">产品列表表单 Suppliers 窗体的右下角的位置。</span><span class="sxs-lookup"><span data-stu-id="8c63e-165">Position the Product List form in the lower right of the Suppliers form.</span></span></p></td>
</tr>
</tbody>
</table>

