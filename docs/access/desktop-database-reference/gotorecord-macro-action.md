---
title: GoToRecord 宏操作
TOCTitle: GoToRecord Macro Action
ms:assetid: 76f936de-739b-63be-9b28-5b0e111408e6
ms:mtpsurl: https://msdn.microsoft.com/library/Ff196037(v=office.15)
ms:contentKeyID: 48545712
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm58124
f1_categories:
- Office.Version=v15
ms.openlocfilehash: f7094d95053e97180526523fd41862dfeb100c86
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468131"
---
# <a name="gotorecord-macro-action"></a><span data-ttu-id="489b5-102">GoToRecord 宏操作</span><span class="sxs-lookup"><span data-stu-id="489b5-102">GoToRecord Macro Action</span></span>


<span data-ttu-id="489b5-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="489b5-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="489b5-104">可以使用 **GoToRecord** 操作将指定记录设置为打开的表、窗体或查询结果集中的当前记录。</span><span class="sxs-lookup"><span data-stu-id="489b5-104">You can use the **GoToRecord** action to make the specified record the current record in an open table, form, or query result set.</span></span>

## <a name="setting"></a><span data-ttu-id="489b5-105">设置</span><span class="sxs-lookup"><span data-stu-id="489b5-105">Setting</span></span>

