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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32314642"
---
# <a name="searchforrecord-macro-action"></a><span data-ttu-id="fed05-102">SearchForRecord 宏操作</span><span class="sxs-lookup"><span data-stu-id="fed05-102">SearchForRecord macro action</span></span>


<span data-ttu-id="fed05-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="fed05-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="fed05-104">可以使用 **SearchForRecord** 操作在表、查询、窗体或报表中搜索特定记录。</span><span class="sxs-lookup"><span data-stu-id="fed05-104">You can use the **SearchForRecord** action to search for a specific record in a table, query, form or report.</span></span>

## <a name="setting"></a><span data-ttu-id="fed05-105">Setting</span><span class="sxs-lookup"><span data-stu-id="fed05-105">Setting</span></span>

<span data-ttu-id="fed05-106">**SearchForRecord** 操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="fed05-106">The **SearchForRecord** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="fed05-107">操作参数</span><span class="sxs-lookup"><span data-stu-id="fed05-107">Action argument</span></span></p></th>
<th><p><span data-ttu-id="fed05-108">说明</span><span class="sxs-lookup"><span data-stu-id="fed05-108">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fed05-109"><strong>对象类型</strong></span><span class="sxs-lookup"><span data-stu-id="fed05-109"><strong>Object Type</strong></span></span></p></td>
<td><p><span data-ttu-id="fed05-110">请输入或选择要在其中进行搜索的数据库对象的类型。</span><span class="sxs-lookup"><span data-stu-id="fed05-110">Enter or select the type of database object that you are searching in.</span></span> <span data-ttu-id="fed05-111">可以选择“表”<strong></strong>、“查询”<strong></strong>、“窗体”<strong></strong>或“报表”<strong></strong>。</span><span class="sxs-lookup"><span data-stu-id="fed05-111">You can select <strong>Table</strong>, <strong>Query</strong>, <strong>Form</strong>, or <strong>Report</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fed05-112"><strong>对象名称</strong></span><span class="sxs-lookup"><span data-stu-id="fed05-112"><strong>Object Name</strong></span></span></p></td>
<td><p><span data-ttu-id="fed05-p102">请输入或选择包含要搜索的记录的特定对象。下拉列表会显示属于您为“对象类型”<strong></strong>参数选择的类型的所有数据库对象。</span><span class="sxs-lookup"><span data-stu-id="fed05-p102">Enter or select the specific object that contains the record to search for. The drop-down list shows all database objects of the type you selected for the <strong>Object Type</strong> argument.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fed05-115"><strong>Record</strong></span><span class="sxs-lookup"><span data-stu-id="fed05-115"><strong>Record</strong></span></span></p></td>
<td><p><span data-ttu-id="fed05-116">指定搜索操作的起点和方向。</span><span class="sxs-lookup"><span data-stu-id="fed05-116">Specify the starting point and direction of the search.</span></span></p>
<div class="tableSection">
<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="fed05-117">Setting</span><span class="sxs-lookup"><span data-stu-id="fed05-117">Setting</span></span></p></th>
<th><p><span data-ttu-id="fed05-118">说明</span><span class="sxs-lookup"><span data-stu-id="fed05-118">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fed05-119"><strong>Previous</strong></span><span class="sxs-lookup"><span data-stu-id="fed05-119"><strong>Previous</strong></span></span></p></td>
<td><p><span data-ttu-id="fed05-120">从当前记录往上搜索。</span><span class="sxs-lookup"><span data-stu-id="fed05-120">Search backward from the current record.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fed05-121"><strong>Next</strong></span><span class="sxs-lookup"><span data-stu-id="fed05-121"><strong>Next</strong></span></span></p></td>
<td><p><span data-ttu-id="fed05-122">从当前记录往下搜索。</span><span class="sxs-lookup"><span data-stu-id="fed05-122">Search forward from the current record.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fed05-123"><strong>第一</strong></span><span class="sxs-lookup"><span data-stu-id="fed05-123"><strong>First</strong></span></span></p></td>
<td><p><span data-ttu-id="fed05-124">从第一条记录往下搜索。</span><span class="sxs-lookup"><span data-stu-id="fed05-124">Search forward from the first record.</span></span> <span data-ttu-id="fed05-125">这是此参数的默认值。</span><span class="sxs-lookup"><span data-stu-id="fed05-125">This is the default value for this argument.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fed05-126"><strong>最后一个</strong></span><span class="sxs-lookup"><span data-stu-id="fed05-126"><strong>Last</strong></span></span></p></td>
<td><p><span data-ttu-id="fed05-127">从最后一条记录往上搜索。</span><span class="sxs-lookup"><span data-stu-id="fed05-127">Search backward from the last record.</span></span></p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fed05-128"><strong>Where 条件</strong></span><span class="sxs-lookup"><span data-stu-id="fed05-128"><strong>Where Condition</strong></span></span></p></td>
<td><p><span data-ttu-id="fed05-129">使用与 SQL WHERE 子句相同的语法输入搜索条件, 而不是在其中包含单词&quot;where。&quot;</span><span class="sxs-lookup"><span data-stu-id="fed05-129">Enter the criteria for the search using the same syntax as an SQL WHERE clause, only without the word &quot;WHERE&quot;.</span></span> <span data-ttu-id="fed05-130">For example,</span><span class="sxs-lookup"><span data-stu-id="fed05-130">For example,</span></span></p>
<p>`Description = "Beverages"`</p>
<p><span data-ttu-id="fed05-131">若要创建包含来自窗体上的文本框的值的条件, 必须创建一个表达式, 将条件的第一部分与包含要搜索的值的文本框的名称相连接。</span><span class="sxs-lookup"><span data-stu-id="fed05-131">To create a criterion that includes a value from a text box on a form, you must create an expression that concatenates the first part of the criterion with the name of the text box containing the value for which to search.</span></span> <span data-ttu-id="fed05-132">例如，下面的条件将在“说明”字段中搜索名为 frmCategories 的窗体上的名为 txtDescription 的文本框中的值。</span><span class="sxs-lookup"><span data-stu-id="fed05-132">For example, the following criterion will search the Description field for the value in the text box named txtDescription on the form named frmCategories.</span></span> <span data-ttu-id="fed05-133">请注意, 表达式开头<strong>=</strong>的等号 () 以及文本框引用两侧使用单引号 (<strong>'</strong>) 的情况如下所示:</span><span class="sxs-lookup"><span data-stu-id="fed05-133">Note the equal sign (<strong>=</strong>) at the beginning of the expression, and the use of single quotation marks (<strong>'</strong>) on either side of the text box reference:</span></span></p>
<p>`="Description = ' " & Forms![frmCategories]![txtDescription] & "'"`</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="fed05-134">注解</span><span class="sxs-lookup"><span data-stu-id="fed05-134">Remarks</span></span>

