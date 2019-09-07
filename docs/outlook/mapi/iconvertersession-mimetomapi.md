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
description: 上次修改时间：2019年9月6日
ms.openlocfilehash: f6f671cbfd5e14d602aaa31d31e54e859f068593
ms.sourcegitcommit: 27a9f3568318470e7ee09ad93a90c3f80d3ef0cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "36790769"
---
# <a name="iconvertersessionmimetomapi"></a><span data-ttu-id="dd110-103">IConverterSession::MIMEToMAPI</span><span class="sxs-lookup"><span data-stu-id="dd110-103">IConverterSession::MIMEToMAPI</span></span>

  
  
<span data-ttu-id="dd110-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="dd110-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="dd110-105">将 MIME 流转换为 MAPI 邮件。</span><span class="sxs-lookup"><span data-stu-id="dd110-105">Converts a MIME stream to a MAPI message.</span></span>
  
```cpp
HRESULT IConverterSession:: MIMEToMAPI ( 
     LPSTREAM pstm, 
     LPMESSAGE pmsg, 
     LPCSTR pszSrcSrv, 
     ULONG ulFlags 
);
```

## <a name="parameters"></a><span data-ttu-id="dd110-106">参数</span><span class="sxs-lookup"><span data-stu-id="dd110-106">Parameters</span></span>

 <span data-ttu-id="dd110-107">_pstm_</span><span class="sxs-lookup"><span data-stu-id="dd110-107">_pstm_</span></span>
  
> <span data-ttu-id="dd110-108">实时MIME 流的[IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx)接口。</span><span class="sxs-lookup"><span data-stu-id="dd110-108">[in] [IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx) interface to a MIME stream.</span></span> 
    
 <span data-ttu-id="dd110-109">_pmsg_</span><span class="sxs-lookup"><span data-stu-id="dd110-109">_pmsg_</span></span>
  
> <span data-ttu-id="dd110-110">实时指向要加载的邮件的指针。</span><span class="sxs-lookup"><span data-stu-id="dd110-110">[in] Pointer to the message to load.</span></span> <span data-ttu-id="dd110-111">调用方必须提供一条消息，以便 API 填写，以便该对象必须进入 [in]。</span><span class="sxs-lookup"><span data-stu-id="dd110-111">The caller must supply a message for the API to fill out, so the object must go [in].</span></span> <span data-ttu-id="dd110-112">有关**LPMESSAGE**的类型定义，请参阅 mapidefs.h。</span><span class="sxs-lookup"><span data-stu-id="dd110-112">See mapidefs.h for the type definition of **LPMESSAGE**.</span></span>
    
 <span data-ttu-id="dd110-113">_pszSrcSrv_</span><span class="sxs-lookup"><span data-stu-id="dd110-113">_pszSrcSrv_</span></span>
  
> <span data-ttu-id="dd110-114">实时此值必须为**null**。</span><span class="sxs-lookup"><span data-stu-id="dd110-114">[in] This value must be **null**.</span></span>
    
 <span data-ttu-id="dd110-115">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="dd110-115">_ulFlags_</span></span>
  
> <span data-ttu-id="dd110-116">实时此参数标识在转换过程中要采取的任何特殊操作。</span><span class="sxs-lookup"><span data-stu-id="dd110-116">[in] This parameter identifies any special action to be taken during the conversion.</span></span> <span data-ttu-id="dd110-117">如果不执行任何特定操作，则必须为零（0），或以下值的组合：</span><span class="sxs-lookup"><span data-stu-id="dd110-117">It must be zero (0) if no specific action is to be taken, or a combination of the following values:</span></span>
    
<span data-ttu-id="dd110-118">CCSF_EMBEDDED_MESSAGE</span><span class="sxs-lookup"><span data-stu-id="dd110-118">CCSF_EMBEDDED_MESSAGE</span></span>
  
