---
title: IConverterSessionMIMEToMAPI
manager: soliver
ms.date: 09/06/2019
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IConverterSession.MIMEToMAPI
api_type:
- COM
ms.assetid: ee190ba7-9e71-97e4-7bf1-7b97adc73eed
description: 上次修改时间：2019 年 9 月 6 日
ms.openlocfilehash: c9fcffa8ad4dc982e869f4ccd449e1377fb1ea57
ms.sourcegitcommit: 41f2ee16badd6009bab642d68a61eaaccb91c3ec
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/17/2020
ms.locfileid: "45160284"
---
# <a name="iconvertersessionmimetomapi"></a><span data-ttu-id="206b6-103">IConverterSession::MIMEToMAPI</span><span class="sxs-lookup"><span data-stu-id="206b6-103">IConverterSession::MIMEToMAPI</span></span>

  
  
<span data-ttu-id="206b6-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="206b6-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="206b6-105">将 MIME 流转换为 MAPI 邮件。</span><span class="sxs-lookup"><span data-stu-id="206b6-105">Converts a MIME stream to a MAPI message.</span></span>
  
```cpp
HRESULT IConverterSession:: MIMEToMAPI ( 
     LPSTREAM pstm, 
     LPMESSAGE pmsg, 
     LPCSTR pszSrcSrv, 
     ULONG ulFlags 
);
```

## <a name="parameters"></a><span data-ttu-id="206b6-106">参数</span><span class="sxs-lookup"><span data-stu-id="206b6-106">Parameters</span></span>

 <span data-ttu-id="206b6-107">_pstm_</span><span class="sxs-lookup"><span data-stu-id="206b6-107">_pstm_</span></span>
  
> <span data-ttu-id="206b6-108">[in] [MIME](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx) 流的 IStream 接口。</span><span class="sxs-lookup"><span data-stu-id="206b6-108">[in] [IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx) interface to a MIME stream.</span></span> 
    
 <span data-ttu-id="206b6-109">_pmsg_</span><span class="sxs-lookup"><span data-stu-id="206b6-109">_pmsg_</span></span>
  
> <span data-ttu-id="206b6-110">[in]指向要加载的消息的指针。</span><span class="sxs-lookup"><span data-stu-id="206b6-110">[in] Pointer to the message to load.</span></span> <span data-ttu-id="206b6-111">调用方必须提供消息，以便 API 填写，因此对象必须进入 [in]。</span><span class="sxs-lookup"><span data-stu-id="206b6-111">The caller must supply a message for the API to fill out, so the object must go [in].</span></span> <span data-ttu-id="206b6-112">有关 **LPMESSAGE** 的类型定义，请参阅 mapidefs.h。</span><span class="sxs-lookup"><span data-stu-id="206b6-112">See mapidefs.h for the type definition of **LPMESSAGE**.</span></span>
    
 <span data-ttu-id="206b6-113">_pszSrcSrv_</span><span class="sxs-lookup"><span data-stu-id="206b6-113">_pszSrcSrv_</span></span>
  
> <span data-ttu-id="206b6-114">[in]此值必须为 **null**。</span><span class="sxs-lookup"><span data-stu-id="206b6-114">[in] This value must be **null**.</span></span>
    
 <span data-ttu-id="206b6-115">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="206b6-115">_ulFlags_</span></span>
  
> <span data-ttu-id="206b6-116">[in]此参数标识转换过程中要执行的任何特殊操作。</span><span class="sxs-lookup"><span data-stu-id="206b6-116">[in] This parameter identifies any special action to be taken during the conversion.</span></span> <span data-ttu-id="206b6-117">如果不执行特定 (，) 0 或以下值的组合，则它必须为零：</span><span class="sxs-lookup"><span data-stu-id="206b6-117">It must be zero (0) if no specific action is to be taken, or a combination of the following values:</span></span>
    
<span data-ttu-id="206b6-118">CCSF_EMBEDDED_MESSAGE</span><span class="sxs-lookup"><span data-stu-id="206b6-118">CCSF_EMBEDDED_MESSAGE</span></span>
  
