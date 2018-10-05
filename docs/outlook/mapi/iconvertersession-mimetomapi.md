---
title: IConverterSessionMIMEToMAPI
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IConverterSession.MIMEToMAPI
api_type:
- COM
ms.assetid: ee190ba7-9e71-97e4-7bf1-7b97adc73eed
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d71dd44d2dfc39124c5300d2597f5d8ed1e95ebb
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25395411"
---
# <a name="iconvertersessionmimetomapi"></a><span data-ttu-id="f193f-103">IConverterSession::MIMEToMAPI</span><span class="sxs-lookup"><span data-stu-id="f193f-103">IConverterSession::MIMEToMAPI</span></span>

  
  
<span data-ttu-id="f193f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f193f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f193f-105">将 MIME 流转换为 MAPI 邮件。</span><span class="sxs-lookup"><span data-stu-id="f193f-105">Converts a MIME stream to a MAPI message.</span></span>
  
```cpp
HRESULT IConverterSession:: MIMEToMAPI ( 
     LPSTREAM pstm, 
     LPMESSAGE pmsg, 
     LPCSTR pszSrcSrv, 
     ULONG ulFlags 
);
```

## <a name="parameters"></a><span data-ttu-id="f193f-106">参数</span><span class="sxs-lookup"><span data-stu-id="f193f-106">Parameters</span></span>

 <span data-ttu-id="f193f-107">_pstm_</span><span class="sxs-lookup"><span data-stu-id="f193f-107">_pstm_</span></span>
  
> <span data-ttu-id="f193f-108">[in]MIME 流[IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx)接口。</span><span class="sxs-lookup"><span data-stu-id="f193f-108">[in] [IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx) interface to a MIME stream.</span></span> 
    
 <span data-ttu-id="f193f-109">_pmsg_</span><span class="sxs-lookup"><span data-stu-id="f193f-109">_pmsg_</span></span>
  
> <span data-ttu-id="f193f-110">[输出]指向要加载的消息。</span><span class="sxs-lookup"><span data-stu-id="f193f-110">[out] Pointer to the message to load.</span></span> <span data-ttu-id="f193f-111">请参阅 mapidefs.h **LPMESSAGE**的类型定义。</span><span class="sxs-lookup"><span data-stu-id="f193f-111">See mapidefs.h for the type definition of **LPMESSAGE**.</span></span>
    
 <span data-ttu-id="f193f-112">_pszSrcSrv_</span><span class="sxs-lookup"><span data-stu-id="f193f-112">_pszSrcSrv_</span></span>
  
> <span data-ttu-id="f193f-113">[in]此值必须为**空**。</span><span class="sxs-lookup"><span data-stu-id="f193f-113">[in] This value must be **null**.</span></span>
    
 <span data-ttu-id="f193f-114">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="f193f-114">_ulFlags_</span></span>
  
> <span data-ttu-id="f193f-115">[in]此参数用于标识转换期间执行任何特殊操作。</span><span class="sxs-lookup"><span data-stu-id="f193f-115">[in] This parameter identifies any special action to be taken during the conversion.</span></span> <span data-ttu-id="f193f-116">零 (0) 任何特定操作时要采取或以下值的组合，则必须将它：</span><span class="sxs-lookup"><span data-stu-id="f193f-116">It must be zero (0) if no specific action is to be taken, or a combination of the following values:</span></span>
    
<span data-ttu-id="f193f-117">CCSF_EMBEDDED_MESSAGE</span><span class="sxs-lookup"><span data-stu-id="f193f-117">CCSF_EMBEDDED_MESSAGE</span></span>
  
> <span data-ttu-id="f193f-118">发送/未发送信息保留在未发送的 X。</span><span class="sxs-lookup"><span data-stu-id="f193f-118">Sent/unsent information is persisted in X-Unsent.</span></span>
    
<span data-ttu-id="f193f-119">CCSF_SMTP</span><span class="sxs-lookup"><span data-stu-id="f193f-119">CCSF_SMTP</span></span>
  
> <span data-ttu-id="f193f-120">简单 MAPI 传输协议 (SMTP) 邮件 MIME 流。</span><span class="sxs-lookup"><span data-stu-id="f193f-120">The MIME stream is for a Simple MAPI Transfer Protocol (SMTP) message.</span></span>
    
<span data-ttu-id="f193f-121">CCSF_INCLUDE_BCC</span><span class="sxs-lookup"><span data-stu-id="f193f-121">CCSF_INCLUDE_BCC</span></span>
  
> <span data-ttu-id="f193f-122">应 MAPI 邮件中包含 MIME stream 的密件抄送收件人。</span><span class="sxs-lookup"><span data-stu-id="f193f-122">BCC recipients of the MIME stream should be included in the MAPI message.</span></span>
    
<span data-ttu-id="f193f-123">CCSF_USE_RTF</span><span class="sxs-lookup"><span data-stu-id="f193f-123">CCSF_USE_RTF</span></span>
  
> <span data-ttu-id="f193f-124">MIME 流的 HTML 正文应转换到富文本格式 (RTF) 中的 MAPI 邮件。</span><span class="sxs-lookup"><span data-stu-id="f193f-124">The HTML body of the MIME stream should be converted to Rich Text Format (RTF) in the MAPI message.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="f193f-125">返回值</span><span class="sxs-lookup"><span data-stu-id="f193f-125">Return value</span></span>

