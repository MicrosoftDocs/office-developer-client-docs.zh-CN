---
title: IMAPISupportGetMemAllocRoutines
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.GetMemAllocRoutines
api_type:
- COM
ms.assetid: 52d45876-367b-42da-b99a-29cdb71fa5a9
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 782c04d05ea5cea811784b031e8a118a9c08cbb7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775626"
---
# <a name="imapisupportgetmemallocroutines"></a><span data-ttu-id="a7556-103">IMAPISupport::GetMemAllocRoutines</span><span class="sxs-lookup"><span data-stu-id="a7556-103">IMAPISupport::GetMemAllocRoutines</span></span>

  
  
<span data-ttu-id="a7556-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="a7556-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="a7556-105">检索 MAPI 内存分配和释放函数 （[MAPIAllocateBuffer](mapiallocatebuffer.md)、 [MAPIAllocateMore](mapiallocatemore.md)和[MAPIFreeBuffer](mapifreebuffer.md)） 的地址。</span><span class="sxs-lookup"><span data-stu-id="a7556-105">Retrieves the addresses of the MAPI memory allocation and deallocation functions ([MAPIAllocateBuffer](mapiallocatebuffer.md), [MAPIAllocateMore](mapiallocatemore.md), and [MAPIFreeBuffer](mapifreebuffer.md)).</span></span>
  
```cpp
HRESULT GetMemAllocRoutines(
  LPALLOCATEBUFFER FAR * lppAllocateBuffer,
  LPALLOCATEMORE FAR * lppAllocateMore,
  LPFREEBUFFER FAR * lppFreeBuffer
);
```

## <a name="parameters"></a><span data-ttu-id="a7556-106">参数</span><span class="sxs-lookup"><span data-stu-id="a7556-106">Parameters</span></span>

 <span data-ttu-id="a7556-107">_lppAllocateBuffer_</span><span class="sxs-lookup"><span data-stu-id="a7556-107">_lppAllocateBuffer_</span></span>
  
> <span data-ttu-id="a7556-108">[输出]指向**MAPIAllocateBuffer**函数的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="a7556-108">[out] A pointer to a pointer to the **MAPIAllocateBuffer** function.</span></span> <span data-ttu-id="a7556-109">**MAPIAllocateBuffer**分配内存。</span><span class="sxs-lookup"><span data-stu-id="a7556-109">**MAPIAllocateBuffer** allocates memory.</span></span> 
    
 <span data-ttu-id="a7556-110">_lppAllocateMore_</span><span class="sxs-lookup"><span data-stu-id="a7556-110">_lppAllocateMore_</span></span>
  
> <span data-ttu-id="a7556-111">[输出]指向**MAPIAllocateMore**函数的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="a7556-111">[out] A pointer to a pointer to the **MAPIAllocateMore** function.</span></span> <span data-ttu-id="a7556-112">**MAPIAllocateMore**为使用**MAPIAllocateBuffer**最初分配的内存分配更多内存。</span><span class="sxs-lookup"><span data-stu-id="a7556-112">**MAPIAllocateMore** allocates additional memory for memory that was originally allocated by using **MAPIAllocateBuffer**.</span></span>
    
 <span data-ttu-id="a7556-113">_lppFreeBuffer_</span><span class="sxs-lookup"><span data-stu-id="a7556-113">_lppFreeBuffer_</span></span>
  
> <span data-ttu-id="a7556-114">[输出]指向**MAPIFreeBuffer**函数的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="a7556-114">[out] A pointer to a pointer to the **MAPIFreeBuffer** function.</span></span> <span data-ttu-id="a7556-115">**MAPIFreeBuffer**释放内存。</span><span class="sxs-lookup"><span data-stu-id="a7556-115">**MAPIFreeBuffer** frees memory.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="a7556-116">返回值</span><span class="sxs-lookup"><span data-stu-id="a7556-116">Return value</span></span>

<span data-ttu-id="a7556-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="a7556-117">S_OK</span></span> 
  
> <span data-ttu-id="a7556-118">已成功返回函数地址。</span><span class="sxs-lookup"><span data-stu-id="a7556-118">The function addresses were successfully returned.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="a7556-119">说明</span><span class="sxs-lookup"><span data-stu-id="a7556-119">Remarks</span></span>

<span data-ttu-id="a7556-120">对于所有支持对象实现**IMAPISupport::GetMemAllocRoutines**方法。</span><span class="sxs-lookup"><span data-stu-id="a7556-120">The **IMAPISupport::GetMemAllocRoutines** method is implemented for all support objects.</span></span> <span data-ttu-id="a7556-121">服务提供商调用**GetMemAllocRoutines**来获取三个内存分配函数传递给其初始化函数 （ [ABProviderInit](abproviderinit.md)、 [MSProviderInit](msproviderinit.md)或[XPProviderInit](xpproviderinit.md)） 的地址。</span><span class="sxs-lookup"><span data-stu-id="a7556-121">Service providers call **GetMemAllocRoutines** to get the addresses of the three memory allocation functions that are passed to their initialization function ( [ABProviderInit](abproviderinit.md), [MSProviderInit](msproviderinit.md), or [XPProviderInit](xpproviderinit.md)).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="a7556-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a7556-122">See also</span></span>



[<span data-ttu-id="a7556-123">MAPIAllocateBuffer</span><span class="sxs-lookup"><span data-stu-id="a7556-123">MAPIAllocateBuffer</span></span>](mapiallocatebuffer.md)
  
[<span data-ttu-id="a7556-124">MAPIAllocateMore</span><span class="sxs-lookup"><span data-stu-id="a7556-124">MAPIAllocateMore</span></span>](mapiallocatemore.md)
  
[<span data-ttu-id="a7556-125">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="a7556-125">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="a7556-126">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="a7556-126">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

