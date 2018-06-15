---
title: IConverterSessionSetTextWrapping
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IConverterSession.SetTextWrapping
api_type:
- COM
ms.assetid: 8674b288-43a3-6376-35ca-9dbaa3a1851e
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 81771a263a7496042d4950b465c0d5b03290399b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/15/2018
ms.locfileid: "19775287"
---
# <a name="iconvertersessionsettextwrapping"></a><span data-ttu-id="6ace6-103">IConverterSession::SetTextWrapping</span><span class="sxs-lookup"><span data-stu-id="6ace6-103">IConverterSession::SetTextWrapping</span></span>

  
  
<span data-ttu-id="6ace6-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="6ace6-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="6ace6-105">设置的文字环绕转换器将返回在[IConverterSession::MAPIToMIMEStm](iconvertersession-mapitomimestm.md)MIME 流宽度。</span><span class="sxs-lookup"><span data-stu-id="6ace6-105">Sets the text wrapping width for a MIME stream that the converter will return in [IConverterSession::MAPIToMIMEStm](iconvertersession-mapitomimestm.md).</span></span>
  
```cpp
HRESULT IConverterSession::SetTextWrapping ( 
    BOOL    fWrapText, 
    ULONG   ulWrapWidth 
);
```

## <a name="parameters"></a><span data-ttu-id="6ace6-106">参数</span><span class="sxs-lookup"><span data-stu-id="6ace6-106">Parameters</span></span>

 <span data-ttu-id="6ace6-107">*fWrapText*</span><span class="sxs-lookup"><span data-stu-id="6ace6-107">*fWrapText*</span></span> 
  
> <span data-ttu-id="6ace6-108">[in]是否换行文本。</span><span class="sxs-lookup"><span data-stu-id="6ace6-108">[in] Whether to wrap text or not.</span></span>
    
 <span data-ttu-id="6ace6-109">*ulWrapWidth*</span><span class="sxs-lookup"><span data-stu-id="6ace6-109">*ulWrapWidth*</span></span> 
  
> <span data-ttu-id="6ace6-110">[in]文字环绕要使用的宽度。</span><span class="sxs-lookup"><span data-stu-id="6ace6-110">[in] The text wrapping width to use.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="6ace6-111">返回值</span><span class="sxs-lookup"><span data-stu-id="6ace6-111">Return value</span></span>

<span data-ttu-id="6ace6-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="6ace6-112">S_OK</span></span>
  
> <span data-ttu-id="6ace6-113">呼叫成功。</span><span class="sxs-lookup"><span data-stu-id="6ace6-113">The call was successful.</span></span>
    
## <a name="mfcmapi-reference"></a><span data-ttu-id="6ace6-114">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="6ace6-114">MFCMAPI reference</span></span>

<span data-ttu-id="6ace6-115">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="6ace6-115">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="6ace6-116">**文件**</span><span class="sxs-lookup"><span data-stu-id="6ace6-116">**File**</span></span>|<span data-ttu-id="6ace6-117">**函数**</span><span class="sxs-lookup"><span data-stu-id="6ace6-117">**Function**</span></span>|<span data-ttu-id="6ace6-118">**Comment**</span><span class="sxs-lookup"><span data-stu-id="6ace6-118">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6ace6-119">MapiMime.cpp</span><span class="sxs-lookup"><span data-stu-id="6ace6-119">MapiMime.cpp</span></span>  <br/> |<span data-ttu-id="6ace6-120">ImportEMLToIMessage</span><span class="sxs-lookup"><span data-stu-id="6ace6-120">ImportEMLToIMessage</span></span>  <br/> |<span data-ttu-id="6ace6-121">MFCMAPI 使用 MimeToMAPI 将 EML 文件转换为 MAPI 邮件。</span><span class="sxs-lookup"><span data-stu-id="6ace6-121">MFCMAPI uses MimeToMAPI to convert an EML file to a MAPI message.</span></span>  <br/> |
|<span data-ttu-id="6ace6-122">MapiMime.cpp</span><span class="sxs-lookup"><span data-stu-id="6ace6-122">MapiMime.cpp</span></span>  <br/> |<span data-ttu-id="6ace6-123">ExportIMessageToEML</span><span class="sxs-lookup"><span data-stu-id="6ace6-123">ExportIMessageToEML</span></span>  <br/> |<span data-ttu-id="6ace6-124">MFCMAPI 使用 MAPIToMIMEStm 将转换为 EML 文件的 MAPI 邮件。</span><span class="sxs-lookup"><span data-stu-id="6ace6-124">MFCMAPI uses MAPIToMIMEStm to convert a MAPI message to an EML file.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="6ace6-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6ace6-125">See also</span></span>



[<span data-ttu-id="6ace6-126">IConverterSession: IUnknown</span><span class="sxs-lookup"><span data-stu-id="6ace6-126">IConverterSession : IUnknown</span></span>](iconvertersessioniunknown.md)
  
[<span data-ttu-id="6ace6-127">IConverterSession::MAPIToMIMEStm</span><span class="sxs-lookup"><span data-stu-id="6ace6-127">IConverterSession::MAPIToMIMEStm</span></span>](iconvertersession-mapitomimestm.md)
  
[<span data-ttu-id="6ace6-128">IConverterSession::MIMEToMAPI</span><span class="sxs-lookup"><span data-stu-id="6ace6-128">IConverterSession::MIMEToMAPI</span></span>](iconvertersession-mimetomapi.md)
  
[<span data-ttu-id="6ace6-129">IConverterSession::SetAdrBook</span><span class="sxs-lookup"><span data-stu-id="6ace6-129">IConverterSession::SetAdrBook</span></span>](iconvertersession-setadrbook.md)
  
[<span data-ttu-id="6ace6-130">IConverterSession::SetCharSet</span><span class="sxs-lookup"><span data-stu-id="6ace6-130">IConverterSession::SetCharSet</span></span>](iconvertersession-setcharset.md)
  
[<span data-ttu-id="6ace6-131">IConverterSession::SetEncoding</span><span class="sxs-lookup"><span data-stu-id="6ace6-131">IConverterSession::SetEncoding</span></span>](iconvertersession-setencoding.md)
  
[<span data-ttu-id="6ace6-132">IConverterSession::SetSaveFormat</span><span class="sxs-lookup"><span data-stu-id="6ace6-132">IConverterSession::SetSaveFormat</span></span>](iconvertersession-setsaveformat.md)


[<span data-ttu-id="6ace6-133">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="6ace6-133">MAPI Constants</span></span>](mapi-constants.md)