<span data-ttu-id="f193f-126">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="f193f-126">E_INVALIDARG</span></span>
  
> <span data-ttu-id="f193f-127">指示_pstm_为**null**， _pmsg_为**null**，或者_ulFlags_无效。</span><span class="sxs-lookup"><span data-stu-id="f193f-127">Indicates that  _pstm_ is **null**,  _pmsg_ is **null**, or  _ulFlags_ is invalid.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="f193f-128">说明</span><span class="sxs-lookup"><span data-stu-id="f193f-128">Remarks</span></span>

<span data-ttu-id="f193f-129">如果您指定**CCSF_USE_RTF** _ulFlags_的一部分，目标消息存储库支持 HTML 和 RTF 的 MAPI 邮件将被转换为 HTML 或 RTF。</span><span class="sxs-lookup"><span data-stu-id="f193f-129">If you have specified **CCSF_USE_RTF** as part of  _ulFlags_ and the destination message store supports both HTML and RTF, the MAPI message will be converted to either HTML or RTF.</span></span> <span data-ttu-id="f193f-130">如果邮件转换为 RTF 时，将压缩转换的格式 RTF，将在压缩的 RTF 字符串中嵌入任何 HTML 和将[PidTagRtfCompressed 规范属性](pidtagrtfcompressed-canonical-property.md)中包含字符串。</span><span class="sxs-lookup"><span data-stu-id="f193f-130">If the message is converted to RTF, the converted format will be compressed RTF, any HTML will be embedded in the compressed RTF string, and the string will be contained in the [PidTagRtfCompressed Canonical Property](pidtagrtfcompressed-canonical-property.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="f193f-131">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="f193f-131">MFCMAPI reference</span></span>

<span data-ttu-id="f193f-132">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="f193f-132">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="f193f-133">**文件**</span><span class="sxs-lookup"><span data-stu-id="f193f-133">**File**</span></span>|<span data-ttu-id="f193f-134">**函数**</span><span class="sxs-lookup"><span data-stu-id="f193f-134">**Function**</span></span>|<span data-ttu-id="f193f-135">**备注**</span><span class="sxs-lookup"><span data-stu-id="f193f-135">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f193f-136">MapiMime.cpp</span><span class="sxs-lookup"><span data-stu-id="f193f-136">MapiMime.cpp</span></span>  <br/> |<span data-ttu-id="f193f-137">ImportEMLToIMessage</span><span class="sxs-lookup"><span data-stu-id="f193f-137">ImportEMLToIMessage</span></span>  <br/> |<span data-ttu-id="f193f-138">MFCMAPI 使用 MimeToMAPI 将 EML 文件转换为 MAPI 邮件。</span><span class="sxs-lookup"><span data-stu-id="f193f-138">MFCMAPI uses MimeToMAPI to convert an EML file to a MAPI message.</span></span>  <br/> |
|<span data-ttu-id="f193f-139">MapiMime.cpp</span><span class="sxs-lookup"><span data-stu-id="f193f-139">MapiMime.cpp</span></span>  <br/> |<span data-ttu-id="f193f-140">ExportIMessageToEML</span><span class="sxs-lookup"><span data-stu-id="f193f-140">ExportIMessageToEML</span></span>  <br/> |<span data-ttu-id="f193f-141">MFCMAPI 使用 MAPIToMIMEStm 将转换为 EML 文件的 MAPI 邮件。</span><span class="sxs-lookup"><span data-stu-id="f193f-141">MFCMAPI uses MAPIToMIMEStm to convert a MAPI message to an EML file.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="f193f-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f193f-142">See also</span></span>



[<span data-ttu-id="f193f-143">IConverterSession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="f193f-143">IConverterSession : IUnknown</span></span>](iconvertersessioniunknown.md)
  
[<span data-ttu-id="f193f-144">IConverterSession::MAPIToMIMEStm</span><span class="sxs-lookup"><span data-stu-id="f193f-144">IConverterSession::MAPIToMIMEStm</span></span>](iconvertersession-mapitomimestm.md)
  
[<span data-ttu-id="f193f-145">IConverterSession::SetAdrBook</span><span class="sxs-lookup"><span data-stu-id="f193f-145">IConverterSession::SetAdrBook</span></span>](iconvertersession-setadrbook.md)
  
[<span data-ttu-id="f193f-146">IConverterSession::SetCharSet</span><span class="sxs-lookup"><span data-stu-id="f193f-146">IConverterSession::SetCharSet</span></span>](iconvertersession-setcharset.md)
  
[<span data-ttu-id="f193f-147">IConverterSession::SetEncoding</span><span class="sxs-lookup"><span data-stu-id="f193f-147">IConverterSession::SetEncoding</span></span>](iconvertersession-setencoding.md)
  
[<span data-ttu-id="f193f-148">IConverterSession::SetSaveFormat</span><span class="sxs-lookup"><span data-stu-id="f193f-148">IConverterSession::SetSaveFormat</span></span>](iconvertersession-setsaveformat.md)
  
[<span data-ttu-id="f193f-149">IConverterSession::SetTextWrapping</span><span class="sxs-lookup"><span data-stu-id="f193f-149">IConverterSession::SetTextWrapping</span></span>](iconvertersession-settextwrapping.md)


[<span data-ttu-id="f193f-150">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="f193f-150">MAPI Constants</span></span>](mapi-constants.md)

