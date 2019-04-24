---
title: ApplyFilter 宏操作
TOCTitle: ApplyFilter macro action
ms:assetid: c63988c4-4506-cc51-98f7-478d1f3fe668
ms:mtpsurl: https://msdn.microsoft.com/library/Ff823130(v=office.15)
ms:contentKeyID: 48547623
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm79035
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: e79ab56778f9429e7f1a985f0f81864ae4363606
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32296995"
---
# <a name="applyfilter-macro-action"></a><span data-ttu-id="0a6ec-102">ApplyFilter 宏操作</span><span class="sxs-lookup"><span data-stu-id="0a6ec-102">ApplyFilter macro action</span></span>

<span data-ttu-id="0a6ec-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="0a6ec-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="0a6ec-p101">可以使用 **ApplyFilter** 操作对表、窗体或报表应用筛选、查询或 SQL WHERE 子句，以便对表、基础表或是窗体或报表查询中的记录进行限制或排序。对于报表，只能在由报表的 **OnOpen** 事件属性所指定的宏中使用此操作。</span><span class="sxs-lookup"><span data-stu-id="0a6ec-p101">You can use the **ApplyFilter** action to apply a filter, a query, or an SQL WHERE clause to a table, form, or report to restrict or sort the records in the table, or the records from the underlying table or query of the form or report. For reports, you can use this action only in a macro specified by the report's **OnOpen** event property.</span></span>

> [!NOTE]
> <span data-ttu-id="0a6ec-p102">[!注释] 只有在应用服务器筛选时，才可以使用该操作以应用 SQL WHERE 子句。服务器筛选不能应用于存储过程记录源。</span><span class="sxs-lookup"><span data-stu-id="0a6ec-p102">You can use this action to apply an SQL WHERE clause only when applying a server filter. A server filter cannot be applied to a stored procedure's record source.</span></span>

## <a name="setting"></a><span data-ttu-id="0a6ec-108">Setting</span><span class="sxs-lookup"><span data-stu-id="0a6ec-108">Setting</span></span>

