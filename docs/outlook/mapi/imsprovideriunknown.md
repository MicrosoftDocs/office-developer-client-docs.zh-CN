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
# <a name="imsprovider--iunknown"></a><span data-ttu-id="4bcfa-103">IMSProvider : IUnknown</span><span class="sxs-lookup"><span data-stu-id="4bcfa-103">IMSProvider : IUnknown</span></span>

  
  
<span data-ttu-id="4bcfa-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4bcfa-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4bcfa-105">通过邮件存储提供程序对象提供对邮件存储区提供程序的访问。</span><span class="sxs-lookup"><span data-stu-id="4bcfa-105">Provides access to a message store provider through a message store provider object.</span></span> <span data-ttu-id="4bcfa-106">在提供程序登录时, 通过邮件存储提供程序的[MSProviderInit](msproviderinit.md)入口点函数返回此邮件存储区提供程序对象。</span><span class="sxs-lookup"><span data-stu-id="4bcfa-106">This message store provider object is returned at provider logon by the message store provider's [MSProviderInit](msproviderinit.md) entry point function.</span></span> <span data-ttu-id="4bcfa-107">邮件存储提供程序对象主要用于客户端应用程序和 MAPI 后台处理程序, 以打开邮件存储区。</span><span class="sxs-lookup"><span data-stu-id="4bcfa-107">The message store provider object is primarily used by client applications and the MAPI spooler to open message stores.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="4bcfa-108">标头文件：</span><span class="sxs-lookup"><span data-stu-id="4bcfa-108">Header file:</span></span>  <br/> |<span data-ttu-id="4bcfa-109">Mapispi</span><span class="sxs-lookup"><span data-stu-id="4bcfa-109">Mapispi.h</span></span>  <br/> |
|<span data-ttu-id="4bcfa-110">公开者:</span><span class="sxs-lookup"><span data-stu-id="4bcfa-110">Exposed by:</span></span>  <br/> |<span data-ttu-id="4bcfa-111">邮件存储提供程序对象</span><span class="sxs-lookup"><span data-stu-id="4bcfa-111">Message store provider objects</span></span>  <br/> |
|<span data-ttu-id="4bcfa-112">实现者：</span><span class="sxs-lookup"><span data-stu-id="4bcfa-112">Implemented by:</span></span>  <br/> |<span data-ttu-id="4bcfa-113">邮件存储区提供程序</span><span class="sxs-lookup"><span data-stu-id="4bcfa-113">Message store providers</span></span>  <br/> |
|<span data-ttu-id="4bcfa-114">调用者：</span><span class="sxs-lookup"><span data-stu-id="4bcfa-114">Called by:</span></span>  <br/> |<span data-ttu-id="4bcfa-115">mapi 和 mapi 后台处理程序</span><span class="sxs-lookup"><span data-stu-id="4bcfa-115">MAPI and the MAPI spooler</span></span>  <br/> |
|<span data-ttu-id="4bcfa-116">接口标识符:</span><span class="sxs-lookup"><span data-stu-id="4bcfa-116">Interface identifier:</span></span>  <br/> |<span data-ttu-id="4bcfa-117">IID_IMSProvider</span><span class="sxs-lookup"><span data-stu-id="4bcfa-117">IID_IMSProvider</span></span>  <br/> |
|<span data-ttu-id="4bcfa-118">指针类型:</span><span class="sxs-lookup"><span data-stu-id="4bcfa-118">Pointer type:</span></span>  <br/> |<span data-ttu-id="4bcfa-119">LPMSPROVIDER</span><span class="sxs-lookup"><span data-stu-id="4bcfa-119">LPMSPROVIDER</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="4bcfa-120">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="4bcfa-120">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="4bcfa-121">关闭</span><span class="sxs-lookup"><span data-stu-id="4bcfa-121">Shutdown</span></span>](imsprovider-shutdown.md) <br/> |<span data-ttu-id="4bcfa-122">以有序的方式关闭邮件存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="4bcfa-122">Closes a message store provider in an orderly fashion.</span></span>  <br/> |
|[<span data-ttu-id="4bcfa-123">登录</span><span class="sxs-lookup"><span data-stu-id="4bcfa-123">Logon</span></span>](imsprovider-logon.md) <br/> |<span data-ttu-id="4bcfa-124">将 MAPI 记录到邮件存储提供程序的一个实例上。</span><span class="sxs-lookup"><span data-stu-id="4bcfa-124">Logs MAPI on to one instance of a message store provider.</span></span>  <br/> |
|[<span data-ttu-id="4bcfa-125">SpoolerLogon</span><span class="sxs-lookup"><span data-stu-id="4bcfa-125">SpoolerLogon</span></span>](imsprovider-spoolerlogon.md) <br/> |<span data-ttu-id="4bcfa-126">将 MAPI 后台处理程序记录到邮件存储区。</span><span class="sxs-lookup"><span data-stu-id="4bcfa-126">Logs the MAPI spooler on to a message store.</span></span>  <br/> |
|[<span data-ttu-id="4bcfa-127">CompareStoreIDs</span><span class="sxs-lookup"><span data-stu-id="4bcfa-127">CompareStoreIDs</span></span>](imsprovider-comparestoreids.md) <br/> |<span data-ttu-id="4bcfa-128">比较两个邮件存储区条目标识符, 以确定它们是否引用同一个存储对象。</span><span class="sxs-lookup"><span data-stu-id="4bcfa-128">Compares two message store entry identifiers to determine whether they refer to the same store object.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="4bcfa-129">说明</span><span class="sxs-lookup"><span data-stu-id="4bcfa-129">Remarks</span></span>

