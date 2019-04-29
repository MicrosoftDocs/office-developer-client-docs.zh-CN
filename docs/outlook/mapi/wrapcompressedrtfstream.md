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
ms.openlocfilehash: 710e0e2fc334194e33c6d8ba1296e4c7b1938bc0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439798"
---
# <a name="wrapcompressedrtfstream"></a><span data-ttu-id="deb60-103">WrapCompressedRTFStream</span><span class="sxs-lookup"><span data-stu-id="deb60-103">WrapCompressedRTFStream</span></span>

  
  
<span data-ttu-id="deb60-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="deb60-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="deb60-105">从**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性中使用的压缩格式创建未压缩的 rtf 格式文本流。</span><span class="sxs-lookup"><span data-stu-id="deb60-105">Creates a text stream in uncompressed Rich Text Format (RTF) from the compressed format used in the **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) property.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="deb60-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="deb60-106">Header file:</span></span>  <br/> |<span data-ttu-id="deb60-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="deb60-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="deb60-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="deb60-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="deb60-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="deb60-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="deb60-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="deb60-110">Called by:</span></span>  <br/> |<span data-ttu-id="deb60-111">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="deb60-111">Client applications</span></span>  <br/> |
   
```cpp
HRESULT WrapCompressedRTFStream(
  LPSTREAM lpCompressedRTFStream,
  ULONG ulflags,
  LPSTREAM FAR * lpUncompressedRTFStream
);
```

## <a name="parameters"></a><span data-ttu-id="deb60-112">参数</span><span class="sxs-lookup"><span data-stu-id="deb60-112">Parameters</span></span>

 <span data-ttu-id="deb60-113">_lpCompressedRTFStream_</span><span class="sxs-lookup"><span data-stu-id="deb60-113">_lpCompressedRTFStream_</span></span>
  
> <span data-ttu-id="deb60-114">实时指向在邮件的 PR_RTF_COMPRESSED 属性上打开的流的指针。</span><span class="sxs-lookup"><span data-stu-id="deb60-114">[in] Pointer to a stream opened on the PR_RTF_COMPRESSED property of a message.</span></span> 
    
 <span data-ttu-id="deb60-115">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="deb60-115">_ulFlags_</span></span>
  
> <span data-ttu-id="deb60-116">实时函数的选项标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="deb60-116">[in] Bitmask of option flags for the function.</span></span> <span data-ttu-id="deb60-117">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="deb60-117">The following flags can be set:</span></span>
    
<span data-ttu-id="deb60-118">MAPI_MODIFY</span><span class="sxs-lookup"><span data-stu-id="deb60-118">MAPI_MODIFY</span></span> 
  
> <span data-ttu-id="deb60-119">客户端是否打算读取或写入返回的已包装流接口。</span><span class="sxs-lookup"><span data-stu-id="deb60-119">Whether the client intends to read or write the wrapped stream interface that is returned.</span></span> 
    
<span data-ttu-id="deb60-120">STORE_UNCOMPRESSED_RTF</span><span class="sxs-lookup"><span data-stu-id="deb60-120">STORE_UNCOMPRESSED_RTF</span></span> 
  
> <span data-ttu-id="deb60-121">应将未压缩的 RTF 写入_lpCompressedRTFStream_指向的流。</span><span class="sxs-lookup"><span data-stu-id="deb60-121">Uncompressed RTF should be written to the stream pointed to by  _lpCompressedRTFStream_</span></span>
    
 <span data-ttu-id="deb60-122">_lpUncompressedRTFStream_</span><span class="sxs-lookup"><span data-stu-id="deb60-122">_lpUncompressedRTFStream_</span></span>
  
> <span data-ttu-id="deb60-123">排除指向**WrapCompressedRTFStream**的位置的指针, 该位置返回未压缩的 RTF 的流。</span><span class="sxs-lookup"><span data-stu-id="deb60-123">[out] Pointer to the location where **WrapCompressedRTFStream** returns a stream for the uncompressed RTF.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="deb60-124">返回值</span><span class="sxs-lookup"><span data-stu-id="deb60-124">Return value</span></span>

<span data-ttu-id="deb60-125">S_OK</span><span class="sxs-lookup"><span data-stu-id="deb60-125">S_OK</span></span> 
  
> <span data-ttu-id="deb60-126">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="deb60-126">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="deb60-127">说明</span><span class="sxs-lookup"><span data-stu-id="deb60-127">Remarks</span></span>

