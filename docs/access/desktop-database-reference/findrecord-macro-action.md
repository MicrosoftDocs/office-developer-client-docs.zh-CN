---
title: FindRecord 宏操作
TOCTitle: FindRecord macro action
ms:assetid: 379e3dda-cb7d-a294-29b1-c6ce9a62ba8a
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192494(v=office.15)
ms:contentKeyID: 48544199
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm7496
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 086993095daef3ff4ad87aed9f572a09124a9d31
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28709969"
---
# <a name="findrecord-macro-action"></a><span data-ttu-id="4103e-102">FindRecord 宏操作</span><span class="sxs-lookup"><span data-stu-id="4103e-102">FindRecord macro action</span></span>

<span data-ttu-id="4103e-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="4103e-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="4103e-p101">可以使用 **FindRecord** 操作查找符合由 **FindRecord** 参数指定的条件的第一个数据实例。此数据可能在当前记录中，也可能在当前记录之前或之后的记录中，或者在第一条记录中。您可以在活动表数据表、查询数据表、窗体数据表或窗体中查找记录。</span><span class="sxs-lookup"><span data-stu-id="4103e-p101">You can use the **FindRecord** action to find the first instance of data that meets the criteria specified by the **FindRecord** arguments. This data can be in the current record, in a succeeding or prior record, or in the first record. You can find records in the active table datasheet, query datasheet, form datasheet, or form.</span></span>

## <a name="setting"></a><span data-ttu-id="4103e-107">设置</span><span class="sxs-lookup"><span data-stu-id="4103e-107">Setting</span></span>

