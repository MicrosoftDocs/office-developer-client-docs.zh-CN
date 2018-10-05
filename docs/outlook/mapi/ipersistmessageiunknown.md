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
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25396181"
---
# <a name="ipersistmessage--iunknown"></a><span data-ttu-id="f1435-103">IPersistMessage : IUnknown</span><span class="sxs-lookup"><span data-stu-id="f1435-103">IPersistMessage : IUnknown</span></span>

  
  
<span data-ttu-id="f1435-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f1435-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f1435-105">启用表单查看器处理存储窗体和各种状态间转换。</span><span class="sxs-lookup"><span data-stu-id="f1435-105">Enables form viewers to handle the storage of a form and to transition between the various states.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="f1435-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="f1435-106">Header file:</span></span>  <br/> |<span data-ttu-id="f1435-107">Mapiform.h</span><span class="sxs-lookup"><span data-stu-id="f1435-107">Mapiform.h</span></span>  <br/> |
|<span data-ttu-id="f1435-108">由公开：</span><span class="sxs-lookup"><span data-stu-id="f1435-108">Exposed by:</span></span>  <br/> |<span data-ttu-id="f1435-109">保留消息对象</span><span class="sxs-lookup"><span data-stu-id="f1435-109">Persist message objects</span></span>  <br/> |
|<span data-ttu-id="f1435-110">实现者：</span><span class="sxs-lookup"><span data-stu-id="f1435-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="f1435-111">窗体对象</span><span class="sxs-lookup"><span data-stu-id="f1435-111">Form objects</span></span>  <br/> |
|<span data-ttu-id="f1435-112">调用者：</span><span class="sxs-lookup"><span data-stu-id="f1435-112">Called by:</span></span>  <br/> |<span data-ttu-id="f1435-113">表单查看器</span><span class="sxs-lookup"><span data-stu-id="f1435-113">Form viewers</span></span>  <br/> |
|<span data-ttu-id="f1435-114">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="f1435-114">Interface identifier:</span></span>  <br/> |<span data-ttu-id="f1435-115">IID_IPersistMessage</span><span class="sxs-lookup"><span data-stu-id="f1435-115">IID_IPersistMessage</span></span>  <br/> |
|<span data-ttu-id="f1435-116">指针类型：</span><span class="sxs-lookup"><span data-stu-id="f1435-116">Pointer type:</span></span>  <br/> |<span data-ttu-id="f1435-117">LPPERSISTMESSAGE</span><span class="sxs-lookup"><span data-stu-id="f1435-117">LPPERSISTMESSAGE</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="f1435-118">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="f1435-118">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="f1435-119">时出错</span><span class="sxs-lookup"><span data-stu-id="f1435-119">GetLastError</span></span>](ipersistmessage-getlasterror.md) <br/> |<span data-ttu-id="f1435-120">返回一个[MAPIERROR](mapierror.md)结构，其中包含有关表单对象中前面的错误的信息。</span><span class="sxs-lookup"><span data-stu-id="f1435-120">Returns a [MAPIERROR](mapierror.md) structure that contains information about the previous error in the form object.</span></span>  <br/> |
|[<span data-ttu-id="f1435-121">GetClassID</span><span class="sxs-lookup"><span data-stu-id="f1435-121">GetClassID</span></span>](ipersistmessage-getclassid.md) <br/> |<span data-ttu-id="f1435-122">返回表示可以管理窗体的窗体服务器的标识符。</span><span class="sxs-lookup"><span data-stu-id="f1435-122">Returns an identifier that represents the form server that can manage the form.</span></span>  <br/> |
|[<span data-ttu-id="f1435-123">IsDirty</span><span class="sxs-lookup"><span data-stu-id="f1435-123">IsDirty</span></span>](ipersistmessage-isdirty.md) <br/> |<span data-ttu-id="f1435-124">检查自上次保存以来所做的更改的表单。</span><span class="sxs-lookup"><span data-stu-id="f1435-124">Checks the form for changes that were made since the last save.</span></span>  <br/> |
|[<span data-ttu-id="f1435-125">丢失</span><span class="sxs-lookup"><span data-stu-id="f1435-125">InitNew</span></span>](ipersistmessage-initnew.md) <br/> |<span data-ttu-id="f1435-126">初始化新邮件。</span><span class="sxs-lookup"><span data-stu-id="f1435-126">Initializes a new message.</span></span>  <br/> |
|[<span data-ttu-id="f1435-127">加载</span><span class="sxs-lookup"><span data-stu-id="f1435-127">Load</span></span>](ipersistmessage-load.md) <br/> |<span data-ttu-id="f1435-128">加载指定的消息的窗体。</span><span class="sxs-lookup"><span data-stu-id="f1435-128">Loads the form for a specified message.</span></span>  <br/> |
|[<span data-ttu-id="f1435-129">Save</span><span class="sxs-lookup"><span data-stu-id="f1435-129">Save</span></span>](ipersistmessage-save.md) <br/> |<span data-ttu-id="f1435-130">将修订后的表单保存回其已加载或创建的邮件。</span><span class="sxs-lookup"><span data-stu-id="f1435-130">Saves a revised form back to the message from which it was loaded or created.</span></span>  <br/> |
|[<span data-ttu-id="f1435-131">SaveCompleted</span><span class="sxs-lookup"><span data-stu-id="f1435-131">SaveCompleted</span></span>](ipersistmessage-savecompleted.md) <br/> |<span data-ttu-id="f1435-132">通知窗体的保存操作已完成。</span><span class="sxs-lookup"><span data-stu-id="f1435-132">Notifies the form that a save operation has been completed.</span></span>  <br/> |
|[<span data-ttu-id="f1435-133">HandsOffMessage</span><span class="sxs-lookup"><span data-stu-id="f1435-133">HandsOffMessage</span></span>](ipersistmessage-handsoffmessage.md) <br/> |<span data-ttu-id="f1435-134">使窗体释放其当前邮件。</span><span class="sxs-lookup"><span data-stu-id="f1435-134">Causes the form to release its current message.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f1435-135">说明</span><span class="sxs-lookup"><span data-stu-id="f1435-135">Remarks</span></span>

<span data-ttu-id="f1435-136">实现**IPersistMessage**接口所需的所有表单。</span><span class="sxs-lookup"><span data-stu-id="f1435-136">All forms are required to implement the **IPersistMessage** interface.</span></span> 
  
 <span data-ttu-id="f1435-137">**IPersistMessage**同样适用于 OLE [IPersistStorage](https://msdn.microsoft.com/library/1c1a20fc-c101-4cbc-a7a6-30613aa387d7%28Office.15%29.aspx)接口。</span><span class="sxs-lookup"><span data-stu-id="f1435-137">**IPersistMessage** works similarly to the OLE [IPersistStorage](https://msdn.microsoft.com/library/1c1a20fc-c101-4cbc-a7a6-30613aa387d7%28Office.15%29.aspx) interface.</span></span> <span data-ttu-id="f1435-138">有关详细信息，请参阅**IPersistStorage**方法。</span><span class="sxs-lookup"><span data-stu-id="f1435-138">For more information, see the **IPersistStorage** methods.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="f1435-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f1435-139">See also</span></span>



[<span data-ttu-id="f1435-140">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="f1435-140">MAPI Interfaces</span></span>](mapi-interfaces.md)

