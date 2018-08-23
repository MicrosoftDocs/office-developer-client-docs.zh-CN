---
title: MAPIAllocateMore
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPIAllocateMore
api_type:
- HeaderDef
ms.assetid: 3e48f76a-bc97-4cbc-9082-c07dd674b73e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0e6226dd0fc9c04070ed3d1dda1770f77fbc585c
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22583006"
---
# <a name="mapiallocatemore"></a><span data-ttu-id="fb158-103">MAPIAllocateMore</span><span class="sxs-lookup"><span data-stu-id="fb158-103">MAPIAllocateMore</span></span>

  
  
<span data-ttu-id="fb158-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fb158-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="fb158-105">分配一个链接到另一个缓冲区[MAPIAllocateBuffer](mapiallocatebuffer.md)函数与先前分配的内存缓冲区。</span><span class="sxs-lookup"><span data-stu-id="fb158-105">Allocates a memory buffer that is linked to another buffer previously allocated with the [MAPIAllocateBuffer](mapiallocatebuffer.md) function.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="fb158-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="fb158-106">Header file:</span></span>  <br/> |<span data-ttu-id="fb158-107">Mapix.h</span><span class="sxs-lookup"><span data-stu-id="fb158-107">Mapix.h</span></span>  <br/> |
|<span data-ttu-id="fb158-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="fb158-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="fb158-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="fb158-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="fb158-110">调用：</span><span class="sxs-lookup"><span data-stu-id="fb158-110">Called by:</span></span>  <br/> |<span data-ttu-id="fb158-111">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="fb158-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
SCODE MAPIAllocateMore(
  ULONG cbSize,
  LPVOID lpObject,
  LPVOID FAR * lppBuffer
);
```

## <a name="parameters"></a><span data-ttu-id="fb158-112">参数</span><span class="sxs-lookup"><span data-stu-id="fb158-112">Parameters</span></span>

 <span data-ttu-id="fb158-113">_cbSize_</span><span class="sxs-lookup"><span data-stu-id="fb158-113">_cbSize_</span></span>
  
> <span data-ttu-id="fb158-114">[in]以字节为单位，要分配的新缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="fb158-114">[in] Size, in bytes, of the new buffer to be allocated.</span></span> 
    
 <span data-ttu-id="fb158-115">_lpObject_</span><span class="sxs-lookup"><span data-stu-id="fb158-115">_lpObject_</span></span>
  
> <span data-ttu-id="fb158-116">[in]指向分配使用**MAPIAllocateBuffer**现有 MAPI 缓冲区。</span><span class="sxs-lookup"><span data-stu-id="fb158-116">[in] Pointer to an existing MAPI buffer allocated using **MAPIAllocateBuffer**.</span></span>
    
 <span data-ttu-id="fb158-117">_lppBuffer_</span><span class="sxs-lookup"><span data-stu-id="fb158-117">_lppBuffer_</span></span>
  
> <span data-ttu-id="fb158-118">[输出]返回的指向新分配缓冲区。</span><span class="sxs-lookup"><span data-stu-id="fb158-118">[out] Pointer to the returned, newly allocated buffer.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="fb158-119">返回值</span><span class="sxs-lookup"><span data-stu-id="fb158-119">Return value</span></span>

<span data-ttu-id="fb158-120">S_OK</span><span class="sxs-lookup"><span data-stu-id="fb158-120">S_OK</span></span> 
  
> <span data-ttu-id="fb158-121">呼叫成功，到请求的内存返回一个指针。</span><span class="sxs-lookup"><span data-stu-id="fb158-121">The call succeeded and has returned a pointer to the requested memory.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="fb158-122">注解</span><span class="sxs-lookup"><span data-stu-id="fb158-122">Remarks</span></span>

<span data-ttu-id="fb158-123">期间**MAPIAllocateMore**呼叫处理中，调用实现获取从操作系统的内存块。</span><span class="sxs-lookup"><span data-stu-id="fb158-123">During **MAPIAllocateMore** call processing, the calling implementation acquires a block of memory from the operating system.</span></span> <span data-ttu-id="fb158-124">内存缓冲区分配偶数字节的地址。</span><span class="sxs-lookup"><span data-stu-id="fb158-124">The memory buffer is allocated on an even-numbered byte address.</span></span> <span data-ttu-id="fb158-125">长整型访问其中是更高效的平台上, 操作系统分配其以字节为单位的大小是四个倍数的地址上的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="fb158-125">On platforms where long integer access is more efficient, the operating system allocates the buffer on an address whose size in bytes is a multiple of four.</span></span> 
  
<span data-ttu-id="fb158-126">释放用**MAPIAllocateMore**分配缓冲区的唯一方法是将传递给[MAPIFreeBuffer](mapifreebuffer.md)函数_lpObject_参数中指定的缓冲区指针。</span><span class="sxs-lookup"><span data-stu-id="fb158-126">The only way to release a buffer allocated with **MAPIAllocateMore** is to pass the buffer pointer specified in the  _lpObject_ parameter to the [MAPIFreeBuffer](mapifreebuffer.md) function.</span></span> <span data-ttu-id="fb158-127">用[MAPIAllocateBuffer](mapiallocatebuffer.md)和**MAPIAllocateMore**分配的内存缓冲区之间的链接使**MAPIFreeBuffer**释放的单个调用进行这两个缓冲区。</span><span class="sxs-lookup"><span data-stu-id="fb158-127">The link between the memory buffers allocated with [MAPIAllocateBuffer](mapiallocatebuffer.md) and **MAPIAllocateMore** enables **MAPIFreeBuffer** to release both buffers with a single call.</span></span> 
  

