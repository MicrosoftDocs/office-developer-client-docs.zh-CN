---
title: NavigateTo 宏操作
TOCTitle: NavigateTo Macro Action
ms:assetid: 6594d614-3ea6-7851-b70e-1661d24f8ba0
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195165(v=office.15)
ms:contentKeyID: 48545324
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm119055
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 6cb9505eaf4a2002b0a4ae73ce4917ac250cda12
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25876055"
---
# <a name="navigateto-macro-action"></a><span data-ttu-id="b550b-102">NavigateTo 宏操作</span><span class="sxs-lookup"><span data-stu-id="b550b-102">NavigateTo Macro Action</span></span>


<span data-ttu-id="b550b-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="b550b-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="b550b-p101">可以使用 **NavigateTo** 操作控制在导航窗格中显示的数据库对象。例如，可以更改数据库对象的分类方式，并可通过筛选对象来仅显示特定的对象。</span><span class="sxs-lookup"><span data-stu-id="b550b-p101">You can use the **NavigateTo** action to control the display of database objects in the Navigation Pane. For example, you can change how the database objects are categorized, and you can filter the objects so that only certain ones are displayed.</span></span>

## <a name="setting"></a><span data-ttu-id="b550b-106">设置</span><span class="sxs-lookup"><span data-stu-id="b550b-106">Setting</span></span>