<span data-ttu-id="4103e-108">**FindRecord** 操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="4103e-108">The **FindRecord** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="4103e-109">操作参数</span><span class="sxs-lookup"><span data-stu-id="4103e-109">Action argument</span></span></p></th>
<th><p><span data-ttu-id="4103e-110">说明</span><span class="sxs-lookup"><span data-stu-id="4103e-110">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4103e-111"><strong>查找内容</strong></span><span class="sxs-lookup"><span data-stu-id="4103e-111"><strong>Find What</strong></span></span></p></td>
<td><p><span data-ttu-id="4103e-112">指定要在记录中查找的数据。</span><span class="sxs-lookup"><span data-stu-id="4103e-112">Specifies the data you want to find in the record.</span></span> <span data-ttu-id="4103e-113">输入文本、 数字或日期您想要查找或键入一个表达式，前面带有等号 (<strong>=</strong>)，在宏生成器窗格的<strong>操作参数</strong>部分的<strong>查找内容</strong>框中。</span><span class="sxs-lookup"><span data-stu-id="4103e-113">Enter the text, number, or date you want to find or type an expression, which is preceded by an equal sign (<strong>=</strong>), in the <strong>Find What</strong> box in the <strong>Action Arguments</strong> section of the Macro Builder pane.</span></span> <span data-ttu-id="4103e-114">可以使用通配符。</span><span class="sxs-lookup"><span data-stu-id="4103e-114">You can use wildcard characters.</span></span> <span data-ttu-id="4103e-115">这是一个必选参数。</span><span class="sxs-lookup"><span data-stu-id="4103e-115">This is a required argument.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4103e-116"><strong>匹配</strong></span><span class="sxs-lookup"><span data-stu-id="4103e-116"><strong>Match</strong></span></span></p></td>
<td><p><span data-ttu-id="4103e-p103">指定数据在字段中的位置。可以指定搜索位于字段任何部分的数据（<strong>“字段任何部分”</strong>）、填充整个字段的数据（<strong>“整个字段”</strong>）或位于字段开头的数据（<strong>“字段开头”</strong>）。默认值为<strong>“整个字段”</strong>。</span><span class="sxs-lookup"><span data-stu-id="4103e-p103">Specifies where the data is located in the field. You can specify a search for data in any part of the field (<strong>Any Part of Field</strong>), for data that fills the entire field (<strong>Whole Field</strong>), or for data located at the beginning of the field (<strong>Start of Field</strong>). The default is <strong>Whole Field</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4103e-120"><strong>区分大小写</strong></span><span class="sxs-lookup"><span data-stu-id="4103e-120"><strong>Match Case</strong></span></span></p></td>
<td><p><span data-ttu-id="4103e-p104">指定搜索是否区分大小写。请单击 <strong>"是"</strong>（执行区分大小写的搜索）或 <strong>"否"</strong>（进行搜索时不精确匹配大写和小写字母）。默认值为 <strong>"否"</strong>。  </span><span class="sxs-lookup"><span data-stu-id="4103e-p104">Specifies whether the search is case-sensitive. Click <strong>Yes</strong> (conduct a case-sensitive search) or <strong>No</strong> (search without matching uppercase and lowercase letters exactly). The default is <strong>No</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4103e-124"><strong>搜索</strong></span><span class="sxs-lookup"><span data-stu-id="4103e-124"><strong>Search</strong></span></span></p></td>
<td><p><span data-ttu-id="4103e-p105">指定搜索方式：从当前记录开始向上搜索到记录开头（<strong>“向上”</strong>）；向下搜索到记录末尾（<strong>“向下”</strong>）；或者向下搜索到记录末尾，然后再从记录开头开始搜索到当前记录，从而搜索所有记录（<strong>“全部”</strong>）。默认值为<strong>“全部”</strong>。</span><span class="sxs-lookup"><span data-stu-id="4103e-p105">Specifies whether the search proceeds from the current record up to the beginning of the records (<strong>Up</strong>); down to the end of the records (<strong>Down</strong>); or down to the end of the records and then from the beginning of the records to the current record, so all records are searched (<strong>All</strong>). The default is <strong>All</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4103e-127"><strong>格式化搜索</strong></span><span class="sxs-lookup"><span data-stu-id="4103e-127"><strong>Search As Formatted</strong></span></span></p></td>
<td><p><span data-ttu-id="4103e-128">指定搜索是否包括带格式的数据。</span><span class="sxs-lookup"><span data-stu-id="4103e-128">Specifies whether the search includes formatted data.</span></span> <span data-ttu-id="4103e-129">单击<strong>是</strong>（Microsoft Office Access 2007 将按其格式并显示在字段中搜索数据） 或<strong>否</strong>（存储在数据库中，这并不总是相同显示时，访问数据的搜索）。</span><span class="sxs-lookup"><span data-stu-id="4103e-129">Click <strong>Yes</strong> (Microsoft Office Access 2007 searches for the data as it is formatted and displayed in the field) or <strong>No</strong> (Access searches for the data as it is stored in the database, which isn't always the same as it's displayed).</span></span> <span data-ttu-id="4103e-130">默认值为 <strong>"否"</strong>。</span><span class="sxs-lookup"><span data-stu-id="4103e-130">The default is <strong>No</strong>.</span></span> <span data-ttu-id="4103e-131">此功能可用于将搜索限制为特定格式的数据。</span><span class="sxs-lookup"><span data-stu-id="4103e-131">You can use this feature to restrict the search to data in a particular format.</span></span> <span data-ttu-id="4103e-132">例如，单击<strong>是</strong>，并在<strong>查找内容</strong>参数来查找格式设置为包含逗号分隔的字段的值为 1234 键入<strong>1234</strong> 。</span><span class="sxs-lookup"><span data-stu-id="4103e-132">For example, click <strong>Yes</strong> and type <strong>1,234</strong> in the <strong>Find What</strong> argument to find a value of 1,234 in a field formatted to include commas.</span></span> <span data-ttu-id="4103e-133">如果您想要键入<strong>1234年</strong>以搜索此字段中的数据，请单击<strong>否</strong>。</span><span class="sxs-lookup"><span data-stu-id="4103e-133">Click <strong>No</strong> if you want to type <strong>1234</strong> to search for the data in this field.</span></span> <span data-ttu-id="4103e-134">要搜索日期，请单击<strong>是</strong>以查找完全按照它的格式设置，如 2003 年 7 月-08-的日期。</span><span class="sxs-lookup"><span data-stu-id="4103e-134">To search for dates, click <strong>Yes</strong> to find a date exactly as it is formatted, such as 08-July-2003.</span></span> <span data-ttu-id="4103e-135">如果您单击<strong>否</strong>，在 Windows 控制面板中的区域设置中设置的格式输入<strong>查找内容</strong>参数的日期。</span><span class="sxs-lookup"><span data-stu-id="4103e-135">If you click <strong>No</strong>, enter the date for the <strong>Find What</strong> argument in the format that is set in the regional settings in Windows Control Panel.</span></span> <span data-ttu-id="4103e-136">在区域设置中的<strong>日期</strong>选项卡上找到的<strong>短日期格式</strong>框中显示此格式。</span><span class="sxs-lookup"><span data-stu-id="4103e-136">This format is shown in the <strong>Short date format</strong> box found on the <strong>Date</strong> tab in the regional settings.</span></span> <span data-ttu-id="4103e-137">例如，如果<strong>短日期格式</strong>框设置为<strong>d/yy</strong>，可以输入 7/8/03，并对应于 2003 年 7 月 8 日，无论该字段的格式的日期字段中，Access 将查找的所有条目。</span><span class="sxs-lookup"><span data-stu-id="4103e-137">For example, if the <strong>Short date format</strong> box is set to <strong>M/d/yy</strong>, you can enter 7/8/03, and Access will find all entries in a Date field that correspond to July 8, 2003, regardless of how this field is formatted.</span></span></p>
<p><span data-ttu-id="4103e-138"><strong>注意</strong>：<strong>格式搜索</strong>参数才会生效，仅在当前字段是绑定的控件，如果<strong>匹配</strong>参数设置为<strong>整个字段</strong>，<strong>只搜索当前字段</strong>参数设置为<strong>是</strong>，和<strong>匹配案例</strong>参数设置为<strong>否</strong>。</span><span class="sxs-lookup"><span data-stu-id="4103e-138"><strong>NOTE</strong>: The <strong>Search As Formatted</strong> argument takes effect only if the current field is a bound control, the <strong>Match</strong> argument is set to <strong>Whole Field</strong>, the <strong>Only Current Field</strong> argument is set to <strong>Yes</strong>, and the <strong>Match Case</strong> argument is set to <strong>No</strong>.</span></span></p>
<p><span data-ttu-id="4103e-139">如果您设置为<strong>是</strong>或<strong>只搜索当前字段</strong>为<strong>否</strong><strong>区分大小写</strong>，还必须设置<strong>格式搜索</strong>为<strong>是</strong>。</span><span class="sxs-lookup"><span data-stu-id="4103e-139">If you set <strong>Match Case</strong> to <strong>Yes</strong> or <strong>Only Current Field</strong> to <strong>No</strong>, you must also set <strong>Search As Formatted</strong> to <strong>Yes</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4103e-140"><strong>只搜索当前字段</strong></span><span class="sxs-lookup"><span data-stu-id="4103e-140"><strong>Only Current Field</strong></span></span></p></td>
<td><p><span data-ttu-id="4103e-p107">指定是将搜索限制在每个记录内的当前字段，还是包括每个记录内的所有字段。在当前字段中进行搜索的速度更快。请单击 <strong>"是"</strong>（将搜索限制在当前字段）或 <strong>"否"</strong>（在每个记录内的所有字段中进行搜索）。默认值为 <strong>"是"</strong>。  </span><span class="sxs-lookup"><span data-stu-id="4103e-p107">Specifies whether the search is confined to the current field in each record or includes all fields in each record. Searching in the current field is faster. Click <strong>Yes</strong> (confine the search to the current field) or <strong>No</strong> (search in all fields in each record). The default is <strong>Yes</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4103e-145"><strong>查找第一个</strong></span><span class="sxs-lookup"><span data-stu-id="4103e-145"><strong>Find First</strong></span></span></p></td>
<td><p><span data-ttu-id="4103e-p108">指定搜索是从第一条记录开始，还是从当前记录开始。请单击 <strong>"是"</strong>（从第一条记录开始）或 <strong>"否"</strong>（从当前记录开始）。默认值为 <strong>"是"</strong>。  </span><span class="sxs-lookup"><span data-stu-id="4103e-p108">Specifies whether the search starts at the first record or at the current record. Click <strong>Yes</strong> (start at the first record) or <strong>No</strong> (start at the current record). The default is <strong>Yes</strong>.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="4103e-149">说明</span><span class="sxs-lookup"><span data-stu-id="4103e-149">Remarks</span></span>