> <span data-ttu-id="dd110-119">发送/发送的信息将保留在 X-未发送中。</span><span class="sxs-lookup"><span data-stu-id="dd110-119">Sent/unsent information is persisted in X-Unsent.</span></span>
    
<span data-ttu-id="dd110-120">CCSF_SMTP</span><span class="sxs-lookup"><span data-stu-id="dd110-120">CCSF_SMTP</span></span>
  
> <span data-ttu-id="dd110-121">MIME 流适用于简单 MAPI 传输协议（SMTP）邮件。</span><span class="sxs-lookup"><span data-stu-id="dd110-121">The MIME stream is for a Simple MAPI Transfer Protocol (SMTP) message.</span></span>
    
<span data-ttu-id="dd110-122">CCSF_INCLUDE_BCC</span><span class="sxs-lookup"><span data-stu-id="dd110-122">CCSF_INCLUDE_BCC</span></span>
  
> <span data-ttu-id="dd110-123">MIME 流的密件抄送收件人应包含在 MAPI 邮件中。</span><span class="sxs-lookup"><span data-stu-id="dd110-123">BCC recipients of the MIME stream should be included in the MAPI message.</span></span>
    
<span data-ttu-id="dd110-124">CCSF_USE_RTF</span><span class="sxs-lookup"><span data-stu-id="dd110-124">CCSF_USE_RTF</span></span>
  
> <span data-ttu-id="dd110-125">MIME 流的 HTML 正文应转换为 MAPI 邮件中的格式文本格式（RTF）。</span><span class="sxs-lookup"><span data-stu-id="dd110-125">The HTML body of the MIME stream should be converted to Rich Text Format (RTF) in the MAPI message.</span></span>

<span data-ttu-id="dd110-126">CCSF_GLOBAL_MESSAGE</span><span class="sxs-lookup"><span data-stu-id="dd110-126">CCSF_GLOBAL_MESSAGE</span></span>
> <span data-ttu-id="dd110-127">转换器应将 MIME 流处理为国际邮件（EAI/RFC6530）。</span><span class="sxs-lookup"><span data-stu-id="dd110-127">The converter should handle the MIME stream as an international message (EAI/RFC6530).</span></span> <span data-ttu-id="dd110-128">在 Outlook 2013 中不受支持。</span><span class="sxs-lookup"><span data-stu-id="dd110-128">Not supported on Outlook 2013.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="dd110-129">返回值</span><span class="sxs-lookup"><span data-stu-id="dd110-129">Return value</span></span>

<span data-ttu-id="dd110-130">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="dd110-130">E_INVALIDARG</span></span>
  
> <span data-ttu-id="dd110-131">指示_pstm_为**null**、 _pmsg_为**null**或_ulFlags_无效。</span><span class="sxs-lookup"><span data-stu-id="dd110-131">Indicates that  _pstm_ is **null**,  _pmsg_ is **null**, or  _ulFlags_ is invalid.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="dd110-132">说明</span><span class="sxs-lookup"><span data-stu-id="dd110-132">Remarks</span></span>