> <span data-ttu-id="206b6-119">已发送/未发送的信息将保留于 X-Unsent 中。</span><span class="sxs-lookup"><span data-stu-id="206b6-119">Sent/unsent information is persisted in X-Unsent.</span></span>
    
<span data-ttu-id="206b6-120">CCSF_SMTP</span><span class="sxs-lookup"><span data-stu-id="206b6-120">CCSF_SMTP</span></span>
  
> <span data-ttu-id="206b6-121">MIME 流用于简单邮件传输协议 (SMTP) 邮件。</span><span class="sxs-lookup"><span data-stu-id="206b6-121">The MIME stream is for a Simple Mail Transfer Protocol (SMTP) message.</span></span>
    
<span data-ttu-id="206b6-122">CCSF_INCLUDE_BCC</span><span class="sxs-lookup"><span data-stu-id="206b6-122">CCSF_INCLUDE_BCC</span></span>
  
> <span data-ttu-id="206b6-123">MIME 流的 BCC 收件人应包含在 MAPI 邮件中。</span><span class="sxs-lookup"><span data-stu-id="206b6-123">BCC recipients of the MIME stream should be included in the MAPI message.</span></span>
    
<span data-ttu-id="206b6-124">CCSF_USE_RTF</span><span class="sxs-lookup"><span data-stu-id="206b6-124">CCSF_USE_RTF</span></span>
  
> <span data-ttu-id="206b6-125">MIME 流的 HTML 正文应在 MAPI 邮件中 (RTF 格式) RTF 格式。</span><span class="sxs-lookup"><span data-stu-id="206b6-125">The HTML body of the MIME stream should be converted to Rich Text Format (RTF) in the MAPI message.</span></span>

<span data-ttu-id="206b6-126">CCSF_GLOBAL_MESSAGE</span><span class="sxs-lookup"><span data-stu-id="206b6-126">CCSF_GLOBAL_MESSAGE</span></span>
> <span data-ttu-id="206b6-127">转换器应该将 MIME 流作为国际邮件流 (EAI/RFC6530) 。</span><span class="sxs-lookup"><span data-stu-id="206b6-127">The converter should handle the MIME stream as an international message (EAI/RFC6530).</span></span> <span data-ttu-id="206b6-128">2013 Outlook不支持。</span><span class="sxs-lookup"><span data-stu-id="206b6-128">Not supported on Outlook 2013.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="206b6-129">返回值</span><span class="sxs-lookup"><span data-stu-id="206b6-129">Return value</span></span>

<span data-ttu-id="206b6-130">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="206b6-130">E_INVALIDARG</span></span>
  
> <span data-ttu-id="206b6-131">指示 _pstm_ 为 _null、pmsg_ 为 **null** 或 _ulFlags_ 无效。 </span><span class="sxs-lookup"><span data-stu-id="206b6-131">Indicates that  _pstm_ is **null**,  _pmsg_ is **null**, or  _ulFlags_ is invalid.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="206b6-132">备注</span><span class="sxs-lookup"><span data-stu-id="206b6-132">Remarks</span></span>

