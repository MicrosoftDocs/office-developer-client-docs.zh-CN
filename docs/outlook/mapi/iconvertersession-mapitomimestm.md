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
description: 上次修改时间： 2017 年 9 月 20，
ms.openlocfilehash: 55c547c4dae1acc3e9874edc7778f53a5d34f957
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25400115"
---
# <a name="iconvertersessionmapitomimestm"></a><span data-ttu-id="f01f7-103">IConverterSession::MAPIToMIMEStm</span><span class="sxs-lookup"><span data-stu-id="f01f7-103">IConverterSession::MAPIToMIMEStm</span></span>
 
  
<span data-ttu-id="f01f7-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f01f7-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f01f7-105">将 MAPI 邮件转换为 MIME 流。</span><span class="sxs-lookup"><span data-stu-id="f01f7-105">Converts a MAPI message to a MIME stream.</span></span>
  
```cpp
HRESULT IConverterSession::MAPIToMIMEStm( 
    LPMESSAGE pmsg, 
    LPSTREAM pstm, 
    ULONG ulFlags 
);
```

## <a name="parameters"></a><span data-ttu-id="f01f7-106">参数</span><span class="sxs-lookup"><span data-stu-id="f01f7-106">Parameters</span></span>

 <span data-ttu-id="f01f7-107">_pmsg_</span><span class="sxs-lookup"><span data-stu-id="f01f7-107">_pmsg_</span></span>
  
> <span data-ttu-id="f01f7-108">[in]指向要转换的消息的指针。</span><span class="sxs-lookup"><span data-stu-id="f01f7-108">[in] Pointer to the message to convert.</span></span> <span data-ttu-id="f01f7-109">请参阅 mapidefs.h **LPMESSAGE**的类型定义。</span><span class="sxs-lookup"><span data-stu-id="f01f7-109">See mapidefs.h for the type definition of **LPMESSAGE**.</span></span>
    
 <span data-ttu-id="f01f7-110">_pstm_</span><span class="sxs-lookup"><span data-stu-id="f01f7-110">_pstm_</span></span>
  
> <span data-ttu-id="f01f7-111">[输出]要输出流[IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx)接口。</span><span class="sxs-lookup"><span data-stu-id="f01f7-111">[out] [IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx) interface to output the stream.</span></span> 
    
 <span data-ttu-id="f01f7-112">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="f01f7-112">_ulFlags_</span></span>
  
>  <span data-ttu-id="f01f7-113">[in]这些标志指示转换器的特定操作：</span><span class="sxs-lookup"><span data-stu-id="f01f7-113">[in] Flags that indicate specific actions for the converter:</span></span> 
    
<span data-ttu-id="f01f7-114">CCSF_8BITHEADERS</span><span class="sxs-lookup"><span data-stu-id="f01f7-114">CCSF_8BITHEADERS</span></span>
  
> <span data-ttu-id="f01f7-115">转换器应允许 8 位标头。</span><span class="sxs-lookup"><span data-stu-id="f01f7-115">The converter should allow 8-bit headers.</span></span>
    
<span data-ttu-id="f01f7-116">CCSF_EMBEDDED_MESSAGE</span><span class="sxs-lookup"><span data-stu-id="f01f7-116">CCSF_EMBEDDED_MESSAGE</span></span>
  
> <span data-ttu-id="f01f7-117">发送/未发送信息保留在未发送的 X。</span><span class="sxs-lookup"><span data-stu-id="f01f7-117">Sent/unsent information is persisted in X-Unsent.</span></span>
    
<span data-ttu-id="f01f7-118">CCSF_GLOBAL_MESSAGE</span><span class="sxs-lookup"><span data-stu-id="f01f7-118">CCSF_GLOBAL_MESSAGE</span></span>
  
> <span data-ttu-id="f01f7-119">转换器应该构建国际邮件 (EAI/RFC6530)。</span><span class="sxs-lookup"><span data-stu-id="f01f7-119">The converter should build an international message (EAI/RFC6530).</span></span>
    
<span data-ttu-id="f01f7-120">CCSF_INCLUDE_BCC</span><span class="sxs-lookup"><span data-stu-id="f01f7-120">CCSF_INCLUDE_BCC</span></span>
  
