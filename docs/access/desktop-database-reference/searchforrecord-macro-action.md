---
title: SearchForRecord 宏操作
TOCTitle: SearchForRecord macro action
ms:assetid: a3483c41-adb5-5923-55f4-1a3c4f60cb2f
ms:mtpsurl: https://msdn.microsoft.com/library/Ff821023(v=office.15)
ms:contentKeyID: 48546781
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm118713
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: efa763a77250e1d5c617358f31421804c772468b
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28702108"
---
# <a name="searchforrecord-macro-action"></a><span data-ttu-id="c9002-102">SearchForRecord 宏操作</span><span class="sxs-lookup"><span data-stu-id="c9002-102">SearchForRecord macro action</span></span>


<span data-ttu-id="c9002-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="c9002-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="c9002-104">可以使用 **SearchForRecord** 操作在表、查询、窗体或报表中搜索特定记录。</span><span class="sxs-lookup"><span data-stu-id="c9002-104">You can use the **SearchForRecord** action to search for a specific record in a table, query, form or report.</span></span>

## <a name="setting"></a><span data-ttu-id="c9002-105">设置</span><span class="sxs-lookup"><span data-stu-id="c9002-105">Setting</span></span>

<span data-ttu-id="c9002-106">**SearchForRecord** 操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="c9002-106">The **SearchForRecord** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="c9002-107">操作参数</span><span class="sxs-lookup"><span data-stu-id="c9002-107">Action argument</span></span></p></th>
<th><p><span data-ttu-id="c9002-108">说明</span><span class="sxs-lookup"><span data-stu-id="c9002-108">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c9002-109"><strong>对象类型</strong></span><span class="sxs-lookup"><span data-stu-id="c9002-109"><strong>Object Type</strong></span></span></p></td>
<td><p><span data-ttu-id="c9002-110">输入或选择要搜索中的数据库对象的类型。</span><span class="sxs-lookup"><span data-stu-id="c9002-110">Enter or select the type of database object that you are searching in.</span></span> <span data-ttu-id="c9002-111">您可以选择<strong>表</strong>、<strong>查询</strong>、<strong>窗体</strong>或<strong>报表</strong>。</span><span class="sxs-lookup"><span data-stu-id="c9002-111">You can select <strong>Table</strong>, <strong>Query</strong>, <strong>Form</strong>, or <strong>Report</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9002-112"><strong>对象名称</strong></span><span class="sxs-lookup"><span data-stu-id="c9002-112"><strong>Object Name</strong></span></span></p></td>
<td><p><span data-ttu-id="c9002-113">输入或选择包含要搜索的记录的特定对象。</span><span class="sxs-lookup"><span data-stu-id="c9002-113">Enter or select the specific object that contains the record to search for.</span></span> <span data-ttu-id="c9002-114">下拉列表显示所选的<strong>对象类型</strong>参数类型的所有数据库对象。</span><span class="sxs-lookup"><span data-stu-id="c9002-114">The drop-down list shows all database objects of the type you selected for the <strong>Object Type</strong> argument.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9002-115"><strong>Record</strong></span><span class="sxs-lookup"><span data-stu-id="c9002-115"><strong>Record</strong></span></span></p></td>
<td><p><span data-ttu-id="c9002-116">指定搜索操作的起点和方向。</span><span class="sxs-lookup"><span data-stu-id="c9002-116">Specify the starting point and direction of the search.</span></span></p>
<div class="tableSection">
<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="c9002-117">设置</span><span class="sxs-lookup"><span data-stu-id="c9002-117">Setting</span></span></p></th>
<th><p><span data-ttu-id="c9002-118">说明</span><span class="sxs-lookup"><span data-stu-id="c9002-118">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c9002-119"><strong>Previous</strong></span><span class="sxs-lookup"><span data-stu-id="c9002-119"><strong>Previous</strong></span></span></p></td>
<td><p><span data-ttu-id="c9002-120">从当前记录往上搜索。</span><span class="sxs-lookup"><span data-stu-id="c9002-120">Search backward from the current record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9002-121"><strong>Next</strong></span><span class="sxs-lookup"><span data-stu-id="c9002-121"><strong>Next</strong></span></span></p></td>
<td><p><span data-ttu-id="c9002-122">从当前记录往下搜索。</span><span class="sxs-lookup"><span data-stu-id="c9002-122">Search forward from the current record.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9002-123"><strong>第一</strong></span><span class="sxs-lookup"><span data-stu-id="c9002-123"><strong>First</strong></span></span></p></td>
<td><p><span data-ttu-id="c9002-p103">从第一条记录往下搜索。这是此参数的默认值。</span><span class="sxs-lookup"><span data-stu-id="c9002-p103">Search forward from the first record. This is the default value for this argument.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9002-126"><strong>最后一个</strong></span><span class="sxs-lookup"><span data-stu-id="c9002-126"><strong>Last</strong></span></span></p></td>
<td><p><span data-ttu-id="c9002-127">从最后一条记录往上搜索。</span><span class="sxs-lookup"><span data-stu-id="c9002-127">Search backward from the last record.</span></span></p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9002-128"><strong>Where 条件</strong></span><span class="sxs-lookup"><span data-stu-id="c9002-128"><strong>Where Condition</strong></span></span></p></td>
<td><p><span data-ttu-id="c9002-129">输入作为 SQL WHERE 子句，只是不 word 使用相同的语法的搜索条件&quot;其中&quot;。</span><span class="sxs-lookup"><span data-stu-id="c9002-129">Enter the criteria for the search using the same syntax as an SQL WHERE clause, only without the word &quot;WHERE&quot;.</span></span> <span data-ttu-id="c9002-130">例如，</span><span class="sxs-lookup"><span data-stu-id="c9002-130">For example,</span></span></p>
<p>`Description = "Beverages"`</p>
<p><span data-ttu-id="c9002-131">若要创建包含中窗体上的文本框的值的条件，必须创建组合条件的第一部分包含要搜索的值的文本框同名的表达式。</span><span class="sxs-lookup"><span data-stu-id="c9002-131">To create a criterion that includes a value from a text box on a form, you must create an expression that concatenates the first part of the criterion with the name of the text box containing the value for which to search.</span></span> <span data-ttu-id="c9002-132">例如，以下条件将名为 txtDescription 名为 frmCategories 窗体上的文本框中搜索说明字段值。</span><span class="sxs-lookup"><span data-stu-id="c9002-132">For example, the following criterion will search the Description field for the value in the text box named txtDescription on the form named frmCategories.</span></span> <span data-ttu-id="c9002-133">请注意等号 (<strong>=</strong>) 的表达式，并使用单引号 （<strong>'</strong>） 在文本框引用任意一侧开头：</span><span class="sxs-lookup"><span data-stu-id="c9002-133">Note the equal sign (<strong>=</strong>) at the beginning of the expression, and the use of single quotation marks (<strong>'</strong>) on either side of the text box reference:</span></span></p>
<p>`="Description = ' " & Forms![frmCategories]![txtDescription] & "'"`</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="c9002-134">说明</span><span class="sxs-lookup"><span data-stu-id="c9002-134">Remarks</span></span>

