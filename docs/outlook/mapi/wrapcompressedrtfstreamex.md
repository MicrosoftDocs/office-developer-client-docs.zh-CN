---
title: WrapCompressedRTFStreamEx
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 45abee1c-d7fb-b0f9-522d-8ba34caf1094
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: af176c0ce327e6498a5d07f6d902c50f7323f813
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25391729"
---
# <a name="wrapcompressedrtfstreamex"></a><span data-ttu-id="cd3a8-103">WrapCompressedRTFStreamEx</span><span class="sxs-lookup"><span data-stu-id="cd3a8-103">WrapCompressedRTFStreamEx</span></span>

<span data-ttu-id="cd3a8-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="cd3a8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="cd3a8-105">解压缩是在压缩富文本格式 (RTF) 中，电子邮件的正文将指示记下解压缩后的 stream 的格式，（可选） 将记下解压缩后的流转换为其本机格式，并返回记下解压缩后的流或转换后的本机流。</span><span class="sxs-lookup"><span data-stu-id="cd3a8-105">Decompresses the the body of an email message that is in compressed Rich Text Format (RTF), indicates the format of the decompressed stream, optionally converts the decompressed stream to its native format, and returns either the decompressed stream or the converted native stream.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="cd3a8-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="cd3a8-106">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="cd3a8-107">导出：</span><span class="sxs-lookup"><span data-stu-id="cd3a8-107">Exported by:</span></span>  <br/> |<span data-ttu-id="cd3a8-108">msmapi32.dll</span><span class="sxs-lookup"><span data-stu-id="cd3a8-108">msmapi32.dll</span></span>  <br/> |
|<span data-ttu-id="cd3a8-109">调用者：</span><span class="sxs-lookup"><span data-stu-id="cd3a8-109">Called by:</span></span>  <br/> |<span data-ttu-id="cd3a8-110">客户端</span><span class="sxs-lookup"><span data-stu-id="cd3a8-110">Client</span></span>  <br/> |
|<span data-ttu-id="cd3a8-111">实现者：</span><span class="sxs-lookup"><span data-stu-id="cd3a8-111">Implemented by:</span></span>  <br/> |<span data-ttu-id="cd3a8-112">Outlook</span><span class="sxs-lookup"><span data-stu-id="cd3a8-112">Outlook</span></span>  <br/> |
   
```cpp
HRESULT __stdcall WrapCompressedRTFStreamEx( 
    LPSTREAM            lpCompressedRTFStream, 
    CONST RTF_WCSINFO   *pWCSInfo, 
    LPSTREAM            *lppUncompressedRTFStream, 
    RTF_WCSRETINFO      *pRetInfo); 

```

## <a name="parameters"></a><span data-ttu-id="cd3a8-113">参数</span><span class="sxs-lookup"><span data-stu-id="cd3a8-113">Parameters</span></span>

<span data-ttu-id="cd3a8-114">_lpCompressedRTFStream_</span><span class="sxs-lookup"><span data-stu-id="cd3a8-114">_lpCompressedRTFStream_</span></span>
  
> <span data-ttu-id="cd3a8-115">[in]这是指向打开一条消息[PidTagRtfCompressed 规范属性](pidtagrtfcompressed-canonical-property.md)流的指针。</span><span class="sxs-lookup"><span data-stu-id="cd3a8-115">[in] This is a pointer to a stream that is opened on the [PidTagRtfCompressed Canonical Property](pidtagrtfcompressed-canonical-property.md) of a message.</span></span> 
    
<span data-ttu-id="cd3a8-116">_pWCSInfo_</span><span class="sxs-lookup"><span data-stu-id="cd3a8-116">_pWCSInfo_</span></span>
  
> <span data-ttu-id="cd3a8-117">[in]这是一个指向</span><span class="sxs-lookup"><span data-stu-id="cd3a8-117">[in] This is a pointer to a</span></span> 
    
   <span data-ttu-id="cd3a8-118">[RTF_WCSINFO](rtf_wcsinfo.md)结构，其中包含函数的选项。</span><span class="sxs-lookup"><span data-stu-id="cd3a8-118">[RTF_WCSINFO](rtf_wcsinfo.md) structure that contains options for the function.</span></span> 
    
<span data-ttu-id="cd3a8-119">_lppUncompressedRTFStream_</span><span class="sxs-lookup"><span data-stu-id="cd3a8-119">_lppUncompressedRTFStream_</span></span>
  
> <span data-ttu-id="cd3a8-120">[输出]这是指向记下解压缩后的 RTF 流返回其中的位置的指针。</span><span class="sxs-lookup"><span data-stu-id="cd3a8-120">[out] This is a pointer to the location where a stream for the decompressed RTF is returned.</span></span> 
    
<span data-ttu-id="cd3a8-121">_pRetInfo_</span><span class="sxs-lookup"><span data-stu-id="cd3a8-121">_pRetInfo_</span></span>
  
> <span data-ttu-id="cd3a8-122">[输出]这是数据流的一个指向[RTF_WCSRETINFO](rtf_wcsretinfo.md)结构，其中包含返回记下解压缩后的格式信息。</span><span class="sxs-lookup"><span data-stu-id="cd3a8-122">[out] This is a pointer to a [RTF_WCSRETINFO](rtf_wcsretinfo.md) structure that contains information about the format of the returned decompressed stream.</span></span> 
    
