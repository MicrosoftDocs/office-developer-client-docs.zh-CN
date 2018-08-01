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
ms.openlocfilehash: 26dcc31f2ebdd1892f966bfb95fda1a65c5140cb
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776391"
---
# <a name="mapireallocatebuffer"></a><span data-ttu-id="d7224-103">MAPIReallocateBuffer</span><span class="sxs-lookup"><span data-stu-id="d7224-103">MAPIReallocateBuffer</span></span>

  
  
<span data-ttu-id="d7224-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="d7224-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="d7224-105">重新分配的内存缓冲区。</span><span class="sxs-lookup"><span data-stu-id="d7224-105">Reallocates a memory buffer.</span></span> <span data-ttu-id="d7224-106">它用于[MAPIAllocateBuffer](mapiallocatebuffer.md)函数。</span><span class="sxs-lookup"><span data-stu-id="d7224-106">It is used with the [MAPIAllocateBuffer](mapiallocatebuffer.md) function.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="d7224-107">头文件：</span><span class="sxs-lookup"><span data-stu-id="d7224-107">Header file:</span></span>  <br/> |<span data-ttu-id="d7224-108">omapix.h</span><span class="sxs-lookup"><span data-stu-id="d7224-108">omapix.h</span></span>  <br/> |
|<span data-ttu-id="d7224-109">调用：</span><span class="sxs-lookup"><span data-stu-id="d7224-109">Called by:</span></span>  <br/> |<span data-ttu-id="d7224-110">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="d7224-110">Client applications and service providers</span></span>  <br/> |
   
```cpp
STDMETHODIMP_(SCODE) MAPIReallocateBuffer
(
LPVOID lpv, 
ULONG ulSize, 
LPVOID * lppv
);
```

## <a name="parameters"></a><span data-ttu-id="d7224-111">参数</span><span class="sxs-lookup"><span data-stu-id="d7224-111">Parameters</span></span>

 <span data-ttu-id="d7224-112">_lpv_</span><span class="sxs-lookup"><span data-stu-id="d7224-112">_lpv_</span></span>
  
> <span data-ttu-id="d7224-113">一个指向可以重新分配的内存。</span><span class="sxs-lookup"><span data-stu-id="d7224-113">A pointer to the memory to be reallocated.</span></span>
    
 <span data-ttu-id="d7224-114">_ulSize_</span><span class="sxs-lookup"><span data-stu-id="d7224-114">_ulSize_</span></span>
  
> <span data-ttu-id="d7224-115">以字节为单位，要分配的缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="d7224-115">The size, in bytes, of the buffer to be allocated.</span></span>
    
 <span data-ttu-id="d7224-116">_lppv_</span><span class="sxs-lookup"><span data-stu-id="d7224-116">_lppv_</span></span>
  
> <span data-ttu-id="d7224-117">指向返回分配的缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="d7224-117">A pointer to the returned allocated buffer.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="d7224-118">说明</span><span class="sxs-lookup"><span data-stu-id="d7224-118">Remarks</span></span>

 <span data-ttu-id="d7224-119">**MAPIReallocateBuffer**分配新请求大小的内存块，并将传递该缓冲区的内容复制到此新块的内存。</span><span class="sxs-lookup"><span data-stu-id="d7224-119">**MAPIReallocateBuffer** allocates a new block of memory of the requested size and copies the contents of the buffer that is passed into this new block of memory.</span></span> <span data-ttu-id="d7224-120">如果传递的内存的块包含内部的指针，指针不会更改要匹配的新位置。</span><span class="sxs-lookup"><span data-stu-id="d7224-120">If the block of memory that is passed contains internal pointers, the pointers do not change to match the new location.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="d7224-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d7224-121">See also</span></span>



[<span data-ttu-id="d7224-122">MAPIAllocateBuffer</span><span class="sxs-lookup"><span data-stu-id="d7224-122">MAPIAllocateBuffer</span></span>](mapiallocatebuffer.md)

