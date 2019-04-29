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
# <a name="mapifreebuffer"></a><span data-ttu-id="92250-103">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="92250-103">MAPIFreeBuffer</span></span>

  
  
<span data-ttu-id="92250-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="92250-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="92250-105">释放通过调用[MAPIAllocateBuffer](mapiallocatebuffer.md)函数或[MAPIAllocateMore](mapiallocatemore.md)函数分配的内存缓冲区。</span><span class="sxs-lookup"><span data-stu-id="92250-105">Frees a memory buffer allocated with a call to the [MAPIAllocateBuffer](mapiallocatebuffer.md) function or the [MAPIAllocateMore](mapiallocatemore.md) function.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="92250-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="92250-106">Header file:</span></span>  <br/> |<span data-ttu-id="92250-107">Mapix</span><span class="sxs-lookup"><span data-stu-id="92250-107">Mapix.h</span></span>  <br/> |
|<span data-ttu-id="92250-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="92250-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="92250-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="92250-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="92250-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="92250-110">Called by:</span></span>  <br/> |<span data-ttu-id="92250-111">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="92250-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
ULONG MAPIFreeBuffer(
  LPVOID lpBuffer
);
```

## <a name="parameters"></a><span data-ttu-id="92250-112">参数</span><span class="sxs-lookup"><span data-stu-id="92250-112">Parameters</span></span>

 <span data-ttu-id="92250-113">_lpBuffer_</span><span class="sxs-lookup"><span data-stu-id="92250-113">_lpBuffer_</span></span>
  
> <span data-ttu-id="92250-114">实时指向以前分配的内存缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="92250-114">[in] Pointer to a previously allocated memory buffer.</span></span> <span data-ttu-id="92250-115">如果在_lpBuffer_参数中传递 NULL, 则**MAPIFreeBuffer**不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="92250-115">If NULL is passed in the  _lpBuffer_ parameter, **MAPIFreeBuffer** does nothing.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="92250-116">返回值</span><span class="sxs-lookup"><span data-stu-id="92250-116">Return value</span></span>

<span data-ttu-id="92250-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="92250-117">S_OK</span></span> 
  
> <span data-ttu-id="92250-118">调用成功, 并释放了请求的内存。</span><span class="sxs-lookup"><span data-stu-id="92250-118">The call succeeded and freed the memory requested.</span></span> <span data-ttu-id="92250-119">**MAPIFreeBuffer**还可以在已释放的位置上返回 S_OK, 或者如果未使用**MAPIAllocateBuffer**和**MAPIAllocateMore**分配内存块。</span><span class="sxs-lookup"><span data-stu-id="92250-119">**MAPIFreeBuffer** can also return S_OK on already freed locations or if memory block is not allocated with **MAPIAllocateBuffer** and **MAPIAllocateMore**.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="92250-120">说明</span><span class="sxs-lookup"><span data-stu-id="92250-120">Remarks</span></span>

<span data-ttu-id="92250-121">通常情况下, 当客户端应用程序或服务提供程序调用[MAPIAllocateBuffer](mapiallocatebuffer.md)或[MAPIAllocateMore](mapiallocatemore.md)时, 操作系统会在一个连续的内存缓冲区中构造一个或多个具有多个指针级别的复杂结构。</span><span class="sxs-lookup"><span data-stu-id="92250-121">Usually, when a client application or service provider calls [MAPIAllocateBuffer](mapiallocatebuffer.md) or [MAPIAllocateMore](mapiallocatemore.md), the operating system constructs in one contiguous memory buffer one or more complex structures with multiple levels of pointers.</span></span> <span data-ttu-id="92250-122">当 mapi 函数或方法创建具有此类内容的缓冲区时, 客户端可以通过向**MAPIFreeBuffer**传递指向由创建该缓冲区的 MAPI 函数返回的缓冲区来释放该缓冲区中包含的所有结构。</span><span class="sxs-lookup"><span data-stu-id="92250-122">When a MAPI function or method creates a buffer with such contents, a client can later free all the structures contained in the buffer by passing to **MAPIFreeBuffer** the pointer to the buffer returned by the MAPI function that created the buffer.</span></span> <span data-ttu-id="92250-123">若要使服务提供程序使用**MAPIFreeBuffer**释放内存缓冲区, 它必须将指针传递给提供程序的支持对象返回的那个缓冲区。</span><span class="sxs-lookup"><span data-stu-id="92250-123">For a service provider to free a memory buffer using **MAPIFreeBuffer**, it must pass the pointer to that buffer returned with the provider's support object.</span></span> 
  
<span data-ttu-id="92250-124">当客户端或提供程序使用此缓冲区完成后, 必须立即调用**MAPIFreeBuffer**以释放特定的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="92250-124">The call to **MAPIFreeBuffer** to free a particular buffer must be made as soon as a client or provider is finished using this buffer.</span></span> <span data-ttu-id="92250-125">在 MAPI 会话结束时只需调用[IMAPISession:: 注销](imapisession-logoff.md)方法, 就不会自动释放内存缓冲区。</span><span class="sxs-lookup"><span data-stu-id="92250-125">Simply calling the [IMAPISession::Logoff](imapisession-logoff.md) method at the end of a MAPI session does not automatically release memory buffers.</span></span> 
  
<span data-ttu-id="92250-126">客户端或服务提供商应假定在从**MAPIFreeBuffer**成功返回后, 在_lpBuffer_中传递的指针无效。</span><span class="sxs-lookup"><span data-stu-id="92250-126">A client or service provider should operate on the assumption that the pointer passed in  _lpBuffer_ is invalid after a successful return from **MAPIFreeBuffer**.</span></span> <span data-ttu-id="92250-127">如果指针指示邮件系统未通过**MAPIAllocateBuffer**或**MAPIAllocateMore**或可用内存块分配的内存块, 则**MAPIFreeBuffer**的行为未定义。</span><span class="sxs-lookup"><span data-stu-id="92250-127">If the pointer indicates either a memory block not allocated by the messaging system through **MAPIAllocateBuffer** or **MAPIAllocateMore** or a free memory block, the behavior of **MAPIFreeBuffer** is undefined.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="92250-128">将 null 指针传递给**MAPIFreeBuffer**会使应用程序清理代码更简单且更小, 因为**MAPIFreeBuffer**可以将指针初始化为 null, 然后在清理代码中释放它们, 而无需先对其进行测试。</span><span class="sxs-lookup"><span data-stu-id="92250-128">Passing a null pointer to **MAPIFreeBuffer** makes application cleanup code simpler and smaller because **MAPIFreeBuffer** can initialize pointers to NULL and then free them in the cleanup code without having to test them first.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="92250-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="92250-129">See also</span></span>



[<span data-ttu-id="92250-130">IMAPISupport::GetMemAllocRoutines</span><span class="sxs-lookup"><span data-stu-id="92250-130">IMAPISupport::GetMemAllocRoutines</span></span>](imapisupport-getmemallocroutines.md)