<span data-ttu-id="4103e-150">当宏运行**FindRecord**操作时，访问搜索 （由**搜索**参数的设置确定的顺序搜索） 的记录中指定的数据。</span><span class="sxs-lookup"><span data-stu-id="4103e-150">When a macro runs the **FindRecord** action, Access searches for the specified data in the records (the order of the search is determined by the setting of the **Search** argument).</span></span> <span data-ttu-id="4103e-151">当访问找到指定的数据时，记录中选定的数据。</span><span class="sxs-lookup"><span data-stu-id="4103e-151">When Access finds the specified data, the data is selected in the record.</span></span>

<span data-ttu-id="4103e-p110">**FindRecord** 操作等效于在 **"开始"** 选项卡上单击 **"查找"**，其参数与 **"查找和替换"** 对话框中的选项相同。如果在"宏生成器"窗格中设置了 **FindRecord** 参数，然后运行宏，则您将看到单击 **"查找"** 时 **"查找和替换"** 对话框中选择的相应选项。</span><span class="sxs-lookup"><span data-stu-id="4103e-p110">The **FindRecord** action is equivalent to clicking **Find** on the **Home** tab, and its arguments are the same as the options in the **Find and Replace** dialog box. If you set the **FindRecord** arguments in the Macro Builder pane and then run the macro, you will see the corresponding options selected in the **Find and Replace** dialog box when you click **Find**.</span></span>

