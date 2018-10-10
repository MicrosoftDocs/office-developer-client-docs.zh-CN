---
title: “删除前”宏事件
TOCTitle: Before Delete Macro Event
ms:assetid: 1a8d3457-5c59-d13e-ada9-6ecd33dfd5b3
ms:mtpsurl: https://msdn.microsoft.com/library/Ff845672(v=office.15)
ms:contentKeyID: 48543520
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm186077
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 7863f8500a81014f3c70b5547fb363c46803f4f1
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467775"
---
# <a name="before-delete-macro-event"></a><span data-ttu-id="8e5b9-102">“删除前”宏事件</span><span class="sxs-lookup"><span data-stu-id="8e5b9-102">Before Delete Macro Event</span></span>

<span data-ttu-id="8e5b9-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="8e5b9-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="8e5b9-104">当记录被删除，但未提交更改时会发生的**删除前**事件。</span><span class="sxs-lookup"><span data-stu-id="8e5b9-104">The **Before Delete** event occurs when a record is deleted, but before the change is committed.</span></span>

> [!NOTE]
> <span data-ttu-id="8e5b9-105">**删除前**事件仅适用于数据宏。</span><span class="sxs-lookup"><span data-stu-id="8e5b9-105">The **Before Delete** event is available only in Data Macros.</span></span>

## <a name="remarks"></a><span data-ttu-id="8e5b9-106">说明</span><span class="sxs-lookup"><span data-stu-id="8e5b9-106">Remarks</span></span>

<span data-ttu-id="8e5b9-107">删除使用的**删除前**事件执行所需记录之前，需要进行任何操作。</span><span class="sxs-lookup"><span data-stu-id="8e5b9-107">Use the **Before Delete** event to perform any actions that you want to occur before a record is deleted.</span></span> <span data-ttu-id="8e5b9-108">**Before Change**常用来执行验证并将引发自定义错误消息。</span><span class="sxs-lookup"><span data-stu-id="8e5b9-108">The **Before Change** is commonly used to perform validation and to raise custom error messages.</span></span>

<span data-ttu-id="8e5b9-109">您可以访问中使用以下语法删除的记录的值：</span><span class="sxs-lookup"><span data-stu-id="8e5b9-109">You can access a value in the record to be deleted by using the following syntax:</span></span>

`[Old].[Field Name]`

<span data-ttu-id="8e5b9-110">例如，若要访问要删除的记录中 QuantityInStock 字段的值，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="8e5b9-110">For example, to access the value of the QuantityInStock field in the record to be deleted, use the following syntax:</span></span>

`[Old].[QuantityInStock]`

<span data-ttu-id="8e5b9-111">在**删除前**事件结束时，包含要删除的记录中的值将被永久删除。</span><span class="sxs-lookup"><span data-stu-id="8e5b9-111">The values contained in the record to be deleted are deleted permanently when the **Before Delete** event ends.</span></span>

<span data-ttu-id="8e5b9-112">您可以通过使用**RaiseError**操作取消的**删除前**事件。</span><span class="sxs-lookup"><span data-stu-id="8e5b9-112">You can cancel the **Before Delete** event by using the **RaiseError** action.</span></span> <span data-ttu-id="8e5b9-113">引发错误时，将丢弃的**删除前**事件中包含的更改。</span><span class="sxs-lookup"><span data-stu-id="8e5b9-113">When an error is raised, the changes contained in the **Before Delete** event are discarded.</span></span>

