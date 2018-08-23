---
title: WrapCompressedRTFStream
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.WrapCompressedRTFStream
api_type:
- COM
ms.assetid: 0949e066-aa28-4ede-ac88-b2dccd5098e8
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a7095907a1fb437e225922d0bef08b4ad79a4b6f
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22594591"
---
# <a name="wrapcompressedrtfstream"></a><span data-ttu-id="dfb43-103">WrapCompressedRTFStream</span><span class="sxs-lookup"><span data-stu-id="dfb43-103">WrapCompressedRTFStream</span></span>

  
  
<span data-ttu-id="dfb43-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="dfb43-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="dfb43-105">创建一个文本流中未压缩富文本格式 (RTF) 从**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性中使用的压缩文件格式。</span><span class="sxs-lookup"><span data-stu-id="dfb43-105">Creates a text stream in uncompressed Rich Text Format (RTF) from the compressed format used in the **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) property.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="dfb43-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="dfb43-106">Header file:</span></span>  <br/> |<span data-ttu-id="dfb43-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="dfb43-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="dfb43-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="dfb43-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="dfb43-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="dfb43-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="dfb43-110">调用：</span><span class="sxs-lookup"><span data-stu-id="dfb43-110">Called by:</span></span>  <br/> |<span data-ttu-id="dfb43-111">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="dfb43-111">Client applications</span></span>  <br/> |
   
```cpp
HRESULT WrapCompressedRTFStream(
  LPSTREAM lpCompressedRTFStream,
  ULONG ulflags,
  LPSTREAM FAR * lpUncompressedRTFStream
);
```

## <a name="parameters"></a><span data-ttu-id="dfb43-112">参数</span><span class="sxs-lookup"><span data-stu-id="dfb43-112">Parameters</span></span>

 <span data-ttu-id="dfb43-113">_lpCompressedRTFStream_</span><span class="sxs-lookup"><span data-stu-id="dfb43-113">_lpCompressedRTFStream_</span></span>
  
> <span data-ttu-id="dfb43-114">[in]到上一条消息的 PR_RTF_COMPRESSED 属性打开流的指针。</span><span class="sxs-lookup"><span data-stu-id="dfb43-114">[in] Pointer to a stream opened on the PR_RTF_COMPRESSED property of a message.</span></span> 
    
 <span data-ttu-id="dfb43-115">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="dfb43-115">_ulFlags_</span></span>
  
> <span data-ttu-id="dfb43-116">[in]函数标记选项的位掩码。</span><span class="sxs-lookup"><span data-stu-id="dfb43-116">[in] Bitmask of option flags for the function.</span></span> <span data-ttu-id="dfb43-117">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="dfb43-117">The following flags can be set:</span></span>
    
<span data-ttu-id="dfb43-118">MAPI_MODIFY</span><span class="sxs-lookup"><span data-stu-id="dfb43-118">MAPI_MODIFY</span></span> 
  
> <span data-ttu-id="dfb43-119">是否客户端打算读取或写入返回的换行的流接口。</span><span class="sxs-lookup"><span data-stu-id="dfb43-119">Whether the client intends to read or write the wrapped stream interface that is returned.</span></span> 
    
<span data-ttu-id="dfb43-120">STORE_UNCOMPRESSED_RTF</span><span class="sxs-lookup"><span data-stu-id="dfb43-120">STORE_UNCOMPRESSED_RTF</span></span> 
  
> <span data-ttu-id="dfb43-121">未压缩的 RTF 应写入所指的_lpCompressedRTFStream_流</span><span class="sxs-lookup"><span data-stu-id="dfb43-121">Uncompressed RTF should be written to the stream pointed to by  _lpCompressedRTFStream_</span></span>
    
 <span data-ttu-id="dfb43-122">_lpUncompressedRTFStream_</span><span class="sxs-lookup"><span data-stu-id="dfb43-122">_lpUncompressedRTFStream_</span></span>
  
> <span data-ttu-id="dfb43-123">[输出]指向**WrapCompressedRTFStream**其中返回 stream 的未压缩 RTF 的位置的指针。</span><span class="sxs-lookup"><span data-stu-id="dfb43-123">[out] Pointer to the location where **WrapCompressedRTFStream** returns a stream for the uncompressed RTF.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="dfb43-124">返回值</span><span class="sxs-lookup"><span data-stu-id="dfb43-124">Return value</span></span>

<span data-ttu-id="dfb43-125">S_OK</span><span class="sxs-lookup"><span data-stu-id="dfb43-125">S_OK</span></span> 
  
