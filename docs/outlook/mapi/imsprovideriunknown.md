---
title: IMSProvider IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMSProvider
api_type:
- COM
ms.assetid: 0f17aa44-abcb-4732-b013-d91652847cf6
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c5305ddd20b690f5c2e5807fb7ce2410549f7124
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412861"
---
# <a name="imsprovider--iunknown"></a><span data-ttu-id="0aaf4-103">IMSProvider : IUnknown</span><span class="sxs-lookup"><span data-stu-id="0aaf4-103">IMSProvider : IUnknown</span></span>

  
  
<span data-ttu-id="0aaf4-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0aaf4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0aaf4-105">通过邮件存储提供程序对象提供对邮件存储提供程序的访问。</span><span class="sxs-lookup"><span data-stu-id="0aaf4-105">Provides access to a message store provider through a message store provider object.</span></span> <span data-ttu-id="0aaf4-106">邮件存储提供程序的 [MSProviderInit](msproviderinit.md) 入口点函数在提供程序登录时返回此消息存储提供程序对象。</span><span class="sxs-lookup"><span data-stu-id="0aaf4-106">This message store provider object is returned at provider logon by the message store provider's [MSProviderInit](msproviderinit.md) entry point function.</span></span> <span data-ttu-id="0aaf4-107">邮件存储提供程序对象主要由客户端应用程序和 MAPI 后台处理程序用于打开邮件存储。</span><span class="sxs-lookup"><span data-stu-id="0aaf4-107">The message store provider object is primarily used by client applications and the MAPI spooler to open message stores.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="0aaf4-108">标头文件：</span><span class="sxs-lookup"><span data-stu-id="0aaf4-108">Header file:</span></span>  <br/> |<span data-ttu-id="0aaf4-109">Mapispi.h</span><span class="sxs-lookup"><span data-stu-id="0aaf4-109">Mapispi.h</span></span>  <br/> |
|<span data-ttu-id="0aaf4-110">公开者：</span><span class="sxs-lookup"><span data-stu-id="0aaf4-110">Exposed by:</span></span>  <br/> |<span data-ttu-id="0aaf4-111">邮件存储提供程序对象</span><span class="sxs-lookup"><span data-stu-id="0aaf4-111">Message store provider objects</span></span>  <br/> |
|<span data-ttu-id="0aaf4-112">实现者：</span><span class="sxs-lookup"><span data-stu-id="0aaf4-112">Implemented by:</span></span>  <br/> |<span data-ttu-id="0aaf4-113">邮件存储提供程序</span><span class="sxs-lookup"><span data-stu-id="0aaf4-113">Message store providers</span></span>  <br/> |
|<span data-ttu-id="0aaf4-114">调用者：</span><span class="sxs-lookup"><span data-stu-id="0aaf4-114">Called by:</span></span>  <br/> |<span data-ttu-id="0aaf4-115">MAPI 和 MAPI 后台处理程序</span><span class="sxs-lookup"><span data-stu-id="0aaf4-115">MAPI and the MAPI spooler</span></span>  <br/> |
|<span data-ttu-id="0aaf4-116">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="0aaf4-116">Interface identifier:</span></span>  <br/> |<span data-ttu-id="0aaf4-117">IID_IMSProvider</span><span class="sxs-lookup"><span data-stu-id="0aaf4-117">IID_IMSProvider</span></span>  <br/> |
|<span data-ttu-id="0aaf4-118">指针类型：</span><span class="sxs-lookup"><span data-stu-id="0aaf4-118">Pointer type:</span></span>  <br/> |<span data-ttu-id="0aaf4-119">LPMSPROVIDER</span><span class="sxs-lookup"><span data-stu-id="0aaf4-119">LPMSPROVIDER</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="0aaf4-120">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="0aaf4-120">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="0aaf4-121">关闭</span><span class="sxs-lookup"><span data-stu-id="0aaf4-121">Shutdown</span></span>](imsprovider-shutdown.md) <br/> |<span data-ttu-id="0aaf4-122">以有序方式关闭邮件存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="0aaf4-122">Closes a message store provider in an orderly fashion.</span></span>  <br/> |
|[<span data-ttu-id="0aaf4-123">登录</span><span class="sxs-lookup"><span data-stu-id="0aaf4-123">Logon</span></span>](imsprovider-logon.md) <br/> |<span data-ttu-id="0aaf4-124">将 MAPI 记录到邮件存储提供程序的一个实例。</span><span class="sxs-lookup"><span data-stu-id="0aaf4-124">Logs MAPI on to one instance of a message store provider.</span></span>  <br/> |
|[<span data-ttu-id="0aaf4-125">SpoolerLogon</span><span class="sxs-lookup"><span data-stu-id="0aaf4-125">SpoolerLogon</span></span>](imsprovider-spoolerlogon.md) <br/> |<span data-ttu-id="0aaf4-126">将 MAPI 后台处理程序记录到邮件存储。</span><span class="sxs-lookup"><span data-stu-id="0aaf4-126">Logs the MAPI spooler on to a message store.</span></span>  <br/> |
|[<span data-ttu-id="0aaf4-127">CompareStoreIDs</span><span class="sxs-lookup"><span data-stu-id="0aaf4-127">CompareStoreIDs</span></span>](imsprovider-comparestoreids.md) <br/> |<span data-ttu-id="0aaf4-128">比较两个邮件存储条目标识符以确定它们是否引用同一存储对象。</span><span class="sxs-lookup"><span data-stu-id="0aaf4-128">Compares two message store entry identifiers to determine whether they refer to the same store object.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="0aaf4-129">备注</span><span class="sxs-lookup"><span data-stu-id="0aaf4-129">Remarks</span></span>