- <span data-ttu-id="fed05-135">如果有多条记录符合“Where 条件”\*\*\*\* 参数中的条件，则最终会找到哪一条记录将由下列因素决定：</span><span class="sxs-lookup"><span data-stu-id="fed05-135">In cases where more than one record matches the criteria in the **Where Condition** argument, the following factors determine which record is found:</span></span>
    
  - <span data-ttu-id="fed05-136">**Record 参数设置**有关**Record**参数的详细信息, 请参阅 "设置" 部分中的表。</span><span class="sxs-lookup"><span data-stu-id="fed05-136">**The Record argument setting**See the table in the Settings section for more information about the **Record** argument.</span></span>
    
  - <span data-ttu-id="fed05-137">**记录的排序顺序**例如, 如果**Record**参数设置为**First**, 则更改记录的排序顺序可能会更改找到的记录。</span><span class="sxs-lookup"><span data-stu-id="fed05-137">**The sort order of the records**For example, if the **Record** argument is set to **First**, changing the sort order of the records might change which record is found.</span></span>

- <span data-ttu-id="fed05-p106">The object specified in the **Object Name** argument must be open before this action is run. Otherwise, an error occurs.</span><span class="sxs-lookup"><span data-stu-id="fed05-p106">The object specified in the **Object Name** argument must be open before this action is run. Otherwise, an error occurs.</span></span>

- <span data-ttu-id="fed05-140">If the criteria in the **Where Condition** argument are not met, no error occurs and the focus remains on the current record.</span><span class="sxs-lookup"><span data-stu-id="fed05-140">If the criteria in the **Where Condition** argument are not met, no error occurs and the focus remains on the current record.</span></span>

- <span data-ttu-id="fed05-p107">When searching for the previous or next record, the search does not "wrap" when it reaches the end of the data. If there are no further records that match the criteria, no error occurs and the focus remains on the current record. To confirm that a match was found, you can enter a condition for the next action, and make the condition the same as the criteria in the **Where Condition** argument.</span><span class="sxs-lookup"><span data-stu-id="fed05-p107">When searching for the previous or next record, the search does not "wrap" when it reaches the end of the data. If there are no further records that match the criteria, no error occurs and the focus remains on the current record. To confirm that a match was found, you can enter a condition for the next action, and make the condition the same as the criteria in the **Where Condition** argument.</span></span>

- <span data-ttu-id="fed05-144">要在 VBA 模块中运行 **SearchForRecord** 操作，请使用 **DoCmd** 对象的 **SearchForRecord** 方法。</span><span class="sxs-lookup"><span data-stu-id="fed05-144">To run the **SearchForRecord** action in a VBA module, use the **SearchForRecord** method of the **DoCmd** object.</span></span>

