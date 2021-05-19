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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 680fd16771b62d705808a04d768115a076e54750
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415535"
---
# <a name="imapisupportgetmemallocroutines"></a><span data-ttu-id="ce311-103">IMAPISupport::GetMemAllocRoutines</span><span class="sxs-lookup"><span data-stu-id="ce311-103">IMAPISupport::GetMemAllocRoutines</span></span>

  
  
<span data-ttu-id="ce311-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ce311-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ce311-105">检索 MAPI 内存分配和处理函数的地址 ([MAPIAllocateBuffer、MAPIAllocateMore](mapiallocatebuffer.md)和[MAPIFreeBuffer](mapifreebuffer.md)) 。 [](mapiallocatemore.md)</span><span class="sxs-lookup"><span data-stu-id="ce311-105">Retrieves the addresses of the MAPI memory allocation and deallocation functions ([MAPIAllocateBuffer](mapiallocatebuffer.md), [MAPIAllocateMore](mapiallocatemore.md), and [MAPIFreeBuffer](mapifreebuffer.md)).</span></span>
  
```cpp
HRESULT GetMemAllocRoutines(
  LPALLOCATEBUFFER FAR * lppAllocateBuffer,
  LPALLOCATEMORE FAR * lppAllocateMore,
  LPFREEBUFFER FAR * lppFreeBuffer
);
```

## <a name="parameters"></a><span data-ttu-id="ce311-106">参数</span><span class="sxs-lookup"><span data-stu-id="ce311-106">Parameters</span></span>

 <span data-ttu-id="ce311-107">_lppAllocateBuffer_</span><span class="sxs-lookup"><span data-stu-id="ce311-107">_lppAllocateBuffer_</span></span>
  
> <span data-ttu-id="ce311-108">[out]指向指向 **MAPIAllocateBuffer 函数的指针的** 指针。</span><span class="sxs-lookup"><span data-stu-id="ce311-108">[out] A pointer to a pointer to the **MAPIAllocateBuffer** function.</span></span> <span data-ttu-id="ce311-109">**MAPIAllocateBuffer** 分配内存。</span><span class="sxs-lookup"><span data-stu-id="ce311-109">**MAPIAllocateBuffer** allocates memory.</span></span> 
    
 <span data-ttu-id="ce311-110">_lppAllocateMore_</span><span class="sxs-lookup"><span data-stu-id="ce311-110">_lppAllocateMore_</span></span>
  
> <span data-ttu-id="ce311-111">[out]指向指向 **MAPIAllocateMore 函数的指针** 的指针。</span><span class="sxs-lookup"><span data-stu-id="ce311-111">[out] A pointer to a pointer to the **MAPIAllocateMore** function.</span></span> <span data-ttu-id="ce311-112">**MAPIAllocateMore** 为最初使用 **MAPIAllocateBuffer 分配的内存分配额外的内存**。</span><span class="sxs-lookup"><span data-stu-id="ce311-112">**MAPIAllocateMore** allocates additional memory for memory that was originally allocated by using **MAPIAllocateBuffer**.</span></span>
    
 <span data-ttu-id="ce311-113">_lppFreeBuffer_</span><span class="sxs-lookup"><span data-stu-id="ce311-113">_lppFreeBuffer_</span></span>
  
> <span data-ttu-id="ce311-114">[out]指向指向 **MAPIFreeBuffer 函数的指针的** 指针。</span><span class="sxs-lookup"><span data-stu-id="ce311-114">[out] A pointer to a pointer to the **MAPIFreeBuffer** function.</span></span> <span data-ttu-id="ce311-115">**MAPIFreeBuffer** 释放内存。</span><span class="sxs-lookup"><span data-stu-id="ce311-115">**MAPIFreeBuffer** frees memory.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="ce311-116">返回值</span><span class="sxs-lookup"><span data-stu-id="ce311-116">Return value</span></span>

<span data-ttu-id="ce311-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="ce311-117">S_OK</span></span> 
  
> <span data-ttu-id="ce311-118">已成功返回函数地址。</span><span class="sxs-lookup"><span data-stu-id="ce311-118">The function addresses were successfully returned.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="ce311-119">备注</span><span class="sxs-lookup"><span data-stu-id="ce311-119">Remarks</span></span>

<span data-ttu-id="ce311-120">**IMAPISupport：：GetMemAllocRoutines** 方法针对所有支持对象实现。</span><span class="sxs-lookup"><span data-stu-id="ce311-120">The **IMAPISupport::GetMemAllocRoutines** method is implemented for all support objects.</span></span> <span data-ttu-id="ce311-121">服务提供商调用 **GetMemAllocRoutines，** 获取传递到其初始化函数 ( [ABProviderInit、MSProviderInit](abproviderinit.md)或 [XPProviderInit](xpproviderinit.md)) 的三个内存分配函数的地址。 [](msproviderinit.md)</span><span class="sxs-lookup"><span data-stu-id="ce311-121">Service providers call **GetMemAllocRoutines** to get the addresses of the three memory allocation functions that are passed to their initialization function ( [ABProviderInit](abproviderinit.md), [MSProviderInit](msproviderinit.md), or [XPProviderInit](xpproviderinit.md)).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="ce311-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ce311-122">See also</span></span>



[<span data-ttu-id="ce311-123">MAPIAllocateBuffer</span><span class="sxs-lookup"><span data-stu-id="ce311-123">MAPIAllocateBuffer</span></span>](mapiallocatebuffer.md)
  
[<span data-ttu-id="ce311-124">MAPIAllocateMore</span><span class="sxs-lookup"><span data-stu-id="ce311-124">MAPIAllocateMore</span></span>](mapiallocatemore.md)
  
[<span data-ttu-id="ce311-125">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="ce311-125">MAPIFreeBuffer</span></span>](mapifreebuffer.md)
  
[<span data-ttu-id="ce311-126">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="ce311-126">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

