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
ms.openlocfilehash: 356f4470be26ae3803a53af1cec34b3ac6eb0cc9
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326927"
---
# <a name="iconvertersessionmimetomapi"></a><span data-ttu-id="39668-103">IConverterSession::MIMEToMAPI</span><span class="sxs-lookup"><span data-stu-id="39668-103">IConverterSession::MIMEToMAPI</span></span>

  
  
<span data-ttu-id="39668-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="39668-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="39668-105">将 MIME 流转换为 MAPI 邮件。</span><span class="sxs-lookup"><span data-stu-id="39668-105">Converts a MIME stream to a MAPI message.</span></span>
  
```cpp
HRESULT IConverterSession:: MIMEToMAPI ( 
     LPSTREAM pstm, 
     LPMESSAGE pmsg, 
     LPCSTR pszSrcSrv, 
     ULONG ulFlags 
);
```

## <a name="parameters"></a><span data-ttu-id="39668-106">参数</span><span class="sxs-lookup"><span data-stu-id="39668-106">Parameters</span></span>

 <span data-ttu-id="39668-107">_pstm_</span><span class="sxs-lookup"><span data-stu-id="39668-107">_pstm_</span></span>
  
> <span data-ttu-id="39668-108">实时MIME 流的[IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx)接口。</span><span class="sxs-lookup"><span data-stu-id="39668-108">[in] [IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx) interface to a MIME stream.</span></span> 
    
 <span data-ttu-id="39668-109">_pmsg_</span><span class="sxs-lookup"><span data-stu-id="39668-109">_pmsg_</span></span>
  
> <span data-ttu-id="39668-110">排除指向要加载的邮件的指针。</span><span class="sxs-lookup"><span data-stu-id="39668-110">[out] Pointer to the message to load.</span></span> <span data-ttu-id="39668-111">有关**LPMESSAGE**的类型定义, 请参阅 mapidefs.h。</span><span class="sxs-lookup"><span data-stu-id="39668-111">See mapidefs.h for the type definition of **LPMESSAGE**.</span></span>
    
 <span data-ttu-id="39668-112">_pszSrcSrv_</span><span class="sxs-lookup"><span data-stu-id="39668-112">_pszSrcSrv_</span></span>
  
> <span data-ttu-id="39668-113">实时此值必须为**null**。</span><span class="sxs-lookup"><span data-stu-id="39668-113">[in] This value must be **null**.</span></span>
    
 <span data-ttu-id="39668-114">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="39668-114">_ulFlags_</span></span>
  
> <span data-ttu-id="39668-115">实时此参数标识在转换过程中要采取的任何特殊操作。</span><span class="sxs-lookup"><span data-stu-id="39668-115">[in] This parameter identifies any special action to be taken during the conversion.</span></span> <span data-ttu-id="39668-116">如果不执行任何特定操作, 则必须为零 (0), 或以下值的组合:</span><span class="sxs-lookup"><span data-stu-id="39668-116">It must be zero (0) if no specific action is to be taken, or a combination of the following values:</span></span>
    
<span data-ttu-id="39668-117">CCSF_EMBEDDED_MESSAGE</span><span class="sxs-lookup"><span data-stu-id="39668-117">CCSF_EMBEDDED_MESSAGE</span></span>
  
> <span data-ttu-id="39668-118">发送/发送的信息将保留在 X-未发送中。</span><span class="sxs-lookup"><span data-stu-id="39668-118">Sent/unsent information is persisted in X-Unsent.</span></span>
    
<span data-ttu-id="39668-119">CCSF_SMTP</span><span class="sxs-lookup"><span data-stu-id="39668-119">CCSF_SMTP</span></span>
  
> <span data-ttu-id="39668-120">MIME 流适用于简单 MAPI 传输协议 (SMTP) 邮件。</span><span class="sxs-lookup"><span data-stu-id="39668-120">The MIME stream is for a Simple MAPI Transfer Protocol (SMTP) message.</span></span>
    
<span data-ttu-id="39668-121">CCSF_INCLUDE_BCC</span><span class="sxs-lookup"><span data-stu-id="39668-121">CCSF_INCLUDE_BCC</span></span>
  
> <span data-ttu-id="39668-122">MIME 流的密件抄送收件人应包含在 MAPI 邮件中。</span><span class="sxs-lookup"><span data-stu-id="39668-122">BCC recipients of the MIME stream should be included in the MAPI message.</span></span>
    
<span data-ttu-id="39668-123">CCSF_USE_RTF</span><span class="sxs-lookup"><span data-stu-id="39668-123">CCSF_USE_RTF</span></span>
  
> <span data-ttu-id="39668-124">MIME 流的 HTML 正文应转换为 MAPI 邮件中的格式文本格式 (rtf)。</span><span class="sxs-lookup"><span data-stu-id="39668-124">The HTML body of the MIME stream should be converted to Rich Text Format (RTF) in the MAPI message.</span></span>

<span data-ttu-id="39668-125">CCSF_GLOBAL_MESSAGE</span><span class="sxs-lookup"><span data-stu-id="39668-125">CCSF_GLOBAL_MESSAGE</span></span>
> <span data-ttu-id="39668-126">转换器应将 MIME 流处理为国际邮件 (EAI/RFC6530)。</span><span class="sxs-lookup"><span data-stu-id="39668-126">The converter should handle the MIME stream as an international message (EAI/RFC6530).</span></span> <span data-ttu-id="39668-127">在 Outlook 2013 中不受支持。</span><span class="sxs-lookup"><span data-stu-id="39668-127">Not supported on Outlook 2013.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="39668-128">返回值</span><span class="sxs-lookup"><span data-stu-id="39668-128">Return value</span></span>

