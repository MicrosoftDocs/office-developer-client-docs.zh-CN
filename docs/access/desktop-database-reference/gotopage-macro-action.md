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
localization_priority: Normal
ms.openlocfilehash: 10d55b435a59594eaf3e8380b6690ebbda63a258
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32292158"
---
# <a name="gotopage-macro-action"></a><span data-ttu-id="9571c-102">GoToPage 宏操作</span><span class="sxs-lookup"><span data-stu-id="9571c-102">GoToPage macro action</span></span>

<span data-ttu-id="9571c-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="9571c-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="9571c-p101">可以使用 **GoToPage** 操作将焦点从活动窗体中移至指定页上的第一个控件上。如果您创建了一个包含若干组相关信息的分页窗体，则可以使用此操作。例如，您可能有一个"员工"窗体，第一页上是个人信息，第二页上是办公室信息，第三页上是销售信息。您可以使用 **GoToPage** 操作移到所需的页。也可以使用选项卡控件将多页信息呈现在单个窗体上。</span><span class="sxs-lookup"><span data-stu-id="9571c-p101">You can use the **GoToPage** action to move the focus in the active form to the first control on a specified page. You can use this action if you have created a form with page breaks that contains groups of related information. For example, you might have an Employees form with personal information on one page, office information on another page, and sales information on a third page. You can use the **GoToPage** action to move to the desired page. You can also present multiple pages of information on a single form by using tab controls.</span></span>

## <a name="setting"></a><span data-ttu-id="9571c-109">Setting</span><span class="sxs-lookup"><span data-stu-id="9571c-109">Setting</span></span>

<span data-ttu-id="9571c-110">**GoToPage** 操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="9571c-110">The **GoToPage** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="9571c-111">操作参数</span><span class="sxs-lookup"><span data-stu-id="9571c-111">Action argument</span></span></p></th>
<th><p><span data-ttu-id="9571c-112">说明</span><span class="sxs-lookup"><span data-stu-id="9571c-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9571c-113"><strong>页码</strong></span><span class="sxs-lookup"><span data-stu-id="9571c-113"><strong>Page Number</strong></span></span></p></td>
<td><p><span data-ttu-id="9571c-p102">要将焦点移到的页码。请在“宏生成器”窗格<strong>“操作参数”</strong>部分的<strong>“页码”</strong>框中输入页码。如果将此参数留空，焦点将留在当前页上。可以使用“右”<strong></strong>和“下”<strong></strong>参数显示要查看的页部分。</span><span class="sxs-lookup"><span data-stu-id="9571c-p102">The number of the page to which you want to move the focus. Enter the page number in the <strong>Page Number</strong> box in the <strong>Action Arguments</strong> section of the Macro Builder pane. If you leave this argument blank, the focus stays on the current page. You can use the <strong>Right</strong> and <strong>Down</strong> arguments to display the part of the page you want to see.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9571c-118"><strong>Right</strong></span><span class="sxs-lookup"><span data-stu-id="9571c-118"><strong>Right</strong></span></span></p></td>
<td><p><span data-ttu-id="9571c-p103">显示在窗口左边缘的页中的点的水平位置，此值从所在窗口的左边缘开始测量。如果指定了“下”<strong></strong>参数，则此参数为必选参数。</span><span class="sxs-lookup"><span data-stu-id="9571c-p103">The horizontal position of the spot on the page, measured from the left edge of its containing window, that is to appear at the left edge of the window. This is required if you specify a <strong>Down</strong> argument.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9571c-121"><strong>Down</strong></span><span class="sxs-lookup"><span data-stu-id="9571c-121"><strong>Down</strong></span></span></p></td>
<td><p><span data-ttu-id="9571c-p104">显示在窗口上边缘的页中的点的垂直位置，此值从所在窗口的上边缘开始测量。如果指定了“右”<strong></strong>参数，则此参数为必选参数。</span><span class="sxs-lookup"><span data-stu-id="9571c-p104">The vertical position of the spot on the page, measured from the top edge of its containing window, that is to appear at the top edge of the window. This is required if you specify a <strong>Right</strong> argument.</span></span></p></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="9571c-124">“右”\*\*\*\* 和“下”\*\*\*\* 参数的测量单位是英寸或厘米，具体取决于 Windows 控制面板中的区域设置。</span><span class="sxs-lookup"><span data-stu-id="9571c-124">The **Right** and **Down** arguments are measured in inches or centimeters, depending on the regional settings in Windows Control Panel.</span></span>

## <a name="remarks"></a><span data-ttu-id="9571c-125">注解</span><span class="sxs-lookup"><span data-stu-id="9571c-125">Remarks</span></span>

<span data-ttu-id="9571c-p105">可以使用此操作选择指定页上的第一个控件（由窗体的 Tab 键次序定义）。使用 **GoToControl** 操作可移至窗体上的特定控件。</span><span class="sxs-lookup"><span data-stu-id="9571c-p105">You can use this action to select the first control (as defined by the form's tab order) on the specified page. Use the **GoToControl** action to move to a particular control on the form.</span></span>

<span data-ttu-id="9571c-128">您可以对页面大小大于 Access 窗口的窗体使用**右**和**下**参数。</span><span class="sxs-lookup"><span data-stu-id="9571c-128">You can use the **Right** and **Down** arguments for forms with pages larger than the Access window.</span></span> <span data-ttu-id="9571c-129">Use the **Page Number** argument to move to the desired page, and then use the **Right** and **Down** arguments to display the part of the page you want to see.</span><span class="sxs-lookup"><span data-stu-id="9571c-129">Use the **Page Number** argument to move to the desired page, and then use the **Right** and **Down** arguments to display the part of the page you want to see.</span></span> <span data-ttu-id="9571c-130">Access displays the part of the page whose upper-left corner is offset the specified distance from the upper-left corner of the page.</span><span class="sxs-lookup"><span data-stu-id="9571c-130">Access displays the part of the page whose upper-left corner is offset the specified distance from the upper-left corner of the page.</span></span>

<span data-ttu-id="9571c-131">在以下情况下，不能使用 **GoToPage** 操作：</span><span class="sxs-lookup"><span data-stu-id="9571c-131">You can't use the **GoToPage** action in the following cases:</span></span>

- <span data-ttu-id="9571c-132">将焦点移到隐藏窗体上的页上。</span><span class="sxs-lookup"><span data-stu-id="9571c-132">To move the focus to a page on a hidden form.</span></span>

- <span data-ttu-id="9571c-133">在选项卡控件中将焦点从某一页移到另一页上。</span><span class="sxs-lookup"><span data-stu-id="9571c-133">To move the focus from one page to another within the tab control.</span></span>

<span data-ttu-id="9571c-134">要在 Visual Basic for Applications (VBA) 模块中运行 **GoToPage** 操作，请使用 **DoCmd** 对象的 **GoToPage** 方法。</span><span class="sxs-lookup"><span data-stu-id="9571c-134">To run the **GoToPage** action in a Visual Basic for Applications (VBA) module, use the **GoToPage** method of the **DoCmd** object.</span></span>

