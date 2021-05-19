---
title: 'CreateRecord Data Block (Access 自定义 Web 应用) '
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
# <a name="createrecord-data-block-access-custom-web-app"></a><span data-ttu-id="a48e4-103">CreateRecord Data Block (Access 自定义 Web 应用) </span><span class="sxs-lookup"><span data-stu-id="a48e4-103">CreateRecord Data Block (Access custom web app)</span></span>

<span data-ttu-id="a48e4-104">您可以使用 **CreateRecord** 数据块在指定表中创建新记录。</span><span class="sxs-lookup"><span data-stu-id="a48e4-104">You can use the **CreateRecord** data block to create a new record in the specified table.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="a48e4-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="a48e4-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a48e4-107">**CreateRecord** 数据块仅适用于数据宏。</span><span class="sxs-lookup"><span data-stu-id="a48e4-107">The **CreateRecord** data block is available only in Data Macros.</span></span> 
  
## <a name="setting"></a><span data-ttu-id="a48e4-108">设置</span><span class="sxs-lookup"><span data-stu-id="a48e4-108">Setting</span></span>

<span data-ttu-id="a48e4-109">**DeleteRecord** 数据块具有以下参数。</span><span class="sxs-lookup"><span data-stu-id="a48e4-109">The **CreateRecord** data block has the following arguments.</span></span> 
  
<span data-ttu-id="a48e4-110">**DeleteRecord** 数据块具有以下参数。</span><span class="sxs-lookup"><span data-stu-id="a48e4-110">The **CreateRecord** data block has the following arguments.</span></span> 
  
|<span data-ttu-id="a48e4-111">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="a48e4-111">**Argument name**</span></span>|<span data-ttu-id="a48e4-112">**必需**</span><span class="sxs-lookup"><span data-stu-id="a48e4-112">**Required**</span></span>|<span data-ttu-id="a48e4-113">**描述**</span><span class="sxs-lookup"><span data-stu-id="a48e4-113">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a48e4-114">**Create a Record In**</span><span class="sxs-lookup"><span data-stu-id="a48e4-114">**Create a Record In**</span></span> <br/> |<span data-ttu-id="a48e4-115">是</span><span class="sxs-lookup"><span data-stu-id="a48e4-115">Yes</span></span>  <br/> |<span data-ttu-id="a48e4-116">要在其中创建新记录的表的名称。</span><span class="sxs-lookup"><span data-stu-id="a48e4-116">The name of the table to create the new record in.</span></span>  <br/> |
|<span data-ttu-id="a48e4-117">**Alias**</span><span class="sxs-lookup"><span data-stu-id="a48e4-117">**Alias**</span></span> <br/> |<span data-ttu-id="a48e4-118">否</span><span class="sxs-lookup"><span data-stu-id="a48e4-118">No</span></span>  <br/> |<span data-ttu-id="a48e4-119">标识记录的字符串。</span><span class="sxs-lookup"><span data-stu-id="a48e4-119">A string that identifies the record.</span></span> <span data-ttu-id="a48e4-120">您可以使用记录的别名来标识该记录</span><span class="sxs-lookup"><span data-stu-id="a48e4-120">You can use the record's alias to identify</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="a48e4-121">备注</span><span class="sxs-lookup"><span data-stu-id="a48e4-121">Remarks</span></span>

<span data-ttu-id="a48e4-122">**CreateRecord** 创建的记录会自动成为当前记录。</span><span class="sxs-lookup"><span data-stu-id="a48e4-122">The record created by **CreateRecord** automatically becomes the current record.</span></span> 
  
<span data-ttu-id="a48e4-123">在 **CreateRecord** 语句之后，可以插入将在提交新记录之前执行的命令块。</span><span class="sxs-lookup"><span data-stu-id="a48e4-123">After **CreateRecord** statement, you can insert a block of commands that will execute before the new record is committed.</span></span> <span data-ttu-id="a48e4-124">以下操作适用于 **CreateRecord** 数据块。</span><span class="sxs-lookup"><span data-stu-id="a48e4-124">The following actions are available in a **CreateRecord** data block.</span></span> 
  
||
|:-----|
|[<span data-ttu-id="a48e4-125">CancelRecordChange 宏操作</span><span class="sxs-lookup"><span data-stu-id="a48e4-125">CancelRecordChange Macro Action</span></span>](cancelrecordchange-macro-action-access-custom-web-app.md) <br/> |
|[<span data-ttu-id="a48e4-126">Comment 宏语句</span><span class="sxs-lookup"><span data-stu-id="a48e4-126">Comment Macro Statement</span></span>](comment-macro-block-access-custom-web-app.md) <br/> |
|[<span data-ttu-id="a48e4-127">Group 宏语句</span><span class="sxs-lookup"><span data-stu-id="a48e4-127">Group Macro Statement</span></span>](group-macro-block-access-custom-web-app.md) <br/> |
|[<span data-ttu-id="a48e4-128">If...Then...Else 宏语句</span><span class="sxs-lookup"><span data-stu-id="a48e4-128">If...Then...Else Macro Statement</span></span>](ifthenelse-macro-block-access-custom-web-app.md) <br/> |
|[<span data-ttu-id="a48e4-129">SetField 宏操作</span><span class="sxs-lookup"><span data-stu-id="a48e4-129">SetField Macro Action</span></span>](setfield-macro-action-access-custom-web-app.md) <br/> |
|[<span data-ttu-id="a48e4-130">SetLocalVar 宏操作</span><span class="sxs-lookup"><span data-stu-id="a48e4-130">SetLocalVar Macro Action</span></span>](setlocalvar-macro-action-access-custom-web-app.md) <br/> |
   
<span data-ttu-id="a48e4-131">在 **CreateRecord** 操作创建记录后，可使用 **SetField** 操作在该新记录中指定字段值。</span><span class="sxs-lookup"><span data-stu-id="a48e4-131">After the **CreateRecord** action creates a record, use the **SetField** action to specify a value of a field in the new record.</span></span> 
  
<span data-ttu-id="a48e4-132">可以使用 **If...然后...基于** 条件执行运算的 Else 语句。</span><span class="sxs-lookup"><span data-stu-id="a48e4-132">You can use an **If...Then...Else** statement to perform operations based on a condition.</span></span> 
  
<span data-ttu-id="a48e4-p104">若要取消创建记录，可使用 **CancelRecordChange** 操作。此操作将阻止提交更改并退出 **CreateRecord** 数据块。</span><span class="sxs-lookup"><span data-stu-id="a48e4-p104">To cancel the creation of a record, use the **CancelRecordChange** action. This prevents the changes from being committed and exits the **CreateRecord** data block.</span></span> 
  
<span data-ttu-id="a48e4-135">提交新记录后，可以使用 **LastCreateRecordIdentity** 本地变量来处理该记录。</span><span class="sxs-lookup"><span data-stu-id="a48e4-135">Once the new record is committed, you can use the **LastCreateRecordIdentity** local variable to work with the record.</span></span> <span data-ttu-id="a48e4-136">例如，使用以下语法引用最近创建的记录的 AssignedTo 字段。</span><span class="sxs-lookup"><span data-stu-id="a48e4-136">For example, use the following syntax to refer to the AssignedTo field of the most recently created record.</span></span> 
  
`[LastCreateRecordIdentity].[AssignedTo]`


