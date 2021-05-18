---
title: IPersistMessage IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IPersistMessage
api_type:
- COM
ms.assetid: 40ec6dd4-2206-4e59-aafe-53aaf693f973
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7eb65bbae2fca6648c3a701dfa5c83c5bf297ec5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32309602"
---
# <a name="ipersistmessage--iunknown"></a><span data-ttu-id="d5520-103">IPersistMessage : IUnknown</span><span class="sxs-lookup"><span data-stu-id="d5520-103">IPersistMessage : IUnknown</span></span>

  
  
<span data-ttu-id="d5520-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d5520-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d5520-105">允许表单查看器处理表单的存储以及在各种状态之间转换。</span><span class="sxs-lookup"><span data-stu-id="d5520-105">Enables form viewers to handle the storage of a form and to transition between the various states.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="d5520-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="d5520-106">Header file:</span></span>  <br/> |<span data-ttu-id="d5520-107">Mapiform.h</span><span class="sxs-lookup"><span data-stu-id="d5520-107">Mapiform.h</span></span>  <br/> |
|<span data-ttu-id="d5520-108">公开者：</span><span class="sxs-lookup"><span data-stu-id="d5520-108">Exposed by:</span></span>  <br/> |<span data-ttu-id="d5520-109">保留邮件对象</span><span class="sxs-lookup"><span data-stu-id="d5520-109">Persist message objects</span></span>  <br/> |
|<span data-ttu-id="d5520-110">实现者：</span><span class="sxs-lookup"><span data-stu-id="d5520-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="d5520-111">表单对象</span><span class="sxs-lookup"><span data-stu-id="d5520-111">Form objects</span></span>  <br/> |
|<span data-ttu-id="d5520-112">调用者：</span><span class="sxs-lookup"><span data-stu-id="d5520-112">Called by:</span></span>  <br/> |<span data-ttu-id="d5520-113">表单查看器</span><span class="sxs-lookup"><span data-stu-id="d5520-113">Form viewers</span></span>  <br/> |
|<span data-ttu-id="d5520-114">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="d5520-114">Interface identifier:</span></span>  <br/> |<span data-ttu-id="d5520-115">IID_IPersistMessage</span><span class="sxs-lookup"><span data-stu-id="d5520-115">IID_IPersistMessage</span></span>  <br/> |
|<span data-ttu-id="d5520-116">指针类型：</span><span class="sxs-lookup"><span data-stu-id="d5520-116">Pointer type:</span></span>  <br/> |<span data-ttu-id="d5520-117">LPPERSISTMESSAGE</span><span class="sxs-lookup"><span data-stu-id="d5520-117">LPPERSISTMESSAGE</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="d5520-118">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="d5520-118">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="d5520-119">GetLastError</span><span class="sxs-lookup"><span data-stu-id="d5520-119">GetLastError</span></span>](ipersistmessage-getlasterror.md) <br/> |<span data-ttu-id="d5520-120">返回一 [个 MAPIERROR](mapierror.md) 结构，其中包含有关表单对象中上一个错误的信息。</span><span class="sxs-lookup"><span data-stu-id="d5520-120">Returns a [MAPIERROR](mapierror.md) structure that contains information about the previous error in the form object.</span></span>  <br/> |
|[<span data-ttu-id="d5520-121">GetClassID</span><span class="sxs-lookup"><span data-stu-id="d5520-121">GetClassID</span></span>](ipersistmessage-getclassid.md) <br/> |<span data-ttu-id="d5520-122">返回一个标识符，该标识符代表可以管理表单的表单服务器。</span><span class="sxs-lookup"><span data-stu-id="d5520-122">Returns an identifier that represents the form server that can manage the form.</span></span>  <br/> |
|[<span data-ttu-id="d5520-123">IsDirty</span><span class="sxs-lookup"><span data-stu-id="d5520-123">IsDirty</span></span>](ipersistmessage-isdirty.md) <br/> |<span data-ttu-id="d5520-124">检查表单中自上次保存以来所做的更改。</span><span class="sxs-lookup"><span data-stu-id="d5520-124">Checks the form for changes that were made since the last save.</span></span>  <br/> |
|[<span data-ttu-id="d5520-125">InitNew</span><span class="sxs-lookup"><span data-stu-id="d5520-125">InitNew</span></span>](ipersistmessage-initnew.md) <br/> |<span data-ttu-id="d5520-126">初始化新邮件。</span><span class="sxs-lookup"><span data-stu-id="d5520-126">Initializes a new message.</span></span>  <br/> |
|[<span data-ttu-id="d5520-127">Load</span><span class="sxs-lookup"><span data-stu-id="d5520-127">Load</span></span>](ipersistmessage-load.md) <br/> |<span data-ttu-id="d5520-128">为指定邮件加载窗体。</span><span class="sxs-lookup"><span data-stu-id="d5520-128">Loads the form for a specified message.</span></span>  <br/> |
|[<span data-ttu-id="d5520-129">Save</span><span class="sxs-lookup"><span data-stu-id="d5520-129">Save</span></span>](ipersistmessage-save.md) <br/> |<span data-ttu-id="d5520-130">将修改后的窗体保存回已加载或创建该窗体的邮件。</span><span class="sxs-lookup"><span data-stu-id="d5520-130">Saves a revised form back to the message from which it was loaded or created.</span></span>  <br/> |
|[<span data-ttu-id="d5520-131">SaveCompleted</span><span class="sxs-lookup"><span data-stu-id="d5520-131">SaveCompleted</span></span>](ipersistmessage-savecompleted.md) <br/> |<span data-ttu-id="d5520-132">通知窗体保存操作已完成。</span><span class="sxs-lookup"><span data-stu-id="d5520-132">Notifies the form that a save operation has been completed.</span></span>  <br/> |
|[<span data-ttu-id="d5520-133">HandsOffMessage</span><span class="sxs-lookup"><span data-stu-id="d5520-133">HandsOffMessage</span></span>](ipersistmessage-handsoffmessage.md) <br/> |<span data-ttu-id="d5520-134">使表单释放其当前邮件。</span><span class="sxs-lookup"><span data-stu-id="d5520-134">Causes the form to release its current message.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d5520-135">备注</span><span class="sxs-lookup"><span data-stu-id="d5520-135">Remarks</span></span>

<span data-ttu-id="d5520-136">实现 **IPersistMessage** 接口需要所有表单。</span><span class="sxs-lookup"><span data-stu-id="d5520-136">All forms are required to implement the **IPersistMessage** interface.</span></span> 
  
 <span data-ttu-id="d5520-137">**IPersistMessage** 的工作方式类似于 OLE [IPersistStorage](https://msdn.microsoft.com/library/1c1a20fc-c101-4cbc-a7a6-30613aa387d7%28Office.15%29.aspx) 接口。</span><span class="sxs-lookup"><span data-stu-id="d5520-137">**IPersistMessage** works similarly to the OLE [IPersistStorage](https://msdn.microsoft.com/library/1c1a20fc-c101-4cbc-a7a6-30613aa387d7%28Office.15%29.aspx) interface.</span></span> <span data-ttu-id="d5520-138">有关详细信息，请参阅 **IPersistStorage** 方法。</span><span class="sxs-lookup"><span data-stu-id="d5520-138">For more information, see the **IPersistStorage** methods.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="d5520-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d5520-139">See also</span></span>



[<span data-ttu-id="d5520-140">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="d5520-140">MAPI Interfaces</span></span>](mapi-interfaces.md)

