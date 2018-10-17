---
title: Requery 宏操作
TOCTitle: Requery Macro Action
ms:assetid: 6dbdcae5-81b6-9925-4cad-64b178c23060
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195544(v=office.15)
ms:contentKeyID: 48545499
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm30402
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 9eea9445912b1a784d9926b2c044c4385a17ee69
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467957"
---
# <a name="requery-macro-action"></a><span data-ttu-id="e127b-102">Requery 宏操作</span><span class="sxs-lookup"><span data-stu-id="e127b-102">Requery Macro Action</span></span>


<span data-ttu-id="e127b-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="e127b-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="e127b-p101">可以使用 **Requery** 操作通过重新查询控件的数据源来更新活动数据库对象上指定控件中的数据。如果未指定任何控件，此操作将重新查询对象的数据源本身。使用此操作可以确保活动对象或它的其中一个控件显示的是最新数据。</span><span class="sxs-lookup"><span data-stu-id="e127b-p101">You can use the **Requery** action to update the data in a specified control on the active object by requerying the source of the control. If no control is specified, this action requeries the source of the object itself. Use this action to ensure that the active object or one of its controls displays the most current data.</span></span>

## <a name="setting"></a><span data-ttu-id="e127b-107">设置</span><span class="sxs-lookup"><span data-stu-id="e127b-107">Setting</span></span>

<span data-ttu-id="e127b-108">**Requery** 操作具有以下参数。</span><span class="sxs-lookup"><span data-stu-id="e127b-108">The **Requery** action has the following argument.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="e127b-109">操作参数</span><span class="sxs-lookup"><span data-stu-id="e127b-109">Action argument</span></span></p></th>
<th><p><span data-ttu-id="e127b-110">说明</span><span class="sxs-lookup"><span data-stu-id="e127b-110">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e127b-111"><strong>控件名称</strong></span><span class="sxs-lookup"><span data-stu-id="e127b-111"><strong>Control Name</strong></span></span></p></td>
<td><p><span data-ttu-id="e127b-p102">要更新的控件的名称。请在“宏生成器”窗格<strong>“操作参数”</strong>部分的<strong>“控件名称”</strong>框中输入控件名称。只应使用控件的名称，而不是完全限定的标识符（例如，<strong>Forms</strong>!<em>窗体名称</em>!<em>控件名称</em>）。将此参数留空可重新查询活动对象的数据源。如果活动对象是数据表或查询结果集，则必须将此参数留空。</span><span class="sxs-lookup"><span data-stu-id="e127b-p102">The name of the control you want to update. Enter the control name in the <strong>Control Name</strong> box in the <strong>Action Arguments</strong> section of the Macro Builder pane. You should use only the name of the control, not the fully qualified identifier (such as <strong>Forms</strong>!<em>formname</em>!<em>controlname</em>). Leave this argument blank to requery the source of the active object. If the active object is a datasheet or a query result set, you must leave this argument blank.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="e127b-117">说明</span><span class="sxs-lookup"><span data-stu-id="e127b-117">Remarks</span></span>

<span data-ttu-id="e127b-118">**Requery** 操作执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="e127b-118">The **Requery** action does one of the following:</span></span>

  - <span data-ttu-id="e127b-119">返回控件或对象所基于的查询。</span><span class="sxs-lookup"><span data-stu-id="e127b-119">Reruns the query on which the control or object is based.</span></span>

  - <span data-ttu-id="e127b-120">显示所有新的或更改的记录，并从控件或对象所基于的表中删除所有已删除的记录。</span><span class="sxs-lookup"><span data-stu-id="e127b-120">Displays any new or changed records, and removes any deleted records from the table on which the control or object is based.</span></span>


> [!NOTE]
> <P><span data-ttu-id="e127b-121">[!注释] <STRONG>Requery</STRONG> 操作不影响记录指针的位置。</span><span class="sxs-lookup"><span data-stu-id="e127b-121">The <STRONG>Requery</STRONG> action does not affect the position of the record pointer.</span></span></P>



