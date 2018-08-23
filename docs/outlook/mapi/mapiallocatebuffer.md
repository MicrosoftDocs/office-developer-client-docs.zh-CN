---
title: MAPIAllocateBuffer
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPIAllocateBuffer
api_type:
- HeaderDef
ms.assetid: f1fc7fc5-c71f-44f7-930a-571773eb6809
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0520b219c87207a54555ba74050761f6ecc4854a
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22579597"
---
# <a name="mapiallocatebuffer"></a><span data-ttu-id="6c68b-103">MAPIAllocateBuffer</span><span class="sxs-lookup"><span data-stu-id="6c68b-103">MAPIAllocateBuffer</span></span>

  
  
<span data-ttu-id="6c68b-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6c68b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6c68b-105">分配内存缓冲区。</span><span class="sxs-lookup"><span data-stu-id="6c68b-105">Allocates a memory buffer.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="6c68b-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="6c68b-106">Header file:</span></span>  <br/> |<span data-ttu-id="6c68b-107">Mapix.h</span><span class="sxs-lookup"><span data-stu-id="6c68b-107">Mapix.h</span></span>  <br/> |
|<span data-ttu-id="6c68b-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="6c68b-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="6c68b-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="6c68b-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="6c68b-110">调用：</span><span class="sxs-lookup"><span data-stu-id="6c68b-110">Called by:</span></span>  <br/> |<span data-ttu-id="6c68b-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="6c68b-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
SCODE MAPIAllocateBuffer(
  ULONG cbSize,
  LPVOID FAR * lppBuffer
);
```

## <a name="parameters"></a><span data-ttu-id="6c68b-112">参数</span><span class="sxs-lookup"><span data-stu-id="6c68b-112">Parameters</span></span>

 <span data-ttu-id="6c68b-113">_cbSize_</span><span class="sxs-lookup"><span data-stu-id="6c68b-113">_cbSize_</span></span>
  
> <span data-ttu-id="6c68b-114">[in]以字节为单位，要分配的缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="6c68b-114">[in] Size, in bytes, of the buffer to be allocated.</span></span> 
    
 <span data-ttu-id="6c68b-115">_lppBuffer_</span><span class="sxs-lookup"><span data-stu-id="6c68b-115">_lppBuffer_</span></span>
  
> <span data-ttu-id="6c68b-116">[输出]指向返回分配缓冲区。</span><span class="sxs-lookup"><span data-stu-id="6c68b-116">[out] Pointer to the returned allocated buffer.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="6c68b-117">返回值</span><span class="sxs-lookup"><span data-stu-id="6c68b-117">Return value</span></span>

<span data-ttu-id="6c68b-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="6c68b-118">S_OK</span></span> 
  
> <span data-ttu-id="6c68b-119">呼叫成功，并具有返回请求的内存缓冲区。</span><span class="sxs-lookup"><span data-stu-id="6c68b-119">The call succeeded and has returned the requested memory buffer.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="6c68b-120">注解</span><span class="sxs-lookup"><span data-stu-id="6c68b-120">Remarks</span></span>

<span data-ttu-id="6c68b-121">期间**MAPIAllocateBuffer**呼叫处理中，调用实现获取从操作系统的内存块。</span><span class="sxs-lookup"><span data-stu-id="6c68b-121">During **MAPIAllocateBuffer** call processing, the calling implementation acquires a block of memory from the operating system.</span></span> <span data-ttu-id="6c68b-122">内存缓冲区分配偶数字节的地址。</span><span class="sxs-lookup"><span data-stu-id="6c68b-122">The memory buffer is allocated on an even-numbered byte address.</span></span> <span data-ttu-id="6c68b-123">长整型访问其中是更高效的平台上, 操作系统分配其以字节为单位的大小是四个倍数的地址上的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="6c68b-123">On platforms where long integer access is more efficient, the operating system allocates the buffer on an address whose size in bytes is a multiple of four.</span></span> 
  
<span data-ttu-id="6c68b-124">调用[MAPIFreeBuffer](mapifreebuffer.md)函数版本由**MAPIAllocateBuffer**，通过调用[MAPIAllocateMore](mapiallocatemore.md)函数和任何缓冲区分配内存缓冲区链接到，，当不再需要的内存。</span><span class="sxs-lookup"><span data-stu-id="6c68b-124">Calling the [MAPIFreeBuffer](mapifreebuffer.md) function releases the memory buffer allocated by **MAPIAllocateBuffer**, by calling the [MAPIAllocateMore](mapiallocatemore.md) function and any buffers linked to it, when the memory is no longer needed.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="6c68b-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6c68b-125">See also</span></span>



[<span data-ttu-id="6c68b-126">MAPIReallocateBuffer</span><span class="sxs-lookup"><span data-stu-id="6c68b-126">MAPIReallocateBuffer</span></span>](mapireallocatebuffer.md)

