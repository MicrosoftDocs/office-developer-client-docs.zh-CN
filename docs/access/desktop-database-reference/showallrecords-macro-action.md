---
title: ShowAllRecords 宏操作
TOCTitle: ShowAllRecords macro action
ms:assetid: 6f9741ad-0440-4b8d-abea-009063c111f8
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195587(v=office.15)
ms:contentKeyID: 48545538
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: c4ea531de8c5b99c9ff85eacddcc79a596caebd5
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25922039"
---
# <a name="showallrecords-macro-action"></a><span data-ttu-id="8775f-102">ShowAllRecords 宏操作</span><span class="sxs-lookup"><span data-stu-id="8775f-102">ShowAllRecords macro action</span></span>


<span data-ttu-id="8775f-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="8775f-103">**Applies to**: Access 2013, Office 2013</span></span>


<span data-ttu-id="8775f-104">您可以使用**ShowAllRecords**操作从活动表、 查询结果集或窗体中，删除任何应用的筛选和显示在表或结果集或窗体的基础表或查询中的所有记录的所有记录。</span><span class="sxs-lookup"><span data-stu-id="8775f-104">You can use the **ShowAllRecords** action to remove any applied filter from the active table, query result set, or form, and display all records in the table or result set or all records in the form's underlying table or query.</span></span>

## <a name="setting"></a><span data-ttu-id="8775f-105">设置</span><span class="sxs-lookup"><span data-stu-id="8775f-105">Setting</span></span>

<span data-ttu-id="8775f-106">**ShowAllRecords**操作不具有任何参数。</span><span class="sxs-lookup"><span data-stu-id="8775f-106">The **ShowAllRecords** action doesn't have any arguments.</span></span>

## <a name="remarks"></a><span data-ttu-id="8775f-107">说明</span><span class="sxs-lookup"><span data-stu-id="8775f-107">Remarks</span></span>

<span data-ttu-id="8775f-108">此操作可用于确保表、 查询结果集，或窗体显示 （包括任何已更改或新记录） 的所有记录。</span><span class="sxs-lookup"><span data-stu-id="8775f-108">You can use this action to ensure that all records (including any changed or new records) are displayed for a table, query result set, or form.</span></span> <span data-ttu-id="8775f-109">此操作会重新查询窗体或子窗体的记录。</span><span class="sxs-lookup"><span data-stu-id="8775f-109">This action causes a requery of the records for a form or subform.</span></span>

<span data-ttu-id="8775f-110">您还可以使用此操作删除与**ApplyFilter**操作，**主页**选项卡或**筛选器名称**或**Where Condition**参数**OpenForm**操作的**筛选器**命令应用的任何筛选器。</span><span class="sxs-lookup"><span data-stu-id="8775f-110">You can also use this action to remove any filter that was applied with the **ApplyFilter** action, the **Filter** command on the **Home** tab, or the **Filter Name** or **Where Condition** argument of the **OpenForm** action.</span></span>

<span data-ttu-id="8775f-111">此操作的效果为单击的**主页**选项卡上，**切换筛选**或右键单击筛选的字段和窗体视图、 布局视图或数据表视图中，单击 **...清除从筛选器**。</span><span class="sxs-lookup"><span data-stu-id="8775f-111">This action has the same effect as clicking **Toggle Filter** on the **Home** tab, or right-clicking the filtered field and clicking **Clear filter from...** in Form view, Layout view, or Datasheet view.</span></span>

<span data-ttu-id="8775f-112">若要在 Visual Basic for Applications (VBA) 模块中运行**ShowAllRecords**操作，请使用**DoCmd**对象的**ShowAllRecords**方法。</span><span class="sxs-lookup"><span data-stu-id="8775f-112">To run the **ShowAllRecords** action in a Visual Basic for Applications (VBA) module, use the **ShowAllRecords** method of the **DoCmd** object.</span></span>

## <a name="example"></a><span data-ttu-id="8775f-113">示例</span><span class="sxs-lookup"><span data-stu-id="8775f-113">Example</span></span>

<span data-ttu-id="8775f-114">**使用宏应用筛选**</span><span class="sxs-lookup"><span data-stu-id="8775f-114">**Apply a filter by using a macro**</span></span>

