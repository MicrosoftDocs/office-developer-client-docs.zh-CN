---
title: CreateRecord 数据块 (Access 自定义 web 应用程序)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 9dd73bae-a8d5-4d8b-b356-01ac72f7e5d9
description: 您可以使用 CreateRecord 数据块在指定表中创建新记录。
ms.openlocfilehash: d89b62180dbe50a0c7dab862b70062a47558c25a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421373"
---
# <a name="createrecord-data-block-access-custom-web-app"></a><span data-ttu-id="30f48-103">CreateRecord 数据块 (Access 自定义 web 应用程序)</span><span class="sxs-lookup"><span data-stu-id="30f48-103">CreateRecord Data Block (Access custom web app)</span></span>

<span data-ttu-id="30f48-104">您可以使用 **CreateRecord** 数据块在指定表中创建新记录。</span><span class="sxs-lookup"><span data-stu-id="30f48-104">You can use the **CreateRecord** data block to create a new record in the specified table.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="30f48-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="30f48-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="30f48-107">**CreateRecord** 数据块仅适用于数据宏。</span><span class="sxs-lookup"><span data-stu-id="30f48-107">The **CreateRecord** data block is available only in Data Macros.</span></span> 
  
## <a name="setting"></a><span data-ttu-id="30f48-108">Setting</span><span class="sxs-lookup"><span data-stu-id="30f48-108">Setting</span></span>

<span data-ttu-id="30f48-109">**DeleteRecord** 数据块具有以下参数。</span><span class="sxs-lookup"><span data-stu-id="30f48-109">The **CreateRecord** data block has the following arguments.</span></span> 
  
<span data-ttu-id="30f48-110">**DeleteRecord** 数据块具有以下参数。</span><span class="sxs-lookup"><span data-stu-id="30f48-110">The **CreateRecord** data block has the following arguments.</span></span> 
  
|<span data-ttu-id="30f48-111">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="30f48-111">**Argument name**</span></span>|<span data-ttu-id="30f48-112">**必需**</span><span class="sxs-lookup"><span data-stu-id="30f48-112">**Required**</span></span>|<span data-ttu-id="30f48-113">**描述**</span><span class="sxs-lookup"><span data-stu-id="30f48-113">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="30f48-114">**Create a Record In**</span><span class="sxs-lookup"><span data-stu-id="30f48-114">**Create a Record In**</span></span> <br/> |<span data-ttu-id="30f48-115">是</span><span class="sxs-lookup"><span data-stu-id="30f48-115">Yes</span></span>  <br/> |<span data-ttu-id="30f48-116">要在其中创建新记录的表的名称。</span><span class="sxs-lookup"><span data-stu-id="30f48-116">The name of the table to create the new record in.</span></span>  <br/> |
|<span data-ttu-id="30f48-117">**Alias**</span><span class="sxs-lookup"><span data-stu-id="30f48-117">**Alias**</span></span> <br/> |<span data-ttu-id="30f48-118">否</span><span class="sxs-lookup"><span data-stu-id="30f48-118">No</span></span>  <br/> |<span data-ttu-id="30f48-119">一个标识记录的字符串。</span><span class="sxs-lookup"><span data-stu-id="30f48-119">A string that identifies the record.</span></span> <span data-ttu-id="30f48-120">您可以使用记录的别名来标识该记录</span><span class="sxs-lookup"><span data-stu-id="30f48-120">You can use the record's alias to identify</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="30f48-121">说明</span><span class="sxs-lookup"><span data-stu-id="30f48-121">Remarks</span></span>

<span data-ttu-id="30f48-122">**CreateRecord** 创建的记录会自动成为当前记录。</span><span class="sxs-lookup"><span data-stu-id="30f48-122">The record created by **CreateRecord** automatically becomes the current record.</span></span> 
  
<span data-ttu-id="30f48-123">在**CreateRecord**语句后, 可以插入一个在新记录提交之前执行的命令块。</span><span class="sxs-lookup"><span data-stu-id="30f48-123">After **CreateRecord** statement, you can insert a block of commands that will execute before the new record is committed.</span></span> <span data-ttu-id="30f48-124">以下操作适用于 **CreateRecord** 数据块。</span><span class="sxs-lookup"><span data-stu-id="30f48-124">The following actions are available in a **CreateRecord** data block.</span></span> 
  
||
|:-----|
|[<span data-ttu-id="30f48-125">CancelRecordChange 宏操作</span><span class="sxs-lookup"><span data-stu-id="30f48-125">CancelRecordChange Macro Action</span></span>](cancelrecordchange-macro-action-access-custom-web-app.md) <br/> |
|[<span data-ttu-id="30f48-126">Comment 宏语句</span><span class="sxs-lookup"><span data-stu-id="30f48-126">Comment Macro Statement</span></span>](comment-macro-block-access-custom-web-app.md) <br/> |
|[<span data-ttu-id="30f48-127">Group 宏语句</span><span class="sxs-lookup"><span data-stu-id="30f48-127">Group Macro Statement</span></span>](group-macro-block-access-custom-web-app.md) <br/> |
|[<span data-ttu-id="30f48-128">If...Then...Else 宏语句</span><span class="sxs-lookup"><span data-stu-id="30f48-128">If...Then...Else Macro Statement</span></span>](ifthenelse-macro-block-access-custom-web-app.md) <br/> |
|[<span data-ttu-id="30f48-129">SetField 宏操作</span><span class="sxs-lookup"><span data-stu-id="30f48-129">SetField Macro Action</span></span>](setfield-macro-action-access-custom-web-app.md) <br/> |
|[<span data-ttu-id="30f48-130">SetLocalVar 宏操作</span><span class="sxs-lookup"><span data-stu-id="30f48-130">SetLocalVar Macro Action</span></span>](setlocalvar-macro-action-access-custom-web-app.md) <br/> |
   
<span data-ttu-id="30f48-131">在 **CreateRecord** 操作创建记录后，可使用 **SetField** 操作在该新记录中指定字段值。</span><span class="sxs-lookup"><span data-stu-id="30f48-131">After the **CreateRecord** action creates a record, use the **SetField** action to specify a value of a field in the new record.</span></span> 
  
<span data-ttu-id="30f48-132">可以使用**If .。。然后 .。。Else**语句来执行基于条件的操作。</span><span class="sxs-lookup"><span data-stu-id="30f48-132">You can use an **If...Then...Else** statement to perform operations based on a condition.</span></span> 
  
<span data-ttu-id="30f48-p104">若要取消创建记录，可使用 **CancelRecordChange** 操作。此操作将阻止提交更改并退出 **CreateRecord** 数据块。</span><span class="sxs-lookup"><span data-stu-id="30f48-p104">To cancel the creation of a record, use the **CancelRecordChange** action. This prevents the changes from being committed and exits the **CreateRecord** data block.</span></span> 
  
<span data-ttu-id="30f48-135">提交新记录后，可以使用 **LastCreateRecordIdentity** 本地变量来处理该记录。</span><span class="sxs-lookup"><span data-stu-id="30f48-135">Once the new record is committed, you can use the **LastCreateRecordIdentity** local variable to work with the record.</span></span> <span data-ttu-id="30f48-136">例如, 使用以下语法来引用最近创建的记录的 "分配给" 字段。</span><span class="sxs-lookup"><span data-stu-id="30f48-136">For example, use the following syntax to refer to the AssignedTo field of the most recently created record.</span></span> 
  
`[LastCreateRecordIdentity].[AssignedTo]`