<span data-ttu-id="dd110-133">如果已将**CCSF_USE_RTF**指定为_ulFlags_的一部分，且目标邮件存储库同时支持 html 和 RTF 格式，则 MAPI 邮件将转换为 html 或 rtf 格式。</span><span class="sxs-lookup"><span data-stu-id="dd110-133">If you have specified **CCSF_USE_RTF** as part of  _ulFlags_ and the destination message store supports both HTML and RTF, the MAPI message will be converted to either HTML or RTF.</span></span> <span data-ttu-id="dd110-134">如果邮件转换为 RTF 格式，则转换后的格式将被压缩为 RTF 格式，任何 HTML 将嵌入在压缩的 RTF 字符串中，并且该字符串将包含在[PidTagRtfCompressed 规范属性](pidtagrtfcompressed-canonical-property.md)中。</span><span class="sxs-lookup"><span data-stu-id="dd110-134">If the message is converted to RTF, the converted format will be compressed RTF, any HTML will be embedded in the compressed RTF string, and the string will be contained in the [PidTagRtfCompressed Canonical Property](pidtagrtfcompressed-canonical-property.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="dd110-135">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="dd110-135">MFCMAPI reference</span></span>

<span data-ttu-id="dd110-136">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="dd110-136">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="dd110-137">**文件**</span><span class="sxs-lookup"><span data-stu-id="dd110-137">**File**</span></span>|<span data-ttu-id="dd110-138">**函数**</span><span class="sxs-lookup"><span data-stu-id="dd110-138">**Function**</span></span>|<span data-ttu-id="dd110-139">**备注**</span><span class="sxs-lookup"><span data-stu-id="dd110-139">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="dd110-140">MapiMime</span><span class="sxs-lookup"><span data-stu-id="dd110-140">MapiMime.cpp</span></span>  <br/> |<span data-ttu-id="dd110-141">ImportEMLToIMessage</span><span class="sxs-lookup"><span data-stu-id="dd110-141">ImportEMLToIMessage</span></span>  <br/> |<span data-ttu-id="dd110-142">MFCMAPI 使用 MimeToMAPI 将 .EML 文件转换为 MAPI 邮件。</span><span class="sxs-lookup"><span data-stu-id="dd110-142">MFCMAPI uses MimeToMAPI to convert an EML file to a MAPI message.</span></span>  <br/> |
|<span data-ttu-id="dd110-143">MapiMime</span><span class="sxs-lookup"><span data-stu-id="dd110-143">MapiMime.cpp</span></span>  <br/> |<span data-ttu-id="dd110-144">ExportIMessageToEML</span><span class="sxs-lookup"><span data-stu-id="dd110-144">ExportIMessageToEML</span></span>  <br/> |<span data-ttu-id="dd110-145">MFCMAPI 使用 MAPIToMIMEStm 将 MAPI 邮件转换为 .EML 文件。</span><span class="sxs-lookup"><span data-stu-id="dd110-145">MFCMAPI uses MAPIToMIMEStm to convert a MAPI message to an EML file.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="dd110-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dd110-146">See also</span></span>



[<span data-ttu-id="dd110-147">IConverterSession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="dd110-147">IConverterSession : IUnknown</span></span>](iconvertersessioniunknown.md)
  
[<span data-ttu-id="dd110-148">IConverterSession::MAPIToMIMEStm</span><span class="sxs-lookup"><span data-stu-id="dd110-148">IConverterSession::MAPIToMIMEStm</span></span>](iconvertersession-mapitomimestm.md)
  
[<span data-ttu-id="dd110-149">IConverterSession::SetAdrBook</span><span class="sxs-lookup"><span data-stu-id="dd110-149">IConverterSession::SetAdrBook</span></span>](iconvertersession-setadrbook.md)
  
[<span data-ttu-id="dd110-150">IConverterSession::SetCharSet</span><span class="sxs-lookup"><span data-stu-id="dd110-150">IConverterSession::SetCharSet</span></span>](iconvertersession-setcharset.md)
  
[<span data-ttu-id="dd110-151">IConverterSession::SetEncoding</span><span class="sxs-lookup"><span data-stu-id="dd110-151">IConverterSession::SetEncoding</span></span>](iconvertersession-setencoding.md)
  
[<span data-ttu-id="dd110-152">IConverterSession::SetSaveFormat</span><span class="sxs-lookup"><span data-stu-id="dd110-152">IConverterSession::SetSaveFormat</span></span>](iconvertersession-setsaveformat.md)
  
[<span data-ttu-id="dd110-153">IConverterSession::SetTextWrapping</span><span class="sxs-lookup"><span data-stu-id="dd110-153">IConverterSession::SetTextWrapping</span></span>](iconvertersession-settextwrapping.md)


[<span data-ttu-id="dd110-154">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="dd110-154">MAPI Constants</span></span>](mapi-constants.md)

