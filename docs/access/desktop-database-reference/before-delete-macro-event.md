---
title: Before Delete 宏事件
TOCTitle: Before Delete macro event
ms:assetid: 1a8d3457-5c59-d13e-ada9-6ecd33dfd5b3
ms:mtpsurl: https://msdn.microsoft.com/library/Ff845672(v=office.15)
ms:contentKeyID: 48543520
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm186077
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 2b2a4f978a4af2ba79cab7807f0142d35d7d30c7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32296911"
---
# <a name="before-delete-macro-event"></a><span data-ttu-id="580cf-102">Before Delete 宏事件</span><span class="sxs-lookup"><span data-stu-id="580cf-102">Before Delete macro event</span></span>

<span data-ttu-id="580cf-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="580cf-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="580cf-104">当记录被删除但未提交更改时会发生“删除前”\*\*\*\* 事件。</span><span class="sxs-lookup"><span data-stu-id="580cf-104">The **Before Delete** event occurs when a record is deleted, but before the change is committed.</span></span>

> [!NOTE]
> <span data-ttu-id="580cf-105">\*\*\*\*“删除前”事件仅适用于数据宏。</span><span class="sxs-lookup"><span data-stu-id="580cf-105">The **Before Delete** event is available only in Data Macros.</span></span>

## <a name="remarks"></a><span data-ttu-id="580cf-106">注解</span><span class="sxs-lookup"><span data-stu-id="580cf-106">Remarks</span></span>

<span data-ttu-id="580cf-107">使用“删除前”\*\*\*\* 事件可以执行您希望在删除记录前发生的任何操作。</span><span class="sxs-lookup"><span data-stu-id="580cf-107">Use the **Before Delete** event to perform any actions that you want to occur before a record is deleted.</span></span> <span data-ttu-id="580cf-108">“更改前”\*\*\*\* 通常用于执行验证和引发自定义错误消息。</span><span class="sxs-lookup"><span data-stu-id="580cf-108">The **Before Change** is commonly used to perform validation and to raise custom error messages.</span></span>

<span data-ttu-id="580cf-109">您可以使用以下语法访问要删除的记录中的值:</span><span class="sxs-lookup"><span data-stu-id="580cf-109">You can access a value in the record to be deleted by using the following syntax:</span></span>

`[Old].[Field Name]`

<span data-ttu-id="580cf-110">例如, 若要访问要删除的记录中的 QuantityInStock 字段的值, 请使用以下语法:</span><span class="sxs-lookup"><span data-stu-id="580cf-110">For example, to access the value of the QuantityInStock field in the record to be deleted, use the following syntax:</span></span>

`[Old].[QuantityInStock]`

<span data-ttu-id="580cf-111">当“删除前”\*\*\*\* 事件结束时，要删除的记录中包含的值将被永久删除。</span><span class="sxs-lookup"><span data-stu-id="580cf-111">The values contained in the record to be deleted are deleted permanently when the **Before Delete** event ends.</span></span>

<span data-ttu-id="580cf-112">您可以使用 **RaiseError** 操作取消“删除前”\*\*\*\* 事件。</span><span class="sxs-lookup"><span data-stu-id="580cf-112">You can cancel the **Before Delete** event by using the **RaiseError** action.</span></span> <span data-ttu-id="580cf-113">在引发错误时, 将放弃**Before Delete**事件中包含的更改。</span><span class="sxs-lookup"><span data-stu-id="580cf-113">When an error is raised, the changes contained in the **Before Delete** event are discarded.</span></span>

