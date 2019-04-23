---
title: NavigateTo 宏操作
TOCTitle: NavigateTo macro action
ms:assetid: 6594d614-3ea6-7851-b70e-1661d24f8ba0
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195165(v=office.15)
ms:contentKeyID: 48545324
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm119055
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 1c37e798e0624a5655b63a76332073e5b57c0823
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288600"
---
# <a name="navigateto-macro-action"></a><span data-ttu-id="d2470-102">NavigateTo 宏操作</span><span class="sxs-lookup"><span data-stu-id="d2470-102">NavigateTo macro action</span></span>

<span data-ttu-id="d2470-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="d2470-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="d2470-p101">可以使用 **NavigateTo** 操作控制在导航窗格中显示的数据库对象。例如，可以更改数据库对象的分类方式，并可通过筛选对象来仅显示特定的对象。</span><span class="sxs-lookup"><span data-stu-id="d2470-p101">You can use the **NavigateTo** action to control the display of database objects in the Navigation Pane. For example, you can change how the database objects are categorized, and you can filter the objects so that only certain ones are displayed.</span></span>

## <a name="setting"></a><span data-ttu-id="d2470-106">Setting</span><span class="sxs-lookup"><span data-stu-id="d2470-106">Setting</span></span>

<span data-ttu-id="d2470-107">**NavigateTo** 操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="d2470-107">The **NavigateTo** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="d2470-108">操作参数</span><span class="sxs-lookup"><span data-stu-id="d2470-108">Action argument</span></span></p></th>
<th><p><span data-ttu-id="d2470-109">说明</span><span class="sxs-lookup"><span data-stu-id="d2470-109">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d2470-110"><strong>类别</strong></span><span class="sxs-lookup"><span data-stu-id="d2470-110"><strong>Category</strong></span></span></p></td>
<td><p><span data-ttu-id="d2470-p102">必选。要让导航窗格在显示对象时依据的类别。请在<strong>“类别”</strong>框中单击<strong>“对象类型”</strong>、<strong>“表和视图”</strong>、<strong>“修改日期”</strong>、<strong>“创建日期”</strong>或<strong>“自定义”</strong>。</span><span class="sxs-lookup"><span data-stu-id="d2470-p102">Required. The category by which you want the Navigation Pane to display objects. Click <strong>Object Type</strong>, <strong>Tables and Views</strong>, <strong>Modified Date</strong>, <strong>Created Date</strong>, or <strong>Custom</strong> in the <strong>Category</strong> box.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d2470-114"><strong>组</strong></span><span class="sxs-lookup"><span data-stu-id="d2470-114"><strong>Group</strong></span></span></p></td>
<td><p><span data-ttu-id="d2470-115">可选。</span><span class="sxs-lookup"><span data-stu-id="d2470-115">Optional.</span></span> <span data-ttu-id="d2470-116">“组”<strong></strong>参数限制类别中可显示在导航窗格中的对象。</span><span class="sxs-lookup"><span data-stu-id="d2470-116">The <strong>Group</strong> argument limits which objects in the category appear in the Navigation Pane.</span></span> <span data-ttu-id="d2470-117">如果将<strong>Group</strong>参数保留为空, 则导航窗格将显示按照您在<strong>Category</strong>参数中指定的条件进行分类的所有数据库对象。</span><span class="sxs-lookup"><span data-stu-id="d2470-117">If you leave the <strong>Group</strong> argument blank, the Navigation Pane displays all database objects, categorized by the criteria you specify in the <strong>Category</strong> argument.</span></span> <span data-ttu-id="d2470-118">下表中显示了各个“类别”参数<strong></strong>的有效“组”<strong></strong>参数的示例。</span><span class="sxs-lookup"><span data-stu-id="d2470-118">Examples of valid <strong>Group</strong> arguments for the various <strong>Category</strong> arguments are shown in the following table.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="d2470-119">注解</span><span class="sxs-lookup"><span data-stu-id="d2470-119">Remarks</span></span>

- <span data-ttu-id="d2470-120">此操作类似于从导航窗格的标题栏中选择类别和组。</span><span class="sxs-lookup"><span data-stu-id="d2470-120">This action is similar to selecting categories and groups from the title bar of the navigation pane.</span></span>

