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
ms.openlocfilehash: 589ad42199e6f2ec1039499dfd9beda044ccc3dd
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425692"
---
# <a name="mapiallocatebuffer"></a><span data-ttu-id="ce153-103">MAPIAllocateBuffer</span><span class="sxs-lookup"><span data-stu-id="ce153-103">MAPIAllocateBuffer</span></span>

  
  
<span data-ttu-id="ce153-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ce153-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ce153-105">分配内存缓冲区。</span><span class="sxs-lookup"><span data-stu-id="ce153-105">Allocates a memory buffer.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="ce153-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="ce153-106">Header file:</span></span>  <br/> |<span data-ttu-id="ce153-107">Mapix</span><span class="sxs-lookup"><span data-stu-id="ce153-107">Mapix.h</span></span>  <br/> |
|<span data-ttu-id="ce153-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="ce153-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="ce153-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="ce153-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="ce153-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="ce153-110">Called by:</span></span>  <br/> |<span data-ttu-id="ce153-111">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="ce153-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
SCODE MAPIAllocateBuffer(
  ULONG cbSize,
  LPVOID FAR * lppBuffer
);
```

## <a name="parameters"></a><span data-ttu-id="ce153-112">参数</span><span class="sxs-lookup"><span data-stu-id="ce153-112">Parameters</span></span>

 <span data-ttu-id="ce153-113">_cbSize_</span><span class="sxs-lookup"><span data-stu-id="ce153-113">_cbSize_</span></span>
  
> <span data-ttu-id="ce153-114">实时要分配的缓冲区的大小 (以字节为单位)。</span><span class="sxs-lookup"><span data-stu-id="ce153-114">[in] Size, in bytes, of the buffer to be allocated.</span></span> 
    
 <span data-ttu-id="ce153-115">_lppBuffer_</span><span class="sxs-lookup"><span data-stu-id="ce153-115">_lppBuffer_</span></span>
  
> <span data-ttu-id="ce153-116">排除指向返回的已分配缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="ce153-116">[out] Pointer to the returned allocated buffer.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="ce153-117">返回值</span><span class="sxs-lookup"><span data-stu-id="ce153-117">Return value</span></span>

<span data-ttu-id="ce153-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="ce153-118">S_OK</span></span> 
  
> <span data-ttu-id="ce153-119">调用成功, 并返回请求的内存缓冲区。</span><span class="sxs-lookup"><span data-stu-id="ce153-119">The call succeeded and has returned the requested memory buffer.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="ce153-120">说明</span><span class="sxs-lookup"><span data-stu-id="ce153-120">Remarks</span></span>

<span data-ttu-id="ce153-121">在**MAPIAllocateBuffer**呼叫处理过程中, 呼叫实现将从操作系统中获取内存块。</span><span class="sxs-lookup"><span data-stu-id="ce153-121">During **MAPIAllocateBuffer** call processing, the calling implementation acquires a block of memory from the operating system.</span></span> <span data-ttu-id="ce153-122">内存缓冲区分配在偶数字节地址上。</span><span class="sxs-lookup"><span data-stu-id="ce153-122">The memory buffer is allocated on an even-numbered byte address.</span></span> <span data-ttu-id="ce153-123">在较长整数访问效率更高的平台上, 操作系统在大小为4个字节的地址上分配缓冲区。</span><span class="sxs-lookup"><span data-stu-id="ce153-123">On platforms where long integer access is more efficient, the operating system allocates the buffer on an address whose size in bytes is a multiple of four.</span></span> 
  
<span data-ttu-id="ce153-124">调用[MAPIFreeBuffer](mapifreebuffer.md)函数将释放**MAPIAllocateBuffer**分配的内存缓冲区, 方法是在不再需要内存时调用[MAPIAllocateMore](mapiallocatemore.md)函数以及链接到它的任何缓冲区。</span><span class="sxs-lookup"><span data-stu-id="ce153-124">Calling the [MAPIFreeBuffer](mapifreebuffer.md) function releases the memory buffer allocated by **MAPIAllocateBuffer**, by calling the [MAPIAllocateMore](mapiallocatemore.md) function and any buffers linked to it, when the memory is no longer needed.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="ce153-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ce153-125">See also</span></span>



[<span data-ttu-id="ce153-126">MAPIReallocateBuffer</span><span class="sxs-lookup"><span data-stu-id="ce153-126">MAPIReallocateBuffer</span></span>](mapireallocatebuffer.md)

