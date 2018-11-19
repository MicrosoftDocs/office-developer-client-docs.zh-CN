---
title: GoToPage 宏操作
TOCTitle: GoToPage macro action
ms:assetid: 611aadff-83b7-e74d-4093-93fb5ce6e3ab
ms:mtpsurl: https://msdn.microsoft.com/library/Ff194858(v=office.15)
ms:contentKeyID: 48545199
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm129285
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 179ee840370cef98c70e947cef555401408bbe12
ms.sourcegitcommit: 45feafb3b55de0402dddf5548c0c1c43a0eabafd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2018
ms.locfileid: "26026220"
---
# <a name="gotopage-macro-action"></a><span data-ttu-id="2e4a8-102">GoToPage 宏操作</span><span class="sxs-lookup"><span data-stu-id="2e4a8-102">GoToPage macro action</span></span>

<span data-ttu-id="2e4a8-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="2e4a8-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="2e4a8-p101">可以使用 **GoToPage** 操作将焦点从活动窗体中移至指定页上的第一个控件上。如果您创建了一个包含若干组相关信息的分页窗体，则可以使用此操作。例如，您可能有一个"员工"窗体，第一页上是个人信息，第二页上是办公室信息，第三页上是销售信息。您可以使用 **GoToPage** 操作移到所需的页。也可以使用选项卡控件将多页信息呈现在单个窗体上。</span><span class="sxs-lookup"><span data-stu-id="2e4a8-p101">You can use the **GoToPage** action to move the focus in the active form to the first control on a specified page. You can use this action if you have created a form with page breaks that contains groups of related information. For example, you might have an Employees form with personal information on one page, office information on another page, and sales information on a third page. You can use the **GoToPage** action to move to the desired page. You can also present multiple pages of information on a single form by using tab controls.</span></span>

## <a name="setting"></a><span data-ttu-id="2e4a8-109">设置</span><span class="sxs-lookup"><span data-stu-id="2e4a8-109">Setting</span></span>

<span data-ttu-id="2e4a8-110">**GoToPage** 操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="2e4a8-110">The **GoToPage** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="2e4a8-111">操作参数</span><span class="sxs-lookup"><span data-stu-id="2e4a8-111">Action argument</span></span></p></th>
<th><p><span data-ttu-id="2e4a8-112">说明</span><span class="sxs-lookup"><span data-stu-id="2e4a8-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2e4a8-113"><strong>页码</strong></span><span class="sxs-lookup"><span data-stu-id="2e4a8-113"><strong>Page Number</strong></span></span></p></td>
<td><p><span data-ttu-id="2e4a8-114">您想要将焦点移到的页的页码。</span><span class="sxs-lookup"><span data-stu-id="2e4a8-114">The number of the page to which you want to move the focus.</span></span> <span data-ttu-id="2e4a8-115">在宏生成器窗格的<strong>操作参数</strong>部分的<strong>页码</strong>框中输入的页号。</span><span class="sxs-lookup"><span data-stu-id="2e4a8-115">Enter the page number in the <strong>Page Number</strong> box in the <strong>Action Arguments</strong> section of the Macro Builder pane.</span></span> <span data-ttu-id="2e4a8-116">如果将此参数留空，焦点将停留在当前页上。</span><span class="sxs-lookup"><span data-stu-id="2e4a8-116">If you leave this argument blank, the focus stays on the current page.</span></span> <span data-ttu-id="2e4a8-117"><strong>右</strong>和<strong>关闭</strong>参数可用于显示您想要查看页上的一部分。</span><span class="sxs-lookup"><span data-stu-id="2e4a8-117">You can use the <strong>Right</strong> and <strong>Down</strong> arguments to display the part of the page you want to see.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2e4a8-118"><strong>Right</strong></span><span class="sxs-lookup"><span data-stu-id="2e4a8-118"><strong>Right</strong></span></span></p></td>
<td><p><span data-ttu-id="2e4a8-119">在页上，从页所在窗口，显示在窗口的左边缘的左边缘开始算起的点的水平位置。</span><span class="sxs-lookup"><span data-stu-id="2e4a8-119">The horizontal position of the spot on the page, measured from the left edge of its containing window, that is to appear at the left edge of the window.</span></span> <span data-ttu-id="2e4a8-120">如果指定的<strong>向下</strong>参数，这是必需的。</span><span class="sxs-lookup"><span data-stu-id="2e4a8-120">This is required if you specify a <strong>Down</strong> argument.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2e4a8-121"><strong>Down</strong></span><span class="sxs-lookup"><span data-stu-id="2e4a8-121"><strong>Down</strong></span></span></p></td>
<td><p><span data-ttu-id="2e4a8-122">在页上，从页所在窗口，要显示在窗口的上边缘的上边缘开始算起的点的垂直位置。</span><span class="sxs-lookup"><span data-stu-id="2e4a8-122">The vertical position of the spot on the page, measured from the top edge of its containing window, that is to appear at the top edge of the window.</span></span> <span data-ttu-id="2e4a8-123">如果指定<strong>右</strong>参数，这是必需的。</span><span class="sxs-lookup"><span data-stu-id="2e4a8-123">This is required if you specify a <strong>Right</strong> argument.</span></span></p></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="2e4a8-124">**右**和**关闭**参数的测量以英寸或厘米，具体取决于 Windows 控制面板中的区域设置。</span><span class="sxs-lookup"><span data-stu-id="2e4a8-124">The **Right** and **Down** arguments are measured in inches or centimeters, depending on the regional settings in Windows Control Panel.</span></span>