<span data-ttu-id="206b6-133">如果 **已指定** CCSF_USE_RTF  _ulFlags_ 的一部分，并且目标邮件存储同时支持 HTML 和 RTF，则 MAPI 邮件将转换为 HTML 或 RTF。</span><span class="sxs-lookup"><span data-stu-id="206b6-133">If you have specified **CCSF_USE_RTF** as part of  _ulFlags_ and the destination message store supports both HTML and RTF, the MAPI message will be converted to either HTML or RTF.</span></span> <span data-ttu-id="206b6-134">如果邮件转换为 RTF，转换后的格式将压缩 RTF，任何 HTML 都将嵌入压缩的 RTF 字符串中，并且该字符串将包含在 [PidTagRtfCompressed 规范属性](pidtagrtfcompressed-canonical-property.md)中。</span><span class="sxs-lookup"><span data-stu-id="206b6-134">If the message is converted to RTF, the converted format will be compressed RTF, any HTML will be embedded in the compressed RTF string, and the string will be contained in the [PidTagRtfCompressed Canonical Property](pidtagrtfcompressed-canonical-property.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="206b6-135">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="206b6-135">MFCMAPI reference</span></span>

<span data-ttu-id="206b6-136">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="206b6-136">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="206b6-137">**文件**</span><span class="sxs-lookup"><span data-stu-id="206b6-137">**File**</span></span>|<span data-ttu-id="206b6-138">**函数**</span><span class="sxs-lookup"><span data-stu-id="206b6-138">**Function**</span></span>|<span data-ttu-id="206b6-139">**备注**</span><span class="sxs-lookup"><span data-stu-id="206b6-139">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="206b6-140">MapiMime.cpp</span><span class="sxs-lookup"><span data-stu-id="206b6-140">MapiMime.cpp</span></span>  <br/> |<span data-ttu-id="206b6-141">ImportEMLToIMessage</span><span class="sxs-lookup"><span data-stu-id="206b6-141">ImportEMLToIMessage</span></span>  <br/> |<span data-ttu-id="206b6-142">MFCMAPI 使用 MimeToMAPI 将 EML 文件转换为 MAPI 邮件。</span><span class="sxs-lookup"><span data-stu-id="206b6-142">MFCMAPI uses MimeToMAPI to convert an EML file to a MAPI message.</span></span>  <br/> |
|<span data-ttu-id="206b6-143">MapiMime.cpp</span><span class="sxs-lookup"><span data-stu-id="206b6-143">MapiMime.cpp</span></span>  <br/> |<span data-ttu-id="206b6-144">ExportIMessageToEML</span><span class="sxs-lookup"><span data-stu-id="206b6-144">ExportIMessageToEML</span></span>  <br/> |<span data-ttu-id="206b6-145">MFCMAPI 使用 MAPIToMIMEStm 将 MAPI 邮件转换为 EML 文件。</span><span class="sxs-lookup"><span data-stu-id="206b6-145">MFCMAPI uses MAPIToMIMEStm to convert a MAPI message to an EML file.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="206b6-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="206b6-146">See also</span></span>



[<span data-ttu-id="206b6-147">IConverterSession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="206b6-147">IConverterSession : IUnknown</span></span>](iconvertersessioniunknown.md)
  
[<span data-ttu-id="206b6-148">IConverterSession::MAPIToMIMEStm</span><span class="sxs-lookup"><span data-stu-id="206b6-148">IConverterSession::MAPIToMIMEStm</span></span>](iconvertersession-mapitomimestm.md)
  
[<span data-ttu-id="206b6-149">IConverterSession::SetAdrBook</span><span class="sxs-lookup"><span data-stu-id="206b6-149">IConverterSession::SetAdrBook</span></span>](iconvertersession-setadrbook.md)
  
[<span data-ttu-id="206b6-150">IConverterSession::SetCharSet</span><span class="sxs-lookup"><span data-stu-id="206b6-150">IConverterSession::SetCharSet</span></span>](iconvertersession-setcharset.md)
  
[<span data-ttu-id="206b6-151">IConverterSession::SetEncoding</span><span class="sxs-lookup"><span data-stu-id="206b6-151">IConverterSession::SetEncoding</span></span>](iconvertersession-setencoding.md)
  
[<span data-ttu-id="206b6-152">IConverterSession::SetSaveFormat</span><span class="sxs-lookup"><span data-stu-id="206b6-152">IConverterSession::SetSaveFormat</span></span>](iconvertersession-setsaveformat.md)
  
[<span data-ttu-id="206b6-153">IConverterSession::SetTextWrapping</span><span class="sxs-lookup"><span data-stu-id="206b6-153">IConverterSession::SetTextWrapping</span></span>](iconvertersession-settextwrapping.md)


[<span data-ttu-id="206b6-154">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="206b6-154">MAPI Constants</span></span>](mapi-constants.md)