<span data-ttu-id="489b5-106">**GoToRecord** 操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="489b5-106">The **GoToRecord** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="489b5-107">操作参数</span><span class="sxs-lookup"><span data-stu-id="489b5-107">Action argument</span></span></p></th>
<th><p><span data-ttu-id="489b5-108">说明</span><span class="sxs-lookup"><span data-stu-id="489b5-108">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="489b5-109"><strong>对象类型</strong></span><span class="sxs-lookup"><span data-stu-id="489b5-109"><strong>Object Type</strong></span></span></p></td>
<td><p><span data-ttu-id="489b5-p101">要设置为当前记录的记录所在的数据库对象的类型。请在“宏生成器”窗格<strong>“操作参数”</strong>部分的<strong>“对象类型”</strong>框中单击<strong>“表”</strong>、<strong>“查询”</strong>、<strong>“窗体”</strong>、<strong>“服务器视图”</strong>、<strong>“存储过程”</strong>或<strong>“函数”</strong>。如果将此参数留空，则会选择活动对象。</span><span class="sxs-lookup"><span data-stu-id="489b5-p101">The type of object that contains the record you want to make current. Click <strong>Table</strong>, <strong>Query</strong>, <strong>Form</strong>, <strong>Server View</strong>, <strong>Stored Procedure</strong>, or <strong>Function</strong> in the <strong>Object Type</strong> box in the <strong>Action Arguments</strong> section of the Macro Builder pane. Leave this argument blank to select the active object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="489b5-113"><strong>对象名称</strong></span><span class="sxs-lookup"><span data-stu-id="489b5-113"><strong>Object Name</strong></span></span></p></td>
<td><p><span data-ttu-id="489b5-114">包含您要使成为当前记录的记录的对象的名称。</span><span class="sxs-lookup"><span data-stu-id="489b5-114">The name of the object that contains the record you want to make the current record.</span></span> <span data-ttu-id="489b5-115"><strong>对象名称</strong>框中显示<strong>对象类型</strong>参数所选类型为当前数据库中的所有对象。</span><span class="sxs-lookup"><span data-stu-id="489b5-115">The <strong>Object Name</strong> box shows all objects in the current database of the type selected by the <strong>Object Type</strong> argument.</span></span> <span data-ttu-id="489b5-116">如果将<strong>对象类型</strong>参数留空，还应将此参数留空。</span><span class="sxs-lookup"><span data-stu-id="489b5-116">If you leave the <strong>Object Type</strong> argument blank, leave this argument blank also.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="489b5-117"><strong>Record</strong></span><span class="sxs-lookup"><span data-stu-id="489b5-117"><strong>Record</strong></span></span></p></td>
<td><p><span data-ttu-id="489b5-p103">要设置为当前记录的记录。请单击<strong>“记录”</strong>框中的<strong>“上一个”</strong>、<strong>“下一个”</strong>、<strong>“第一个”</strong>、<strong>“最后一个”</strong>、<strong>“转至”</strong>或<strong>“新建”</strong>。默认值为<strong>“下一个”</strong>。</span><span class="sxs-lookup"><span data-stu-id="489b5-p103">The record to make the current record. Click <strong>Previous</strong>, <strong>Next</strong>, <strong>First</strong>, <strong>Last</strong>, <strong>Go To</strong>, or <strong>New</strong> in the <strong>Record</strong> box. The default is <strong>Next</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="489b5-121"><strong>Offset</strong></span><span class="sxs-lookup"><span data-stu-id="489b5-121"><strong>Offset</strong></span></span></p></td>
<td><p><span data-ttu-id="489b5-122">整数或计算结果为一个整数值的表达式。</span><span class="sxs-lookup"><span data-stu-id="489b5-122">An integer or expression that evaluates to an integer.</span></span> <span data-ttu-id="489b5-123">一个表达式前面必须有一个等号 (<strong>=</strong>)。</span><span class="sxs-lookup"><span data-stu-id="489b5-123">An expression must be preceded by an equal sign (<strong>=</strong>).</span></span> <span data-ttu-id="489b5-124">此参数指定要使成为当前记录的记录。</span><span class="sxs-lookup"><span data-stu-id="489b5-124">This argument specifies the record to make the current record.</span></span> <span data-ttu-id="489b5-125">您可以使用两种方式的<strong>偏移量</strong>参数：</span><span class="sxs-lookup"><span data-stu-id="489b5-125">You can use the <strong>Offset</strong> argument in two ways:</span></span></p>
<ul>
<li><p><span data-ttu-id="489b5-126">当<strong>记录</strong>参数为<strong>下一个</strong>或<strong>上一步</strong>时，Microsoft Office Access 2007 将移动向前或向后<strong>偏移</strong>参数中指定的记录数。</span><span class="sxs-lookup"><span data-stu-id="489b5-126">When the <strong>Record</strong> argument is <strong>Next</strong> or <strong>Previous</strong>, Microsoft Office Access 2007 moves the number of records forward or backward specified in the <strong>Offset</strong> argument.</span></span></p></li>
<li><p><span data-ttu-id="489b5-127"><strong>转到</strong><strong>记录</strong>参数时，Access 将移动到的记录数等于<strong>偏移量</strong>参数中。</span><span class="sxs-lookup"><span data-stu-id="489b5-127">When the <strong>Record</strong> argument is <strong>Go To</strong>, Access moves to the record with the number equal to the <strong>Offset</strong> argument.</span></span> <span data-ttu-id="489b5-128">记录号显示在窗口底部的记录编号框。</span><span class="sxs-lookup"><span data-stu-id="489b5-128">The record number is shown in the record number box at the bottom of the window.</span></span></p></li>
</ul>

> [!NOTE]
> <P><span data-ttu-id="489b5-129">如果您使用的<STRONG>第一个</STRONG>、<STRONG>最后一个</STRONG>，或<STRONG>新建</STRONG>设置为<STRONG>记录</STRONG>参数，则 Access 将忽略<STRONG>偏移量</STRONG>参数。</span><span class="sxs-lookup"><span data-stu-id="489b5-129">If you use the <STRONG>First</STRONG>, <STRONG>Last</STRONG>, or <STRONG>New</STRONG> setting for the <STRONG>Record</STRONG> argument, Access ignores the <STRONG>Offset</STRONG> argument.</span></span> <span data-ttu-id="489b5-130">如果输入太大的<STRONG>偏移量</STRONG>参数，则 Access 将显示一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="489b5-130">If you enter an <STRONG>Offset</STRONG> argument that is too large, Access displays an error message.</span></span> <span data-ttu-id="489b5-131">不能的<STRONG>偏移量</STRONG>参数输入负数。</span><span class="sxs-lookup"><span data-stu-id="489b5-131">You can't enter negative numbers for the <STRONG>Offset</STRONG> argument.</span></span></P>


