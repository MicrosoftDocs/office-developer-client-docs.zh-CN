---
title: IConverterSessionMAPIToMIMEStm
ms.date: 9/20/2017
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IConverterSession.MAPIToMIMEStm
api_type:
- COM
ms.assetid: 8660c701-f7f4-8d92-7984-5dae7f677783
description: 上次修改时间：2017 年 9 月 20 日
ms.openlocfilehash: 55c547c4dae1acc3e9874edc7778f53a5d34f957
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326942"
---
# <a name="iconvertersessionmapitomimestm"></a><span data-ttu-id="3b015-103">IConverterSession::MAPIToMIMEStm</span><span class="sxs-lookup"><span data-stu-id="3b015-103">IConverterSession::MAPIToMIMEStm</span></span>
 
  
<span data-ttu-id="3b015-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3b015-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3b015-105">将 MAPI 邮件转换为 MIME 流。</span><span class="sxs-lookup"><span data-stu-id="3b015-105">Converts a MAPI message to a MIME stream.</span></span>
  
```cpp
HRESULT IConverterSession::MAPIToMIMEStm( 
    LPMESSAGE pmsg, 
    LPSTREAM pstm, 
    ULONG ulFlags 
);
```

## <a name="parameters"></a><span data-ttu-id="3b015-106">参数</span><span class="sxs-lookup"><span data-stu-id="3b015-106">Parameters</span></span>

 <span data-ttu-id="3b015-107">_pmsg_</span><span class="sxs-lookup"><span data-stu-id="3b015-107">_pmsg_</span></span>
  
> <span data-ttu-id="3b015-108">[in]指向要转换的消息的指针。</span><span class="sxs-lookup"><span data-stu-id="3b015-108">[in] Pointer to the message to convert.</span></span> <span data-ttu-id="3b015-109">有关 **LPMESSAGE** 的类型定义，请参阅 mapidefs.h。</span><span class="sxs-lookup"><span data-stu-id="3b015-109">See mapidefs.h for the type definition of **LPMESSAGE**.</span></span>
    
 <span data-ttu-id="3b015-110">_pstm_</span><span class="sxs-lookup"><span data-stu-id="3b015-110">_pstm_</span></span>
  
> <span data-ttu-id="3b015-111">[out]用于输出流的 [IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx) 接口。</span><span class="sxs-lookup"><span data-stu-id="3b015-111">[out] [IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx) interface to output the stream.</span></span> 
    
 <span data-ttu-id="3b015-112">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="3b015-112">_ulFlags_</span></span>
  
>  <span data-ttu-id="3b015-113">[in]指示转换器的特定操作的标志：</span><span class="sxs-lookup"><span data-stu-id="3b015-113">[in] Flags that indicate specific actions for the converter:</span></span> 
    
<span data-ttu-id="3b015-114">CCSF_8BITHEADERS</span><span class="sxs-lookup"><span data-stu-id="3b015-114">CCSF_8BITHEADERS</span></span>
  
> <span data-ttu-id="3b015-115">转换器应允许使用 8 位标头。</span><span class="sxs-lookup"><span data-stu-id="3b015-115">The converter should allow 8-bit headers.</span></span>
    
<span data-ttu-id="3b015-116">CCSF_EMBEDDED_MESSAGE</span><span class="sxs-lookup"><span data-stu-id="3b015-116">CCSF_EMBEDDED_MESSAGE</span></span>
  
> <span data-ttu-id="3b015-117">已发送/未发送的信息将保留于 X-Unsent 中。</span><span class="sxs-lookup"><span data-stu-id="3b015-117">Sent/unsent information is persisted in X-Unsent.</span></span>
    
<span data-ttu-id="3b015-118">CCSF_GLOBAL_MESSAGE</span><span class="sxs-lookup"><span data-stu-id="3b015-118">CCSF_GLOBAL_MESSAGE</span></span>
  
> <span data-ttu-id="3b015-119">转换器应在 EAI/RFC6530 (生成国际) 。</span><span class="sxs-lookup"><span data-stu-id="3b015-119">The converter should build an international message (EAI/RFC6530).</span></span>
    
<span data-ttu-id="3b015-120">CCSF_INCLUDE_BCC</span><span class="sxs-lookup"><span data-stu-id="3b015-120">CCSF_INCLUDE_BCC</span></span>
  