<span data-ttu-id="0aaf4-130">MAPI 每个会话使用一个邮件存储提供程序对象，无论存储提供程序打开的邮件存储数如何。</span><span class="sxs-lookup"><span data-stu-id="0aaf4-130">MAPI uses one message store provider object per session, no matter how many message stores are opened by the store provider.</span></span> <span data-ttu-id="0aaf4-131">如果第二个 MAPI 会话登录到任何打开的存储区，MAPI 将第二次调用 **MSProviderInit，** 以创建供该会话使用的新邮件存储提供程序对象。</span><span class="sxs-lookup"><span data-stu-id="0aaf4-131">If a second MAPI session logs on to any open stores, MAPI calls **MSProviderInit** a second time to create a new message store provider object for that session to use.</span></span> 
  
<span data-ttu-id="0aaf4-132">邮件存储提供程序对象必须包含以下内容，以正常运行：</span><span class="sxs-lookup"><span data-stu-id="0aaf4-132">A message store provider object must contain the following to operate correctly:</span></span>
  
- <span data-ttu-id="0aaf4-133">供使用此提供程序对象打开的所有存储区使用的  _lpMalloc_ 内存分配例程指针。</span><span class="sxs-lookup"><span data-stu-id="0aaf4-133">An  _lpMalloc_ memory-allocation routine pointer for use by all stores opened by using this provider object.</span></span> 
    
- <span data-ttu-id="0aaf4-134">_lpfAllocateBuffer_、_ lpfAllocateMore _和 _lpfFreeBuffer_ 例程指针，指向 [MAPIAllocateBuffer、MAPIAllocateMore](mapiallocatebuffer.md)和 [MAPIFreeBuffer](mapifreebuffer.md)内存分配函数。 [](mapiallocatemore.md)</span><span class="sxs-lookup"><span data-stu-id="0aaf4-134">The  _lpfAllocateBuffer_,  _ lpfAllocateMore _, and  _lpfFreeBuffer_ routine pointers to the [MAPIAllocateBuffer](mapiallocatebuffer.md), [MAPIAllocateMore](mapiallocatemore.md), and [MAPIFreeBuffer](mapifreebuffer.md) memory allocation functions.</span></span> 
    
- <span data-ttu-id="0aaf4-135">使用此提供程序对象打开但尚未关闭的所有存储区的链接列表。</span><span class="sxs-lookup"><span data-stu-id="0aaf4-135">A linked list of all the stores opened by using this provider object and not yet closed.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="0aaf4-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0aaf4-136">See also</span></span>



[<span data-ttu-id="0aaf4-137">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="0aaf4-137">MAPI Interfaces</span></span>](mapi-interfaces.md)