## <a name="remarks"></a><span data-ttu-id="2e4a8-125">说明</span><span class="sxs-lookup"><span data-stu-id="2e4a8-125">Remarks</span></span>

<span data-ttu-id="2e4a8-p105">可以使用此操作选择指定页上的第一个控件（由窗体的 Tab 键次序定义）。使用 **GoToControl** 操作可移至窗体上的特定控件。</span><span class="sxs-lookup"><span data-stu-id="2e4a8-p105">You can use this action to select the first control (as defined by the form's tab order) on the specified page. Use the **GoToControl** action to move to a particular control on the form.</span></span>

<span data-ttu-id="2e4a8-128">可以在页面大于在 Access 窗口中使用窗体**右**和**关闭**的参数。</span><span class="sxs-lookup"><span data-stu-id="2e4a8-128">You can use the **Right** and **Down** arguments for forms with pages larger than the Access window.</span></span> <span data-ttu-id="2e4a8-129">**页码**参数用于将移动到所需的页，然后使用**右**和**关闭**参数以显示您想要查看页上的一部分。</span><span class="sxs-lookup"><span data-stu-id="2e4a8-129">Use the **Page Number** argument to move to the desired page, and then use the **Right** and **Down** arguments to display the part of the page you want to see.</span></span> <span data-ttu-id="2e4a8-130">Access 将显示其左上角存在一定偏移的指定页面的左上角距离页上的一部分。</span><span class="sxs-lookup"><span data-stu-id="2e4a8-130">Access displays the part of the page whose upper-left corner is offset the specified distance from the upper-left corner of the page.</span></span>

<span data-ttu-id="2e4a8-131">在以下情况下，不能使用 **GoToPage** 操作：</span><span class="sxs-lookup"><span data-stu-id="2e4a8-131">You can't use the **GoToPage** action in the following cases:</span></span>

- <span data-ttu-id="2e4a8-132">将焦点移到隐藏窗体上的页上。</span><span class="sxs-lookup"><span data-stu-id="2e4a8-132">To move the focus to a page on a hidden form.</span></span>

- <span data-ttu-id="2e4a8-133">在选项卡控件中将焦点从某一页移到另一页上。</span><span class="sxs-lookup"><span data-stu-id="2e4a8-133">To move the focus from one page to another within the tab control.</span></span>

<span data-ttu-id="2e4a8-134">要在 Visual Basic for Applications (VBA) 模块中运行 **GoToPage** 操作，请使用 **DoCmd** 对象的 **GoToPage** 方法。</span><span class="sxs-lookup"><span data-stu-id="2e4a8-134">To run the **GoToPage** action in a Visual Basic for Applications (VBA) module, use the **GoToPage** method of the **DoCmd** object.</span></span>

