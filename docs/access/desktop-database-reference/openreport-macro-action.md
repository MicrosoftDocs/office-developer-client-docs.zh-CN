---
title: OpenReport 宏操作
TOCTitle: OpenReport macro action
ms:assetid: cd35faf2-190d-ac48-cf59-81c1599eb764
ms:mtpsurl: https://msdn.microsoft.com/library/Ff834462(v=office.15)
ms:contentKeyID: 48547758
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm188079
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: cff57a185d226328792bef79072dfc46c6134f98
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288348"
---
# <a name="openreport-macro-action"></a><span data-ttu-id="7d3bb-102">OpenReport 宏操作</span><span class="sxs-lookup"><span data-stu-id="7d3bb-102">OpenReport macro action</span></span>

<span data-ttu-id="7d3bb-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="7d3bb-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="7d3bb-p101">可以使用 **OpenReport** 操作在设计视图或打印预览中打开报表，或者将报表直接发送到打印机。此外还可以限制要从报表中打印的记录。</span><span class="sxs-lookup"><span data-stu-id="7d3bb-p101">You can use the **OpenReport** action to open a report in Design view or Print Preview, or to send the report directly to the printer. You can also restrict the records that are printed in the report.</span></span>

## <a name="setting"></a><span data-ttu-id="7d3bb-106">Setting</span><span class="sxs-lookup"><span data-stu-id="7d3bb-106">Setting</span></span>