<span data-ttu-id="4bcfa-130">无论由存储提供程序打开多少个邮件存储区, MAPI 都会对每个会话使用一个邮件存储提供程序对象。</span><span class="sxs-lookup"><span data-stu-id="4bcfa-130">MAPI uses one message store provider object per session, no matter how many message stores are opened by the store provider.</span></span> <span data-ttu-id="4bcfa-131">如果第二个 mapi 会话登录到任何打开的存储, 则 MAPI 会再次调用**MSProviderInit**以创建一个新的邮件存储提供程序对象, 以供该会话使用。</span><span class="sxs-lookup"><span data-stu-id="4bcfa-131">If a second MAPI session logs on to any open stores, MAPI calls **MSProviderInit** a second time to create a new message store provider object for that session to use.</span></span> 
  
<span data-ttu-id="4bcfa-132">若要正确运行, 邮件存储提供程序对象必须包含以下内容:</span><span class="sxs-lookup"><span data-stu-id="4bcfa-132">A message store provider object must contain the following to operate correctly:</span></span>
  
- <span data-ttu-id="4bcfa-133">一个_lpMalloc_内存分配例程指针, 可供使用此 provider 对象打开的所有存储使用。</span><span class="sxs-lookup"><span data-stu-id="4bcfa-133">An  _lpMalloc_ memory-allocation routine pointer for use by all stores opened by using this provider object.</span></span> 
    
- <span data-ttu-id="4bcfa-134">_lpfAllocateBuffer_、_ lpfAllocateMore _ 和_lpfFreeBuffer_例程指向[MAPIAllocateBuffer](mapiallocatebuffer.md)、 [MAPIAllocateMore](mapiallocatemore.md)和[MAPIFreeBuffer](mapifreebuffer.md)内存分配函数的指针。</span><span class="sxs-lookup"><span data-stu-id="4bcfa-134">The  _lpfAllocateBuffer_,  _ lpfAllocateMore _, and  _lpfFreeBuffer_ routine pointers to the [MAPIAllocateBuffer](mapiallocatebuffer.md), [MAPIAllocateMore](mapiallocatemore.md), and [MAPIFreeBuffer](mapifreebuffer.md) memory allocation functions.</span></span> 
    
- <span data-ttu-id="4bcfa-135">使用此提供程序对象打开且尚未关闭的所有存储的链接列表。</span><span class="sxs-lookup"><span data-stu-id="4bcfa-135">A linked list of all the stores opened by using this provider object and not yet closed.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="4bcfa-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4bcfa-136">See also</span></span>



[<span data-ttu-id="4bcfa-137">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="4bcfa-137">MAPI Interfaces</span></span>](mapi-interfaces.md)

