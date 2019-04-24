---
title: CreateRecord 数据块
TOCTitle: CreateRecord data block
ms:assetid: e18f47f8-2aad-9a14-ad63-ab603a4d5b07
ms:mtpsurl: https://msdn.microsoft.com/library/Ff835671(v=office.15)
ms:contentKeyID: 48548263
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 63e189143e77f9fcc42fa8d48c3ebfb2feda6633
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32295350"
---
# <a name="createrecord-data-block"></a><span data-ttu-id="12a6f-102">CreateRecord 数据块</span><span class="sxs-lookup"><span data-stu-id="12a6f-102">CreateRecord data block</span></span>


<span data-ttu-id="12a6f-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="12a6f-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="12a6f-104">您可以使用 **CreateRecord** 数据块在指定表中创建新记录。</span><span class="sxs-lookup"><span data-stu-id="12a6f-104">You can use the **CreateRecord** data block to create a new record in the specified table.</span></span>

> [!NOTE]
> <span data-ttu-id="12a6f-105">**CreateRecord** 数据块仅适用于数据宏。</span><span class="sxs-lookup"><span data-stu-id="12a6f-105">The **CreateRecord** data block is available only in Data Macros.</span></span>

## <a name="setting"></a><span data-ttu-id="12a6f-106">Setting</span><span class="sxs-lookup"><span data-stu-id="12a6f-106">Setting</span></span>

<span data-ttu-id="12a6f-107">**DeleteRecord** 数据块具有以下参数。</span><span class="sxs-lookup"><span data-stu-id="12a6f-107">The **CreateRecord** data block has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="12a6f-108">参数</span><span class="sxs-lookup"><span data-stu-id="12a6f-108">Argument</span></span></p></th>
<th><p><span data-ttu-id="12a6f-109">必需</span><span class="sxs-lookup"><span data-stu-id="12a6f-109">Required</span></span></p></th>
<th><p><span data-ttu-id="12a6f-110">说明</span><span class="sxs-lookup"><span data-stu-id="12a6f-110">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="12a6f-111"><strong>Create a Record In</strong></span><span class="sxs-lookup"><span data-stu-id="12a6f-111"><strong>Create a Record In</strong></span></span></p></td>
<td><p><span data-ttu-id="12a6f-112">是</span><span class="sxs-lookup"><span data-stu-id="12a6f-112">Yes</span></span></p></td>
<td><p><span data-ttu-id="12a6f-113">要在其中创建新记录的表的名称。</span><span class="sxs-lookup"><span data-stu-id="12a6f-113">The name of the table to create the new record in.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12a6f-114"><strong>Alias</strong></span><span class="sxs-lookup"><span data-stu-id="12a6f-114"><strong>Alias</strong></span></span></p></td>
<td><p><span data-ttu-id="12a6f-115">否</span><span class="sxs-lookup"><span data-stu-id="12a6f-115">No</span></span></p></td>
<td><p><span data-ttu-id="12a6f-116">一个用于标识记录的字符串。</span><span class="sxs-lookup"><span data-stu-id="12a6f-116">An string that identifies the record.</span></span> <span data-ttu-id="12a6f-117">您可以使用记录的别名来标识该记录</span><span class="sxs-lookup"><span data-stu-id="12a6f-117">You can use the record's alias to identify</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="12a6f-118">注解</span><span class="sxs-lookup"><span data-stu-id="12a6f-118">Remarks</span></span>

<span data-ttu-id="12a6f-119">**CreateRecord** 创建的记录会自动成为当前记录。</span><span class="sxs-lookup"><span data-stu-id="12a6f-119">The record created by **CreateRecord** automatically becomes the current record.</span></span>

<span data-ttu-id="12a6f-120">在**CreateRecord**语句后, 可以插入一个在新记录提交之前执行的命令块。</span><span class="sxs-lookup"><span data-stu-id="12a6f-120">After **CreateRecord** statement, you can insert a block of commands that will execute before the new record is committed.</span></span> <span data-ttu-id="12a6f-121">以下操作适用于 **CreateRecord** 数据块。</span><span class="sxs-lookup"><span data-stu-id="12a6f-121">The following actions are available in a **CreateRecord** data block.</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="12a6f-122"><a href="cancelrecordchange-macro-action.md">CancelRecordChange 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="12a6f-122"><a href="cancelrecordchange-macro-action.md">CancelRecordChange macro action</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12a6f-123"><a href="comment-macro-statement.md">Comment 宏语句</a></span><span class="sxs-lookup"><span data-stu-id="12a6f-123"><a href="comment-macro-statement.md">Comment macro statement</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12a6f-124"><a href="group-macro-statement.md">Group 宏语句</a></span><span class="sxs-lookup"><span data-stu-id="12a6f-124"><a href="group-macro-statement.md">Group macro statement</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12a6f-125"><a href="if-then-else-macro-block.md">If .。。然后 .。。Else 宏语句</a></span><span class="sxs-lookup"><span data-stu-id="12a6f-125"><a href="if-then-else-macro-block.md">If...Then...Else macro statement</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="12a6f-126"><a href="setfield-macro-action.md">SetField 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="12a6f-126"><a href="setfield-macro-action.md">SetField macro action</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="12a6f-127"><a href="setlocalvar-macro-action.md">SetLocalVar 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="12a6f-127"><a href="setlocalvar-macro-action.md">SetLocalVar macro action</a></span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="12a6f-128">在 **CreateRecord** 操作创建记录后，可使用 **SetField** 操作在该新记录中指定字段值。</span><span class="sxs-lookup"><span data-stu-id="12a6f-128">After the **CreateRecord** action creates a record, use the **SetField** action to specify a value of a field in the new record.</span></span>

<span data-ttu-id="12a6f-129">可以使用 **If...Then...Else** 语句基于条件来执行操作。</span><span class="sxs-lookup"><span data-stu-id="12a6f-129">You can use an **If...Then...Else** statment to perform operations based on a condition.</span></span>

<span data-ttu-id="12a6f-p103">若要取消创建记录，可使用 **CancelRecordChange** 操作。此操作将阻止提交更改并退出 **CreateRecord** 数据块。</span><span class="sxs-lookup"><span data-stu-id="12a6f-p103">To cancel the creation of a record, use the **CancelRecordChange** action. This prevents the changes from being committed and exits the **CreateRecord** data block.</span></span>

<span data-ttu-id="12a6f-132">提交新记录后，可以使用 **LastCreateRecordIdentity** 本地变量来处理该记录。</span><span class="sxs-lookup"><span data-stu-id="12a6f-132">Once the new record is committed, you can use the **LastCreateRecordIdentity** local variable to work with the record.</span></span> <span data-ttu-id="12a6f-133">例如, 使用以下语法来引用最近创建的记录的 "分配给" 字段。</span><span class="sxs-lookup"><span data-stu-id="12a6f-133">For example, use the following syntax to refer to the AssignedTo field of the most recently created record.</span></span>

`[LastCreateRecordIdentity].[AssignedTo]`

<span data-ttu-id="12a6f-134">**CreateRecord** 数据块只能用于 **[插入后](after-insert-macro-event.md)** 、 **[更新后](after-update-macro-event.md)** 和 **[删除后](after-update-macro-event.md)** 数据宏事件。</span><span class="sxs-lookup"><span data-stu-id="12a6f-134">The **CreateRecord** data block can only be used in the **[After Insert](after-insert-macro-event.md)**, **[After Update](after-update-macro-event.md)**, and **[After Update](after-update-macro-event.md)** data macro events.</span></span>

