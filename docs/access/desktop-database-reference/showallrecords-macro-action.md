---
title: ShowAllRecords 宏操作
TOCTitle: ShowAllRecords macro action
ms:assetid: 6f9741ad-0440-4b8d-abea-009063c111f8
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195587(v=office.15)
ms:contentKeyID: 48545538
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 201b284a56fbd3030b41a95424b41c73ee13e385
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32308643"
---
# <a name="showallrecords-macro-action"></a><span data-ttu-id="919db-102">ShowAllRecords 宏操作</span><span class="sxs-lookup"><span data-stu-id="919db-102">ShowAllRecords macro action</span></span>


<span data-ttu-id="919db-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="919db-103">**Applies to**: Access 2013, Office 2013</span></span>


<span data-ttu-id="919db-104">您可以使用**ShowAllRecords**操作从活动表、查询结果集或窗体中删除任何已应用的筛选, 并显示表或结果集中的所有记录, 或者窗体的基础表或查询中的所有记录。</span><span class="sxs-lookup"><span data-stu-id="919db-104">You can use the **ShowAllRecords** action to remove any applied filter from the active table, query result set, or form, and display all records in the table or result set or all records in the form's underlying table or query.</span></span>

## <a name="setting"></a><span data-ttu-id="919db-105">Setting</span><span class="sxs-lookup"><span data-stu-id="919db-105">Setting</span></span>

<span data-ttu-id="919db-106">**ShowAllRecords**操作不具有任何参数。</span><span class="sxs-lookup"><span data-stu-id="919db-106">The **ShowAllRecords** action doesn't have any arguments.</span></span>

## <a name="remarks"></a><span data-ttu-id="919db-107">注解</span><span class="sxs-lookup"><span data-stu-id="919db-107">Remarks</span></span>

<span data-ttu-id="919db-108">您可以使用此操作来确保为表、查询结果集或窗体显示所有记录 (包括任何已更改或新记录)。</span><span class="sxs-lookup"><span data-stu-id="919db-108">You can use this action to ensure that all records (including any changed or new records) are displayed for a table, query result set, or form.</span></span> <span data-ttu-id="919db-109">此操作会对窗体或子窗体的记录进行重新查询。</span><span class="sxs-lookup"><span data-stu-id="919db-109">This action causes a requery of the records for a form or subform.</span></span>

<span data-ttu-id="919db-110">您还可以使用此操作删除应用于**ApplyFilter**操作的任何筛选器、"**开始**" 选项卡上的 "**筛选**" 命令或 "**筛选器名称**" 或 "在**OpenForm** " 操作的 " **Where 条件**" 参数。</span><span class="sxs-lookup"><span data-stu-id="919db-110">You can also use this action to remove any filter that was applied with the **ApplyFilter** action, the **Filter** command on the **Home** tab, or the **Filter Name** or **Where Condition** argument of the **OpenForm** action.</span></span>

<span data-ttu-id="919db-111">此操作等效于单击 "**开始**" 选项卡上的 "**切换筛选**", 或右键单击筛选字段, 然后单击 "窗体" 视图、"布局视图" 或 "数据表视图" 中的 "**清除筛选 ...** "。</span><span class="sxs-lookup"><span data-stu-id="919db-111">This action has the same effect as clicking **Toggle Filter** on the **Home** tab, or right-clicking the filtered field and clicking **Clear filter from...** in Form view, Layout view, or Datasheet view.</span></span>

<span data-ttu-id="919db-112">若要在 Visual Basic for Applications (VBA) 模块中运行**ShowAllRecords**操作, 请使用**DoCmd**对象的**ShowAllRecords**方法。</span><span class="sxs-lookup"><span data-stu-id="919db-112">To run the **ShowAllRecords** action in a Visual Basic for Applications (VBA) module, use the **ShowAllRecords** method of the **DoCmd** object.</span></span>

## <a name="example"></a><span data-ttu-id="919db-113">示例</span><span class="sxs-lookup"><span data-stu-id="919db-113">Example</span></span>

<span data-ttu-id="919db-114">**使用宏应用筛选**</span><span class="sxs-lookup"><span data-stu-id="919db-114">**Apply a filter by using a macro**</span></span>

