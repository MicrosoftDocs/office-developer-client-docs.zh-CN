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
ms.openlocfilehash: 1c00e54d02ba494c94c9826eabe142e1bd3b9a80
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22579625"
---
# <a name="imsprovider--iunknown"></a><span data-ttu-id="acbb3-103">IMSProvider : IUnknown</span><span class="sxs-lookup"><span data-stu-id="acbb3-103">IMSProvider : IUnknown</span></span>

  
  
<span data-ttu-id="acbb3-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="acbb3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="acbb3-105">提供对通过消息存储提供程序对象的消息存储提供程序的访问。</span><span class="sxs-lookup"><span data-stu-id="acbb3-105">Provides access to a message store provider through a message store provider object.</span></span> <span data-ttu-id="acbb3-106">此消息存储提供程序对象由消息存储提供程序的[MSProviderInit](msproviderinit.md)入口点函数返回在提供程序登录。</span><span class="sxs-lookup"><span data-stu-id="acbb3-106">This message store provider object is returned at provider logon by the message store provider's [MSProviderInit](msproviderinit.md) entry point function.</span></span> <span data-ttu-id="acbb3-107">消息存储提供程序对象主要由客户端应用程序和 MAPI 后台处理程序用于打开消息存储库。</span><span class="sxs-lookup"><span data-stu-id="acbb3-107">The message store provider object is primarily used by client applications and the MAPI spooler to open message stores.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="acbb3-108">头文件：</span><span class="sxs-lookup"><span data-stu-id="acbb3-108">Header file:</span></span>  <br/> |<span data-ttu-id="acbb3-109">Mapispi.h</span><span class="sxs-lookup"><span data-stu-id="acbb3-109">Mapispi.h</span></span>  <br/> |
|<span data-ttu-id="acbb3-110">由公开：</span><span class="sxs-lookup"><span data-stu-id="acbb3-110">Exposed by:</span></span>  <br/> |<span data-ttu-id="acbb3-111">消息存储提供程序对象</span><span class="sxs-lookup"><span data-stu-id="acbb3-111">Message store provider objects</span></span>  <br/> |
|<span data-ttu-id="acbb3-112">通过实现：</span><span class="sxs-lookup"><span data-stu-id="acbb3-112">Implemented by:</span></span>  <br/> |<span data-ttu-id="acbb3-113">消息存储提供程序</span><span class="sxs-lookup"><span data-stu-id="acbb3-113">Message store providers</span></span>  <br/> |
|<span data-ttu-id="acbb3-114">调用：</span><span class="sxs-lookup"><span data-stu-id="acbb3-114">Called by:</span></span>  <br/> |<span data-ttu-id="acbb3-115">MAPI 和 MAPI 后台处理程序</span><span class="sxs-lookup"><span data-stu-id="acbb3-115">MAPI and the MAPI spooler</span></span>  <br/> |
|<span data-ttu-id="acbb3-116">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="acbb3-116">Interface identifier:</span></span>  <br/> |<span data-ttu-id="acbb3-117">IID_IMSProvider</span><span class="sxs-lookup"><span data-stu-id="acbb3-117">IID_IMSProvider</span></span>  <br/> |
|<span data-ttu-id="acbb3-118">指针类型：</span><span class="sxs-lookup"><span data-stu-id="acbb3-118">Pointer type:</span></span>  <br/> |<span data-ttu-id="acbb3-119">LPMSPROVIDER</span><span class="sxs-lookup"><span data-stu-id="acbb3-119">LPMSPROVIDER</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="acbb3-120">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="acbb3-120">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="acbb3-121">关闭</span><span class="sxs-lookup"><span data-stu-id="acbb3-121">Shutdown</span></span>](imsprovider-shutdown.md) <br/> |<span data-ttu-id="acbb3-122">关闭中有序的方式的消息存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="acbb3-122">Closes a message store provider in an orderly fashion.</span></span>  <br/> |
|[<span data-ttu-id="acbb3-123">登录</span><span class="sxs-lookup"><span data-stu-id="acbb3-123">Logon</span></span>](imsprovider-logon.md) <br/> |<span data-ttu-id="acbb3-124">日志 MAPI 到消息存储提供程序的一个实例。</span><span class="sxs-lookup"><span data-stu-id="acbb3-124">Logs MAPI on to one instance of a message store provider.</span></span>  <br/> |
|[<span data-ttu-id="acbb3-125">SpoolerLogon</span><span class="sxs-lookup"><span data-stu-id="acbb3-125">SpoolerLogon</span></span>](imsprovider-spoolerlogon.md) <br/> |<span data-ttu-id="acbb3-126">记录到的消息存储 MAPI 后台处理程序。</span><span class="sxs-lookup"><span data-stu-id="acbb3-126">Logs the MAPI spooler on to a message store.</span></span>  <br/> |
|[<span data-ttu-id="acbb3-127">CompareStoreIDs</span><span class="sxs-lookup"><span data-stu-id="acbb3-127">CompareStoreIDs</span></span>](imsprovider-comparestoreids.md) <br/> |<span data-ttu-id="acbb3-128">比较两个邮件存储条目标识符，以确定它们是否引用同一个 store 对象。</span><span class="sxs-lookup"><span data-stu-id="acbb3-128">Compares two message store entry identifiers to determine whether they refer to the same store object.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="acbb3-129">注解</span><span class="sxs-lookup"><span data-stu-id="acbb3-129">Remarks</span></span>

