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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32325772"
---
# <a name="wrapcompressedrtfstreamex"></a><span data-ttu-id="64665-103">WrapCompressedRTFStreamEx</span><span class="sxs-lookup"><span data-stu-id="64665-103">WrapCompressedRTFStreamEx</span></span>

<span data-ttu-id="64665-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="64665-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="64665-105">解压缩 RTF (RTF) 格式的电子邮件正文，指示解压缩流的格式，（可选）将解压缩的流转换为本机格式，并返回解压缩的流或已转换的本机流。</span><span class="sxs-lookup"><span data-stu-id="64665-105">Decompresses the the body of an email message that is in compressed Rich Text Format (RTF), indicates the format of the decompressed stream, optionally converts the decompressed stream to its native format, and returns either the decompressed stream or the converted native stream.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="64665-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="64665-106">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="64665-107">导出者：</span><span class="sxs-lookup"><span data-stu-id="64665-107">Exported by:</span></span>  <br/> |<span data-ttu-id="64665-108">msmapi32.dll</span><span class="sxs-lookup"><span data-stu-id="64665-108">msmapi32.dll</span></span>  <br/> |
|<span data-ttu-id="64665-109">调用者：</span><span class="sxs-lookup"><span data-stu-id="64665-109">Called by:</span></span>  <br/> |<span data-ttu-id="64665-110">客户端</span><span class="sxs-lookup"><span data-stu-id="64665-110">Client</span></span>  <br/> |
|<span data-ttu-id="64665-111">实现者：</span><span class="sxs-lookup"><span data-stu-id="64665-111">Implemented by:</span></span>  <br/> |<span data-ttu-id="64665-112">Outlook</span><span class="sxs-lookup"><span data-stu-id="64665-112">Outlook</span></span>  <br/> |
   
```cpp
HRESULT __stdcall WrapCompressedRTFStreamEx( 
    LPSTREAM            lpCompressedRTFStream, 
    CONST RTF_WCSINFO   *pWCSInfo, 
    LPSTREAM            *lppUncompressedRTFStream, 
    RTF_WCSRETINFO      *pRetInfo); 

```

## <a name="parameters"></a><span data-ttu-id="64665-113">参数</span><span class="sxs-lookup"><span data-stu-id="64665-113">Parameters</span></span>

<span data-ttu-id="64665-114">_lpCompressedRTFStream_</span><span class="sxs-lookup"><span data-stu-id="64665-114">_lpCompressedRTFStream_</span></span>
  
> <span data-ttu-id="64665-115">[in]这是一个指针，指向在 [邮件的 PidTagRtfCompressed 规范属性](pidtagrtfcompressed-canonical-property.md) 上打开的流。</span><span class="sxs-lookup"><span data-stu-id="64665-115">[in] This is a pointer to a stream that is opened on the [PidTagRtfCompressed Canonical Property](pidtagrtfcompressed-canonical-property.md) of a message.</span></span> 
    
<span data-ttu-id="64665-116">_pWCSInfo_</span><span class="sxs-lookup"><span data-stu-id="64665-116">_pWCSInfo_</span></span>
  
> <span data-ttu-id="64665-117">[in]This is a pointer to a</span><span class="sxs-lookup"><span data-stu-id="64665-117">[in] This is a pointer to a</span></span> 
    
   <span data-ttu-id="64665-118">[RTF_WCSINFO](rtf_wcsinfo.md) 包含函数选项的一个结构。</span><span class="sxs-lookup"><span data-stu-id="64665-118">[RTF_WCSINFO](rtf_wcsinfo.md) structure that contains options for the function.</span></span> 
    
<span data-ttu-id="64665-119">_lppUncompressedRTFStream_</span><span class="sxs-lookup"><span data-stu-id="64665-119">_lppUncompressedRTFStream_</span></span>
  
> <span data-ttu-id="64665-120">[out]This is a pointer to the location where a stream for the decompressed RTF is returned.</span><span class="sxs-lookup"><span data-stu-id="64665-120">[out] This is a pointer to the location where a stream for the decompressed RTF is returned.</span></span> 
    
<span data-ttu-id="64665-121">_pRetInfo_</span><span class="sxs-lookup"><span data-stu-id="64665-121">_pRetInfo_</span></span>
  
> <span data-ttu-id="64665-122">[out]This is a pointer to a [RTF_WCSRETINFO](rtf_wcsretinfo.md) structure that contains information about the format of the returned decompressed stream.</span><span class="sxs-lookup"><span data-stu-id="64665-122">[out] This is a pointer to a [RTF_WCSRETINFO](rtf_wcsretinfo.md) structure that contains information about the format of the returned decompressed stream.</span></span> 
    
## <a name="return-values"></a><span data-ttu-id="64665-123">返回值</span><span class="sxs-lookup"><span data-stu-id="64665-123">Return values</span></span>