<span data-ttu-id="7d3bb-107">**OpenReport** 操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="7d3bb-107">The **OpenReport** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="7d3bb-108">操作参数</span><span class="sxs-lookup"><span data-stu-id="7d3bb-108">Action argument</span></span></p></th>
<th><p><span data-ttu-id="7d3bb-109">说明</span><span class="sxs-lookup"><span data-stu-id="7d3bb-109">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7d3bb-110">报表名称</span><span class="sxs-lookup"><span data-stu-id="7d3bb-110">Report Name</span></span></p></td>
<td><p><span data-ttu-id="7d3bb-111">要打开的报表的名称。</span><span class="sxs-lookup"><span data-stu-id="7d3bb-111">The name of the report to open.</span></span> <span data-ttu-id="7d3bb-112">"<strong>宏生成器</strong>" 窗格的 "<strong>操作参数</strong>" 部分的 "<strong>报告名称</strong>" 框中显示了当前数据库中的所有报告。</span><span class="sxs-lookup"><span data-stu-id="7d3bb-112">The <strong>Report Name</strong> box in the <strong>Action Arguments</strong> section of the <strong>Macro Builder</strong> pane shows all reports in the current database.</span></span> <span data-ttu-id="7d3bb-113">这是一个必选参数。</span><span class="sxs-lookup"><span data-stu-id="7d3bb-113">This is a required argument.</span></span> <span data-ttu-id="7d3bb-114">如果在类库数据库中运行包含 OpenReport 操作的宏，Microsoft Access 将先在该类库数据库中查找具有此名称的报表，然后再在当前数据库中查找。</span><span class="sxs-lookup"><span data-stu-id="7d3bb-114">If you run a macro containing the OpenReport action in a library database, Microsoft Access first looks for the report with this name in the library database, and then in the current database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d3bb-115">View</span><span class="sxs-lookup"><span data-stu-id="7d3bb-115">View</span></span></p></td>
<td><p><span data-ttu-id="7d3bb-p103">打开报表时将使用的视图。请在<strong>“视图”</strong>框中单击<strong>“打印”</strong>（立即打印报表）、<strong>“设计”</strong>或<strong>“打印预览”</strong>。默认值为<strong>“打印”</strong>。</span><span class="sxs-lookup"><span data-stu-id="7d3bb-p103">The view in which the report will open. Click <strong>Print</strong> (print the report immediately), <strong>Design</strong>, or <strong>Print Preview</strong> in the <strong>View</strong> box. The default is <strong>Print</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d3bb-119">筛选名称</span><span class="sxs-lookup"><span data-stu-id="7d3bb-119">Filter Name</span></span></p></td>
<td><p><span data-ttu-id="7d3bb-p104">用于限制报表记录的筛选。您可以输入现有查询的名称，也可以输入另存为查询的筛选的名称。但是，该查询必须包括要打开的报表中的所有字段，或必须将其 <strong>OutputAllFields</strong> 属性设置为“是”<strong></strong>。</span><span class="sxs-lookup"><span data-stu-id="7d3bb-p104">A filter that restricts the report's records. You can enter the name of either an existing query or a filter that was saved as a query. However, the query must include all the fields in the report you are opening or have its <strong>OutputAllFields</strong> property set to <strong>Yes</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d3bb-123">Where 条件</span><span class="sxs-lookup"><span data-stu-id="7d3bb-123">Where Condition</span></span></p></td>
<td><p><span data-ttu-id="7d3bb-124">Access 用于从报表的基础表或查询中选择记录的有效 SQL WHERE 子句（不含单词 WHERE）或表达式。</span><span class="sxs-lookup"><span data-stu-id="7d3bb-124">A valid SQL WHERE clause (without the word WHERE) or expression that Access uses to select records from the report's underlying table or query.</span></span> <span data-ttu-id="7d3bb-125">如果您通过“筛选名称”参数选择筛选，Access 会将此 WHERE 子句应用于筛选的结果。</span><span class="sxs-lookup"><span data-stu-id="7d3bb-125">If you select a filter with the Filter Name argument, Access applies this WHERE clause to the results of the filter.</span></span> <span data-ttu-id="7d3bb-126">要打开报表并将其记录限制为由某个窗体控件的值指定的记录，请使用以下表达式：</span><span class="sxs-lookup"><span data-stu-id="7d3bb-126">To open a report and restrict its records to those specified by the value of a control on a form, use the following expression:</span></span><br /><span data-ttu-id="7d3bb-127">
<strong>[</strong><em>fieldname</em><strong>] = Forms![</strong><em>formname</em><strong>]![</strong><em>controlname on form</em><strong>]</strong></span><span class="sxs-lookup"><span data-stu-id="7d3bb-127">
<strong>[</strong><em>fieldname</em><strong>] = Forms![</strong><em>formname</em><strong>]![</strong><em>controlname on form</em><strong>]</strong></span></span><br />
<span data-ttu-id="7d3bb-128">将<em>fieldname</em>替换为要打开的报表的基础表或查询中的字段的名称。</span><span class="sxs-lookup"><span data-stu-id="7d3bb-128">Replace <em>fieldname</em> with the name of a field in the underlying table or query of the report you want to open.</span></span> <span data-ttu-id="7d3bb-129">将窗体<em>上</em>的<em>formname</em>和 controlname 替换为窗体的名称和窗体上包含您希望报表中的记录匹配的值的控件。</span><span class="sxs-lookup"><span data-stu-id="7d3bb-129">Replace <em>formname</em> and <em>controlname on form</em> with the name of the form and the control on the form that contains the value you want records in the report to match.</span></span></p>
<p><span data-ttu-id="7d3bb-130"><b>注意</b>: Where Condition 参数的最大长度为255个字符。</span><span class="sxs-lookup"><span data-stu-id="7d3bb-130"><b>NOTE</b>: The maximum length of the Where Condition argument is 255 characters.</span></span> <span data-ttu-id="7d3bb-131">如果需要输入超过此限制的更复杂的 SQL WHERE 子句，请改用 Visual Basic for Applications (VBA) 模块中 <b>DoCmd</b> 对象的 <b>OpenReport</b> 方法。</span><span class="sxs-lookup"><span data-stu-id="7d3bb-131">If you need to enter a more complex SQL WHERE clause longer than this, use the <b>OpenReport</b> method of the <b>DoCmd</b> object in a Visual Basic for Applications (VBA) module instead.</span></span> <span data-ttu-id="7d3bb-132">在 VBA 中，可输入长达 32,768 个字符的 SQL WHERE 子句语句。</span><span class="sxs-lookup"><span data-stu-id="7d3bb-132">You can enter SQL WHERE clause statements of up to 32,768 characters in VBA.</span></span></p>
</td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d3bb-133">窗口模式</span><span class="sxs-lookup"><span data-stu-id="7d3bb-133">Window Mode</span></span></p></td>
<td><p><span data-ttu-id="7d3bb-134">打开报表时将使用的模式。</span><span class="sxs-lookup"><span data-stu-id="7d3bb-134">The mode in which the report will open.</span></span> <span data-ttu-id="7d3bb-135">在<strong>窗口模式</strong>框中单击 "<strong>常规</strong>"、"<strong>隐藏</strong>"、"<strong>图标</strong>" 或 "<strong>对话框</strong>"。</span><span class="sxs-lookup"><span data-stu-id="7d3bb-135">Click <strong>Normal</strong>, <strong>Hidden</strong>, <strong>Icon</strong>, or <strong>Dialog</strong> in the <strong>Window Mode</strong> box.</span></span> <span data-ttu-id="7d3bb-136">默认值为<strong>“普通”</strong>。</span><span class="sxs-lookup"><span data-stu-id="7d3bb-136">The default is <strong>Normal</strong>.</span></span></p>
<p><span data-ttu-id="7d3bb-137"><b>注意</b>: 使用选项卡式文档时, 某些窗口模式参数设置不适用。</span><span class="sxs-lookup"><span data-stu-id="7d3bb-137"><b>NOTE</b>: Some Window Mode argument settings do not apply when using tabbed documents.</span></span> <span data-ttu-id="7d3bb-138">要切换到重叠窗口，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="7d3bb-138">To switch to overlapping windows:</span></span>
<ol>
<li><p><span data-ttu-id="7d3bb-139">单击 <strong>"选项"</strong>。</span><span class="sxs-lookup"><span data-stu-id="7d3bb-139">Click <strong>Options</strong>.</span></span></p></li>
<li><p><span data-ttu-id="7d3bb-140">在<strong>“Access 选项”</strong>对话框中，单击<strong>“当前数据库”</strong>。</span><span class="sxs-lookup"><span data-stu-id="7d3bb-140">In the <strong>Access Options</strong> dialog box, click <strong>Current Database</strong>.</span></span></p></li>
<li><p><span data-ttu-id="7d3bb-141">在<strong>“应用程序选项”</strong>部分中的<strong>“文档窗口选项”</strong>下，单击<strong>“重叠窗口”</strong>。</span><span class="sxs-lookup"><span data-stu-id="7d3bb-141">In the <strong>Application Options</strong> section, under <strong>Document Window Options</strong>, click <strong>Overlapping Windows</strong>.</span></span></p></li>
<li><p><span data-ttu-id="7d3bb-142">单击<strong>"确定</strong>", 然后关闭并重新打开数据库。</span><span class="sxs-lookup"><span data-stu-id="7d3bb-142">Click <strong>OK</strong>, and then close and reopen the database.</span></span></p></li>
</ol>
</td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="7d3bb-143">注解</span><span class="sxs-lookup"><span data-stu-id="7d3bb-143">Remarks</span></span>