<span data-ttu-id="0a6ec-109">**ApplyFilter** 操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="0a6ec-109">The **ApplyFilter** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="0a6ec-110">操作参数</span><span class="sxs-lookup"><span data-stu-id="0a6ec-110">Action argument</span></span></p></th>
<th><p><span data-ttu-id="0a6ec-111">说明</span><span class="sxs-lookup"><span data-stu-id="0a6ec-111">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0a6ec-112">Filter Name</span><span class="sxs-lookup"><span data-stu-id="0a6ec-112">Filter Name</span></span></p></td>
<td><p><span data-ttu-id="0a6ec-113">用于对表、窗体或报表中的记录进行限制或排序的筛选或查询的名称。</span><span class="sxs-lookup"><span data-stu-id="0a6ec-113">The name of a filter or query that restricts or sorts the records of the table, form, or report.</span></span> <span data-ttu-id="0a6ec-114">可以在 "<strong>宏生成器</strong>" 窗格的 "<strong>操作参数</strong>" 部分的 "<strong>筛选名称</strong>" 框中输入已作为查询保存的现有查询或筛选器的名称。</span><span class="sxs-lookup"><span data-stu-id="0a6ec-114">You can enter the name of either an existing query or a filter that has been saved as a query in the <strong>Filter Name</strong> box in the <strong>Action Arguments</strong> section of the <strong>Macro Builder</strong> pane.</span></span></p><p><span data-ttu-id="0a6ec-115"><strong>注意</strong>: 使用此操作应用服务器筛选器时, 筛选器名称参数必须为空。</span><span class="sxs-lookup"><span data-stu-id="0a6ec-115"><strong>NOTE</strong>: When you are using this action to apply a server filter, the Filter Name argument must be blank.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a6ec-116">Where 条件</span><span class="sxs-lookup"><span data-stu-id="0a6ec-116">Where Condition</span></span></p></td>
<td><p><span data-ttu-id="0a6ec-117">用于限制表、窗体或报表中的记录的有效 SQL WHERE 子句（不含单词 WHERE）或表达式。</span><span class="sxs-lookup"><span data-stu-id="0a6ec-117">A valid SQL WHERE clause (without the word WHERE) or an expression that restricts the records of the table, form, or report.</span></span></p>
<p><span data-ttu-id="0a6ec-118"><b>注意</b>: 在 Where 条件参数表达式中, 表达式的左侧通常包含来自窗体或报表的基础表或查询中的字段名称。</span><span class="sxs-lookup"><span data-stu-id="0a6ec-118"><b>NOTE</b>: In a Where Condition argument expression, the left side of the expression typically contains a field name from the underlying table or query for the form or report.</span></span> <span data-ttu-id="0a6ec-119">表达式的右侧则通常包含要向此字段应用以对记录进行限制或排序的条件。</span><span class="sxs-lookup"><span data-stu-id="0a6ec-119">The right side of the expression typically contains the criteria you want to apply to this field to restrict or sort the records.</span></span> <span data-ttu-id="0a6ec-120">例如，条件可以是另一个窗体上某个控件的名称，该控件包含要让第一个窗体中的记录与之匹配的值。</span><span class="sxs-lookup"><span data-stu-id="0a6ec-120">For example, the criteria can be the name of a control on another form that contains the value you want the records in the first form to match.</span></span> <span data-ttu-id="0a6ec-121">该控件的名称应完全限定，例如：</span><span class="sxs-lookup"><span data-stu-id="0a6ec-121">The name of the control should be fully qualified, for example:</span></span></p>
<p><span data-ttu-id="0a6ec-122"><strong>Forms</strong>!<em>formname</em>!<em>controlname</em>字段名应括在双引号中, 而字符串文本应括在单引号中。</span><span class="sxs-lookup"><span data-stu-id="0a6ec-122"><strong>Forms</strong>!<em>formname</em>!<em>controlname</em> Field names should be surrounded by double quotation marks and string literals should be surrounded by single quotation marks.</span></span> <span data-ttu-id="0a6ec-123">“Where 条件”参数的最大长度为 255 个字符。</span><span class="sxs-lookup"><span data-stu-id="0a6ec-123">The maximum length of the Where Condition argument is 255 characters.</span></span> <span data-ttu-id="0a6ec-124">如果需要输入更长的 SQL WHERE 子句，请使用 Visual Basic for Applications (VBA) 模块中 <strong>DoCmd</strong> 对象的 <strong>ApplyFilter</strong> 方法。</span><span class="sxs-lookup"><span data-stu-id="0a6ec-124">If you need to enter a longer SQL WHERE clause, use the <strong>ApplyFilter</strong> method of the <strong>DoCmd</strong> object in a Visual Basic for Applications (VBA) module.</span></span> <span data-ttu-id="0a6ec-125">在 VBA 中，可输入长达 32,768 个字符的 SQL WHERE 子句语句。</span><span class="sxs-lookup"><span data-stu-id="0a6ec-125">You can enter SQL WHERE clause statements of up to 32,768 characters in VBA.</span></span></p></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="0a6ec-126">You can use the Filter Name argument if you have already defined a filter that provides the appropriate data.</span><span class="sxs-lookup"><span data-stu-id="0a6ec-126">You can use the Filter Name argument if you have already defined a filter that provides the appropriate data.</span></span> <span data-ttu-id="0a6ec-127">也可以直接使用“Where 条件”参数来输入限制条件。</span><span class="sxs-lookup"><span data-stu-id="0a6ec-127">You can use the Where Condition argument to enter the restriction criteria directly.</span></span> <span data-ttu-id="0a6ec-128">If you use both arguments, Microsoft Office Access 2007 applies the WHERE clause to the results of the filter.</span><span class="sxs-lookup"><span data-stu-id="0a6ec-128">If you use both arguments, Microsoft Office Access 2007 applies the WHERE clause to the results of the filter.</span></span> <span data-ttu-id="0a6ec-129">必须使用这两个参数之一，或同时使用它们。</span><span class="sxs-lookup"><span data-stu-id="0a6ec-129">You must use one or both arguments.</span></span>

## <a name="remarks"></a><span data-ttu-id="0a6ec-130">注解</span><span class="sxs-lookup"><span data-stu-id="0a6ec-130">Remarks</span></span>

<span data-ttu-id="0a6ec-131">可以对窗体视图或数据表视图中的窗体应用筛选或查询。</span><span class="sxs-lookup"><span data-stu-id="0a6ec-131">You can apply a filter or query to a form in Form view or Datasheet view.</span></span>

<span data-ttu-id="0a6ec-132">所应用的筛选和 WHERE 条件将成为窗体或报表的 **"Filter"** 或 **"ServerFilter"** 属性设置。</span><span class="sxs-lookup"><span data-stu-id="0a6ec-132">The filter and WHERE condition you apply become the setting of the form's or report's **Filter** or **ServerFilter** property.</span></span>

