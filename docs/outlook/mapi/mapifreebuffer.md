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
ms.openlocfilehash: 8794bb233eb69d0f246fb1019954ab718db6f464
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410551"
---
# <a name="mapifreebuffer"></a><span data-ttu-id="43c1c-103">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="43c1c-103">MAPIFreeBuffer</span></span>

  
  
<span data-ttu-id="43c1c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="43c1c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="43c1c-105">释放通过调用 [MAPIAllocateBuffer](mapiallocatebuffer.md) 函数或 [MAPIAllocateMore](mapiallocatemore.md) 函数分配的内存缓冲区。</span><span class="sxs-lookup"><span data-stu-id="43c1c-105">Frees a memory buffer allocated with a call to the [MAPIAllocateBuffer](mapiallocatebuffer.md) function or the [MAPIAllocateMore](mapiallocatemore.md) function.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="43c1c-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="43c1c-106">Header file:</span></span>  <br/> |<span data-ttu-id="43c1c-107">Mapix.h</span><span class="sxs-lookup"><span data-stu-id="43c1c-107">Mapix.h</span></span>  <br/> |
|<span data-ttu-id="43c1c-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="43c1c-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="43c1c-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="43c1c-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="43c1c-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="43c1c-110">Called by:</span></span>  <br/> |<span data-ttu-id="43c1c-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="43c1c-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
ULONG MAPIFreeBuffer(
  LPVOID lpBuffer
);
```

## <a name="parameters"></a><span data-ttu-id="43c1c-112">参数</span><span class="sxs-lookup"><span data-stu-id="43c1c-112">Parameters</span></span>

 <span data-ttu-id="43c1c-113">_lpBuffer_</span><span class="sxs-lookup"><span data-stu-id="43c1c-113">_lpBuffer_</span></span>
  
> <span data-ttu-id="43c1c-114">[in]指向以前分配的内存缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="43c1c-114">[in] Pointer to a previously allocated memory buffer.</span></span> <span data-ttu-id="43c1c-115">如果在  _lpBuffer_ 参数中传递 NULL， **则 MAPIFreeBuffer** 不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="43c1c-115">If NULL is passed in the  _lpBuffer_ parameter, **MAPIFreeBuffer** does nothing.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="43c1c-116">返回值</span><span class="sxs-lookup"><span data-stu-id="43c1c-116">Return value</span></span>

<span data-ttu-id="43c1c-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="43c1c-117">S_OK</span></span> 
  
> <span data-ttu-id="43c1c-118">调用成功并释放所请求的内存。</span><span class="sxs-lookup"><span data-stu-id="43c1c-118">The call succeeded and freed the memory requested.</span></span> <span data-ttu-id="43c1c-119">**MAPIFreeBuffer** 还可以返回S_OK释放位置的内存，或者如果未使用 **MAPIAllocateBuffer** 和 **MAPIAllocateMore** 分配内存块。</span><span class="sxs-lookup"><span data-stu-id="43c1c-119">**MAPIFreeBuffer** can also return S_OK on already freed locations or if memory block is not allocated with **MAPIAllocateBuffer** and **MAPIAllocateMore**.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="43c1c-120">备注</span><span class="sxs-lookup"><span data-stu-id="43c1c-120">Remarks</span></span>

<span data-ttu-id="43c1c-121">通常，当客户端应用程序或服务提供商调用 [MAPIAllocateBuffer](mapiallocatebuffer.md) 或 [MAPIAllocateMore](mapiallocatemore.md)时，操作系统在一个具有多个指针级别的连续内存缓冲区中构造一个或多个复杂结构。</span><span class="sxs-lookup"><span data-stu-id="43c1c-121">Usually, when a client application or service provider calls [MAPIAllocateBuffer](mapiallocatebuffer.md) or [MAPIAllocateMore](mapiallocatemore.md), the operating system constructs in one contiguous memory buffer one or more complex structures with multiple levels of pointers.</span></span> <span data-ttu-id="43c1c-122">当 MAPI 函数或方法创建包含此类内容的缓冲区时，客户端稍后可以通过将指针传递到 **MAPIFreeBuffer** 来释放缓冲区中包含的所有结构，方法是将指针传递给创建缓冲区的 MAPI 函数返回的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="43c1c-122">When a MAPI function or method creates a buffer with such contents, a client can later free all the structures contained in the buffer by passing to **MAPIFreeBuffer** the pointer to the buffer returned by the MAPI function that created the buffer.</span></span> <span data-ttu-id="43c1c-123">对于使用 **MAPIFreeBuffer** 释放内存缓冲区的服务提供商，它必须将指针传递到使用提供程序的支持对象返回的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="43c1c-123">For a service provider to free a memory buffer using **MAPIFreeBuffer**, it must pass the pointer to that buffer returned with the provider's support object.</span></span> 
  
<span data-ttu-id="43c1c-124">在客户端或提供程序使用此缓冲区完成后，必须立即调用 **MAPIFreeBuffer** 以释放特定缓冲区。</span><span class="sxs-lookup"><span data-stu-id="43c1c-124">The call to **MAPIFreeBuffer** to free a particular buffer must be made as soon as a client or provider is finished using this buffer.</span></span> <span data-ttu-id="43c1c-125">只需在 MAPI 会话结束时调用 [IMAPISession：：Logoff](imapisession-logoff.md) 方法，不会自动释放内存缓冲区。</span><span class="sxs-lookup"><span data-stu-id="43c1c-125">Simply calling the [IMAPISession::Logoff](imapisession-logoff.md) method at the end of a MAPI session does not automatically release memory buffers.</span></span> 
  
<span data-ttu-id="43c1c-126">客户端或服务提供商应假定传入  _lpBuffer_ 的指针在 **从 MAPIFreeBuffer** 成功返回后无效。</span><span class="sxs-lookup"><span data-stu-id="43c1c-126">A client or service provider should operate on the assumption that the pointer passed in  _lpBuffer_ is invalid after a successful return from **MAPIFreeBuffer**.</span></span> <span data-ttu-id="43c1c-127">如果指针指示邮件系统未通过 **MAPIAllocateBuffer** 或 **MAPIAllocateMore** 分配的内存块或可用内存块， **则 MAPIFreeBuffer** 的行为未定义。</span><span class="sxs-lookup"><span data-stu-id="43c1c-127">If the pointer indicates either a memory block not allocated by the messaging system through **MAPIAllocateBuffer** or **MAPIAllocateMore** or a free memory block, the behavior of **MAPIFreeBuffer** is undefined.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="43c1c-128">将空指针传递到 **MAPIFreeBuffer** 可以使应用程序清理代码更简单、更小，因为 **MAPIFreeBuffer** 可以初始化指向 NULL 的指针，然后在清理代码中释放它们，而不必首先测试它们。</span><span class="sxs-lookup"><span data-stu-id="43c1c-128">Passing a null pointer to **MAPIFreeBuffer** makes application cleanup code simpler and smaller because **MAPIFreeBuffer** can initialize pointers to NULL and then free them in the cleanup code without having to test them first.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="43c1c-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="43c1c-129">See also</span></span>



[<span data-ttu-id="43c1c-130">IMAPISupport::GetMemAllocRoutines</span><span class="sxs-lookup"><span data-stu-id="43c1c-130">IMAPISupport::GetMemAllocRoutines</span></span>](imapisupport-getmemallocroutines.md)