<span data-ttu-id="e127b-122">基于查询或表的控件包括：</span><span class="sxs-lookup"><span data-stu-id="e127b-122">Controls based on a query or table include:</span></span>

  - <span data-ttu-id="e127b-123">列表框和组合框。</span><span class="sxs-lookup"><span data-stu-id="e127b-123">List boxes and combo boxes.</span></span>

  - <span data-ttu-id="e127b-124">子窗体/子报表控件。</span><span class="sxs-lookup"><span data-stu-id="e127b-124">Subform controls.</span></span>

  - <span data-ttu-id="e127b-125">OLE 对象，如图表。</span><span class="sxs-lookup"><span data-stu-id="e127b-125">OLE objects, such as charts.</span></span>

  - <span data-ttu-id="e127b-126">包含域聚合函数的控件，如 **DSum** 。</span><span class="sxs-lookup"><span data-stu-id="e127b-126">Controls containing domain aggregate functions, such as **DSum**.</span></span>

<span data-ttu-id="e127b-127">如果指定的控件并不基于查询或表，此操作将强行对该控件进行重新计算。</span><span class="sxs-lookup"><span data-stu-id="e127b-127">If the specified control isn't based on a query or table, this action forces a recalculation of the control.</span></span>

<span data-ttu-id="e127b-128">如果将**控件名称**参数留空，则**Requery**操作具有对象具有焦点时按 SHIFT + F9 相同的效果。</span><span class="sxs-lookup"><span data-stu-id="e127b-128">If you leave the **Control Name** argument blank, the **Requery** action has the same effect as pressing SHIFT+F9 when the object has the focus.</span></span> <span data-ttu-id="e127b-129">如果子窗体控件具有焦点，该操作将只重新查询子窗体的数据源（就像按 Shift+F9 一样）。</span><span class="sxs-lookup"><span data-stu-id="e127b-129">If a subform control has the focus, this action requeries only the source of the subform (just as pressing SHIFT+F9 does).</span></span>


> [!NOTE]
> <P><span data-ttu-id="e127b-p104">[!注释] <STRONG>Requery</STRONG> 操作重新查询控件或对象的数据源。而 <STRONG>RepaintObject</STRONG> 操作重画则指定对象中的控件，但不重新查询数据库或者显示新记录。 <STRONG>ShowAllRecords</STRONG> 操作不仅重新查询活动对象，它还删除所有已应用的筛选，而 <STRONG>Requery</STRONG> 操作不这么做。</span><span class="sxs-lookup"><span data-stu-id="e127b-p104">The <STRONG>Requery</STRONG> action requeries the source of the control or object. In contrast, the <STRONG>RepaintObject</STRONG> action repaints controls in the specified object but doesn't requery the database or display new records. The <STRONG>ShowAllRecords</STRONG> action not only requeries the active object, but it also removes any applied filters, which the <STRONG>Requery</STRONG> action doesn't do.</span></span></P>



<span data-ttu-id="e127b-p105">如果要重新查询的控件不在活动对象上，则必须在 Visual Basic for Applications (VBA) 模块中使用 **Requery** 方法，而不是使用 **Requery** 操作或者与之对应的 **DoCmd** 对象的 **Requery** 方法。VBA 中的 **Requery** 方法比 **Requery** 操作或 **DoCmd.Requery** 方法更快。此外，在使用 **Requery** 操作或 **DoCmd.Requery** 方法时，Microsoft Access 会关闭查询并从数据库中重新加载它，但在使用 **Requery** 方法时，Access 会重新运行查询，而不关闭并重新加载它。请注意，ActiveX 数据对象 (ADO) **Requery** 方法与 Access **Requery** 方法的工作方式相同。</span><span class="sxs-lookup"><span data-stu-id="e127b-p105">If you want to requery a control that isn't on the active object, you must use the **Requery** method in a Visual Basic for Applications (VBA) module, not the **Requery** action or its corresponding **Requery** method of the **DoCmd** object. The **Requery** method in VBA is faster than the **Requery** action or the **DoCmd.Requery** method. In addition, when you use the **Requery** action or the **DoCmd.Requery** method, Microsoft Access closes the query and reloads it from the database, but when you use the **Requery** method, Access reruns the query without closing and reloading it. Note that the ActiveX Data Object (ADO) **Requery** method works the same way as the Access **Requery** method.</span></span>