<span data-ttu-id="39668-129">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="39668-129">E_INVALIDARG</span></span>
  
> <span data-ttu-id="39668-130">指示_pstm_为**null**、 _pmsg_为**null**或_ulFlags_无效。</span><span class="sxs-lookup"><span data-stu-id="39668-130">Indicates that  _pstm_ is **null**,  _pmsg_ is **null**, or  _ulFlags_ is invalid.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="39668-131">注解</span><span class="sxs-lookup"><span data-stu-id="39668-131">Remarks</span></span>

<span data-ttu-id="39668-132">如果已将**CCSF_USE_RTF**指定为_ulFlags_的一部分, 且目标邮件存储库同时支持 html 和 rtf 格式, 则 MAPI 邮件将转换为 html 或 rtf 格式。</span><span class="sxs-lookup"><span data-stu-id="39668-132">If you have specified **CCSF_USE_RTF** as part of  _ulFlags_ and the destination message store supports both HTML and RTF, the MAPI message will be converted to either HTML or RTF.</span></span> <span data-ttu-id="39668-133">如果邮件转换为 rtf 格式, 则转换后的格式将被压缩为 rtf 格式, 任何 HTML 将嵌入在压缩的 RTF 字符串中, 并且该字符串将包含在[PidTagRtfCompressed 规范属性](pidtagrtfcompressed-canonical-property.md)中。</span><span class="sxs-lookup"><span data-stu-id="39668-133">If the message is converted to RTF, the converted format will be compressed RTF, any HTML will be embedded in the compressed RTF string, and the string will be contained in the [PidTagRtfCompressed Canonical Property](pidtagrtfcompressed-canonical-property.md).</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="39668-134">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="39668-134">MFCMAPI reference</span></span>

<span data-ttu-id="39668-135">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="39668-135">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="39668-136">**文件**</span><span class="sxs-lookup"><span data-stu-id="39668-136">**File**</span></span>|<span data-ttu-id="39668-137">**函数**</span><span class="sxs-lookup"><span data-stu-id="39668-137">**Function**</span></span>|<span data-ttu-id="39668-138">**备注**</span><span class="sxs-lookup"><span data-stu-id="39668-138">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="39668-139">MapiMime</span><span class="sxs-lookup"><span data-stu-id="39668-139">MapiMime.cpp</span></span>  <br/> |<span data-ttu-id="39668-140">ImportEMLToIMessage</span><span class="sxs-lookup"><span data-stu-id="39668-140">ImportEMLToIMessage</span></span>  <br/> |<span data-ttu-id="39668-141">MFCMAPI 使用 MimeToMAPI 将 .eml 文件转换为 MAPI 邮件。</span><span class="sxs-lookup"><span data-stu-id="39668-141">MFCMAPI uses MimeToMAPI to convert an EML file to a MAPI message.</span></span>  <br/> |
|<span data-ttu-id="39668-142">MapiMime</span><span class="sxs-lookup"><span data-stu-id="39668-142">MapiMime.cpp</span></span>  <br/> |<span data-ttu-id="39668-143">ExportIMessageToEML</span><span class="sxs-lookup"><span data-stu-id="39668-143">ExportIMessageToEML</span></span>  <br/> |<span data-ttu-id="39668-144">MFCMAPI 使用 MAPIToMIMEStm 将 MAPI 邮件转换为 .eml 文件。</span><span class="sxs-lookup"><span data-stu-id="39668-144">MFCMAPI uses MAPIToMIMEStm to convert a MAPI message to an EML file.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="39668-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="39668-145">See also</span></span>



[<span data-ttu-id="39668-146">IConverterSession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="39668-146">IConverterSession : IUnknown</span></span>](iconvertersessioniunknown.md)
  
[<span data-ttu-id="39668-147">IConverterSession::MAPIToMIMEStm</span><span class="sxs-lookup"><span data-stu-id="39668-147">IConverterSession::MAPIToMIMEStm</span></span>](iconvertersession-mapitomimestm.md)
  
[<span data-ttu-id="39668-148">IConverterSession::SetAdrBook</span><span class="sxs-lookup"><span data-stu-id="39668-148">IConverterSession::SetAdrBook</span></span>](iconvertersession-setadrbook.md)
  
[<span data-ttu-id="39668-149">IConverterSession::SetCharSet</span><span class="sxs-lookup"><span data-stu-id="39668-149">IConverterSession::SetCharSet</span></span>](iconvertersession-setcharset.md)
  
[<span data-ttu-id="39668-150">IConverterSession::SetEncoding</span><span class="sxs-lookup"><span data-stu-id="39668-150">IConverterSession::SetEncoding</span></span>](iconvertersession-setencoding.md)
  
[<span data-ttu-id="39668-151">IConverterSession::SetSaveFormat</span><span class="sxs-lookup"><span data-stu-id="39668-151">IConverterSession::SetSaveFormat</span></span>](iconvertersession-setsaveformat.md)
  
[<span data-ttu-id="39668-152">IConverterSession::SetTextWrapping</span><span class="sxs-lookup"><span data-stu-id="39668-152">IConverterSession::SetTextWrapping</span></span>](iconvertersession-settextwrapping.md)


[<span data-ttu-id="39668-153">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="39668-153">MAPI Constants</span></span>](mapi-constants.md)