> <span data-ttu-id="f01f7-121">应 MIME 用于将 stream 中包含的 MAPI 邮件的密件抄送收件人。</span><span class="sxs-lookup"><span data-stu-id="f01f7-121">BCC recipients of the MAPI message should be included in the MIME stream.</span></span>
    
<span data-ttu-id="f01f7-122">CCSF_NO_MSGID</span><span class="sxs-lookup"><span data-stu-id="f01f7-122">CCSF_NO_MSGID</span></span>
  
> <span data-ttu-id="f01f7-123">传出消息中不包括消息 Id 字段。</span><span class="sxs-lookup"><span data-stu-id="f01f7-123">Do not include Message-Id field in outgoing messages.</span></span>
    
<span data-ttu-id="f01f7-124">CCSF_NOHEADERS</span><span class="sxs-lookup"><span data-stu-id="f01f7-124">CCSF_NOHEADERS</span></span>
  
> <span data-ttu-id="f01f7-125">转换器忽略外部邮件的标头。</span><span class="sxs-lookup"><span data-stu-id="f01f7-125">The converter should ignore the headers of the outside message.</span></span>
    
<span data-ttu-id="f01f7-126">CCSF_PLAIN_TEXT_ONLY</span><span class="sxs-lookup"><span data-stu-id="f01f7-126">CCSF_PLAIN_TEXT_ONLY</span></span>
  
> <span data-ttu-id="f01f7-127">转换器应只发送纯文本。</span><span class="sxs-lookup"><span data-stu-id="f01f7-127">The converter should just send plain text.</span></span>
    
<span data-ttu-id="f01f7-128">CCSF_SMTP</span><span class="sxs-lookup"><span data-stu-id="f01f7-128">CCSF_SMTP</span></span>
  
> <span data-ttu-id="f01f7-129">转换器所传递的 SMTP 邮件。</span><span class="sxs-lookup"><span data-stu-id="f01f7-129">The converter is being passed an SMTP message.</span></span> <span data-ttu-id="f01f7-130">必须始终设置此标志。</span><span class="sxs-lookup"><span data-stu-id="f01f7-130">This flag must always be set.</span></span>
    
<span data-ttu-id="f01f7-131">CCSF_USE_RTF</span><span class="sxs-lookup"><span data-stu-id="f01f7-131">CCSF_USE_RTF</span></span>
  
> <span data-ttu-id="f01f7-132">转换器应为 MIME 邮件中的 RTF 格式转换的 HTML。</span><span class="sxs-lookup"><span data-stu-id="f01f7-132">The converter should convert from HTML to RTF format in the MIME message.</span></span>
    
<span data-ttu-id="f01f7-133">CCSF_USE_TNEF</span><span class="sxs-lookup"><span data-stu-id="f01f7-133">CCSF_USE_TNEF</span></span>
  
> <span data-ttu-id="f01f7-134">转换器应该 MIME 邮件中使用传输中性封装格式 (TNEF) 格式。</span><span class="sxs-lookup"><span data-stu-id="f01f7-134">The converter should use Transport Neutral Encapsulation Format (TNEF) format in the MIME message.</span></span>
    
## <a name="return-values"></a><span data-ttu-id="f01f7-135">返回值</span><span class="sxs-lookup"><span data-stu-id="f01f7-135">Return values</span></span>

<span data-ttu-id="f01f7-136">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="f01f7-136">E_INVALIDARG</span></span>
  
> <span data-ttu-id="f01f7-137">传递标志无效，或*pmsg*或*pstm*为 NULL。</span><span class="sxs-lookup"><span data-stu-id="f01f7-137">Invalid flags were passed, or  *pmsg*  or  *pstm*  is NULL.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="f01f7-138">说明</span><span class="sxs-lookup"><span data-stu-id="f01f7-138">Remarks</span></span>

<span data-ttu-id="f01f7-139">仅支持标准的 Outlook 邮件类型。</span><span class="sxs-lookup"><span data-stu-id="f01f7-139">Supported only for standard Outlook message types.</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="f01f7-140">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="f01f7-140">MFCMAPI reference</span></span>

