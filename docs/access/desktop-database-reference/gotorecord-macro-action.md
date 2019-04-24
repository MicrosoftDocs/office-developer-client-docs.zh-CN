---
title: GoToRecord 宏操作
TOCTitle: GoToRecord macro action
ms:assetid: 76f936de-739b-63be-9b28-5b0e111408e6
ms:mtpsurl: https://msdn.microsoft.com/library/Ff196037(v=office.15)
ms:contentKeyID: 48545712
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm58124
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 7534ae84b57d14450009865ea330a4c54d4cfb44
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32292137"
---
# <a name="gotorecord-macro-action"></a><span data-ttu-id="ca39b-102">GoToRecord 宏操作</span><span class="sxs-lookup"><span data-stu-id="ca39b-102">GoToRecord macro action</span></span>


<span data-ttu-id="ca39b-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="ca39b-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="ca39b-104">可以使用 **GoToRecord** 操作将指定记录设置为打开的表、窗体或查询结果集中的当前记录。</span><span class="sxs-lookup"><span data-stu-id="ca39b-104">You can use the **GoToRecord** action to make the specified record the current record in an open table, form, or query result set.</span></span>

## <a name="setting"></a><span data-ttu-id="ca39b-105">Setting</span><span class="sxs-lookup"><span data-stu-id="ca39b-105">Setting</span></span>

<span data-ttu-id="ca39b-106">**GoToRecord** 操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="ca39b-106">The **GoToRecord** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="ca39b-107">操作参数</span><span class="sxs-lookup"><span data-stu-id="ca39b-107">Action argument</span></span></p></th>
<th><p><span data-ttu-id="ca39b-108">说明</span><span class="sxs-lookup"><span data-stu-id="ca39b-108">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ca39b-109"><strong>对象类型</strong></span><span class="sxs-lookup"><span data-stu-id="ca39b-109"><strong>Object Type</strong></span></span></p></td>
<td><p><span data-ttu-id="ca39b-p101">要设置为当前记录的记录所在的数据库对象的类型。请在“宏生成器”窗格<strong>“操作参数”</strong>部分的<strong>“对象类型”</strong>框中单击<strong>“表”</strong>、<strong>“查询”</strong>、<strong>“窗体”</strong>、<strong>“服务器视图”</strong>、<strong>“存储过程”</strong>或<strong>“函数”</strong>。如果将此参数留空，则会选择活动对象。</span><span class="sxs-lookup"><span data-stu-id="ca39b-p101">The type of object that contains the record you want to make current. Click <strong>Table</strong>, <strong>Query</strong>, <strong>Form</strong>, <strong>Server View</strong>, <strong>Stored Procedure</strong>, or <strong>Function</strong> in the <strong>Object Type</strong> box in the <strong>Action Arguments</strong> section of the Macro Builder pane. Leave this argument blank to select the active object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca39b-113"><strong>对象名称</strong></span><span class="sxs-lookup"><span data-stu-id="ca39b-113"><strong>Object Name</strong></span></span></p></td>
<td><p><span data-ttu-id="ca39b-p102">要设置为当前记录的记录所在的对象的名称。“对象名称”<strong></strong>框显示属于“对象类型”<strong></strong>参数所选类型的当前数据库中的所有对象。如果将“对象类型”<strong></strong>参数留空，则也要将此参数留空。</span><span class="sxs-lookup"><span data-stu-id="ca39b-p102">The name of the object that contains the record you want to make the current record. The <strong>Object Name</strong> box shows all objects in the current database of the type selected by the <strong>Object Type</strong> argument. If you leave the <strong>Object Type</strong> argument blank, leave this argument blank also.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca39b-117"><strong>Record</strong></span><span class="sxs-lookup"><span data-stu-id="ca39b-117"><strong>Record</strong></span></span></p></td>
<td><p><span data-ttu-id="ca39b-p103">要设置为当前记录的记录。请单击<strong>“记录”</strong>框中的<strong>“上一个”</strong>、<strong>“下一个”</strong>、<strong>“第一个”</strong>、<strong>“最后一个”</strong>、<strong>“转至”</strong>或<strong>“新建”</strong>。默认值为<strong>“下一个”</strong>。</span><span class="sxs-lookup"><span data-stu-id="ca39b-p103">The record to make the current record. Click <strong>Previous</strong>, <strong>Next</strong>, <strong>First</strong>, <strong>Last</strong>, <strong>Go To</strong>, or <strong>New</strong> in the <strong>Record</strong> box. The default is <strong>Next</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca39b-121"><strong>Offset</strong></span><span class="sxs-lookup"><span data-stu-id="ca39b-121"><strong>Offset</strong></span></span></p></td>
<td><p><span data-ttu-id="ca39b-122">一个整数或求值结果为整数的表达式。</span><span class="sxs-lookup"><span data-stu-id="ca39b-122">An integer or expression that evaluates to an integer.</span></span> <span data-ttu-id="ca39b-123">表达式的前面必须有等号 (<strong>=</strong>)。</span><span class="sxs-lookup"><span data-stu-id="ca39b-123">An expression must be preceded by an equal sign (<strong>=</strong>).</span></span> <span data-ttu-id="ca39b-124">此参数指定要设置为当前记录的记录。</span><span class="sxs-lookup"><span data-stu-id="ca39b-124">This argument specifies the record to make the current record.</span></span> <span data-ttu-id="ca39b-125">“偏移量”<strong></strong>参数有两种用法：</span><span class="sxs-lookup"><span data-stu-id="ca39b-125">You can use the <strong>Offset</strong> argument in two ways:</span></span></p>
<ul>
<li><p><span data-ttu-id="ca39b-126">当“记录”<strong></strong>参数为<strong>“下一个”</strong>或<strong>“上一个”</strong>时，Microsoft Office Access 2007 会向前或向后移动“偏移量”<strong></strong>参数指定的记录数。</span><span class="sxs-lookup"><span data-stu-id="ca39b-126">When the <strong>Record</strong> argument is <strong>Next</strong> or <strong>Previous</strong>, Microsoft Office Access 2007 moves the number of records forward or backward specified in the <strong>Offset</strong> argument.</span></span></p></li>
<li><p><span data-ttu-id="ca39b-p105">当“记录”<strong></strong>参数为<strong>“转至”</strong>时，Access 会移到编号等于“偏移量”<strong></strong>参数的记录。记录编号显示在窗口底部的记录编号框中。</span><span class="sxs-lookup"><span data-stu-id="ca39b-p105">When the <strong>Record</strong> argument is <strong>Go To</strong>, Access moves to the record with the number equal to the <strong>Offset</strong> argument. The record number is shown in the record number box at the bottom of the window.</span></span></p>
<p><span data-ttu-id="ca39b-129"><strong>注意</strong>: 如果使用<strong>Record</strong>参数的<strong>第一个</strong>、<strong>最后一个</strong>或<strong>新</strong>设置, Access 将忽略<strong>Offset</strong>参数。</span><span class="sxs-lookup"><span data-stu-id="ca39b-129"><strong>NOTE</strong>: If you use the <strong>First</strong>, <strong>Last</strong>, or <strong>New</strong> setting for the <strong>Record</strong> argument, Access ignores the <strong>Offset</strong> argument.</span></span> <span data-ttu-id="ca39b-130">如果输入的“偏移量”<strong></strong>参数过大，Access 将显示一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="ca39b-130">If you enter an <strong>Offset</strong> argument that is too large, Access displays an error message.</span></span> <span data-ttu-id="ca39b-131">不能为“偏移量”<strong></strong>参数输入负数。</span><span class="sxs-lookup"><span data-stu-id="ca39b-131">You can't enter negative numbers for the <strong>Offset</strong> argument.</span></span></p></li>
<li><p><span data-ttu-id="ca39b-132">当“记录”<strong></strong>参数为<strong>“下一个”</strong>或<strong>“上一个”</strong>时，Microsoft Office Access 2007 会向前或向后移动“偏移量”<strong></strong>参数指定的记录数。</span><span class="sxs-lookup"><span data-stu-id="ca39b-132">When the <strong>Record</strong> argument is <strong>Next</strong> or <strong>Previous</strong>, Microsoft Office Access 2007 moves the number of records forward or backward specified in the <strong>Offset</strong> argument.</span></span></p></li>
<li><p><span data-ttu-id="ca39b-p107">当“记录”<strong></strong>参数为<strong>“转至”</strong>时，Access 会移到编号等于“偏移量”<strong></strong>参数的记录。记录编号显示在窗口底部的记录编号框中。</span><span class="sxs-lookup"><span data-stu-id="ca39b-p107">When the <strong>Record</strong> argument is <strong>Go To</strong>, Access moves to the record with the number equal to the <strong>Offset</strong> argument. The record number is shown in the record number box at the bottom of the window.</span></span></p></li>
</ul>
</td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="ca39b-135">注解</span><span class="sxs-lookup"><span data-stu-id="ca39b-135">Remarks</span></span>

