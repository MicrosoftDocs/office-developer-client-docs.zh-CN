---
title: SetDisplayedCategories 宏操作
TOCTitle: SetDisplayedCategories macro action
ms:assetid: e8bf39a6-c639-2232-7b21-3b0badf37e4b
ms:mtpsurl: https://msdn.microsoft.com/library/Ff836053(v=office.15)
ms:contentKeyID: 48548429
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm20026
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: f08b9a8980fc6f08a9f91366d38f65e4365a037e
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28711418"
---
# <a name="setdisplayedcategories-macro-action"></a><span data-ttu-id="04847-102">SetDisplayedCategories 宏操作</span><span class="sxs-lookup"><span data-stu-id="04847-102">SetDisplayedCategories macro action</span></span>


<span data-ttu-id="04847-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="04847-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="04847-p101">可以使用 **SetDisplayedCategories** 操作指定哪些类别在导航窗格标题栏中的 **"浏览类别"** 下显示。例如，如果希望阻止用户切换导航窗格，以便显示按 **"创建日期"** 排序的对象，则可以使用此操作在标题栏的下拉列表中隐藏该选项。</span><span class="sxs-lookup"><span data-stu-id="04847-p101">You can use the **SetDisplayedCategories** action to specify which categories are displayed under **Navigate to Category** in the title bar of the Navigation Pane. For example, if you want to prevent users from switching the Navigation Pane so that it displays objects sorted by **Created Date**, you can use this action to hide that option in the title bar's drop-down list.</span></span>

## <a name="setting"></a><span data-ttu-id="04847-106">设置</span><span class="sxs-lookup"><span data-stu-id="04847-106">Setting</span></span>

<span data-ttu-id="04847-107">**SetDisplayedCategories** 操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="04847-107">The **SetDisplayedCategories** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="04847-108">操作参数</span><span class="sxs-lookup"><span data-stu-id="04847-108">Action argument</span></span></p></th>
<th><p><span data-ttu-id="04847-109">说明</span><span class="sxs-lookup"><span data-stu-id="04847-109">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="04847-110"><strong>Show</strong></span><span class="sxs-lookup"><span data-stu-id="04847-110"><strong>Show</strong></span></span></p></td>
<td><p><span data-ttu-id="04847-p102">选择<strong>“是”</strong>可显示一个或多个类别。选择<strong>“否”</strong>可隐藏类别。</span><span class="sxs-lookup"><span data-stu-id="04847-p102">Select <strong>Yes</strong> to show the category or categories. Select <strong>No</strong> to hide them.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="04847-113"><strong>类别</strong></span><span class="sxs-lookup"><span data-stu-id="04847-113"><strong>Category</strong></span></span></p></td>
<td><p><span data-ttu-id="04847-p103">请输入或选择要显示或隐藏的类别的名称。将此参数留空可显示或隐藏所有类别。</span><span class="sxs-lookup"><span data-stu-id="04847-p103">Enter or select the name of the category you want to show or hide. Leave blank to show or hide all categories.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="04847-116">说明</span><span class="sxs-lookup"><span data-stu-id="04847-116">Remarks</span></span>

  - <span data-ttu-id="04847-p104">导航窗格的标题栏中的标题指示哪种筛选（如果有）当前处于活动状态。请单击标题栏的任意位置以显示下拉列表。此宏操作控制的项会在 **"浏览类别"** 下列出。</span><span class="sxs-lookup"><span data-stu-id="04847-p104">The caption in the title bar of the Navigation pane indicates which filter, if any, is currently active. Click anywhere in the bar to display the drop-down list. The items that this macro action controls are listed under **Navigate to Category**.</span></span>

  - <span data-ttu-id="04847-p105">此操作仅启用或禁用指定的一个或多个类别的显示；它不执行在任何导航窗格显示之间的切换。例如，如果正在显示按 **"创建日期"** 排序的对象并且使用 **SetDisplayedCategories** 操作禁用 **"创建日期"** 选项，则 Access 不会将导航窗格切换到其他类别。</span><span class="sxs-lookup"><span data-stu-id="04847-p105">This action only enables or disables the display of the specified category or categories; it does not perform any switching of the Navigation Pane display. For example, if you are displaying objects sorted by **Creation Date** and you use the **SetDisplayedCategories** action to disable the **Creation Date** option, Access does not switch the Navigation Pane to another category.</span></span>

  - <span data-ttu-id="04847-122">要在 VBA 模块中运行 **SetDisplayedCategories** 操作，请使用 **DoCmd** 对象的 **SetDisplayedCategories** 方法。</span><span class="sxs-lookup"><span data-stu-id="04847-122">To run the **SetDisplayedCategories** action in a VBA module, use the **SetDisplayedCategories** method of the **DoCmd** object.</span></span>