> <span data-ttu-id="3b015-121">MAPI 邮件的 BCC 收件人应包含在 MIME 流中。</span><span class="sxs-lookup"><span data-stu-id="3b015-121">BCC recipients of the MAPI message should be included in the MIME stream.</span></span>
    
<span data-ttu-id="3b015-122">CCSF_NO_MSGID</span><span class="sxs-lookup"><span data-stu-id="3b015-122">CCSF_NO_MSGID</span></span>
  
> <span data-ttu-id="3b015-123">请勿在传出Message-Id字段。</span><span class="sxs-lookup"><span data-stu-id="3b015-123">Do not include Message-Id field in outgoing messages.</span></span>
    
<span data-ttu-id="3b015-124">CCSF_NOHEADERS</span><span class="sxs-lookup"><span data-stu-id="3b015-124">CCSF_NOHEADERS</span></span>
  
> <span data-ttu-id="3b015-125">转换器应忽略外部邮件的标题。</span><span class="sxs-lookup"><span data-stu-id="3b015-125">The converter should ignore the headers of the outside message.</span></span>
    
<span data-ttu-id="3b015-126">CCSF_PLAIN_TEXT_ONLY</span><span class="sxs-lookup"><span data-stu-id="3b015-126">CCSF_PLAIN_TEXT_ONLY</span></span>
  
> <span data-ttu-id="3b015-127">转换器应只发送纯文本。</span><span class="sxs-lookup"><span data-stu-id="3b015-127">The converter should just send plain text.</span></span>
    
<span data-ttu-id="3b015-128">CCSF_SMTP</span><span class="sxs-lookup"><span data-stu-id="3b015-128">CCSF_SMTP</span></span>
  
> <span data-ttu-id="3b015-129">正在向转换器传递 SMTP 邮件。</span><span class="sxs-lookup"><span data-stu-id="3b015-129">The converter is being passed an SMTP message.</span></span> <span data-ttu-id="3b015-130">必须始终设置此标志。</span><span class="sxs-lookup"><span data-stu-id="3b015-130">This flag must always be set.</span></span>
    
<span data-ttu-id="3b015-131">CCSF_USE_RTF</span><span class="sxs-lookup"><span data-stu-id="3b015-131">CCSF_USE_RTF</span></span>
  
> <span data-ttu-id="3b015-132">转换器应在 MIME 邮件中从 HTML 转换为 RTF 格式。</span><span class="sxs-lookup"><span data-stu-id="3b015-132">The converter should convert from HTML to RTF format in the MIME message.</span></span>
    
<span data-ttu-id="3b015-133">CCSF_USE_TNEF</span><span class="sxs-lookup"><span data-stu-id="3b015-133">CCSF_USE_TNEF</span></span>
  
> <span data-ttu-id="3b015-134">转换器应在 MIME 邮件 (传输中性封装) TNEF 格式。</span><span class="sxs-lookup"><span data-stu-id="3b015-134">The converter should use Transport Neutral Encapsulation Format (TNEF) format in the MIME message.</span></span>
    
## <a name="return-values"></a><span data-ttu-id="3b015-135">返回值</span><span class="sxs-lookup"><span data-stu-id="3b015-135">Return values</span></span>

<span data-ttu-id="3b015-136">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="3b015-136">E_INVALIDARG</span></span>
  
> <span data-ttu-id="3b015-137">传递了无效标志，  *或者 pmsg*  或  *pstm*  为 NULL。</span><span class="sxs-lookup"><span data-stu-id="3b015-137">Invalid flags were passed, or  *pmsg*  or  *pstm*  is NULL.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="3b015-138">备注</span><span class="sxs-lookup"><span data-stu-id="3b015-138">Remarks</span></span>

<span data-ttu-id="3b015-139">仅支持标准Outlook邮件类型。</span><span class="sxs-lookup"><span data-stu-id="3b015-139">Supported only for standard Outlook message types.</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="3b015-140">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="3b015-140">MFCMAPI reference</span></span>

