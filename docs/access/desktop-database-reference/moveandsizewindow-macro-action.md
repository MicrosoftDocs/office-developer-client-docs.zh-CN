---
title: MoveAndSizeWindow 宏操作
TOCTitle: MoveAndSizeWindow Macro Action
ms:assetid: 86bcf45f-90ce-4ca2-a7fb-efbe5347d137
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197001(v=office.15)
ms:contentKeyID: 48546090
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: ab2998140f46fd3275f564684995d9a4d8d56968
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25882537"
---
# <a name="moveandsizewindow-macro-action"></a><span data-ttu-id="41382-102">MoveAndSizeWindow 宏操作</span><span class="sxs-lookup"><span data-stu-id="41382-102">MoveAndSizeWindow Macro Action</span></span>


<span data-ttu-id="41382-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="41382-103">**Applies to**: Access 2013, Office 2013</span></span>


<span data-ttu-id="41382-104">如果已将文档设置为使用重叠窗口而不是选项卡式文档的窗口选项，您可以使用**MoveAndSizeWindow**操作移动或调整活动窗口。</span><span class="sxs-lookup"><span data-stu-id="41382-104">If you have set your document window options to use overlapping windows instead of tabbed documents, you can use the **MoveAndSizeWindow** action to move or resize the active window.</span></span> <span data-ttu-id="41382-105">有关如何设置文档窗口选项的信息，请参阅备注部分。</span><span class="sxs-lookup"><span data-stu-id="41382-105">For information on how to set document window options, see the Remarks section.</span></span>

## <a name="setting"></a><span data-ttu-id="41382-106">设置</span><span class="sxs-lookup"><span data-stu-id="41382-106">Setting</span></span>

<span data-ttu-id="41382-107">**MoveAndSizeWindow**操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="41382-107">The **MoveAndSizeWindow** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="41382-108">操作参数</span><span class="sxs-lookup"><span data-stu-id="41382-108">Action argument</span></span></p></th>
<th><p><span data-ttu-id="41382-109">说明</span><span class="sxs-lookup"><span data-stu-id="41382-109">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="41382-110"><strong>Right</strong></span><span class="sxs-lookup"><span data-stu-id="41382-110"><strong>Right</strong></span></span></p></td>
<td><p><span data-ttu-id="41382-111">窗口左上角的新水平位置，从页所在窗口的左边缘开始算起。</span><span class="sxs-lookup"><span data-stu-id="41382-111">The new horizontal position of the window's upper-left corner, measured from the left edge of its containing window.</span></span> <span data-ttu-id="41382-112">在宏生成器窗格的<strong>操作参数</strong>部分中输入<strong>右</strong>框中的位置。</span><span class="sxs-lookup"><span data-stu-id="41382-112">Enter the position in the <strong>Right</strong> box in the <strong>Action Arguments</strong> section of the Macro Builder pane.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41382-113"><strong>Down</strong></span><span class="sxs-lookup"><span data-stu-id="41382-113"><strong>Down</strong></span></span></p></td>
<td><p><span data-ttu-id="41382-114">活动窗口左上角的新垂直位置，从页所在窗口的上边缘开始算起。</span><span class="sxs-lookup"><span data-stu-id="41382-114">The new vertical position of the window's upper-left corner, measured from the top edge of its containing window.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41382-115"><strong>Width</strong></span><span class="sxs-lookup"><span data-stu-id="41382-115"><strong>Width</strong></span></span></p></td>
<td><p><span data-ttu-id="41382-116">活动窗口的新宽度。</span><span class="sxs-lookup"><span data-stu-id="41382-116">The window's new width.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41382-117"><strong>Height</strong></span><span class="sxs-lookup"><span data-stu-id="41382-117"><strong>Height</strong></span></span></p></td>
<td><p><span data-ttu-id="41382-118">活动窗口的新高度。</span><span class="sxs-lookup"><span data-stu-id="41382-118">The window's new height.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="41382-119">如果参数为空，Microsoft Access 将使用窗口的当前设置。</span><span class="sxs-lookup"><span data-stu-id="41382-119">If you leave an argument blank, Microsoft Access uses the window's current setting.</span></span>