<span data-ttu-id="8e5b9-114">下表列出了可在**删除前**事件中使用的宏命令。</span><span class="sxs-lookup"><span data-stu-id="8e5b9-114">The following table lists macro commands that can be used in the **Before Delete** event.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="8e5b9-115">命令类型</span><span class="sxs-lookup"><span data-stu-id="8e5b9-115">Command Type</span></span></p></th>
<th><p><span data-ttu-id="8e5b9-116">命令</span><span class="sxs-lookup"><span data-stu-id="8e5b9-116">Command</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8e5b9-117">程序流</span><span class="sxs-lookup"><span data-stu-id="8e5b9-117">Program Flow</span></span></p></td>
<td><p><span data-ttu-id="8e5b9-118"><a href="comment-macro-statement.md">Comment 宏语句</a></span><span class="sxs-lookup"><span data-stu-id="8e5b9-118"><a href="comment-macro-statement.md">Comment Macro Statement</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e5b9-119">程序流</span><span class="sxs-lookup"><span data-stu-id="8e5b9-119">Program Flow</span></span></p></td>
<td><p><span data-ttu-id="8e5b9-120"><a href="group-macro-statement.md">Group 宏语句</a></span><span class="sxs-lookup"><span data-stu-id="8e5b9-120"><a href="group-macro-statement.md">Group Macro Statement</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e5b9-121">程序流</span><span class="sxs-lookup"><span data-stu-id="8e5b9-121">Program Flow</span></span></p></td>
<td><p><span data-ttu-id="8e5b9-122"><a href="if-then-else-macro-block.md">If...Then...Else 宏程序块</a></span><span class="sxs-lookup"><span data-stu-id="8e5b9-122"><a href="if-then-else-macro-block.md">If...Then...Else Macro Block</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e5b9-123">数据块</span><span class="sxs-lookup"><span data-stu-id="8e5b9-123">Data Block</span></span></p></td>
<td><p><span data-ttu-id="8e5b9-124"><a href="lookuprecord-data-block.md">LookupRecord 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="8e5b9-124"><a href="lookuprecord-data-block.md">LookupRecord Macro Action</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e5b9-125">数据操作</span><span class="sxs-lookup"><span data-stu-id="8e5b9-125">Data Action</span></span></p></td>
<td><p><span data-ttu-id="8e5b9-126"><a href="clearmacroerror-macro-action.md">ClearMacroError 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="8e5b9-126"><a href="clearmacroerror-macro-action.md">ClearMacroError Macro Action</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e5b9-127">数据操作</span><span class="sxs-lookup"><span data-stu-id="8e5b9-127">Data Action</span></span></p></td>
<td><p><span data-ttu-id="8e5b9-128"><a href="onerror-macro-action.md">OnError 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="8e5b9-128"><a href="onerror-macro-action.md">OnError Macro Action</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e5b9-129">数据操作</span><span class="sxs-lookup"><span data-stu-id="8e5b9-129">Data Action</span></span></p></td>
<td><p><span data-ttu-id="8e5b9-130"><a href="raiseerror-macro-action.md">RaiseError 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="8e5b9-130"><a href="raiseerror-macro-action.md">RaiseError Macro Action</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8e5b9-131">数据操作</span><span class="sxs-lookup"><span data-stu-id="8e5b9-131">Data Action</span></span></p></td>
<td><p><span data-ttu-id="8e5b9-132"><a href="setlocalvar-macro-action.md">SetLocalVar 宏操作</a></span><span class="sxs-lookup"><span data-stu-id="8e5b9-132"><a href="setlocalvar-macro-action.md">SetLocalVar Macro Action</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8e5b9-133">数据操作</span><span class="sxs-lookup"><span data-stu-id="8e5b9-133">Data Action</span></span></p></td>
<td><p><span data-ttu-id="8e5b9-134"><a href="stopmacro-macro-action.md">StopMacro Macro Action</a></span><span class="sxs-lookup"><span data-stu-id="8e5b9-134"><a href="stopmacro-macro-action.md">StopMacro Macro Action</a></span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8e5b9-135">若要创建可捕获**删除前**事件的数据宏，请使用以下步骤。</span><span class="sxs-lookup"><span data-stu-id="8e5b9-135">To create a Data macro that captures the **Before Delete** event, use the following steps.</span></span>

1.  <span data-ttu-id="8e5b9-136">打开要为其捕获**删除前**事件的表格。</span><span class="sxs-lookup"><span data-stu-id="8e5b9-136">Open the table for which you want to capture the **Before Delete** event.</span></span>

2.  <span data-ttu-id="8e5b9-137">在**表**选项卡中的**前期事件**组中，选择**删除前**。</span><span class="sxs-lookup"><span data-stu-id="8e5b9-137">On the **Table** tab, in the **Before Events** group, select **Before Delete**.</span></span>