<span data-ttu-id="3b015-141">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="3b015-141">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="3b015-142">**文件**</span><span class="sxs-lookup"><span data-stu-id="3b015-142">**File**</span></span>|<span data-ttu-id="3b015-143">**函数**</span><span class="sxs-lookup"><span data-stu-id="3b015-143">**Function**</span></span>|<span data-ttu-id="3b015-144">**备注**</span><span class="sxs-lookup"><span data-stu-id="3b015-144">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3b015-145">MapiMime.cpp</span><span class="sxs-lookup"><span data-stu-id="3b015-145">MapiMime.cpp</span></span>  <br/> |<span data-ttu-id="3b015-146">ImportEMLToIMessage</span><span class="sxs-lookup"><span data-stu-id="3b015-146">ImportEMLToIMessage</span></span>  <br/> |<span data-ttu-id="3b015-147">MFCMAPI 使用 MimeToMAPI 将 EML 文件转换为 MAPI 邮件。</span><span class="sxs-lookup"><span data-stu-id="3b015-147">MFCMAPI uses MimeToMAPI to convert an EML file to a MAPI message.</span></span>  <br/> |
|<span data-ttu-id="3b015-148">MapiMime.cpp</span><span class="sxs-lookup"><span data-stu-id="3b015-148">MapiMime.cpp</span></span>  <br/> |<span data-ttu-id="3b015-149">ExportIMessageToEML</span><span class="sxs-lookup"><span data-stu-id="3b015-149">ExportIMessageToEML</span></span>  <br/> |<span data-ttu-id="3b015-150">MFCMAPI 使用 MAPIToMIMEStm 将 MAPI 邮件转换为 EML 文件。</span><span class="sxs-lookup"><span data-stu-id="3b015-150">MFCMAPI uses MAPIToMIMEStm to convert a MAPI message to an EML file.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="3b015-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3b015-151">See also</span></span>



[<span data-ttu-id="3b015-152">IConverterSession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="3b015-152">IConverterSession : IUnknown</span></span>](iconvertersessioniunknown.md)
  
[<span data-ttu-id="3b015-153">IConverterSession::MAPIToMIMEStm</span><span class="sxs-lookup"><span data-stu-id="3b015-153">IConverterSession::MAPIToMIMEStm</span></span>](iconvertersession-mapitomimestm.md)
  
[<span data-ttu-id="3b015-154">IConverterSession::MIMEToMAPI</span><span class="sxs-lookup"><span data-stu-id="3b015-154">IConverterSession::MIMEToMAPI</span></span>](iconvertersession-mimetomapi.md)
  
[<span data-ttu-id="3b015-155">IConverterSession::SetAdrBook</span><span class="sxs-lookup"><span data-stu-id="3b015-155">IConverterSession::SetAdrBook</span></span>](iconvertersession-setadrbook.md)
  
[<span data-ttu-id="3b015-156">IConverterSession::SetCharSet</span><span class="sxs-lookup"><span data-stu-id="3b015-156">IConverterSession::SetCharSet</span></span>](iconvertersession-setcharset.md)
  
[<span data-ttu-id="3b015-157">IConverterSession::SetEncoding</span><span class="sxs-lookup"><span data-stu-id="3b015-157">IConverterSession::SetEncoding</span></span>](iconvertersession-setencoding.md)
  
[<span data-ttu-id="3b015-158">IConverterSession::SetSaveFormat</span><span class="sxs-lookup"><span data-stu-id="3b015-158">IConverterSession::SetSaveFormat</span></span>](iconvertersession-setsaveformat.md)
  
[<span data-ttu-id="3b015-159">IConverterSession::SetTextWrapping</span><span class="sxs-lookup"><span data-stu-id="3b015-159">IConverterSession::SetTextWrapping</span></span>](iconvertersession-settextwrapping.md)
  
[<span data-ttu-id="3b015-160">PidTagMessageEditorFormat 规范属性</span><span class="sxs-lookup"><span data-stu-id="3b015-160">PidTagMessageEditorFormat Canonical Property</span></span>](pidtagmessageeditorformat-canonical-property.md)
  
[<span data-ttu-id="3b015-161">PidLidUseTnef 规范属性</span><span class="sxs-lookup"><span data-stu-id="3b015-161">PidLidUseTnef Canonical Property</span></span>](pidlidusetnef-canonical-property.md)


[<span data-ttu-id="3b015-162">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="3b015-162">MAPI Constants</span></span>](mapi-constants.md)