- <span data-ttu-id="c9002-135">在多个记录与**Where Condition**参数中的条件相匹配的情况下，以下因素将确定找到哪个记录：</span><span class="sxs-lookup"><span data-stu-id="c9002-135">In cases where more than one record matches the criteria in the **Where Condition** argument, the following factors determine which record is found:</span></span>
    
  - <span data-ttu-id="c9002-136">**Record 参数设置**请参阅有关**记录**参数的详细信息设置部分中的表。</span><span class="sxs-lookup"><span data-stu-id="c9002-136">**The Record argument setting**See the table in the Settings section for more information about the **Record** argument.</span></span>
    
  - <span data-ttu-id="c9002-137">**记录的排序顺序**例如，如果**记录**参数设置为**第一个**，更改的记录的排序顺序可能会更改找到哪个记录。</span><span class="sxs-lookup"><span data-stu-id="c9002-137">**The sort order of the records**For example, if the **Record** argument is set to **First**, changing the sort order of the records might change which record is found.</span></span>

- <span data-ttu-id="c9002-138">在运行此操作之前，必须打开**对象名称**参数中指定的对象。</span><span class="sxs-lookup"><span data-stu-id="c9002-138">The object specified in the **Object Name** argument must be open before this action is run.</span></span> <span data-ttu-id="c9002-139">否则，就会出错。</span><span class="sxs-lookup"><span data-stu-id="c9002-139">Otherwise, an error occurs.</span></span>

- <span data-ttu-id="c9002-140">如果不满足**Where Condition**参数中的条件，不会发生错误，焦点仍保留在当前记录。</span><span class="sxs-lookup"><span data-stu-id="c9002-140">If the criteria in the **Where Condition** argument are not met, no error occurs and the focus remains on the current record.</span></span>

- <span data-ttu-id="c9002-141">搜索时的上一个或下一条记录，搜索不"换行"时到达数据的结尾。</span><span class="sxs-lookup"><span data-stu-id="c9002-141">When searching for the previous or next record, the search does not "wrap" when it reaches the end of the data.</span></span> <span data-ttu-id="c9002-142">如果没有进一步记录符合条件，不会发生错误，焦点仍保留在当前记录。</span><span class="sxs-lookup"><span data-stu-id="c9002-142">If there are no further records that match the criteria, no error occurs and the focus remains on the current record.</span></span> <span data-ttu-id="c9002-143">若要确认已找到匹配项，可以为下一个操作中，输入一个条件和**Where Condition**参数中的条件相同使该条件。</span><span class="sxs-lookup"><span data-stu-id="c9002-143">To confirm that a match was found, you can enter a condition for the next action, and make the condition the same as the criteria in the **Where Condition** argument.</span></span>