- <span data-ttu-id="fed05-p108">**SearchForRecord** 操作类似于 **[FindRecord](findrecord-macro-action.md)** 操作，但 **SearchForRecord** 的搜索功能更加强大。 **FindRecord** 操作主要用于查找字符串，其功能与 **"查找"** 对话框相同。 **SearchForRecord** 操作使用的条件更像是筛选或 SQL 查询的条件。下面的列表显示了可以通过 **SearchForRecord** 操作执行的一些操作：</span><span class="sxs-lookup"><span data-stu-id="fed05-p108">The **SearchForRecord** action is similar to the **[FindRecord](findrecord-macro-action.md)** action, but **SearchForRecord** has more powerful search features. The **FindRecord** action is primarily used for finding strings, and it duplicates the functionality of the **Find** dialog box. The **SearchForRecord** action uses criteria that are more like those of a filter or an SQL query. The following list demonstrates some things you can do with the **SearchForRecord** action:</span></span>
    
  - <span data-ttu-id="fed05-149">可以在“Where 条件”\*\*\*\* 参数中使用复杂条件，例如</span><span class="sxs-lookup"><span data-stu-id="fed05-149">You can use complex criteria in the **Where Condition** argument, such as</span></span>
        
    `Description = "Beverages" and CategoryID = 11`
    
  - <span data-ttu-id="fed05-150">可以引用位于窗体或报表的记录源中但没有在窗体或报表上显示的字段。</span><span class="sxs-lookup"><span data-stu-id="fed05-150">You can refer to fields that are in the record source of a form or report but aren't displayed on the form or report.</span></span> <span data-ttu-id="fed05-151">在上面的示例中, 说明和类别 id 都必须显示在窗体或报表上, 条件才有效。</span><span class="sxs-lookup"><span data-stu-id="fed05-151">In the preceding example, neither Description nor CategoryID must be displayed on the form or report for the criteria to work.</span></span>
    
  - <span data-ttu-id="fed05-p110">可以使用逻辑运算符，例如 **\<** 、 **\>** 、 **AND** 、 **OR** 和 **BETWEEN** 。 **FindRecord** 操作仅匹配与被搜索字符串相同、以被搜索的字符串开头或者包含被搜索的字符串的字符串。</span><span class="sxs-lookup"><span data-stu-id="fed05-p110">You can use logical operators, such as **\<**, **\>**, **AND**, **OR**, and **BETWEEN**. The **FindRecord** action only matches strings that equal, start with, or contain the string being searched for.</span></span>

## <a name="example"></a><span data-ttu-id="fed05-154">示例</span><span class="sxs-lookup"><span data-stu-id="fed05-154">Example</span></span>

<span data-ttu-id="fed05-p111">下面的宏先使用 **OpenTable** 操作打开“类别”表，然后使用 **SearchForRecord** 操作找到表中的第一条记录，其中“说明”字段中为“饮料”。</span><span class="sxs-lookup"><span data-stu-id="fed05-p111">The following macro first opens the Categories table by using the **OpenTable** action. The macro then uses the **SearchForRecord** action to find the first record in the table where the Description field equals "Beverages."</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="fed05-157">操作</span><span class="sxs-lookup"><span data-stu-id="fed05-157">Action</span></span></p></th>
<th><p><span data-ttu-id="fed05-158">参数</span><span class="sxs-lookup"><span data-stu-id="fed05-158">Arguments</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fed05-159"><strong>OpenTable</strong></span><span class="sxs-lookup"><span data-stu-id="fed05-159"><strong>OpenTable</strong></span></span></p></td>
<td><p><span data-ttu-id="fed05-160"><strong>表名称</strong>: 类别<strong>视图</strong>: <strong>DatasheetData 模式</strong>:<strong>编辑</strong></span><span class="sxs-lookup"><span data-stu-id="fed05-160"><strong>Table Name</strong>: Categories<strong>View</strong>: <strong>DatasheetData Mode</strong>: <strong>Edit</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fed05-161"><strong>SearchForRecord</strong></span><span class="sxs-lookup"><span data-stu-id="fed05-161"><strong>SearchForRecord</strong></span></span></p></td>
<td><p><span data-ttu-id="fed05-162"><strong>对象类型</strong>: <strong>TableObject 名称</strong>: 类别<strong>记录</strong>: <strong>FirstWhere 条件</strong>: Description = &quot;饮料&quot;</span><span class="sxs-lookup"><span data-stu-id="fed05-162"><strong>Object Type</strong>: <strong>TableObject Name</strong>: Categories<strong>Record</strong>: <strong>FirstWhere Condition</strong>: Description = &quot;Beverages&quot;</span></span></p></td>
</tr>
</tbody>
</table>

