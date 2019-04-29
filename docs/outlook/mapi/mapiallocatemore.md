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
ms.openlocfilehash: 01980b2da735838eeffa9afa5a0d139b69e76d0c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435388"
---
# <a name="mapiallocatemore"></a><span data-ttu-id="69366-103">MAPIAllocateMore</span><span class="sxs-lookup"><span data-stu-id="69366-103">MAPIAllocateMore</span></span>

  
  
<span data-ttu-id="69366-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="69366-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="69366-105">分配链接到以前使用[MAPIAllocateBuffer](mapiallocatebuffer.md)函数分配的另一个缓冲区的内存缓冲区。</span><span class="sxs-lookup"><span data-stu-id="69366-105">Allocates a memory buffer that is linked to another buffer previously allocated with the [MAPIAllocateBuffer](mapiallocatebuffer.md) function.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="69366-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="69366-106">Header file:</span></span>  <br/> |<span data-ttu-id="69366-107">Mapix</span><span class="sxs-lookup"><span data-stu-id="69366-107">Mapix.h</span></span>  <br/> |
|<span data-ttu-id="69366-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="69366-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="69366-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="69366-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="69366-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="69366-110">Called by:</span></span>  <br/> |<span data-ttu-id="69366-111">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="69366-111">Client applications and service providers</span></span>  <br/> |
   
```cpp
SCODE MAPIAllocateMore(
  ULONG cbSize,
  LPVOID lpObject,
  LPVOID FAR * lppBuffer
);
```

## <a name="parameters"></a><span data-ttu-id="69366-112">参数</span><span class="sxs-lookup"><span data-stu-id="69366-112">Parameters</span></span>

 <span data-ttu-id="69366-113">_cbSize_</span><span class="sxs-lookup"><span data-stu-id="69366-113">_cbSize_</span></span>
  
> <span data-ttu-id="69366-114">实时要分配的新缓冲区的大小 (以字节为单位)。</span><span class="sxs-lookup"><span data-stu-id="69366-114">[in] Size, in bytes, of the new buffer to be allocated.</span></span> 
    
 <span data-ttu-id="69366-115">_lpObject_</span><span class="sxs-lookup"><span data-stu-id="69366-115">_lpObject_</span></span>
  
> <span data-ttu-id="69366-116">实时指向使用**MAPIAllocateBuffer**分配的现有 MAPI 缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="69366-116">[in] Pointer to an existing MAPI buffer allocated using **MAPIAllocateBuffer**.</span></span>
    
 <span data-ttu-id="69366-117">_lppBuffer_</span><span class="sxs-lookup"><span data-stu-id="69366-117">_lppBuffer_</span></span>
  
> <span data-ttu-id="69366-118">排除指向返回的新分配的缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="69366-118">[out] Pointer to the returned, newly allocated buffer.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="69366-119">返回值</span><span class="sxs-lookup"><span data-stu-id="69366-119">Return value</span></span>

<span data-ttu-id="69366-120">S_OK</span><span class="sxs-lookup"><span data-stu-id="69366-120">S_OK</span></span> 
  
> <span data-ttu-id="69366-121">调用成功, 并返回指向请求的内存的指针。</span><span class="sxs-lookup"><span data-stu-id="69366-121">The call succeeded and has returned a pointer to the requested memory.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="69366-122">说明</span><span class="sxs-lookup"><span data-stu-id="69366-122">Remarks</span></span>

<span data-ttu-id="69366-123">在**MAPIAllocateMore**呼叫处理过程中, 呼叫实现将从操作系统中获取内存块。</span><span class="sxs-lookup"><span data-stu-id="69366-123">During **MAPIAllocateMore** call processing, the calling implementation acquires a block of memory from the operating system.</span></span> <span data-ttu-id="69366-124">内存缓冲区分配在偶数字节地址上。</span><span class="sxs-lookup"><span data-stu-id="69366-124">The memory buffer is allocated on an even-numbered byte address.</span></span> <span data-ttu-id="69366-125">在较长整数访问效率更高的平台上, 操作系统在大小为4个字节的地址上分配缓冲区。</span><span class="sxs-lookup"><span data-stu-id="69366-125">On platforms where long integer access is more efficient, the operating system allocates the buffer on an address whose size in bytes is a multiple of four.</span></span> 
  
<span data-ttu-id="69366-126">释放用**MAPIAllocateMore**分配的缓冲区的唯一方法是将_lpObject_参数中指定的缓冲区指针传递给[MAPIFreeBuffer](mapifreebuffer.md)函数。</span><span class="sxs-lookup"><span data-stu-id="69366-126">The only way to release a buffer allocated with **MAPIAllocateMore** is to pass the buffer pointer specified in the  _lpObject_ parameter to the [MAPIFreeBuffer](mapifreebuffer.md) function.</span></span> <span data-ttu-id="69366-127">使用[MAPIAllocateBuffer](mapiallocatebuffer.md)和**MAPIAllocateMore**分配的内存缓冲区之间的链接使**MAPIFreeBuffer**能够通过单个调用释放两个缓冲区。</span><span class="sxs-lookup"><span data-stu-id="69366-127">The link between the memory buffers allocated with [MAPIAllocateBuffer](mapiallocatebuffer.md) and **MAPIAllocateMore** enables **MAPIFreeBuffer** to release both buffers with a single call.</span></span> 
  