<span data-ttu-id="4103e-p111">在数据库会话过程中，Access 会保留最近的 **FindRecord** 参数，因而您在使用 **FindRecord** 操作执行后续操作时无需重复输入相同的条件。如果您将某个参数留空，Access 将使用该参数的最近设置，与在前一个 **FindRecord** 操作或 **"查找和替换"** 对话框中的设置相同。</span><span class="sxs-lookup"><span data-stu-id="4103e-p111">Access retains the most recent **FindRecord** arguments during a database session so that you don't need to enter the same criteria repeatedly as you perform subsequent operations with the **FindRecord** action. If you leave an argument blank, Access uses the most recent setting for the argument, as set either by a previous **FindRecord** action or in the **Find and Replace** dialog box.</span></span>

<span data-ttu-id="4103e-156">当需要使用宏查找记录时，请使用 **FindRecord** 操作，而不是其参数设置为运行 **"查找"** 命令的 **RunMenuCommand** 操作。</span><span class="sxs-lookup"><span data-stu-id="4103e-156">When you want to find a record by using a macro, use the **FindRecord** action, not the **RunMenuCommand** action with its argument set to run the **Find** command.</span></span>

> [!NOTE]
> <span data-ttu-id="4103e-p112">[!注释] 针对表、查询和窗体的 **FindRecord** 操作对应于 **"开始"** 选项卡上的 **"查找"** 命令，而不对应于"代码"窗口的 **"编辑"** 菜单上的 **"查找"** 命令。不能使用 **FindRecord** 操作在模块中搜索文本。</span><span class="sxs-lookup"><span data-stu-id="4103e-p112">While the **FindRecord** action corresponds to the **Find** command on the **Home** tab for tables, queries, and forms, it doesn't correspond to the **Find** command on the **Edit** menu in the Code window. You can't use the **FindRecord** action to search for text in modules.</span></span>

