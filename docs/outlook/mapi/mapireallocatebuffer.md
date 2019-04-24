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
ms.openlocfilehash: 59d0ce192605257dc0aebed46d8093a352fce05f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32270236"
---
# <a name="mapireallocatebuffer"></a><span data-ttu-id="6e4cc-103">MAPIReallocateBuffer</span><span class="sxs-lookup"><span data-stu-id="6e4cc-103">MAPIReallocateBuffer</span></span>

  
  
<span data-ttu-id="6e4cc-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6e4cc-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6e4cc-105">再次分配内存缓冲区。</span><span class="sxs-lookup"><span data-stu-id="6e4cc-105">Reallocates a memory buffer.</span></span> <span data-ttu-id="6e4cc-106">它与[MAPIAllocateBuffer](mapiallocatebuffer.md)函数一起使用。</span><span class="sxs-lookup"><span data-stu-id="6e4cc-106">It is used with the [MAPIAllocateBuffer](mapiallocatebuffer.md) function.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="6e4cc-107">标头文件：</span><span class="sxs-lookup"><span data-stu-id="6e4cc-107">Header file:</span></span>  <br/> |<span data-ttu-id="6e4cc-108">omapix</span><span class="sxs-lookup"><span data-stu-id="6e4cc-108">omapix.h</span></span>  <br/> |
|<span data-ttu-id="6e4cc-109">调用者：</span><span class="sxs-lookup"><span data-stu-id="6e4cc-109">Called by:</span></span>  <br/> |<span data-ttu-id="6e4cc-110">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="6e4cc-110">Client applications and service providers</span></span>  <br/> |
   
```cpp
STDMETHODIMP_(SCODE) MAPIReallocateBuffer
(
LPVOID lpv, 
ULONG ulSize, 
LPVOID * lppv
);
```

## <a name="parameters"></a><span data-ttu-id="6e4cc-111">参数</span><span class="sxs-lookup"><span data-stu-id="6e4cc-111">Parameters</span></span>

 <span data-ttu-id="6e4cc-112">_lpv_</span><span class="sxs-lookup"><span data-stu-id="6e4cc-112">_lpv_</span></span>
  
> <span data-ttu-id="6e4cc-113">指向要重新分配的内存的指针。</span><span class="sxs-lookup"><span data-stu-id="6e4cc-113">A pointer to the memory to be reallocated.</span></span>
    
 <span data-ttu-id="6e4cc-114">_ulSize_</span><span class="sxs-lookup"><span data-stu-id="6e4cc-114">_ulSize_</span></span>
  
> <span data-ttu-id="6e4cc-115">要分配的缓冲区的大小 (以字节为单位)。</span><span class="sxs-lookup"><span data-stu-id="6e4cc-115">The size, in bytes, of the buffer to be allocated.</span></span>
    
 <span data-ttu-id="6e4cc-116">_lppv_</span><span class="sxs-lookup"><span data-stu-id="6e4cc-116">_lppv_</span></span>
  
> <span data-ttu-id="6e4cc-117">指向返回的已分配缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="6e4cc-117">A pointer to the returned allocated buffer.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="6e4cc-118">注解</span><span class="sxs-lookup"><span data-stu-id="6e4cc-118">Remarks</span></span>

 <span data-ttu-id="6e4cc-119">**MAPIReallocateBuffer**分配一个新的请求大小内存块, 并复制传入此新内存块的缓冲区的内容。</span><span class="sxs-lookup"><span data-stu-id="6e4cc-119">**MAPIReallocateBuffer** allocates a new block of memory of the requested size and copies the contents of the buffer that is passed into this new block of memory.</span></span> <span data-ttu-id="6e4cc-120">如果传递的内存块包含内部指针, 则指针不会更改以匹配新位置。</span><span class="sxs-lookup"><span data-stu-id="6e4cc-120">If the block of memory that is passed contains internal pointers, the pointers do not change to match the new location.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="6e4cc-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6e4cc-121">See also</span></span>



[<span data-ttu-id="6e4cc-122">MAPIAllocateBuffer</span><span class="sxs-lookup"><span data-stu-id="6e4cc-122">MAPIAllocateBuffer</span></span>](mapiallocatebuffer.md)