<span data-ttu-id="deb60-128">如果在_ulFlags_参数中传递了 MAPI_MODIFY 标志, 则必须已打开_lpCompressedRTFStream_参数以进行读取和写入。</span><span class="sxs-lookup"><span data-stu-id="deb60-128">If the MAPI_MODIFY flag is passed in the  _ulFlags_ parameter, the  _lpCompressedRTFStream_ parameter must already be open for reading and writing.</span></span> <span data-ttu-id="deb60-129">新的、未压缩的 RTF 文本应写入_lpUncompressedRTFStream_中返回的 stream 接口。</span><span class="sxs-lookup"><span data-stu-id="deb60-129">New, uncompressed RTF text should be written into the stream interface returned in  _lpUncompressedRTFStream_.</span></span> <span data-ttu-id="deb60-130">由于无法追加现有流, 因此必须写入整个消息文本。</span><span class="sxs-lookup"><span data-stu-id="deb60-130">Because it is not possible to append the existing stream, the entire message text must be written.</span></span> 
  
<span data-ttu-id="deb60-131">如果在_ulFlags_参数中传递零, 则_lpCompressedRTFStream_可能会以只读的打开。</span><span class="sxs-lookup"><span data-stu-id="deb60-131">If zero is passed in the  _ulFlags_ parameter, then  _lpCompressedRTFStream_ may be opened read-only.</span></span> <span data-ttu-id="deb60-132">仅可从_lpUncompressedRTFStream_中返回的流接口读取整个邮件文本。</span><span class="sxs-lookup"><span data-stu-id="deb60-132">Only the entire message text can be read out of the stream interface returned in  _lpUncompressedRTFStream_.</span></span> <span data-ttu-id="deb60-133">无法在流的中间开始搜索。</span><span class="sxs-lookup"><span data-stu-id="deb60-133">It is not possible to search starting the middle of the stream.</span></span> 
  
 <span data-ttu-id="deb60-134">**WrapCompressedRTFStream**假定压缩流的指针设置为流的开头。</span><span class="sxs-lookup"><span data-stu-id="deb60-134">**WrapCompressedRTFStream** assumes that the compressed stream's pointer is set to the beginning of the stream.</span></span> <span data-ttu-id="deb60-135">返回的未压缩流不支持某些 OLE **IStream**方法。</span><span class="sxs-lookup"><span data-stu-id="deb60-135">Certain OLE **IStream** methods are not supported by the returned uncompressed stream.</span></span> <span data-ttu-id="deb60-136">其中包括**IStream:: Clone**、 **istream:: LockRegion**、 **istream:: Revert**、 **IStream:: Seek**、 **IStream:: SetSize**、 **istream:: Stat**和**IStream:: UnlockRegion**。</span><span class="sxs-lookup"><span data-stu-id="deb60-136">These include **IStream::Clone**, **IStream::LockRegion**, **IStream::Revert**, **IStream::Seek**, **IStream::SetSize**, **IStream::Stat**, and **IStream::UnlockRegion**.</span></span> <span data-ttu-id="deb60-137">若要复制到整个流, 需要具有读/写循环。</span><span class="sxs-lookup"><span data-stu-id="deb60-137">In order to copy to the entire stream, a read/write loop is needed.</span></span> 
  
<span data-ttu-id="deb60-138">由于客户端以未压缩格式写入新 RTF, 因此它应使用**WrapCompressedRTFStream**, 而不是直接写入流。</span><span class="sxs-lookup"><span data-stu-id="deb60-138">Because the client writes new RTF in uncompressed format, it should use **WrapCompressedRTFStream**, instead of directly writing to the stream.</span></span> <span data-ttu-id="deb60-139">RTF 感知客户端应在**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性中搜索 STORE_UNCOMPRESSED_RTF 标志, 并将其传递到**WrapCompressed RTFStream** (如果已设置)。</span><span class="sxs-lookup"><span data-stu-id="deb60-139">RTF-aware clients should search for the STORE_UNCOMPRESSED_RTF flag in the **PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) property and pass it to **WrapCompressed RTFStream** if it is set.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="deb60-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="deb60-140">See also</span></span>



[<span data-ttu-id="deb60-141">RTFSync</span><span class="sxs-lookup"><span data-stu-id="deb60-141">RTFSync</span></span>](rtfsync.md)