<span data-ttu-id="4103e-p113">在执行 **FindRecord** 操作时，如果当前选择的文本与搜索文本相同，则会从所选文本之后开始在包含该文本的同一字段和同一记录中进行搜索。否则将从当前记录的起始位置开始搜索。这样可以找到单个记录中可能出现的符合相同搜索条件的多个实例。</span><span class="sxs-lookup"><span data-stu-id="4103e-p113">If the currently selected text is the same as the search text at the time the **FindRecord** action is carried out, the search begins immediately following the selection in the same field as the selection, and in the same record. Otherwise, the search begins at the start of the current record. This enables you to find multiple instances of the same search criteria that might appear in a single record.</span></span>

<span data-ttu-id="4103e-p114">但请注意，如果使用命令按钮运行包含 **FindRecord** 操作的宏，则将重复找到搜索条件的第一个实例。出现这种情况的原因是，单击命令按钮会将焦点从包含匹配值的字段中移走。然后， **FindRecord** 操作将从记录开头开始搜索。为了避免此问题，请使用不更改焦点的技术（例如自定义工具栏按钮或在 AutoKeys 宏中定义的组合键）运行宏，或在执行 **FindRecord** 操作之前将宏中的焦点设置为包含搜索条件的字段。</span><span class="sxs-lookup"><span data-stu-id="4103e-p114">However, note that if you use a command button to run a macro containing the **FindRecord** action, the first instance of the search criteria will be found repeatedly. This behavior occurs because clicking the command button removes the focus from the field containing the matching value. The **FindRecord** action will then begin searching from the start of the record. To avoid this problem, run the macro by using a technique that doesn't change the focus, such as a custom toolbar button or a key combination defined in an AutoKeys macro, or set the focus in the macro to the field containing the search criteria before you carry out the **FindRecord** action.</span></span>

<table>
<thead>
<tr class="header">
<th><img src="media/access-alert-security.gif" title="安全说明" alt="Security note" /><span data-ttu-id="4103e-167"><strong>安全注释</strong></span><span class="sxs-lookup"><span data-stu-id="4103e-167"><strong>Security Note</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="4103e-p115">
      避免使用 <strong>SendKeys</strong> 语句或带敏感或机密信息的 AutoKeys 宏。恶意用户可能会拦截键击并损害您的计算机和数据的安全性。
</span><span class="sxs-lookup"><span data-stu-id="4103e-p115">Avoid using the <strong>SendKeys</strong> statement or an AutoKeys macro with sensitive or confidential information. A malicious user could intercept the keystrokes and compromise the security of your computer and data.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="4103e-170">如果使用命令按钮运行包含 **FindNext** 操作的宏，也会出现同样的情况。</span><span class="sxs-lookup"><span data-stu-id="4103e-170">The same behavior also occurs if you use a command button to run a macro containing the **FindNext** action.</span></span>

<span data-ttu-id="4103e-171">要在 Visual Basic for Applications (VBA) 模块中运行 **FindRecord** 操作，请使用 **DoCmd** 对象的 **FindRecord** 方法。</span><span class="sxs-lookup"><span data-stu-id="4103e-171">To run the **FindRecord** action in a Visual Basic for Applications (VBA) module, use the **FindRecord** method of the **DoCmd** object.</span></span>

<span data-ttu-id="4103e-172">要进行更加复杂的搜索，您可能需要使用 **SearchForRecord** 宏操作。</span><span class="sxs-lookup"><span data-stu-id="4103e-172">For more complex searches, you may want to use the **SearchForRecord** macro action.</span></span>