<span data-ttu-id="580cf-114">下表列出了可在**Before Delete**事件中使用的宏命令。</span><span class="sxs-lookup"><span data-stu-id="580cf-114">The following table lists macro commands that can be used in the **Before Delete** event.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="580cf-115">命令类型</span><span class="sxs-lookup"><span data-stu-id="580cf-115">Command Type</span></span></p></th>
<th><p><span data-ttu-id="580cf-116">Command</span><span class="sxs-lookup"><span data-stu-id="580cf-116">Command</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="580cf-117">程序流</span><span class="sxs-lookup"><span data-stu-id="580cf-117">Program Flow</span></span></p></td>
<td><p><span data-ttu-id="580cf-118"><a href="comment-macro-statement.md">Comment 宏语句</a></span><span class="sxs-lookup"><span data-stu-id="580cf-118"><a href="comment-macro-statement.md">Comment macro statement</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="580cf-119">程序流</span><span class="sxs-lookup"><span data-stu-id="580cf-119">Program Flow</span></span></p></td>
<td><p><span data-ttu-id="580cf-120"><a href="group-macro-statement.md">Group 宏语句</a></span><span class="sxs-lookup"><span data-stu-id="580cf-120"><a href="group-macro-statement.md">Group macro statement</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="580cf-121">程序流</span><span class="sxs-lookup"><span data-stu-id="580cf-121">Program Flow</span></span></p></td>
<td><p><span data-ttu-id="580cf-122"><a href="if-then-else-macro-block.md">If...Then...Else 宏程序块</a></span><span class="sxs-lookup"><span data-stu-id="580cf-122"><a href="if-then-else-macro-block.md">If...Then...Else macro block</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="580cf-123">数据块</span><span class="sxs-lookup"><span data-stu-id="580cf-123">Data Block</span></span></p></td>
<td><p><span data-ttu-id="580cf-124"><a href="lookuprecord-data-block.md">LookupRecord 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="580cf-124"><a href="lookuprecord-data-block.md">LookupRecord macro action</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="580cf-125">数据操作</span><span class="sxs-lookup"><span data-stu-id="580cf-125">Data Action</span></span></p></td>
<td><p><span data-ttu-id="580cf-126"><a href="clearmacroerror-macro-action.md">ClearMacroError 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="580cf-126"><a href="clearmacroerror-macro-action.md">ClearMacroError macro action</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="580cf-127">数据操作</span><span class="sxs-lookup"><span data-stu-id="580cf-127">Data Action</span></span></p></td>
<td><p><span data-ttu-id="580cf-128"><a href="onerror-macro-action.md">OnError 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="580cf-128"><a href="onerror-macro-action.md">OnError macro action</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="580cf-129">数据操作</span><span class="sxs-lookup"><span data-stu-id="580cf-129">Data Action</span></span></p></td>
<td><p><span data-ttu-id="580cf-130"><a href="raiseerror-macro-action.md">RaiseError 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="580cf-130"><a href="raiseerror-macro-action.md">RaiseError macro action</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="580cf-131">数据操作</span><span class="sxs-lookup"><span data-stu-id="580cf-131">Data Action</span></span></p></td>
<td><p><span data-ttu-id="580cf-132"><a href="setlocalvar-macro-action.md">SetLocalVar 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="580cf-132"><a href="setlocalvar-macro-action.md">SetLocalVar macro action</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="580cf-133">数据操作</span><span class="sxs-lookup"><span data-stu-id="580cf-133">Data Action</span></span></p></td>
<td><p><span data-ttu-id="580cf-134"><a href="stopmacro-macro-action.md">StopMacro 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="580cf-134"><a href="stopmacro-macro-action.md">StopMacro macro action</a></span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="580cf-135">若要创建可捕获“删除前”\*\*\*\* 事件的数据宏，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="580cf-135">To create a Data macro that captures the **Before Delete** event, use the following steps.</span></span>

1.  <span data-ttu-id="580cf-136">打开要捕获其“删除前”\*\*\*\* 事件的表格。</span><span class="sxs-lookup"><span data-stu-id="580cf-136">Open the table for which you want to capture the **Before Delete** event.</span></span>

2.  <span data-ttu-id="580cf-137">在 "**表**" 选项卡上的 "前期**事件**" 组中, 选择 "**之前删除**"。</span><span class="sxs-lookup"><span data-stu-id="580cf-137">On the **Table** tab, in the **Before Events** group, select **Before Delete**.</span></span>