<span data-ttu-id="41382-120">您必须至少一个参数输入值。</span><span class="sxs-lookup"><span data-stu-id="41382-120">You must enter a value for at least one argument.</span></span>


> [!NOTE]
> <P><span data-ttu-id="41382-121">每个度量值是以英寸或厘米，具体取决于 Windows 控制面板中的区域设置。</span><span class="sxs-lookup"><span data-stu-id="41382-121">Each measurement is in inches or centimeters, depending on the regional settings in Windows Control Panel.</span></span></P>



## <a name="remarks"></a><span data-ttu-id="41382-122">说明</span><span class="sxs-lookup"><span data-stu-id="41382-122">Remarks</span></span>

<span data-ttu-id="41382-123">若要设置应用程序使用重叠窗口而不是选项卡式文档，请使用以下过程：</span><span class="sxs-lookup"><span data-stu-id="41382-123">To set up an application to use overlapping windows instead of tabbed documents, use the following procedure:</span></span>

1.  <span data-ttu-id="41382-124">，然后单击**选项**</span><span class="sxs-lookup"><span data-stu-id="41382-124">and then click **Options**</span></span>

2.  <span data-ttu-id="41382-125">单击**当前数据库**。</span><span class="sxs-lookup"><span data-stu-id="41382-125">Click **Current Database**.</span></span>

3.  <span data-ttu-id="41382-126">在 **“应用程序选项”** 部分中的 **“文档窗口选项”** 下，单击 **“重叠窗口”**。</span><span class="sxs-lookup"><span data-stu-id="41382-126">In the **Application Options** section, under **Document Window Options**, click **Overlapping Windows**.</span></span>

4.  <span data-ttu-id="41382-127">单击**确定**，然后关闭并重新打开数据库。</span><span class="sxs-lookup"><span data-stu-id="41382-127">Click **OK**, and then close and reopen the database.</span></span>

<span data-ttu-id="41382-128">此操作类似于单击窗口**控件**菜单上的**移动**或**大小**。</span><span class="sxs-lookup"><span data-stu-id="41382-128">This action is similar to clicking **Move** or **Size** on the window's **Control** menu.</span></span> <span data-ttu-id="41382-129">与菜单命令中，您可以使用键盘的箭头键来移动或调整窗口大小。</span><span class="sxs-lookup"><span data-stu-id="41382-129">With the menu commands, you use the keyboard's arrow keys to move or resize the window.</span></span> <span data-ttu-id="41382-130">如果使用**MoveAndSizeWindow**操作，您输入的位置和大小度量直接。</span><span class="sxs-lookup"><span data-stu-id="41382-130">With the **MoveAndSizeWindow** action, you enter the position and size measurements directly.</span></span> <span data-ttu-id="41382-131">您还可以使用鼠标移动和调整窗口大小。</span><span class="sxs-lookup"><span data-stu-id="41382-131">You can also use the mouse to move and size windows.</span></span>

<span data-ttu-id="41382-132">您可以在任何窗口中，在任何视图中使用此操作。</span><span class="sxs-lookup"><span data-stu-id="41382-132">You can use this action on any window, in any view.</span></span>

<span data-ttu-id="41382-133">**提示**</span><span class="sxs-lookup"><span data-stu-id="41382-133">**Tips**</span></span>

  - <span data-ttu-id="41382-134">若要移动窗口而不调整其大小，**右边**和**向下**参数输入值，但将**Width**和**Height**参数留空。</span><span class="sxs-lookup"><span data-stu-id="41382-134">To move a window without resizing it, enter values for the **Right** and **Down** arguments but leave the **Width** and **Height** arguments blank.</span></span>

  - <span data-ttu-id="41382-135">若要调整窗口大小而不移动的**宽度**和**高度**参数输入值，但将**右**和**关闭**参数留空。</span><span class="sxs-lookup"><span data-stu-id="41382-135">To resize a window without moving it, enter values for the **Width** and **Height** arguments but leave the **Right** and **Down** arguments blank.</span></span>