<span data-ttu-id="7d3bb-p110">The **Print** setting for the **View** argument prints the report immediately by using the current printer settings, without bringing up the **Print** dialog box. You can also use the **OpenReport** action to open and set up a report and then use the PrintOut action to print it. For example, you may want to modify the report or use the **PrintOut** action to change the printer settings before you print.</span><span class="sxs-lookup"><span data-stu-id="7d3bb-p110">The **Print** setting for the **View** argument prints the report immediately by using the current printer settings, without bringing up the **Print** dialog box. You can also use the **OpenReport** action to open and set up a report and then use the PrintOut action to print it. For example, you may want to modify the report or use the **PrintOut** action to change the printer settings before you print.</span></span>

<span data-ttu-id="7d3bb-147">所应用的筛选和 WHERE 条件将成为报表的 **Filter** 属性设置。</span><span class="sxs-lookup"><span data-stu-id="7d3bb-147">The filter and WHERE condition you apply become the setting of the report's **Filter** property.</span></span>

<span data-ttu-id="7d3bb-148">**OpenReport** 操作类似于在导航窗格中双击报表，或是在导航窗格中右键单击报表并选择视图或 **"打印"** 命令。</span><span class="sxs-lookup"><span data-stu-id="7d3bb-148">The **OpenReport** action is similar to double-clicking the report in the Navigation Pane, or right-clicking the report in the Navigation Pane and selecting a view or the **Print** command.</span></span>

> [!TIP] 
> - <span data-ttu-id="7d3bb-149">To print similar reports for different sets of data, use a filter or a WHERE clause to restrict the records printed in the report.</span><span class="sxs-lookup"><span data-stu-id="7d3bb-149">To print similar reports for different sets of data, use a filter or a WHERE clause to restrict the records printed in the report.</span></span> <span data-ttu-id="7d3bb-150">Then edit the macro to apply a different filter or change the Where Condition argument.</span><span class="sxs-lookup"><span data-stu-id="7d3bb-150">Then edit the macro to apply a different filter or change the Where Condition argument.</span></span>
> 
> - <span data-ttu-id="7d3bb-p112">您可以将报表从导航窗格拖至宏操作行。这会自动创建一个在"报表"视图中打开该报表的 **OpenReport** 操作。</span><span class="sxs-lookup"><span data-stu-id="7d3bb-p112">You can drag a report from the Navigation Pane to a macro action row. This automatically creates an **OpenReport** action that opens the report in Report view.</span></span>

## <a name="example"></a><span data-ttu-id="7d3bb-153">示例</span><span class="sxs-lookup"><span data-stu-id="7d3bb-153">Example</span></span>

<span data-ttu-id="7d3bb-154">下面的示例演示如何使用 OpenReport 操作在打开时传递筛选报表的参数。</span><span class="sxs-lookup"><span data-stu-id="7d3bb-154">The following example shows how to use the OpenReport action to pass a parameter that filters a report as it is opened.</span></span> <span data-ttu-id="7d3bb-155">**rptChapters**报告通过将**cboAuthors**组合框中选定的项传递给 SelectedAuthor 参数, 来显示指定作者的记录。</span><span class="sxs-lookup"><span data-stu-id="7d3bb-155">The **rptChapters** report displays the records for the specified author by passing the item selected in the **cboAuthors** combo box to the SelectedAuthor parameter.</span></span>

<span data-ttu-id="7d3bb-156">**示例代码提供方：**[Microsoft Access 2010 程序员参考](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。</span><span class="sxs-lookup"><span data-stu-id="7d3bb-156">**Sample code provided by** the [Microsoft Access 2010 Programmer’s Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125).</span></span>

```vb
    OpenReport
        Report Name rptChapters
        View Report
        Filter Name
        Where Condition
        Window Mode Normal
    
    Parameters
        SelectedAuthor =[cboAuthor]
```