- <span data-ttu-id="d2470-p104">Valid **Group** arguments depend on which **Category** argument is used. If you enter an invalid **Group** argument, an error message appears.The following table contains examples of valid **Group** arguments for each **Category** argument.</span><span class="sxs-lookup"><span data-stu-id="d2470-p104">Valid **Group** arguments depend on which **Category** argument is used. If you enter an invalid **Group** argument, an error message appears.The following table contains examples of valid **Group** arguments for each **Category** argument.</span></span>
    
  <table>
  <colgroup>
  <col style="width: 50%" />
  <col style="width: 50%" />
  </colgroup>
  <thead>
  <tr class="header">
  <th><p><span data-ttu-id="d2470-123">Category 参数</span><span class="sxs-lookup"><span data-stu-id="d2470-123">Category argument</span></span></p></th>
  <th><p><span data-ttu-id="d2470-124">Group 参数的示例</span><span class="sxs-lookup"><span data-stu-id="d2470-124">Example Group arguments</span></span></p></th>
  </tr>
  </thead>
  <tbody>
  <tr class="odd">
  <td><p><span data-ttu-id="d2470-125">对象类型</span><span class="sxs-lookup"><span data-stu-id="d2470-125">Object Type</span></span></p></td>
  <td><p><span data-ttu-id="d2470-126">表；窗体；查询；页；宏；模块</span><span class="sxs-lookup"><span data-stu-id="d2470-126">Tables; Forms; Queries; Pages; Macros; Modules</span></span></p></td>
  </tr>
  <tr class="even">
  <td><p><span data-ttu-id="d2470-127">表和视图</span><span class="sxs-lookup"><span data-stu-id="d2470-127">Tables and Views</span></span></p></td>
  <td><p><span data-ttu-id="d2470-128">数据库中特定表的名称</span><span class="sxs-lookup"><span data-stu-id="d2470-128">Names of specific tables in your database</span></span></p></td>
  </tr>
  <tr class="odd">
  <td><p><span data-ttu-id="d2470-129">修改日期</span><span class="sxs-lookup"><span data-stu-id="d2470-129">Modified Date</span></span></p></td>
  <td><p><span data-ttu-id="d2470-130">今天；昨天；上个月；更早</span><span class="sxs-lookup"><span data-stu-id="d2470-130">Today; Yesterday; Last Month; Older</span></span></p></td>
  </tr>
  <tr class="even">
  <td><p><span data-ttu-id="d2470-131">创建日期</span><span class="sxs-lookup"><span data-stu-id="d2470-131">Created Date</span></span></p></td>
  <td><p><span data-ttu-id="d2470-132">今天、昨天、上个月、更早</span><span class="sxs-lookup"><span data-stu-id="d2470-132">Today; Yesterday; Last Month; Older</span></span></p></td>
  </tr>
  <tr class="odd">
  <td><p><span data-ttu-id="d2470-133">自定义类别</span><span class="sxs-lookup"><span data-stu-id="d2470-133">Custom category</span></span></p></td>
  <td><p><span data-ttu-id="d2470-134">为指定的自定义类别创建的组名</span><span class="sxs-lookup"><span data-stu-id="d2470-134">Names of groups you have created for the specified custom category</span></span></p></td>
  </tr>
  </tbody>
  </table>

- <span data-ttu-id="d2470-135">要在 VBA 模块中运行 **NavigateTo** 操作，请使用 **DoCmd** 对象的 **NavigateTo** 方法。</span><span class="sxs-lookup"><span data-stu-id="d2470-135">To run the **NavigateTo** action in a VBA module, use the **NavigateTo** method of the **DoCmd** object.</span></span>

> [!NOTE]
> <span data-ttu-id="d2470-p105">To navigate to the top level of a category (for example, **All Tables**, **All Access Objects**, or **All Dates**), you must leave the Group argument blank. For example, when the **Category** argument is **Object Type**, entering **All Access Objects** as a **Group** argument results in an error.</span><span class="sxs-lookup"><span data-stu-id="d2470-p105">To navigate to the top level of a category (for example, **All Tables**, **All Access Objects**, or **All Dates**), you must leave the Group argument blank. For example, when the **Category** argument is **Object Type**, entering **All Access Objects** as a **Group** argument results in an error.</span></span>


