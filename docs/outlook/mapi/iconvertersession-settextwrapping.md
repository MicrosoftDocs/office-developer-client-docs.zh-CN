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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a89f6dd14e8bbea9d0d4145dc05bf332af95234a
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22573628"
---
# <a name="iconvertersessionsettextwrapping"></a><span data-ttu-id="ae656-103">IConverterSession::SetTextWrapping</span><span class="sxs-lookup"><span data-stu-id="ae656-103">IConverterSession::SetTextWrapping</span></span>

  
  
<span data-ttu-id="ae656-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ae656-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ae656-105">设置的文字环绕转换器将返回在[IConverterSession::MAPIToMIMEStm](iconvertersession-mapitomimestm.md)MIME 流宽度。</span><span class="sxs-lookup"><span data-stu-id="ae656-105">Sets the text wrapping width for a MIME stream that the converter will return in [IConverterSession::MAPIToMIMEStm](iconvertersession-mapitomimestm.md).</span></span>
  
```cpp
HRESULT IConverterSession::SetTextWrapping ( 
    BOOL    fWrapText, 
    ULONG   ulWrapWidth 
);
```

## <a name="parameters"></a><span data-ttu-id="ae656-106">参数</span><span class="sxs-lookup"><span data-stu-id="ae656-106">Parameters</span></span>

 <span data-ttu-id="ae656-107">*fWrapText*</span><span class="sxs-lookup"><span data-stu-id="ae656-107">*fWrapText*</span></span> 
  
> <span data-ttu-id="ae656-108">[in]是否换行文本。</span><span class="sxs-lookup"><span data-stu-id="ae656-108">[in] Whether to wrap text or not.</span></span>
    
 <span data-ttu-id="ae656-109">*ulWrapWidth*</span><span class="sxs-lookup"><span data-stu-id="ae656-109">*ulWrapWidth*</span></span> 
  
> <span data-ttu-id="ae656-110">[in]文字环绕要使用的宽度。</span><span class="sxs-lookup"><span data-stu-id="ae656-110">[in] The text wrapping width to use.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="ae656-111">返回值</span><span class="sxs-lookup"><span data-stu-id="ae656-111">Return value</span></span>

<span data-ttu-id="ae656-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="ae656-112">S_OK</span></span>
  
> <span data-ttu-id="ae656-113">呼叫成功。</span><span class="sxs-lookup"><span data-stu-id="ae656-113">The call was successful.</span></span>
    
## <a name="mfcmapi-reference"></a><span data-ttu-id="ae656-114">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="ae656-114">MFCMAPI reference</span></span>

<span data-ttu-id="ae656-115">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="ae656-115">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="ae656-116">**文件**</span><span class="sxs-lookup"><span data-stu-id="ae656-116">**File**</span></span>|<span data-ttu-id="ae656-117">**函数**</span><span class="sxs-lookup"><span data-stu-id="ae656-117">**Function**</span></span>|<span data-ttu-id="ae656-118">**Comment**</span><span class="sxs-lookup"><span data-stu-id="ae656-118">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ae656-119">MapiMime.cpp</span><span class="sxs-lookup"><span data-stu-id="ae656-119">MapiMime.cpp</span></span>  <br/> |<span data-ttu-id="ae656-120">ImportEMLToIMessage</span><span class="sxs-lookup"><span data-stu-id="ae656-120">ImportEMLToIMessage</span></span>  <br/> |<span data-ttu-id="ae656-121">MFCMAPI 使用 MimeToMAPI 将 EML 文件转换为 MAPI 邮件。</span><span class="sxs-lookup"><span data-stu-id="ae656-121">MFCMAPI uses MimeToMAPI to convert an EML file to a MAPI message.</span></span>  <br/> |
|<span data-ttu-id="ae656-122">MapiMime.cpp</span><span class="sxs-lookup"><span data-stu-id="ae656-122">MapiMime.cpp</span></span>  <br/> |<span data-ttu-id="ae656-123">ExportIMessageToEML</span><span class="sxs-lookup"><span data-stu-id="ae656-123">ExportIMessageToEML</span></span>  <br/> |<span data-ttu-id="ae656-124">MFCMAPI 使用 MAPIToMIMEStm 将转换为 EML 文件的 MAPI 邮件。</span><span class="sxs-lookup"><span data-stu-id="ae656-124">MFCMAPI uses MAPIToMIMEStm to convert a MAPI message to an EML file.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="ae656-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ae656-125">See also</span></span>



[<span data-ttu-id="ae656-126">IConverterSession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="ae656-126">IConverterSession : IUnknown</span></span>](iconvertersessioniunknown.md)
  
[<span data-ttu-id="ae656-127">IConverterSession::MAPIToMIMEStm</span><span class="sxs-lookup"><span data-stu-id="ae656-127">IConverterSession::MAPIToMIMEStm</span></span>](iconvertersession-mapitomimestm.md)
  
[<span data-ttu-id="ae656-128">IConverterSession::MIMEToMAPI</span><span class="sxs-lookup"><span data-stu-id="ae656-128">IConverterSession::MIMEToMAPI</span></span>](iconvertersession-mimetomapi.md)
  
[<span data-ttu-id="ae656-129">IConverterSession::SetAdrBook</span><span class="sxs-lookup"><span data-stu-id="ae656-129">IConverterSession::SetAdrBook</span></span>](iconvertersession-setadrbook.md)
  
[<span data-ttu-id="ae656-130">IConverterSession::SetCharSet</span><span class="sxs-lookup"><span data-stu-id="ae656-130">IConverterSession::SetCharSet</span></span>](iconvertersession-setcharset.md)
  
[<span data-ttu-id="ae656-131">IConverterSession::SetEncoding</span><span class="sxs-lookup"><span data-stu-id="ae656-131">IConverterSession::SetEncoding</span></span>](iconvertersession-setencoding.md)
  
[<span data-ttu-id="ae656-132">IConverterSession::SetSaveFormat</span><span class="sxs-lookup"><span data-stu-id="ae656-132">IConverterSession::SetSaveFormat</span></span>](iconvertersession-setsaveformat.md)


[<span data-ttu-id="ae656-133">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="ae656-133">MAPI Constants</span></span>](mapi-constants.md)