<span data-ttu-id="f01f7-141">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="f01f7-141">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="f01f7-142">**文件**</span><span class="sxs-lookup"><span data-stu-id="f01f7-142">**File**</span></span>|<span data-ttu-id="f01f7-143">**函数**</span><span class="sxs-lookup"><span data-stu-id="f01f7-143">**Function**</span></span>|<span data-ttu-id="f01f7-144">**备注**</span><span class="sxs-lookup"><span data-stu-id="f01f7-144">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f01f7-145">MapiMime.cpp</span><span class="sxs-lookup"><span data-stu-id="f01f7-145">MapiMime.cpp</span></span>  <br/> |<span data-ttu-id="f01f7-146">ImportEMLToIMessage</span><span class="sxs-lookup"><span data-stu-id="f01f7-146">ImportEMLToIMessage</span></span>  <br/> |<span data-ttu-id="f01f7-147">MFCMAPI 使用 MimeToMAPI 将 EML 文件转换为 MAPI 邮件。</span><span class="sxs-lookup"><span data-stu-id="f01f7-147">MFCMAPI uses MimeToMAPI to convert an EML file to a MAPI message.</span></span>  <br/> |
|<span data-ttu-id="f01f7-148">MapiMime.cpp</span><span class="sxs-lookup"><span data-stu-id="f01f7-148">MapiMime.cpp</span></span>  <br/> |<span data-ttu-id="f01f7-149">ExportIMessageToEML</span><span class="sxs-lookup"><span data-stu-id="f01f7-149">ExportIMessageToEML</span></span>  <br/> |<span data-ttu-id="f01f7-150">MFCMAPI 使用 MAPIToMIMEStm 将转换为 EML 文件的 MAPI 邮件。</span><span class="sxs-lookup"><span data-stu-id="f01f7-150">MFCMAPI uses MAPIToMIMEStm to convert a MAPI message to an EML file.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="f01f7-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f01f7-151">See also</span></span>



[<span data-ttu-id="f01f7-152">IConverterSession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="f01f7-152">IConverterSession : IUnknown</span></span>](iconvertersessioniunknown.md)
  
[<span data-ttu-id="f01f7-153">IConverterSession::MAPIToMIMEStm</span><span class="sxs-lookup"><span data-stu-id="f01f7-153">IConverterSession::MAPIToMIMEStm</span></span>](iconvertersession-mapitomimestm.md)
  
[<span data-ttu-id="f01f7-154">IConverterSession::MIMEToMAPI</span><span class="sxs-lookup"><span data-stu-id="f01f7-154">IConverterSession::MIMEToMAPI</span></span>](iconvertersession-mimetomapi.md)
  
[<span data-ttu-id="f01f7-155">IConverterSession::SetAdrBook</span><span class="sxs-lookup"><span data-stu-id="f01f7-155">IConverterSession::SetAdrBook</span></span>](iconvertersession-setadrbook.md)
  
[<span data-ttu-id="f01f7-156">IConverterSession::SetCharSet</span><span class="sxs-lookup"><span data-stu-id="f01f7-156">IConverterSession::SetCharSet</span></span>](iconvertersession-setcharset.md)
  
[<span data-ttu-id="f01f7-157">IConverterSession::SetEncoding</span><span class="sxs-lookup"><span data-stu-id="f01f7-157">IConverterSession::SetEncoding</span></span>](iconvertersession-setencoding.md)
  
[<span data-ttu-id="f01f7-158">IConverterSession::SetSaveFormat</span><span class="sxs-lookup"><span data-stu-id="f01f7-158">IConverterSession::SetSaveFormat</span></span>](iconvertersession-setsaveformat.md)
  
[<span data-ttu-id="f01f7-159">IConverterSession::SetTextWrapping</span><span class="sxs-lookup"><span data-stu-id="f01f7-159">IConverterSession::SetTextWrapping</span></span>](iconvertersession-settextwrapping.md)
  
[<span data-ttu-id="f01f7-160">PidTagMessageEditorFormat 规范属性</span><span class="sxs-lookup"><span data-stu-id="f01f7-160">PidTagMessageEditorFormat Canonical Property</span></span>](pidtagmessageeditorformat-canonical-property.md)
  
[<span data-ttu-id="f01f7-161">PidLidUseTnef 规范属性</span><span class="sxs-lookup"><span data-stu-id="f01f7-161">PidLidUseTnef Canonical Property</span></span>](pidlidusetnef-canonical-property.md)


[<span data-ttu-id="f01f7-162">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="f01f7-162">MAPI Constants</span></span>](mapi-constants.md)

