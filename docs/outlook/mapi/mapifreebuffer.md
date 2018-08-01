---
title: MAPIFreeBuffer
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPIFreeBuffer
api_type:
- HeaderDef
ms.assetid: 9412594f-8acc-4c7e-a668-4ec1da0ad9cf
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 22aad12010a4f367e18443d8c0831c6262cc37fc
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776390"
---
# <a name="mapifreebuffer"></a><span data-ttu-id="ed5dc-103">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="ed5dc-103">MAPIFreeBuffer</span></span>

  
  
<span data-ttu-id="ed5dc-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="ed5dc-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="ed5dc-105">释放内存缓冲区分配为[MAPIAllocateBuffer](mapiallocatebuffer.md)函数或[MAPIAllocateMore](mapiallocatemore.md)函数的调用。</span><span class="sxs-lookup"><span data-stu-id="ed5dc-105">Frees a memory buffer allocated with a call to the [MAPIAllocateBuffer](mapiallocatebuffer.md) function or the [MAPIAllocateMore](mapiallocatemore.md) function.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="ed5dc-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="ed5dc-106">Header file:</span></span>  <br/> |<span data-ttu-id="ed5dc-107">Mapix.h</span><span class="sxs-lookup"><span data-stu-id="ed5dc-107">Mapix.h</span></span>  <br/> |
|<span data-ttu-id="ed5dc-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="ed5dc-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="ed5dc-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="ed5dc-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="ed5dc-110">调用：</span><span class="sxs-lookup"><span data-stu-id="ed5dc-110">Called by:</span></span>  <br/> |<span data-ttu-id="ed5dc-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="ed5dc-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
ULONG MAPIFreeBuffer(
  LPVOID lpBuffer
);
```

## <a name="parameters"></a><span data-ttu-id="ed5dc-112">参数</span><span class="sxs-lookup"><span data-stu-id="ed5dc-112">Parameters</span></span>

 <span data-ttu-id="ed5dc-113">_lpBuffer_</span><span class="sxs-lookup"><span data-stu-id="ed5dc-113">_lpBuffer_</span></span>
  
> <span data-ttu-id="ed5dc-114">[in]指向以前分配的内存缓冲区。</span><span class="sxs-lookup"><span data-stu-id="ed5dc-114">[in] Pointer to a previously allocated memory buffer.</span></span> <span data-ttu-id="ed5dc-115">如果_lpBuffer_参数中传递 NULL，则**MAPIFreeBuffer**无实际作用。</span><span class="sxs-lookup"><span data-stu-id="ed5dc-115">If NULL is passed in the  _lpBuffer_ parameter, **MAPIFreeBuffer** does nothing.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="ed5dc-116">返回值</span><span class="sxs-lookup"><span data-stu-id="ed5dc-116">Return value</span></span>

<span data-ttu-id="ed5dc-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="ed5dc-117">S_OK</span></span> 
  
> <span data-ttu-id="ed5dc-118">呼叫成功并释放请求的内存。</span><span class="sxs-lookup"><span data-stu-id="ed5dc-118">The call succeeded and freed the memory requested.</span></span> <span data-ttu-id="ed5dc-119">**MAPIFreeBuffer**也可以在已释放的位置或如果内存块则不会分配与**MAPIAllocateBuffer** **MAPIAllocateMore**返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="ed5dc-119">**MAPIFreeBuffer** can also return S_OK on already freed locations or if memory block is not allocated with **MAPIAllocateBuffer** and **MAPIAllocateMore**.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="ed5dc-120">说明</span><span class="sxs-lookup"><span data-stu-id="ed5dc-120">Remarks</span></span>

<span data-ttu-id="ed5dc-121">通常，当客户端应用程序或服务提供商调用[MAPIAllocateBuffer](mapiallocatebuffer.md)或[MAPIAllocateMore](mapiallocatemore.md)，一个连续内存缓冲区中的操作系统构造一个或多个复杂的指针的多个级别结构。</span><span class="sxs-lookup"><span data-stu-id="ed5dc-121">Usually, when a client application or service provider calls [MAPIAllocateBuffer](mapiallocatebuffer.md) or [MAPIAllocateMore](mapiallocatemore.md), the operating system constructs in one contiguous memory buffer one or more complex structures with multiple levels of pointers.</span></span> <span data-ttu-id="ed5dc-122">当 MAPI 函数或方法创建此类内容缓冲区时，客户端可以更高版本来释放通过将传递给**MAPIFreeBuffer**指向创建缓冲区的 MAPI 函数返回的缓冲区的缓冲区中包含的所有结构。</span><span class="sxs-lookup"><span data-stu-id="ed5dc-122">When a MAPI function or method creates a buffer with such contents, a client can later free all the structures contained in the buffer by passing to **MAPIFreeBuffer** the pointer to the buffer returned by the MAPI function that created the buffer.</span></span> <span data-ttu-id="ed5dc-123">以释放内存缓冲区使用**MAPIFreeBuffer**服务提供程序，它必须将指针传递给提供程序的支持对象返回的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="ed5dc-123">For a service provider to free a memory buffer using **MAPIFreeBuffer**, it must pass the pointer to that buffer returned with the provider's support object.</span></span> 
  
<span data-ttu-id="ed5dc-124">必须尽快客户端进行**MAPIFreeBuffer**调用以释放特定缓冲区或提供程序是使用此缓冲区完。</span><span class="sxs-lookup"><span data-stu-id="ed5dc-124">The call to **MAPIFreeBuffer** to free a particular buffer must be made as soon as a client or provider is finished using this buffer.</span></span> <span data-ttu-id="ed5dc-125">只需在 MAPI 会话结束调用[IMAPISession::Logoff](imapisession-logoff.md)方法不会自动释放内存缓冲区。</span><span class="sxs-lookup"><span data-stu-id="ed5dc-125">Simply calling the [IMAPISession::Logoff](imapisession-logoff.md) method at the end of a MAPI session does not automatically release memory buffers.</span></span> 
  
<span data-ttu-id="ed5dc-126">假设后从**MAPIFreeBuffer**的成功返回_lpBuffer_中传递的指针是无效的客户端或服务提供程序应对执行操作。</span><span class="sxs-lookup"><span data-stu-id="ed5dc-126">A client or service provider should operate on the assumption that the pointer passed in  _lpBuffer_ is invalid after a successful return from **MAPIFreeBuffer**.</span></span> <span data-ttu-id="ed5dc-127">如果将指针指示通过**MAPIAllocateBuffer**或**MAPIAllocateMore**或可用内存块消息系统未分配的内存块，未定义**MAPIFreeBuffer**的行为。</span><span class="sxs-lookup"><span data-stu-id="ed5dc-127">If the pointer indicates either a memory block not allocated by the messaging system through **MAPIAllocateBuffer** or **MAPIAllocateMore** or a free memory block, the behavior of **MAPIFreeBuffer** is undefined.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="ed5dc-128">将 null 指针传递给**MAPIFreeBuffer**会使应用程序清理代码简单和较小因为**MAPIFreeBuffer**可以指针初始化为 NULL，而不必先测试它们然后释放它们在清理代码。</span><span class="sxs-lookup"><span data-stu-id="ed5dc-128">Passing a null pointer to **MAPIFreeBuffer** makes application cleanup code simpler and smaller because **MAPIFreeBuffer** can initialize pointers to NULL and then free them in the cleanup code without having to test them first.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="ed5dc-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ed5dc-129">See also</span></span>



[<span data-ttu-id="ed5dc-130">IMAPISupport::GetMemAllocRoutines</span><span class="sxs-lookup"><span data-stu-id="ed5dc-130">IMAPISupport::GetMemAllocRoutines</span></span>](imapisupport-getmemallocroutines.md)