<span data-ttu-id="41382-136">若要在 Visual Basic for Applications (VBA) 模块中运行**MoveAndSizeWindow**操作，请使用**DoCmd**对象的**MoveSize**方法。</span><span class="sxs-lookup"><span data-stu-id="41382-136">To run the **MoveAndSizeWindow** action in a Visual Basic for Applications (VBA) module, use the **MoveSize** method of the **DoCmd** object.</span></span>

## <a name="example"></a><span data-ttu-id="41382-137">示例</span><span class="sxs-lookup"><span data-stu-id="41382-137">Example</span></span>

<span data-ttu-id="41382-138">**通过使用宏同步处理窗体**</span><span class="sxs-lookup"><span data-stu-id="41382-138">**Synchronize forms by using a macro**</span></span>

<span data-ttu-id="41382-139">下面的宏将在显示当前供应商的产品 Suppliers 窗体的右下角中打开产品列表窗体。</span><span class="sxs-lookup"><span data-stu-id="41382-139">The following macro opens a Product List form in the lower-right corner of the Suppliers form, displaying the current supplier's products.</span></span> <span data-ttu-id="41382-140">它演示如何使用**回声**、 **MessageBox**、 **GoToControl**、 **StopMacro**、 **OpenForm**，和**MoveAndSizeWindow**操作。</span><span class="sxs-lookup"><span data-stu-id="41382-140">It shows the use of the **Echo**, **MessageBox**, **GoToControl**, **StopMacro**, **OpenForm**, and **MoveAndSizeWindow** actions.</span></span> <span data-ttu-id="41382-141">它还会显示具有**MessageBox**、 **GoToControl**和**StopMacro**操作的条件表达式使用。</span><span class="sxs-lookup"><span data-stu-id="41382-141">It also shows the use of a conditional expression with the **MessageBox**, **GoToControl**, and **StopMacro** actions.</span></span> <span data-ttu-id="41382-142">这个宏应附加到 Suppliers 窗体上的查看产品按钮。</span><span class="sxs-lookup"><span data-stu-id="41382-142">This macro should be attached to the Review Products button on the Suppliers form.</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="41382-143">条件</span><span class="sxs-lookup"><span data-stu-id="41382-143">Condition</span></span></p></th>
<th><p><span data-ttu-id="41382-144">操作</span><span class="sxs-lookup"><span data-stu-id="41382-144">Action</span></span></p></th>
<th><p><span data-ttu-id="41382-145">参数：设置</span><span class="sxs-lookup"><span data-stu-id="41382-145">Arguments: Setting</span></span></p></th>
<th><p><span data-ttu-id="41382-146">注释</span><span class="sxs-lookup"><span data-stu-id="41382-146">Comment</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p></p></td>
<td><p><span data-ttu-id="41382-147"><strong>Echo</strong></span><span class="sxs-lookup"><span data-stu-id="41382-147"><strong>Echo</strong></span></span></p></td>
<td><p><span data-ttu-id="41382-148"><strong>打开回响</strong>：<strong>否</strong></span><span class="sxs-lookup"><span data-stu-id="41382-148"><strong>Echo On</strong>: <strong>No</strong></span></span></p></td>
<td><p><span data-ttu-id="41382-149">停止屏幕更新时运行宏。</span><span class="sxs-lookup"><span data-stu-id="41382-149">Stop screen updating while the macro is running.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41382-150">IsNull ([供应商 ID])</span><span class="sxs-lookup"><span data-stu-id="41382-150">IsNull([Supplier ID])</span></span></p></td>
<td><p><span data-ttu-id="41382-151"><strong>MessageBox</strong></span><span class="sxs-lookup"><span data-stu-id="41382-151"><strong>MessageBox</strong></span></span></p></td>
<td><p><span data-ttu-id="41382-152"><strong>消息</strong>： 移动到您要查看其的产品然后再次单击查看产品按钮的供应商记录。</span><span class="sxs-lookup"><span data-stu-id="41382-152"><strong>Message</strong>: Move to the supplier record whose products you want to see, then click the Review Products button again.</span></span> <span data-ttu-id="41382-153"><strong>发嘟嘟声</strong>： <strong>YesType</strong>: <strong>NoneTitle</strong>： 选择一个供应商</span><span class="sxs-lookup"><span data-stu-id="41382-153"><strong>Beep</strong>: <strong>YesType</strong>: <strong>NoneTitle</strong>: Select a Supplier</span></span></p></td>
<td><p><span data-ttu-id="41382-154">如果 Suppliers 窗体上没有当前供应商，显示一条消息。</span><span class="sxs-lookup"><span data-stu-id="41382-154">If there is no current supplier on the Suppliers form, display a message.</span></span></p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p><span data-ttu-id="41382-155"><strong>GoToControl</strong></span><span class="sxs-lookup"><span data-stu-id="41382-155"><strong>GoToControl</strong></span></span></p></td>
<td><p><span data-ttu-id="41382-156"><strong>控件名称</strong>： 公司名称</span><span class="sxs-lookup"><span data-stu-id="41382-156"><strong>Control Name</strong>: CompanyName</span></span></p></td>
<td><p><span data-ttu-id="41382-157">将焦点移到公司名称控件。</span><span class="sxs-lookup"><span data-stu-id="41382-157">Move focus to the CompanyName control.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41382-158">...</span><span class="sxs-lookup"><span data-stu-id="41382-158"></span></span></p></td>
<td><p><span data-ttu-id="41382-159"><strong>StopMacro</strong></span><span class="sxs-lookup"><span data-stu-id="41382-159"><strong>StopMacro</strong></span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="41382-160">停止宏。</span><span class="sxs-lookup"><span data-stu-id="41382-160">Stop the macro.</span></span></p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p><span data-ttu-id="41382-161"><strong>OpenForm</strong></span><span class="sxs-lookup"><span data-stu-id="41382-161"><strong>OpenForm</strong></span></span></p></td>
<td><p><span data-ttu-id="41382-162"><strong>窗体名称</strong>： 产品列表<strong>视图</strong>： <strong>DatasheetFilter 名称</strong>： <strong>Where 条件</strong>: [供应商 ID] = [窗体] ！[供应商] ！[SupplierID]<strong>数据模式</strong>：<strong>读取 OnlyWindow 模式</strong>：<strong>普通</strong></span><span class="sxs-lookup"><span data-stu-id="41382-162"><strong>Form Name</strong>: Product List <strong>View</strong>: <strong>DatasheetFilter Name</strong>: <strong>Where Condition</strong>: [Supplier ID] = [Forms]![Suppliers]![SupplierID] <strong>Data Mode</strong>: <strong>Read OnlyWindow Mode</strong>: <strong>Normal</strong></span></span></p></td>
<td><p><span data-ttu-id="41382-163">打开产品列表窗体并显示当前供应商的产品。</span><span class="sxs-lookup"><span data-stu-id="41382-163">Open the Product List form and show the current supplier's products.</span></span></p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p><span data-ttu-id="41382-164"><strong>MoveAndSizeWindow</strong></span><span class="sxs-lookup"><span data-stu-id="41382-164"><strong>MoveAndSizeWindow</strong></span></span></p></td>
<td><p><span data-ttu-id="41382-165"><strong>右</strong>： 0.7799&quot; <strong>下</strong>： 1.8&quot;</span><span class="sxs-lookup"><span data-stu-id="41382-165"><strong>Right</strong>: 0.7799&quot; <strong>Down</strong>: 1.8&quot;</span></span></p></td>
<td><p><span data-ttu-id="41382-166">产品列表表单 Suppliers 窗体的右下角的位置。</span><span class="sxs-lookup"><span data-stu-id="41382-166">Position the Product List form in the lower right of the Suppliers form.</span></span></p></td>
</tr>
</tbody>
</table>