## <a name="return-values"></a><span data-ttu-id="cd3a8-123">返回值</span><span class="sxs-lookup"><span data-stu-id="cd3a8-123">Return values</span></span>

<span data-ttu-id="cd3a8-124">S_OK</span><span class="sxs-lookup"><span data-stu-id="cd3a8-124">S_OK</span></span> 
  
- <span data-ttu-id="cd3a8-125">成功函数调用。</span><span class="sxs-lookup"><span data-stu-id="cd3a8-125">The function call is successful.</span></span>
    
<span data-ttu-id="cd3a8-126">MAPI_E_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="cd3a8-126">MAPI_E_INVALID_PARAMETER</span></span> 
  
- <span data-ttu-id="cd3a8-127">如果**MAPI_NATIVE_BODY**标志结合在由*pWCSInfo*指向**RTF_WCSINFO**结构的**ulFlags**字段中的**MAPI_MODIFY**标志，则返回此。</span><span class="sxs-lookup"><span data-stu-id="cd3a8-127">This is returned if the **MAPI_NATIVE_BODY** flag is combined with the **MAPI_MODIFY** flag in the **ulFlags** field of the **RTF_WCSINFO** structure pointed at by  *pWCSInfo*  .</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="cd3a8-128">说明</span><span class="sxs-lookup"><span data-stu-id="cd3a8-128">Remarks</span></span>

<span data-ttu-id="cd3a8-129">记下解压缩后的流和其格式，和 （可选） 的本机正文流，使您可以访问由解压缩流封装在压缩 RTF 电子邮件的正文返回**WrapCompressedRTFStreamEx** 。</span><span class="sxs-lookup"><span data-stu-id="cd3a8-129">**WrapCompressedRTFStreamEx** allows you to access the body of an email message encapsulated in compressed RTF by decompressing the stream, returns the decompressed stream and its format, and optionally the native body stream.</span></span> <span data-ttu-id="cd3a8-130">本机正文流可以的 RTF、 纯文本或 HTML。</span><span class="sxs-lookup"><span data-stu-id="cd3a8-130">The native body stream can be in RTF, plain text, or HTML.</span></span> 
  
<span data-ttu-id="cd3a8-131">Microsoft Office Outlook 对象模型提供的**MailItem**对象和[MailItem.BodyFormat 属性 (Outlook)](https://msdn.microsoft.com/library/f635a0bc-20b7-206c-f558-a4ca2519670f%28Office.15%29.aspx)指示正文文本的格式的**Body**属性。</span><span class="sxs-lookup"><span data-stu-id="cd3a8-131">The Microsoft Office Outlook object model provides a **Body** property for **MailItem** objects and a [MailItem.BodyFormat Property (Outlook)](https://msdn.microsoft.com/library/f635a0bc-20b7-206c-f558-a4ca2519670f%28Office.15%29.aspx) that indicates the format of the body text.</span></span> <span data-ttu-id="cd3a8-132">按照设计，不受信任的 Outlook 解决方案调用生成的 Outlook 安全 Guard 的安全对话框。</span><span class="sxs-lookup"><span data-stu-id="cd3a8-132">By design, a solution that is not trusted by Outlook invokes security dialog boxes generated by the Outlook Security Guard.</span></span> <span data-ttu-id="cd3a8-133">使用导出 MAPI 函数**WrapCompressedRTFStreamEx**允许使用 MAPI，而不是 Outlook 对象模型，并避免这些安全对话框的解决方案。</span><span class="sxs-lookup"><span data-stu-id="cd3a8-133">Using the exported MAPI function **WrapCompressedRTFStreamEx** allows a solution to use MAPI instead of the Outlook object model and avoid these security dialog boxes.</span></span> 
  
<span data-ttu-id="cd3a8-134">因为**MAPI\_NATIVE_BODY**标志不能组合与**MAPI\_修改** **ulFlags**字段中的标志**RTF\_WCSINFO**结构指向*pWCSInfo*，您只能访问本机在只读模式下的正文流。</span><span class="sxs-lookup"><span data-stu-id="cd3a8-134">Because the **MAPI\_NATIVE_BODY** flag cannot be combined with the **MAPI\_MODIFY** flag in the **ulFlags** field of the **RTF\_WCSINFO** structure pointed at by *pWCSInfo*, you can only access the native body stream in read-only mode.</span></span> <span data-ttu-id="cd3a8-135">若要访问本机正文流读/写模式，您应使用**WrapCompressedRTFStream**函数。</span><span class="sxs-lookup"><span data-stu-id="cd3a8-135">To access the native body stream in read/write mode, you should use the **WrapCompressedRTFStream** function.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="cd3a8-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cd3a8-136">See also</span></span>

- [<span data-ttu-id="cd3a8-137">检索压缩 RTF 格式的邮件正文，并将其转换为本机格式</span><span class="sxs-lookup"><span data-stu-id="cd3a8-137">Retrieve the Body of a Message in Compressed RTF and Convert It to Its Native Format</span></span>](how-to-retrieve-the-body-of-a-message-in-compressed-rtf-and-convert.md)