> <span data-ttu-id="dfb43-126">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="dfb43-126">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="dfb43-127">注解</span><span class="sxs-lookup"><span data-stu-id="dfb43-127">Remarks</span></span>

<span data-ttu-id="dfb43-128">如果_ulFlags_参数中传递 MAPI_MODIFY 标志，则_lpCompressedRTFStream_参数必须已被打开的读取和写入。</span><span class="sxs-lookup"><span data-stu-id="dfb43-128">If the MAPI_MODIFY flag is passed in the  _ulFlags_ parameter, the  _lpCompressedRTFStream_ parameter must already be open for reading and writing.</span></span> <span data-ttu-id="dfb43-129">新的、 未压缩 RTF 的文本应写入_lpUncompressedRTFStream_中返回的流接口。</span><span class="sxs-lookup"><span data-stu-id="dfb43-129">New, uncompressed RTF text should be written into the stream interface returned in  _lpUncompressedRTFStream_.</span></span> <span data-ttu-id="dfb43-130">因为它不可能要追加的现有流，必须编写的整个邮件文本。</span><span class="sxs-lookup"><span data-stu-id="dfb43-130">Because it is not possible to append the existing stream, the entire message text must be written.</span></span> 
  
<span data-ttu-id="dfb43-131">如果_ulFlags_参数中传递零，则然后_lpCompressedRTFStream_可能是以只读方式打开。</span><span class="sxs-lookup"><span data-stu-id="dfb43-131">If zero is passed in the  _ulFlags_ parameter, then  _lpCompressedRTFStream_ may be opened read-only.</span></span> <span data-ttu-id="dfb43-132">可以利用_lpUncompressedRTFStream_中返回的流接口读取只将整个邮件文本。</span><span class="sxs-lookup"><span data-stu-id="dfb43-132">Only the entire message text can be read out of the stream interface returned in  _lpUncompressedRTFStream_.</span></span> <span data-ttu-id="dfb43-133">不能开始 stream 的中间搜索。</span><span class="sxs-lookup"><span data-stu-id="dfb43-133">It is not possible to search starting the middle of the stream.</span></span> 
  
 <span data-ttu-id="dfb43-134">**WrapCompressedRTFStream**假定压缩的流的指针设置为 stream 的开头。</span><span class="sxs-lookup"><span data-stu-id="dfb43-134">**WrapCompressedRTFStream** assumes that the compressed stream's pointer is set to the beginning of the stream.</span></span> <span data-ttu-id="dfb43-135">返回未压缩流不支持某些 OLE **IStream**方法。</span><span class="sxs-lookup"><span data-stu-id="dfb43-135">Certain OLE **IStream** methods are not supported by the returned uncompressed stream.</span></span> <span data-ttu-id="dfb43-136">包括**IStream::Clone**、 **IStream::LockRegion**、 **IStream::Revert**、 **IStream::Seek**、 **IStream::SetSize**、 **IStream::Stat**和**IStream::UnlockRegion**。</span><span class="sxs-lookup"><span data-stu-id="dfb43-136">These include **IStream::Clone**, **IStream::LockRegion**, **IStream::Revert**, **IStream::Seek**, **IStream::SetSize**, **IStream::Stat**, and **IStream::UnlockRegion**.</span></span> <span data-ttu-id="dfb43-137">若要复制到整个流，需要读/写循环。</span><span class="sxs-lookup"><span data-stu-id="dfb43-137">In order to copy to the entire stream, a read/write loop is needed.</span></span> 
  
<span data-ttu-id="dfb43-138">客户端未压缩格式写入新 RTF，因为它应使用**WrapCompressedRTFStream**，而不是直接写入到流。</span><span class="sxs-lookup"><span data-stu-id="dfb43-138">Because the client writes new RTF in uncompressed format, it should use **WrapCompressedRTFStream**, instead of directly writing to the stream.</span></span> <span data-ttu-id="dfb43-139">RTF 感知客户端应 STORE_UNCOMPRESSED_RTF 标志**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性中搜索，并将其传递给**WrapCompressed RTFStream** ，如果将其设置。</span><span class="sxs-lookup"><span data-stu-id="dfb43-139">RTF-aware clients should search for the STORE_UNCOMPRESSED_RTF flag in the **PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) property and pass it to **WrapCompressed RTFStream** if it is set.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="dfb43-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dfb43-140">See also</span></span>



[<span data-ttu-id="dfb43-141">RTFSync</span><span class="sxs-lookup"><span data-stu-id="dfb43-141">RTFSync</span></span>](rtfsync.md)