<span data-ttu-id="8775f-p102">下面的宏包含一组操作，其中每项操作都会对"客户电话列表"窗体中的记录进行筛选。它演示如何使用 **ApplyFilter** 、 **ShowAllRecords** 和 **GoToControl** 操作。它还演示了如何使用条件来确定已在窗体的选项组中选择了哪个切换按钮。每个操作行都与一个切换按钮相关联，这些切换按钮分别用于选择以 A、B、C 等字母开头的一组记录或所有记录。此宏应附加到 CompanyNameFilter 选项组的 **AfterUpdate** 事件。</span><span class="sxs-lookup"><span data-stu-id="8775f-p102">The following macro contains a set of actions, each of which filters the records for a Customer Phone List form. It shows the use of the **ApplyFilter**, **ShowAllRecords**, and **GoToControl** actions. It also shows the use of conditions to determine which toggle button in an option group has been selected on the form. Each action row is associated with a toggle button that selects the set of records starting with A, B, C, and so on, or all records. This macro should be attached to the **AfterUpdate** event of the CompanyNameFilter option group.</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="8775f-120">条件</span><span class="sxs-lookup"><span data-stu-id="8775f-120">Condition</span></span></p></th>
<th><p><span data-ttu-id="8775f-121">操作</span><span class="sxs-lookup"><span data-stu-id="8775f-121">Action</span></span></p></th>
<th><p><span data-ttu-id="8775f-122">参数：设置</span><span class="sxs-lookup"><span data-stu-id="8775f-122">Arguments: Setting</span></span></p></th>
<th><p><span data-ttu-id="8775f-123">注释</span><span class="sxs-lookup"><span data-stu-id="8775f-123">Comment</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8775f-124">[公司名称筛选] = 1</span><span class="sxs-lookup"><span data-stu-id="8775f-124">[Company Name Filters] =1</span></span></p></td>
<td><p><span data-ttu-id="8775f-125"><strong>ApplyFilter</strong></span><span class="sxs-lookup"><span data-stu-id="8775f-125"><strong>ApplyFilter</strong></span></span></p></td>
<td><p><span data-ttu-id="8775f-126"><strong>Where 条件</strong>: [公司名称] 像&quot;[AÀÁÂÃÄ] \*&quot;</span><span class="sxs-lookup"><span data-stu-id="8775f-126"><strong>Where Condition</strong>: [Company Name] Like &quot;[AÀÁÂÃÄ]\*&quot;</span></span></p></td>
<td><p><span data-ttu-id="8775f-127">筛选以 A、À、Á、Â、Ã 或 Ä 开头的公司名称。</span><span class="sxs-lookup"><span data-stu-id="8775f-127">Filter for company names that start with A, À, Á, Â, Ã, or Ä.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8775f-128">[公司名称筛选] = 2</span><span class="sxs-lookup"><span data-stu-id="8775f-128">[Company Name Filters] =2</span></span></p></td>
<td><p><span data-ttu-id="8775f-129"><strong>ApplyFilter</strong></span><span class="sxs-lookup"><span data-stu-id="8775f-129"><strong>ApplyFilter</strong></span></span></p></td>
<td><p><span data-ttu-id="8775f-130"><strong>Where 条件</strong>: [公司名称] 像&quot;B \*&quot;</span><span class="sxs-lookup"><span data-stu-id="8775f-130"><strong>Where Condition</strong>: [Company Name] Like &quot;B\*&quot;</span></span></p></td>
<td><p><span data-ttu-id="8775f-131">筛选以 B 开头的公司名称。</span><span class="sxs-lookup"><span data-stu-id="8775f-131">Filter for company names that start with B.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8775f-132">[公司名称筛选] = 3</span><span class="sxs-lookup"><span data-stu-id="8775f-132">[Company Name Filters] =3</span></span></p></td>
<td><p><span data-ttu-id="8775f-133"><strong>ApplyFilter</strong></span><span class="sxs-lookup"><span data-stu-id="8775f-133"><strong>ApplyFilter</strong></span></span></p></td>
<td><p><span data-ttu-id="8775f-134"><strong>Where 条件</strong>: [公司名称] 像&quot;[CÇ] \*&quot;</span><span class="sxs-lookup"><span data-stu-id="8775f-134"><strong>Where Condition</strong>: [Company Name] Like &quot;[CÇ]\*&quot;</span></span></p></td>
<td><p><span data-ttu-id="8775f-135">筛选以 C 或 Ç 开头的公司名称。</span><span class="sxs-lookup"><span data-stu-id="8775f-135">Filter for company names that start with C or Ç.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8775f-136">... D 到 Y 的操作行与 A 到 C 的操作行具有相同的格式 ...</span><span class="sxs-lookup"><span data-stu-id="8775f-136">... Action rows for D through Y have the same format as A through C ...</span></span></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8775f-137">[公司名称筛选] = 26</span><span class="sxs-lookup"><span data-stu-id="8775f-137">[Company Name Filters] =26</span></span></p></td>
<td><p><span data-ttu-id="8775f-138"><strong>ApplyFilter</strong></span><span class="sxs-lookup"><span data-stu-id="8775f-138"><strong>ApplyFilter</strong></span></span></p></td>
<td><p><span data-ttu-id="8775f-139"><strong>Where 条件</strong>: [公司名称] 像&quot;[ZÆØÅ] \*&quot;</span><span class="sxs-lookup"><span data-stu-id="8775f-139"><strong>Where Condition</strong>: [Company Name] Like &quot;[ZÆØÅ]\*&quot;</span></span></p></td>
<td><p><span data-ttu-id="8775f-140">筛选以 Z、Æ、Ø 或 Å 开头的公司名称。</span><span class="sxs-lookup"><span data-stu-id="8775f-140">Filter for company names that start with Z, Æ, Ø, or Å.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8775f-141">[公司名称筛选] = 27</span><span class="sxs-lookup"><span data-stu-id="8775f-141">[Company Name Filters] =27</span></span></p></td>
<td><p><span data-ttu-id="8775f-142"><strong>ShowAllRecords</strong></span><span class="sxs-lookup"><span data-stu-id="8775f-142"><strong>ShowAllRecords</strong></span></span></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="8775f-143">显示所有记录。</span><span class="sxs-lookup"><span data-stu-id="8775f-143">Show all records.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8775f-144">[RecordsetClone]。[RecordCount]&gt;0</span><span class="sxs-lookup"><span data-stu-id="8775f-144">[RecordsetClone].[RecordCount]&gt;0</span></span></p></td>
<td><p><span data-ttu-id="8775f-145"><strong>GoToControl</strong></span><span class="sxs-lookup"><span data-stu-id="8775f-145"><strong>GoToControl</strong></span></span></p></td>
<td><p><span data-ttu-id="8775f-146"><strong>控件名称</strong>： 公司名称</span><span class="sxs-lookup"><span data-stu-id="8775f-146"><strong>Control Name</strong>: CompanyName</span></span></p></td>
<td><p><span data-ttu-id="8775f-147">如果返回了针对所选字母的记录，则将焦点移到“公司名称”控件上。</span><span class="sxs-lookup"><span data-stu-id="8775f-147">If records are returned for the selected letter, move focus to the CompanyName control.</span></span></p></td>
</tr>
</tbody>
</table>