<p></p>
<ul>
<li><p><span data-ttu-id="489b5-132">当<strong>记录</strong>参数为<strong>下一个</strong>或<strong>上一步</strong>时，Microsoft Office Access 2007 将移动向前或向后<strong>偏移</strong>参数中指定的记录数。</span><span class="sxs-lookup"><span data-stu-id="489b5-132">When the <strong>Record</strong> argument is <strong>Next</strong> or <strong>Previous</strong>, Microsoft Office Access 2007 moves the number of records forward or backward specified in the <strong>Offset</strong> argument.</span></span></p></li>
<li><p><span data-ttu-id="489b5-133"><strong>转到</strong><strong>记录</strong>参数时，Access 将移动到的记录数等于<strong>偏移量</strong>参数中。</span><span class="sxs-lookup"><span data-stu-id="489b5-133">When the <strong>Record</strong> argument is <strong>Go To</strong>, Access moves to the record with the number equal to the <strong>Offset</strong> argument.</span></span> <span data-ttu-id="489b5-134">记录号显示在窗口底部的记录编号框。</span><span class="sxs-lookup"><span data-stu-id="489b5-134">The record number is shown in the record number box at the bottom of the window.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="489b5-135">说明</span><span class="sxs-lookup"><span data-stu-id="489b5-135">Remarks</span></span>

<span data-ttu-id="489b5-136">如果焦点位于记录中的某个特定控件中，此操作会将焦点留在新记录的相同控件中。</span><span class="sxs-lookup"><span data-stu-id="489b5-136">If the focus is in a particular control in a record, this action leaves it in the same control for the new record.</span></span>

<span data-ttu-id="489b5-137">您可以使用**记录**参数的**新**设置移至窗体或表末尾的空白记录，以便您可以输入新的数据。</span><span class="sxs-lookup"><span data-stu-id="489b5-137">You can use the **New** setting for the **Record** argument to move to the blank record at the end of a form or table so you can enter new data.</span></span>

<span data-ttu-id="489b5-138">类似于单击下**主页**选项卡上的**查找**按钮的箭头，然后单击**转到**此操作。</span><span class="sxs-lookup"><span data-stu-id="489b5-138">This action is similar to clicking the arrow below the **Find** button on the **Home** tab and then clicking **Go To**.</span></span> <span data-ttu-id="489b5-139">**第一个**、**最后一个**、**下一个**、**上一步**和**新记录**子命令的**转到**命令具有对所选对象作为**第一个**、**最后一个**、**下一个**、**上一步**，相同的影响和**记录**参数的**新**设置。</span><span class="sxs-lookup"><span data-stu-id="489b5-139">The **First**, **Last**, **Next**, **Previous**, and **New Record** subcommands of the **Go To** command have the same effect on the selected object as the **First**, **Last**, **Next**, **Previous**, and **New** settings for the **Record** argument.</span></span> <span data-ttu-id="489b5-140">您还可以使用窗口的底部的导航按钮记录移动。</span><span class="sxs-lookup"><span data-stu-id="489b5-140">You can also move to records by using the navigation buttons at the bottom of the window.</span></span>

<span data-ttu-id="489b5-141">您可以使用**GoToRecord**操作使隐藏窗体上的当前记录的记录，如果在**对象类型**和**对象名称**参数中指定了隐藏窗体。</span><span class="sxs-lookup"><span data-stu-id="489b5-141">You can use the **GoToRecord** action to make a record on a hidden form the current record if you specify the hidden form in the **Object Type** and **Object Name** arguments.</span></span>

<span data-ttu-id="489b5-142">要在 Visual Basic for Applications (VBA) 模块中运行 **GoToRecord** 操作，请使用 **DoCmd** 对象的 **GoToRecord** 方法。</span><span class="sxs-lookup"><span data-stu-id="489b5-142">To run the **GoToRecord** action in a Visual Basic for Applications (VBA) module, use the **GoToRecord** method of the **DoCmd** object.</span></span>