<span data-ttu-id="64665-124">S_OK</span><span class="sxs-lookup"><span data-stu-id="64665-124">S_OK</span></span> 
  
- <span data-ttu-id="64665-125">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="64665-125">The function call is successful.</span></span>
    
<span data-ttu-id="64665-126">MAPI_E_INVALID_PARAMETER</span><span class="sxs-lookup"><span data-stu-id="64665-126">MAPI_E_INVALID_PARAMETER</span></span> 
  
- <span data-ttu-id="64665-127">如果 MAPI_NATIVE_BODY 标记 **与** *pWCSInfo* 指向的 RTF_WCSINFO 结构的 **ulFlags** 字段中的 **MAPI_MODIFY** 标志组合在一起 **，** 则返回此标记。</span><span class="sxs-lookup"><span data-stu-id="64665-127">This is returned if the **MAPI_NATIVE_BODY** flag is combined with the **MAPI_MODIFY** flag in the **ulFlags** field of the **RTF_WCSINFO** structure pointed at by  *pWCSInfo*  .</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="64665-128">备注</span><span class="sxs-lookup"><span data-stu-id="64665-128">Remarks</span></span>

<span data-ttu-id="64665-129">**WrapCompressedRTFStreamEx** 允许你通过解压缩流访问封装在压缩 RTF 中的电子邮件正文、返回解压缩的流及其格式以及本机正文流（可选）。</span><span class="sxs-lookup"><span data-stu-id="64665-129">**WrapCompressedRTFStreamEx** allows you to access the body of an email message encapsulated in compressed RTF by decompressing the stream, returns the decompressed stream and its format, and optionally the native body stream.</span></span> <span data-ttu-id="64665-130">本机正文流可以是 RTF、纯文本或 HTML 格式。</span><span class="sxs-lookup"><span data-stu-id="64665-130">The native body stream can be in RTF, plain text, or HTML.</span></span> 
  
<span data-ttu-id="64665-131">The Microsoft Office Outlook object model provides a **Body** property for **MailItem** objects and a [MailItem.BodyFormat Property (Outlook)](https://msdn.microsoft.com/library/f635a0bc-20b7-206c-f558-a4ca2519670f%28Office.15%29.aspx) that indicates the format of the body text.</span><span class="sxs-lookup"><span data-stu-id="64665-131">The Microsoft Office Outlook object model provides a **Body** property for **MailItem** objects and a [MailItem.BodyFormat Property (Outlook)](https://msdn.microsoft.com/library/f635a0bc-20b7-206c-f558-a4ca2519670f%28Office.15%29.aspx) that indicates the format of the body text.</span></span> <span data-ttu-id="64665-132">根据设计，Outlook 不信任的解决方案会调用由 Outlook 安全防护生成的安全对话框。</span><span class="sxs-lookup"><span data-stu-id="64665-132">By design, a solution that is not trusted by Outlook invokes security dialog boxes generated by the Outlook Security Guard.</span></span> <span data-ttu-id="64665-133">使用导出的 MAPI 函数 **WrapCompressedRTFStreamEx** 允许解决方案使用 MAPI 而不是 Outlook 对象模型，并避免这些安全对话框。</span><span class="sxs-lookup"><span data-stu-id="64665-133">Using the exported MAPI function **WrapCompressedRTFStreamEx** allows a solution to use MAPI instead of the Outlook object model and avoid these security dialog boxes.</span></span> 
  
<span data-ttu-id="64665-134">由于 **MAPI \_ NATIVE_BODY** 标志不能与 *pWCSInfo* 指向的 **RTF \_ WCSINFO** 结构的 **ulFlags** 字段中的 **MAPI \_ MODIFY** 标志组合在一起，因此只能在只读模式下访问本机正文流。</span><span class="sxs-lookup"><span data-stu-id="64665-134">Because the **MAPI\_NATIVE_BODY** flag cannot be combined with the **MAPI\_MODIFY** flag in the **ulFlags** field of the **RTF\_WCSINFO** structure pointed at by *pWCSInfo*, you can only access the native body stream in read-only mode.</span></span> <span data-ttu-id="64665-135">若要在读/写模式下访问本机正文流，你应该使用 **WrapCompressedRTFStream** 函数。</span><span class="sxs-lookup"><span data-stu-id="64665-135">To access the native body stream in read/write mode, you should use the **WrapCompressedRTFStream** function.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="64665-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="64665-136">See also</span></span>

- [<span data-ttu-id="64665-137">检索压缩 RTF 格式的邮件正文并将其转换为本机格式</span><span class="sxs-lookup"><span data-stu-id="64665-137">Retrieve the Body of a Message in Compressed RTF and Convert It to Its Native Format</span></span>](how-to-retrieve-the-body-of-a-message-in-compressed-rtf-and-convert.md)