<span data-ttu-id="ca39b-136">如果焦点位于记录中的某个特定控件中，此操作会将焦点留在新记录的相同控件中。</span><span class="sxs-lookup"><span data-stu-id="ca39b-136">If the focus is in a particular control in a record, this action leaves it in the same control for the new record.</span></span>

<span data-ttu-id="ca39b-137">You can use the **New** setting for the **Record** argument to move to the blank record at the end of a form or table so you can enter new data.</span><span class="sxs-lookup"><span data-stu-id="ca39b-137">You can use the **New** setting for the **Record** argument to move to the blank record at the end of a form or table so you can enter new data.</span></span>

<span data-ttu-id="ca39b-p108">This action is similar to clicking the arrow below the **Find** button on the **Home** tab and then clicking **Go To**. The **First**, **Last**, **Next**, **Previous**, and **New Record** subcommands of the **Go To** command have the same effect on the selected object as the **First**, **Last**, **Next**, **Previous**, and **New** settings for the **Record** argument. You can also move to records by using the navigation buttons at the bottom of the window.</span><span class="sxs-lookup"><span data-stu-id="ca39b-p108">This action is similar to clicking the arrow below the **Find** button on the **Home** tab and then clicking **Go To**. The **First**, **Last**, **Next**, **Previous**, and **New Record** subcommands of the **Go To** command have the same effect on the selected object as the **First**, **Last**, **Next**, **Previous**, and **New** settings for the **Record** argument. You can also move to records by using the navigation buttons at the bottom of the window.</span></span>

<span data-ttu-id="ca39b-141">You can use the **GoToRecord** action to make a record on a hidden form the current record if you specify the hidden form in the **Object Type** and **Object Name** arguments.</span><span class="sxs-lookup"><span data-stu-id="ca39b-141">You can use the **GoToRecord** action to make a record on a hidden form the current record if you specify the hidden form in the **Object Type** and **Object Name** arguments.</span></span>

<span data-ttu-id="ca39b-142">要在 Visual Basic for Applications (VBA) 模块中运行 **GoToRecord** 操作，请使用 **DoCmd** 对象的 **GoToRecord** 方法。</span><span class="sxs-lookup"><span data-stu-id="ca39b-142">To run the **GoToRecord** action in a Visual Basic for Applications (VBA) module, use the **GoToRecord** method of the **DoCmd** object.</span></span>