<span data-ttu-id="b550b-107">**NavigateTo** 操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="b550b-107">The **NavigateTo** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="b550b-108">操作参数</span><span class="sxs-lookup"><span data-stu-id="b550b-108">Action argument</span></span></p></th>
<th><p><span data-ttu-id="b550b-109">说明</span><span class="sxs-lookup"><span data-stu-id="b550b-109">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b550b-110"><strong>类别</strong></span><span class="sxs-lookup"><span data-stu-id="b550b-110"><strong>Category</strong></span></span></p></td>
<td><p><span data-ttu-id="b550b-p102">必选。要让导航窗格在显示对象时依据的类别。请在<strong>“类别”</strong>框中单击<strong>“对象类型”</strong>、<strong>“表和视图”</strong>、<strong>“修改日期”</strong>、<strong>“创建日期”</strong>或<strong>“自定义”</strong>。</span><span class="sxs-lookup"><span data-stu-id="b550b-p102">Required. The category by which you want the Navigation Pane to display objects. Click <strong>Object Type</strong>, <strong>Tables and Views</strong>, <strong>Modified Date</strong>, <strong>Created Date</strong>, or <strong>Custom</strong> in the <strong>Category</strong> box.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b550b-114"><strong>Group</strong></span><span class="sxs-lookup"><span data-stu-id="b550b-114"><strong>Group</strong></span></span></p></td>
<td><p><span data-ttu-id="b550b-115">可选。</span><span class="sxs-lookup"><span data-stu-id="b550b-115">Optional.</span></span> <span data-ttu-id="b550b-116">在导航窗格中显示的<strong>组</strong>参数限制类别中的哪些对象。</span><span class="sxs-lookup"><span data-stu-id="b550b-116">The <strong>Group</strong> argument limits which objects in the category appear in the Navigation Pane.</span></span> <span data-ttu-id="b550b-117">如果将<strong>组</strong>参数留空，导航窗格将显示<strong>类别</strong>参数中指定的条件进行分类的所有数据库对象。</span><span class="sxs-lookup"><span data-stu-id="b550b-117">If you leave the <strong>Group</strong> argument blank, the Navigation Pane displays all database objects, categorized by the criteria you specify in the <strong>Category</strong> argument.</span></span> <span data-ttu-id="b550b-118">下表中显示了各种 <strong>Category</strong> 参数的有效 <strong>Group</strong> 参数的示例。</span><span class="sxs-lookup"><span data-stu-id="b550b-118">Examples of valid <strong>Group</strong> arguments for the various <strong>Category</strong> arguments are shown in the following table.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="b550b-119">说明</span><span class="sxs-lookup"><span data-stu-id="b550b-119">Remarks</span></span>

  - <span data-ttu-id="b550b-120">此操作类似于从导航窗格的标题栏中选择类别和组。</span><span class="sxs-lookup"><span data-stu-id="b550b-120">This action is similar to selecting categories and groups from the title bar of the Navigation Pane.</span></span>

  - <span data-ttu-id="b550b-121">有效**Group**参数取决于使用哪些**Category**参数。</span><span class="sxs-lookup"><span data-stu-id="b550b-121">Valid **Group** arguments depend on which **Category** argument is used.</span></span> <span data-ttu-id="b550b-122">如果您输入了无效的**组**参数，将显示一条错误消息。下表包含每个**Category**参数的有效**Group**参数的示例。</span><span class="sxs-lookup"><span data-stu-id="b550b-122">If you enter an invalid **Group** argument, an error message appears.The following table contains examples of valid **Group** arguments for each **Category** argument.</span></span>
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p><span data-ttu-id="b550b-123">“类别”参数</span><span class="sxs-lookup"><span data-stu-id="b550b-123">Category argument</span></span></p></th>
    <th><p><span data-ttu-id="b550b-124">“组”参数示例</span><span class="sxs-lookup"><span data-stu-id="b550b-124">Example Group arguments</span></span></p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="b550b-125">对象类型</span><span class="sxs-lookup"><span data-stu-id="b550b-125">Object Type</span></span></p></td>
    <td><p><span data-ttu-id="b550b-126">表、窗体、查询、页、宏、模块</span><span class="sxs-lookup"><span data-stu-id="b550b-126">Tables; Forms; Queries; Pages; Macros; Modules</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="b550b-127">表和视图</span><span class="sxs-lookup"><span data-stu-id="b550b-127">Tables and Views</span></span></p></td>
    <td><p><span data-ttu-id="b550b-128">数据库中特定表的名称</span><span class="sxs-lookup"><span data-stu-id="b550b-128">Names of specific tables in your database</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="b550b-129">修改日期</span><span class="sxs-lookup"><span data-stu-id="b550b-129">Modified Date</span></span></p></td>
    <td><p><span data-ttu-id="b550b-130">今天；昨天；上个月；更早</span><span class="sxs-lookup"><span data-stu-id="b550b-130">Today; Yesterday; Last Month; Older</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="b550b-131">创建日期</span><span class="sxs-lookup"><span data-stu-id="b550b-131">Created Date</span></span></p></td>
    <td><p><span data-ttu-id="b550b-132">今天、昨天、上个月、更早</span><span class="sxs-lookup"><span data-stu-id="b550b-132">Today; Yesterday; Last Month; Older</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="b550b-133">自定义类别</span><span class="sxs-lookup"><span data-stu-id="b550b-133">Custom category</span></span></p></td>
    <td><p><span data-ttu-id="b550b-134">为指定的自定义类别创建的组名</span><span class="sxs-lookup"><span data-stu-id="b550b-134">Names of groups you have created for the specified custom category</span></span></p></td>
    </tr>
    </tbody>
    </table>


  - <span data-ttu-id="b550b-135">要在 VBA 模块中运行 **NavigateTo** 操作，请使用 **DoCmd** 对象的 **NavigateTo** 方法。</span><span class="sxs-lookup"><span data-stu-id="b550b-135">To run the **NavigateTo** action in a VBA module, use the **NavigateTo** method of the **DoCmd** object.</span></span>


> [!NOTE]
> <P><span data-ttu-id="b550b-136">要导航到类别 （例如，<STRONG>所有表</STRONG>、<STRONG>所有 Access 对象</STRONG>或<STRONG>所有日期</STRONG>） 的最高级别，您必须将组参数留空。</span><span class="sxs-lookup"><span data-stu-id="b550b-136">To navigate to the top level of a category (for example, <STRONG>All Tables</STRONG>, <STRONG>All Access Objects</STRONG>, or <STRONG>All Dates</STRONG>), you must leave the Group argument blank.</span></span> <span data-ttu-id="b550b-137">例如，<STRONG>对象类型</STRONG><STRONG>类别</STRONG>参数时，将<STRONG>所有 Access 对象</STRONG>都输入为<STRONG>组</STRONG>参数会导致出错。</span><span class="sxs-lookup"><span data-stu-id="b550b-137">For example, when the <STRONG>Category</STRONG> argument is <STRONG>Object Type</STRONG>, entering <STRONG>All Access Objects</STRONG> as a <STRONG>Group</STRONG> argument results in an error.</span></span></P>