- <span data-ttu-id="c9002-144">要在 VBA 模块中运行 **SearchForRecord** 操作，请使用 **DoCmd** 对象的 **SearchForRecord** 方法。</span><span class="sxs-lookup"><span data-stu-id="c9002-144">To run the **SearchForRecord** action in a VBA module, use the **SearchForRecord** method of the **DoCmd** object.</span></span>

- <span data-ttu-id="c9002-p108">**SearchForRecord** 操作类似于 **[FindRecord](findrecord-macro-action.md)** 操作，但 **SearchForRecord** 的搜索功能更加强大。 **FindRecord** 操作主要用于查找字符串，其功能与 **"查找"** 对话框相同。 **SearchForRecord** 操作使用的条件更像是筛选或 SQL 查询的条件。下面的列表显示了可以通过 **SearchForRecord** 操作执行的一些操作：</span><span class="sxs-lookup"><span data-stu-id="c9002-p108">The **SearchForRecord** action is similar to the **[FindRecord](findrecord-macro-action.md)** action, but **SearchForRecord** has more powerful search features. The **FindRecord** action is primarily used for finding strings, and it duplicates the functionality of the **Find** dialog box. The **SearchForRecord** action uses criteria that are more like those of a filter or an SQL query. The following list demonstrates some things you can do with the **SearchForRecord** action:</span></span>
    
  - <span data-ttu-id="c9002-149">您可以使用复杂条件中的**Where Condition**参数如</span><span class="sxs-lookup"><span data-stu-id="c9002-149">You can use complex criteria in the **Where Condition** argument, such as</span></span>
        
    `Description = "Beverages" and CategoryID = 11`
    
  - <span data-ttu-id="c9002-150">可以引用位于窗体或报表的记录源中但没有在窗体或报表上显示的字段。</span><span class="sxs-lookup"><span data-stu-id="c9002-150">You can refer to fields that are in the record source of a form or report but aren't displayed on the form or report.</span></span> <span data-ttu-id="c9002-151">在上述示例中，说明和 CategoryID 都不必须显示在窗体或报表的条件来处理。</span><span class="sxs-lookup"><span data-stu-id="c9002-151">In the preceding example, neither Description nor CategoryID must be displayed on the form or report for the criteria to work.</span></span>
    
  - <span data-ttu-id="c9002-p110">可以使用逻辑运算符，例如 **\<** 、 **\>** 、 **AND** 、 **OR** 和 **BETWEEN** 。 **FindRecord** 操作仅匹配与被搜索字符串相同、以被搜索的字符串开头或者包含被搜索的字符串的字符串。</span><span class="sxs-lookup"><span data-stu-id="c9002-p110">You can use logical operators, such as **\<**, **\>**, **AND**, **OR**, and **BETWEEN**. The **FindRecord** action only matches strings that equal, start with, or contain the string being searched for.</span></span>

## <a name="example"></a><span data-ttu-id="c9002-154">示例</span><span class="sxs-lookup"><span data-stu-id="c9002-154">Example</span></span>

<span data-ttu-id="c9002-p111">下面的宏先使用 **OpenTable** 操作打开"类别"表，然后使用 **SearchForRecord** 操作找到表中的第一条记录，其中"说明"字段中为"饮料"。</span><span class="sxs-lookup"><span data-stu-id="c9002-p111">The following macro first opens the Categories table by using the **OpenTable** action. The macro then uses the **SearchForRecord** action to find the first record in the table where the Description field equals "Beverages."</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="c9002-157">操作</span><span class="sxs-lookup"><span data-stu-id="c9002-157">Action</span></span></p></th>
<th><p><span data-ttu-id="c9002-158">参数</span><span class="sxs-lookup"><span data-stu-id="c9002-158">Arguments</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c9002-159"><strong>OpenTable</strong></span><span class="sxs-lookup"><span data-stu-id="c9002-159"><strong>OpenTable</strong></span></span></p></td>
<td><p><span data-ttu-id="c9002-160"><strong>表名称</strong>： 类别<strong>视图</strong>： <strong>DatasheetData 模式</strong>：<strong>编辑</strong></span><span class="sxs-lookup"><span data-stu-id="c9002-160"><strong>Table Name</strong>: Categories<strong>View</strong>: <strong>DatasheetData Mode</strong>: <strong>Edit</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9002-161"><strong>SearchForRecord</strong></span><span class="sxs-lookup"><span data-stu-id="c9002-161"><strong>SearchForRecord</strong></span></span></p></td>
<td><p><span data-ttu-id="c9002-162"><strong>对象类型</strong>： <strong>TableObject 名称</strong>： 类别<strong>记录</strong>： <strong>FirstWhere 条件</strong>： 说明 =&quot;饮料&quot;</span><span class="sxs-lookup"><span data-stu-id="c9002-162"><strong>Object Type</strong>: <strong>TableObject Name</strong>: Categories<strong>Record</strong>: <strong>FirstWhere Condition</strong>: Description = &quot;Beverages&quot;</span></span></p></td>
</tr>
</tbody>
</table>