<span data-ttu-id="0a6ec-p107">对于表和窗体，此操作类似于单击 **"记录"** 菜单上的 **"应用筛选/排序"** 或 **"应用服务器筛选"**。菜单命令会向表或窗体应用最近创建的筛选，而 **ApplyFilter** 操作则应用指定的筛选或查询。</span><span class="sxs-lookup"><span data-stu-id="0a6ec-p107">For tables and forms, this action is similar to clicking **Apply Filter/Sort** or **Apply Server Filter** on the **Records** menu. The menu command applies the most recently created filter to the table or form, whereas the **ApplyFilter** action applies a specified filter or query.</span></span>

<span data-ttu-id="0a6ec-135">在数据库中，如果在运行 **ApplyFilter** 操作后指向 **"记录"** 菜单上的 **"筛选"** 并单击 **"高级筛选/排序"**，"高级筛选/排序"窗口将显示您使用此操作选择的筛选条件。</span><span class="sxs-lookup"><span data-stu-id="0a6ec-135">In an Access database, if you point to **Filter** on the **Records** menu and then click **Advanced Filter/Sort** after running the **ApplyFilter** action, the Advanced Filter/Sort window shows the filter criteria you have selected with this action.</span></span>

<span data-ttu-id="0a6ec-p108">要在 Office Access 2007 数据库中删除筛选并显示表或窗体的所有记录，可以使用 **ShowAllRecords** 操作或 **"记录"** 菜单上的 **"取消筛选/排序"** 命令。要在 Microsoft Access 项目 (.adp) 中删除筛选，可以返回到"按窗体服务器筛选"窗口并删除所有的筛选条件，然后在工具栏的 **"记录"** 菜单上单击 **"应用服务器筛选"**，也可以将 **"ServerFilterByForm"** 属性设置为 **"False"**(0)。</span><span class="sxs-lookup"><span data-stu-id="0a6ec-p108">To remove a filter and display all of the records for a table or form in an Office Access 2007 database, you can use the **ShowAllRecords** action or the **Remove Filter/Sort** command on the **Records** menu. To remove a filter in an Access project (.adp), you can return to the Server Filter By Form window and remove all filter criteria and then click **Apply Server Filter** on the **Records** menu on the toolbar, or set the **ServerFilterByForm** property to **False** (0).</span></span>

<span data-ttu-id="0a6ec-p109">在保存表或窗体时，Access 会保存当前在该对象中定义的任何筛选，但不会在下次打开该对象时自动应用筛选（不过，它会自动应用保存该对象之前应用的任何排序）。如果要在首次打开某个窗体时自动应用筛选，请指定一个包含 **ApplyFilter** 操作的宏，或指定一个包含 **DoCmd** 对象的 **ApplyFilter** 方法的事件过程，并将其作为该窗体的 **OnOpen** 事件属性设置。您也可以使用 **OpenForm** 操作、 **OpenReport** 操作或与它们相对应的方法应用筛选。要在首次打开某个表时自动应用筛选，可以使用接连包含 **OpenTable** 操作和 **ApplyFilter** 操作的宏打开该表。</span><span class="sxs-lookup"><span data-stu-id="0a6ec-p109">When you save a table or form, Access saves any filter currently defined in that object, but won't apply the filter automatically the next time the object is opened (although it will automatically apply any sort you applied to the object before it was saved). If you want to apply a filter automatically when a form is first opened, specify a macro containing the **ApplyFilter** action or an event procedure containing the **ApplyFilter** method of the **DoCmd** object as the **OnOpen** event property setting of the form. You can also apply a filter by using the **OpenForm** or **OpenReport** action, or their corresponding methods. To apply a filter automatically when a table is first opened, you can open the table by using a macro containing the **OpenTable** action, followed immediately by the **ApplyFilter** action.</span></span>

## <a name="example"></a><span data-ttu-id="0a6ec-142">示例</span><span class="sxs-lookup"><span data-stu-id="0a6ec-142">Example</span></span>

<span data-ttu-id="0a6ec-143">下面的示例演示如何使用 ApplyFilter 操作在 frmFoods 表单打开时对其进行筛选。</span><span class="sxs-lookup"><span data-stu-id="0a6ec-143">The following example shows how to use the ApplyFilter action to filter the frmFoods form as it is opened.</span></span>

<span data-ttu-id="0a6ec-144">**示例代码提供方：**[Microsoft Access 2010 程序员参考](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。</span><span class="sxs-lookup"><span data-stu-id="0a6ec-144">**Sample code provided by** the [Microsoft Access 2010 Programmer’s Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125).</span></span>

```vb
    OpenForm
        Form Name sfrmFoods
        View Form
        Filter Name
        Where Condition
        Data Mode
        Window Mode Normal
    
    ApplyFilter
        Filter Name
        Where Condition=[display_name] Link "*cheese*"
        Control Name
```