<span data-ttu-id="acbb3-130">MAPI 使用一个每个会话的消息存储提供程序对象，无论多少消息存储打开存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="acbb3-130">MAPI uses one message store provider object per session, no matter how many message stores are opened by the store provider.</span></span> <span data-ttu-id="acbb3-131">如果第二个 MAPI 会话登录到任何打开的存储，MAPI 调用**MSProviderInit**第二次创建该会话中使用新的消息存储提供程序对象。</span><span class="sxs-lookup"><span data-stu-id="acbb3-131">If a second MAPI session logs on to any open stores, MAPI calls **MSProviderInit** a second time to create a new message store provider object for that session to use.</span></span> 
  
<span data-ttu-id="acbb3-132">消息存储提供程序对象必须包含以下内容以正常运行：</span><span class="sxs-lookup"><span data-stu-id="acbb3-132">A message store provider object must contain the following to operate correctly:</span></span>
  
- <span data-ttu-id="acbb3-133">_LpMalloc_内存分配例行指针以供使用此提供商对象打开的所有存储区。</span><span class="sxs-lookup"><span data-stu-id="acbb3-133">An  _lpMalloc_ memory-allocation routine pointer for use by all stores opened by using this provider object.</span></span> 
    
- <span data-ttu-id="acbb3-134">_LpfAllocateBuffer_、 _ lpfAllocateMore _ 和_lpfFreeBuffer_例行指针[MAPIAllocateBuffer](mapiallocatebuffer.md)、 [MAPIAllocateMore](mapiallocatemore.md)和[MAPIFreeBuffer](mapifreebuffer.md)内存分配功能。</span><span class="sxs-lookup"><span data-stu-id="acbb3-134">The  _lpfAllocateBuffer_,  _ lpfAllocateMore _, and  _lpfFreeBuffer_ routine pointers to the [MAPIAllocateBuffer](mapiallocatebuffer.md), [MAPIAllocateMore](mapiallocatemore.md), and [MAPIFreeBuffer](mapifreebuffer.md) memory allocation functions.</span></span> 
    
- <span data-ttu-id="acbb3-135">使用此提供商对象打开并且尚未关闭的所有存储的链接的列表。</span><span class="sxs-lookup"><span data-stu-id="acbb3-135">A linked list of all the stores opened by using this provider object and not yet closed.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="acbb3-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="acbb3-136">See also</span></span>



[<span data-ttu-id="acbb3-137">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="acbb3-137">MAPI Interfaces</span></span>](mapi-interfaces.md)

