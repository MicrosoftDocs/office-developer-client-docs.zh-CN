---
title: MAPIReallocateBuffer
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 182ab0c6-c9d3-4cc8-892f-f6b09312ceb9
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e85e2da4d63442dc1fb912c5941be9d6f6f53824
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22593786"
---
# <a name="mapireallocatebuffer"></a><span data-ttu-id="33d06-103">MAPIReallocateBuffer</span><span class="sxs-lookup"><span data-stu-id="33d06-103">MAPIReallocateBuffer</span></span>

  
  
<span data-ttu-id="33d06-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="33d06-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="33d06-105">重新分配的内存缓冲区。</span><span class="sxs-lookup"><span data-stu-id="33d06-105">Reallocates a memory buffer.</span></span> <span data-ttu-id="33d06-106">它用于[MAPIAllocateBuffer](mapiallocatebuffer.md)函数。</span><span class="sxs-lookup"><span data-stu-id="33d06-106">It is used with the [MAPIAllocateBuffer](mapiallocatebuffer.md) function.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="33d06-107">头文件：</span><span class="sxs-lookup"><span data-stu-id="33d06-107">Header file:</span></span>  <br/> |<span data-ttu-id="33d06-108">omapix.h</span><span class="sxs-lookup"><span data-stu-id="33d06-108">omapix.h</span></span>  <br/> |
|<span data-ttu-id="33d06-109">调用：</span><span class="sxs-lookup"><span data-stu-id="33d06-109">Called by:</span></span>  <br/> |<span data-ttu-id="33d06-110">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="33d06-110">Client applications and service providers</span></span>  <br/> |
   
```cpp
STDMETHODIMP_(SCODE) MAPIReallocateBuffer
(
LPVOID lpv, 
ULONG ulSize, 
LPVOID * lppv
);
```

## <a name="parameters"></a><span data-ttu-id="33d06-111">参数</span><span class="sxs-lookup"><span data-stu-id="33d06-111">Parameters</span></span>

 <span data-ttu-id="33d06-112">_lpv_</span><span class="sxs-lookup"><span data-stu-id="33d06-112">_lpv_</span></span>
  
> <span data-ttu-id="33d06-113">一个指向可以重新分配的内存。</span><span class="sxs-lookup"><span data-stu-id="33d06-113">A pointer to the memory to be reallocated.</span></span>
    
 <span data-ttu-id="33d06-114">_ulSize_</span><span class="sxs-lookup"><span data-stu-id="33d06-114">_ulSize_</span></span>
  
> <span data-ttu-id="33d06-115">以字节为单位，要分配的缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="33d06-115">The size, in bytes, of the buffer to be allocated.</span></span>
    
 <span data-ttu-id="33d06-116">_lppv_</span><span class="sxs-lookup"><span data-stu-id="33d06-116">_lppv_</span></span>
  
> <span data-ttu-id="33d06-117">指向返回分配的缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="33d06-117">A pointer to the returned allocated buffer.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="33d06-118">注解</span><span class="sxs-lookup"><span data-stu-id="33d06-118">Remarks</span></span>

 <span data-ttu-id="33d06-119">**MAPIReallocateBuffer**分配新请求大小的内存块，并将传递该缓冲区的内容复制到此新块的内存。</span><span class="sxs-lookup"><span data-stu-id="33d06-119">**MAPIReallocateBuffer** allocates a new block of memory of the requested size and copies the contents of the buffer that is passed into this new block of memory.</span></span> <span data-ttu-id="33d06-120">如果传递的内存的块包含内部的指针，指针不会更改要匹配的新位置。</span><span class="sxs-lookup"><span data-stu-id="33d06-120">If the block of memory that is passed contains internal pointers, the pointers do not change to match the new location.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="33d06-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="33d06-121">See also</span></span>



[<span data-ttu-id="33d06-122">MAPIAllocateBuffer</span><span class="sxs-lookup"><span data-stu-id="33d06-122">MAPIAllocateBuffer</span></span>](mapiallocatebuffer.md)