<span data-ttu-id="919db-p102">下面的宏包含一组操作，其中每项操作都会对"客户电话列表"窗体中的记录进行筛选。它演示如何使用 **ApplyFilter** 、 **ShowAllRecords** 和 **GoToControl** 操作。它还演示了如何使用条件来确定已在窗体的选项组中选择了哪个切换按钮。每个操作行都与一个切换按钮相关联，这些切换按钮分别用于选择以 A、B、C 等字母开头的一组记录或所有记录。此宏应附加到 CompanyNameFilter 选项组的 **AfterUpdate** 事件。</span><span class="sxs-lookup"><span data-stu-id="919db-p102">The following macro contains a set of actions, each of which filters the records for a Customer Phone List form. It shows the use of the **ApplyFilter**, **ShowAllRecords**, and **GoToControl** actions. It also shows the use of conditions to determine which toggle button in an option group has been selected on the form. Each action row is associated with a toggle button that selects the set of records starting with A, B, C, and so on, or all records. This macro should be attached to the **AfterUpdate** event of the CompanyNameFilter option group.</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="919db-120">条件</span><span class="sxs-lookup"><span data-stu-id="919db-120">Condition</span></span></p></th>
<th><p><span data-ttu-id="919db-121">操作</span><span class="sxs-lookup"><span data-stu-id="919db-121">Action</span></span></p></th>
<th><p><span data-ttu-id="919db-122">参数：设置</span><span class="sxs-lookup"><span data-stu-id="919db-122">Arguments: Setting</span></span></p></th>
<th><p><span data-ttu-id="919db-123">Comment</span><span class="sxs-lookup"><span data-stu-id="919db-123">Comment</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="919db-124">[公司名称筛选器] = 1</span><span class="sxs-lookup"><span data-stu-id="919db-124">[Company Name Filters] =1</span></span></p></td>
<td><p><span data-ttu-id="919db-125"><strong>ApplyFilter</strong></span><span class="sxs-lookup"><span data-stu-id="919db-125"><strong>ApplyFilter</strong></span></span></p></td>
<td><p><span data-ttu-id="919db-126"><strong>Where 条件</strong>: [公司名称] Like &quot;[AÀÁÂÃÄ] \*&quot;</span><span class="sxs-lookup"><span data-stu-id="919db-126"><strong>Where Condition</strong>: [Company Name] Like &quot;[AÀÁÂÃÄ]\*&quot;</span></span></p></td>
<td><p><span data-ttu-id="919db-127">筛选以 A、À、Á、Â、Ã 或 Ä 开头的公司名称。</span><span class="sxs-lookup"><span data-stu-id="919db-127">Filter for company names that start with A, À, Á, Â, Ã, or Ä.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="919db-128">[公司名称筛选器] = 2</span><span class="sxs-lookup"><span data-stu-id="919db-128">[Company Name Filters] =2</span></span></p></td>
<td><p><span data-ttu-id="919db-129"><strong>ApplyFilter</strong></span><span class="sxs-lookup"><span data-stu-id="919db-129"><strong>ApplyFilter</strong></span></span></p></td>
<td><p><span data-ttu-id="919db-130"><strong>Where 条件</strong>: [公司名称] Like &quot;B \*&quot;</span><span class="sxs-lookup"><span data-stu-id="919db-130"><strong>Where Condition</strong>: [Company Name] Like &quot;B\*&quot;</span></span></p></td>
<td><p><span data-ttu-id="919db-131">筛选以 B 开头的公司名称。</span><span class="sxs-lookup"><span data-stu-id="919db-131">Filter for company names that start with B.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="919db-132">[公司名称筛选器] = 3</span><span class="sxs-lookup"><span data-stu-id="919db-132">[Company Name Filters] =3</span></span></p></td>
<td><p><span data-ttu-id="919db-133"><strong>ApplyFilter</strong></span><span class="sxs-lookup"><span data-stu-id="919db-133"><strong>ApplyFilter</strong></span></span></p></td>
<td><p><span data-ttu-id="919db-134"><strong>Where 条件</strong>: [公司名称] Like &quot;[CÇ] \*&quot;</span><span class="sxs-lookup"><span data-stu-id="919db-134"><strong>Where Condition</strong>: [Company Name] Like &quot;[CÇ]\*&quot;</span></span></p></td>
<td><p><span data-ttu-id="919db-135">筛选以 C 或 Ç 开头的公司名称。</span><span class="sxs-lookup"><span data-stu-id="919db-135">Filter for company names that start with C or Ç.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="919db-136">... D 到 Y 的操作行与 A 到 C 的操作行具有相同的格式 ...</span><span class="sxs-lookup"><span data-stu-id="919db-136">... Action rows for D through Y have the same format as A through C ...</span></span></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="919db-137">[公司名称筛选器] = 26</span><span class="sxs-lookup"><span data-stu-id="919db-137">[Company Name Filters] =26</span></span></p></td>
<td><p><span data-ttu-id="919db-138"><strong>ApplyFilter</strong></span><span class="sxs-lookup"><span data-stu-id="919db-138"><strong>ApplyFilter</strong></span></span></p></td>
<td><p><span data-ttu-id="919db-139"><strong>Where 条件</strong>: [公司名称] Like &quot;[ZÆØÅ] \*&quot;</span><span class="sxs-lookup"><span data-stu-id="919db-139"><strong>Where Condition</strong>: [Company Name] Like &quot;[ZÆØÅ]\*&quot;</span></span></p></td>
<td><p><span data-ttu-id="919db-140">筛选以 Z、Æ、Ø 或 Å 开头的公司名称。</span><span class="sxs-lookup"><span data-stu-id="919db-140">Filter for company names that start with Z, Æ, Ø, or Å.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="919db-141">[公司名称筛选器] = 27</span><span class="sxs-lookup"><span data-stu-id="919db-141">[Company Name Filters] =27</span></span></p></td>
<td><p><span data-ttu-id="919db-142"><strong>ShowAllRecords</strong></span><span class="sxs-lookup"><span data-stu-id="919db-142"><strong>ShowAllRecords</strong></span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="919db-143">显示所有记录。</span><span class="sxs-lookup"><span data-stu-id="919db-143">Show all records.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="919db-144">[RecordsetClone]。RecordCount&gt;0</span><span class="sxs-lookup"><span data-stu-id="919db-144">[RecordsetClone].[RecordCount]&gt;0</span></span></p></td>
<td><p><span data-ttu-id="919db-145"><strong>GoToControl</strong></span><span class="sxs-lookup"><span data-stu-id="919db-145"><strong>GoToControl</strong></span></span></p></td>
<td><p><span data-ttu-id="919db-146"><strong>控件名称</strong>: 公司名称</span><span class="sxs-lookup"><span data-stu-id="919db-146"><strong>Control Name</strong>: CompanyName</span></span></p></td>
<td><p><span data-ttu-id="919db-147">如果返回了针对所选字母的记录，则将焦点移到“公司名称”控件上。</span><span class="sxs-lookup"><span data-stu-id="919db-147">If records are returned for the selected letter, move focus to the CompanyName control.</span></span></p></td>
</tr>
</tbody>
</table>

