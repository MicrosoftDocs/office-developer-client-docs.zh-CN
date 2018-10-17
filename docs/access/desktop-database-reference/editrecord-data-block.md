---
title: EditRecord 数据块
TOCTitle: EditRecord Data Block
ms:assetid: fe9f55eb-d7ed-1914-65a9-fa2fcb332b98
ms:mtpsurl: https://msdn.microsoft.com/library/Ff837277(v=office.15)
ms:contentKeyID: 48548940
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 07763e32e0f8687816dc39298f91733ca814d275
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465558"
---
# <a name="editrecord-data-block"></a><span data-ttu-id="ded90-102">EditRecord 数据块</span><span class="sxs-lookup"><span data-stu-id="ded90-102">EditRecord Data Block</span></span>

<span data-ttu-id="ded90-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="ded90-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="ded90-104">您可以使用 **EditRecord** 数据块更改现有记录中包含的值。</span><span class="sxs-lookup"><span data-stu-id="ded90-104">You can use the **EditRecord** data block to change the values contained in an existing record.</span></span>

> [!NOTE]
> <span data-ttu-id="ded90-105">[!注释] **EditRecord** 数据块仅适用于数据宏。</span><span class="sxs-lookup"><span data-stu-id="ded90-105">The **EditRecord** data block is available only in Data Macros.</span></span>


## <a name="setting"></a><span data-ttu-id="ded90-106">设置</span><span class="sxs-lookup"><span data-stu-id="ded90-106">Setting</span></span>

<span data-ttu-id="ded90-107">**EditRecord** 数据块具有以下参数。</span><span class="sxs-lookup"><span data-stu-id="ded90-107">The **EditRecord** data block has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="ded90-108">参数</span><span class="sxs-lookup"><span data-stu-id="ded90-108">Argument</span></span></p></th>
<th><p><span data-ttu-id="ded90-109">说明</span><span class="sxs-lookup"><span data-stu-id="ded90-109">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ded90-110"><strong>Alias</strong></span><span class="sxs-lookup"><span data-stu-id="ded90-110"><strong>Alias</strong></span></span></p></td>
<td><p><span data-ttu-id="ded90-p101">一个用于标识要编辑的记录的字符串。如果未指定 <em>Alias</em> 参数，则编辑当前记录。</span><span class="sxs-lookup"><span data-stu-id="ded90-p101">A string that identifies the record to edit. If the <em>Alias</em> argument is not specified, then the current record is edited.</span></span></p></td>
</tr>
</tbody>
</table>

## <a name="remarks"></a><span data-ttu-id="ded90-113">注释</span><span class="sxs-lookup"><span data-stu-id="ded90-113">Remarks</span></span>

<span data-ttu-id="ded90-p102">可在 **EditRecord** 语句之后插入将在提交记录更改之前执行的命令块。以下操作适用于 **EditRecord** 数据块。</span><span class="sxs-lookup"><span data-stu-id="ded90-p102">After **EditRecord** statement, you can insert a block of commands that will execute before the changes to the record are comitted. The following actions are available in a **EditRecord** data block.</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ded90-116"><a href="cancelrecordchange-macro-action.md">CancelRecordChange 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="ded90-116"><a href="cancelrecordchange-macro-action.md">CancelRecordChange Macro Action</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ded90-117"><a href="comment-macro-statement.md">Comment 宏语句</a></span><span class="sxs-lookup"><span data-stu-id="ded90-117"><a href="comment-macro-statement.md">Comment Macro Statement</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ded90-118"><a href="group-macro-statement.md">Group 宏语句</a></span><span class="sxs-lookup"><span data-stu-id="ded90-118"><a href="group-macro-statement.md">Group Macro Statement</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ded90-119"><a href="if-then-else-macro-block.md">如果...然后...Else 宏语句</a></span><span class="sxs-lookup"><span data-stu-id="ded90-119"><a href="if-then-else-macro-block.md">If...Then...Else Macro Statement</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ded90-120"><a href="setfield-macro-action.md">SetField 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="ded90-120"><a href="setfield-macro-action.md">SetField Macro Action</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ded90-121"><a href="setlocalvar-macro-action.md">SetLocalVar 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="ded90-121"><a href="setlocalvar-macro-action.md">SetLocalVar Macro Action</a></span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ded90-122">使用 **SetField** 操作可以指定已编辑记录中某一字段的新值。</span><span class="sxs-lookup"><span data-stu-id="ded90-122">Use the **SetField** action to specify the new values of a field in the edited record.</span></span>

<span data-ttu-id="ded90-123">可以使用 **If...Then...Else** 语句基于条件来执行操作。</span><span class="sxs-lookup"><span data-stu-id="ded90-123">You can use an **If...Then...Else** statment to perform operations based on a condition.</span></span>

<span data-ttu-id="ded90-p103">若要取消编辑记录，可使用 **CancelRecordChange** 操作。此操作将阻止提交更改并退出 **EditRecord** 数据块。</span><span class="sxs-lookup"><span data-stu-id="ded90-p103">To cancel the editing of a record, use the **CancelRecordChange** action. This prevents the changes from being committed and exits the **EditRecord** data block.</span></span>

<span data-ttu-id="ded90-126">您可以使用 **LastCreateRecordIdentity** 本地变量来处理在 **CreateRecord** 数据块中创建的最后一条记录。</span><span class="sxs-lookup"><span data-stu-id="ded90-126">You can use the **LastCreateRecordIdentity** local variable to work with last record created in a **CreateRecord** data block.</span></span> <span data-ttu-id="ded90-127">例如，使用以下语法引用 AssignedTo 字段的最近创建的记录：</span><span class="sxs-lookup"><span data-stu-id="ded90-127">For example, use the following syntax to refer to the AssignedTo field of the most recently created record:</span></span>

`[LastCreateRecordIdentity].[AssignedTo]`

<span data-ttu-id="ded90-128">CreateRecord 数据块只能用于 **[插入后](after-insert-macro-event.md)** 、 **[更新后](after-update-macro-event.md)** 和 **[更新后](after-update-macro-event.md)** 数据宏事件。</span><span class="sxs-lookup"><span data-stu-id="ded90-128">The CreateRecord data block can only be used in the **[After Insert](after-insert-macro-event.md)**, **[After Update](after-update-macro-event.md)**, and **[After Update](after-update-macro-event.md)** data macro events.</span></span>
