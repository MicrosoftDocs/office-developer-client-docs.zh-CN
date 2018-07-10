---
title: EditRecord 数据块 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 54975434-78b2-4010-b2f9-f277831fa92e
description: 您可以使用 EditRecord 数据块更改现有记录中包含的值。
ms.openlocfilehash: 6c214e48326a93cff220b5436d7e7802cd6e3431
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773434"
---
# <a name="editrecord-data-block-access-custom-web-app"></a><span data-ttu-id="c862b-103">EditRecord 数据块 （访问自定义 web 应用程序）</span><span class="sxs-lookup"><span data-stu-id="c862b-103">EditRecord Data Block (Access custom web app)</span></span>

<span data-ttu-id="c862b-104">您可以使用 **EditRecord** 数据块更改现有记录中包含的值。</span><span class="sxs-lookup"><span data-stu-id="c862b-104">You can use the **EditRecord** data block to change the values contained in an existing record.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="c862b-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/zh-cn/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="c862b-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/zh-cn/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="c862b-107">**EditRecord** 数据块仅适用于数据宏。</span><span class="sxs-lookup"><span data-stu-id="c862b-107">The **EditRecord** data block is available only in Data Macros.</span></span> 
  
## <a name="setting"></a><span data-ttu-id="c862b-108">设置</span><span class="sxs-lookup"><span data-stu-id="c862b-108">Setting</span></span>

<span data-ttu-id="c862b-109">**EditRecord** 数据块具有以下参数。</span><span class="sxs-lookup"><span data-stu-id="c862b-109">The **EditRecord** data block has the following arguments.</span></span> 
  
|<span data-ttu-id="c862b-110">**参数**</span><span class="sxs-lookup"><span data-stu-id="c862b-110">**Argument**</span></span>|<span data-ttu-id="c862b-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="c862b-111">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c862b-112">**Alias**</span><span class="sxs-lookup"><span data-stu-id="c862b-112">**Alias**</span></span> <br/> |<span data-ttu-id="c862b-113">一个字符串，标识要编辑的记录。</span><span class="sxs-lookup"><span data-stu-id="c862b-113">A string that identifies the record to edit.</span></span> <span data-ttu-id="c862b-114">如果不指定*Alias*参数，则被编辑当前记录。</span><span class="sxs-lookup"><span data-stu-id="c862b-114">If the  *Alias*  argument is not specified, then the current record is edited.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="c862b-115">备注</span><span class="sxs-lookup"><span data-stu-id="c862b-115">Remarks</span></span>

<span data-ttu-id="c862b-116">**EditRecord**语句之后, 可插入的命令将执行提交到记录更改之前的块。</span><span class="sxs-lookup"><span data-stu-id="c862b-116">After the **EditRecord** statement, you can insert a block of commands that will execute before the changes to the record are committed.</span></span> <span data-ttu-id="c862b-117">**EditRecord**数据块有以下操作。</span><span class="sxs-lookup"><span data-stu-id="c862b-117">The following actions are available in an **EditRecord** data block.</span></span> 
  
||
|:-----|
|[<span data-ttu-id="c862b-118">CancelRecordChange 宏操作</span><span class="sxs-lookup"><span data-stu-id="c862b-118">CancelRecordChange Macro Action</span></span>](cancelrecordchange-macro-action-access-custom-web-app.md) <br/> |
|[<span data-ttu-id="c862b-119">注释宏语句</span><span class="sxs-lookup"><span data-stu-id="c862b-119">Comment Macro Statement</span></span>](comment-macro-block-access-custom-web-app.md) <br/> |
|[<span data-ttu-id="c862b-120">Group 宏语句</span><span class="sxs-lookup"><span data-stu-id="c862b-120">Group Macro Statement</span></span>](group-macro-block-access-custom-web-app.md) <br/> |
|[<span data-ttu-id="c862b-121">如果...然后...Else 宏语句</span><span class="sxs-lookup"><span data-stu-id="c862b-121">If...Then...Else Macro Statement</span></span>](ifthenelse-macro-block-access-custom-web-app.md) <br/> |
|[<span data-ttu-id="c862b-122">SetField 宏操作</span><span class="sxs-lookup"><span data-stu-id="c862b-122">SetField Macro Action</span></span>](setfield-macro-action-access-custom-web-app.md) <br/> |
|[<span data-ttu-id="c862b-123">SetLocalVar 宏操作</span><span class="sxs-lookup"><span data-stu-id="c862b-123">SetLocalVar Macro Action</span></span>](setlocalvar-macro-action-access-custom-web-app.md) <br/> |
   
<span data-ttu-id="c862b-124">使用 **SetField** 操作可以指定已编辑记录中某一字段的新值。</span><span class="sxs-lookup"><span data-stu-id="c862b-124">Use the **SetField** action to specify the new values of a field in the edited record.</span></span> 
  
<span data-ttu-id="c862b-125">如果，则可以使用 **...然后...其他**执行操作的语句基于条件。</span><span class="sxs-lookup"><span data-stu-id="c862b-125">You can use an **If...Then...Else** statement to perform operations based on a condition.</span></span> 
  
<span data-ttu-id="c862b-p104">若要取消编辑记录，可使用 **CancelRecordChange** 操作。此操作将阻止提交更改并退出 **EditRecord** 数据块。</span><span class="sxs-lookup"><span data-stu-id="c862b-p104">To cancel the editing of a record, use the **CancelRecordChange** action. This prevents the changes from being committed and exits the **EditRecord** data block.</span></span> 
  
<span data-ttu-id="c862b-128">您可以使用 **LastCreateRecordIdentity** 本地变量来处理在 **CreateRecord** 数据块中创建的最后一条记录。</span><span class="sxs-lookup"><span data-stu-id="c862b-128">You can use the **LastCreateRecordIdentity** local variable to work with last record created in a **CreateRecord** data block.</span></span> <span data-ttu-id="c862b-129">例如，使用以下语法引用 AssignedTo 字段的最近创建的记录：</span><span class="sxs-lookup"><span data-stu-id="c862b-129">For example, use the following syntax to refer to the AssignedTo field of the most recently created record:</span></span> 
  
`[LastCreateRecordIdentity].[AssignedTo]`


