---
title: IConverterSessionSetCharSet
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IConverterSession.SetCharSet
api_type:
- COM
ms.assetid: 25af3683-3a65-2d39-6f6e-76c8d36f866d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 69023d2c13037fb52a4d1dc4f7376efbd839aebc
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22581697"
---
# <a name="iconvertersessionsetcharset"></a><span data-ttu-id="881ad-103">IConverterSession::SetCharSet</span><span class="sxs-lookup"><span data-stu-id="881ad-103">IConverterSession::SetCharSet</span></span>

  
  
<span data-ttu-id="881ad-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="881ad-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="881ad-105">指定一个可选的字符的 MAPI 时设置为 MIME 转换器使用将 MAPI 邮件转换为 MIME 流。</span><span class="sxs-lookup"><span data-stu-id="881ad-105">Specifies an optional character set that the MAPI to MIME converter use when converting a MAPI message to a MIME stream.</span></span>
  
```cpp
HRESULT SetCharset( 
     BOOL fApply, 
     HCHARSET hcharset, 
     CSETAPPLYTYPE csetapplytype); 
```

## <a name="parameters"></a><span data-ttu-id="881ad-106">参数</span><span class="sxs-lookup"><span data-stu-id="881ad-106">Parameters</span></span>

 <span data-ttu-id="881ad-107">_fApply_</span><span class="sxs-lookup"><span data-stu-id="881ad-107">_fApply_</span></span>
  
> <span data-ttu-id="881ad-108">[in]指示是否使用转换为特定字符集。</span><span class="sxs-lookup"><span data-stu-id="881ad-108">[in] Indicates whether to use a specific character set for the conversion.</span></span> <span data-ttu-id="881ad-109">此参数设置为**true**可应用后续转换中的字符集。</span><span class="sxs-lookup"><span data-stu-id="881ad-109">Set this parameter to **true** to apply the character set in subsequent conversions.</span></span> <span data-ttu-id="881ad-110">如果您不再希望应用任何特定的字符集，并返回到后续的消息的默认值，请将此参数设置为**false** 。</span><span class="sxs-lookup"><span data-stu-id="881ad-110">Set this parameter to **false** if you no longer want to apply any specific character set and return to the defaults for subsequent messages.</span></span> 
    
 <span data-ttu-id="881ad-111">_hcharset_</span><span class="sxs-lookup"><span data-stu-id="881ad-111">_hcharset_</span></span>
  
> <span data-ttu-id="881ad-112">[in]设置 Windows Mail 的 mimeole.h 中定义的字符句柄。</span><span class="sxs-lookup"><span data-stu-id="881ad-112">[in] A handle to a character set as defined in mimeole.h of Windows Mail.</span></span> <span data-ttu-id="881ad-113">指定**null**以指定您不希望应用任何特定的字符集。</span><span class="sxs-lookup"><span data-stu-id="881ad-113">Specify **null** to specify that you do not want to apply any specific character set.</span></span> <span data-ttu-id="881ad-114">对于非**null**值，使用如[MimeOleGetCodePageCharset](http://msdn.microsoft.com/en-us/library/ms714746%28VS.85%29.aspx)函数获取句柄的字符集。</span><span class="sxs-lookup"><span data-stu-id="881ad-114">For non- **null** values, use a function such as [MimeOleGetCodePageCharset](http://msdn.microsoft.com/en-us/library/ms714746%28VS.85%29.aspx) to obtain a handle to the character set.</span></span> 
    
 <span data-ttu-id="881ad-115">_csetapplytype_</span><span class="sxs-lookup"><span data-stu-id="881ad-115">_csetapplytype_</span></span>
  
> <span data-ttu-id="881ad-116">[in]指示如何应用转换一条消息，根据定义设置 Windows Mail 的 mimeole.h 中的字符。</span><span class="sxs-lookup"><span data-stu-id="881ad-116">[in] Indicates how to apply a character set to convert a message, as defined in mimeole.h of Windows Mail.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="881ad-117">返回值</span><span class="sxs-lookup"><span data-stu-id="881ad-117">Return value</span></span>

<span data-ttu-id="881ad-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="881ad-118">S_OK</span></span>
  
> <span data-ttu-id="881ad-119">成功函数调用。</span><span class="sxs-lookup"><span data-stu-id="881ad-119">The function call is successful.</span></span>
    
## <a name="mfcmapi-reference"></a><span data-ttu-id="881ad-120">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="881ad-120">MFCMAPI reference</span></span>

<span data-ttu-id="881ad-121">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="881ad-121">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="881ad-122">**文件**</span><span class="sxs-lookup"><span data-stu-id="881ad-122">**File**</span></span>|<span data-ttu-id="881ad-123">**函数**</span><span class="sxs-lookup"><span data-stu-id="881ad-123">**Function**</span></span>|<span data-ttu-id="881ad-124">**Comment**</span><span class="sxs-lookup"><span data-stu-id="881ad-124">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="881ad-125">MapiMime.cpp</span><span class="sxs-lookup"><span data-stu-id="881ad-125">MapiMime.cpp</span></span>  <br/> |<span data-ttu-id="881ad-126">ImportEMLToIMessage</span><span class="sxs-lookup"><span data-stu-id="881ad-126">ImportEMLToIMessage</span></span>  <br/> |<span data-ttu-id="881ad-127">MFCMAPI 使用 MimeToMAPI 将 EML 文件转换为 MAPI 邮件。</span><span class="sxs-lookup"><span data-stu-id="881ad-127">MFCMAPI uses MimeToMAPI to convert an EML file to a MAPI message.</span></span>  <br/> |
|<span data-ttu-id="881ad-128">MapiMime.cpp</span><span class="sxs-lookup"><span data-stu-id="881ad-128">MapiMime.cpp</span></span>  <br/> |<span data-ttu-id="881ad-129">ExportIMessageToEML</span><span class="sxs-lookup"><span data-stu-id="881ad-129">ExportIMessageToEML</span></span>  <br/> |<span data-ttu-id="881ad-130">MFCMAPI 使用 MAPIToMIMEStm 将转换为 EML 文件的 MAPI 邮件。</span><span class="sxs-lookup"><span data-stu-id="881ad-130">MFCMAPI uses MAPIToMIMEStm to convert a MAPI message to an EML file.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="881ad-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="881ad-131">See also</span></span>



[<span data-ttu-id="881ad-132">IConverterSession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="881ad-132">IConverterSession : IUnknown</span></span>](iconvertersessioniunknown.md)
  
[<span data-ttu-id="881ad-133">IConverterSession::MAPIToMIMEStm</span><span class="sxs-lookup"><span data-stu-id="881ad-133">IConverterSession::MAPIToMIMEStm</span></span>](iconvertersession-mapitomimestm.md)
  
[<span data-ttu-id="881ad-134">IConverterSession::MIMEToMAPI</span><span class="sxs-lookup"><span data-stu-id="881ad-134">IConverterSession::MIMEToMAPI</span></span>](iconvertersession-mimetomapi.md)
  
[<span data-ttu-id="881ad-135">IConverterSession::SetAdrBook</span><span class="sxs-lookup"><span data-stu-id="881ad-135">IConverterSession::SetAdrBook</span></span>](iconvertersession-setadrbook.md)
  
[<span data-ttu-id="881ad-136">IConverterSession::SetEncoding</span><span class="sxs-lookup"><span data-stu-id="881ad-136">IConverterSession::SetEncoding</span></span>](iconvertersession-setencoding.md)
  
[<span data-ttu-id="881ad-137">IConverterSession::SetSaveFormat</span><span class="sxs-lookup"><span data-stu-id="881ad-137">IConverterSession::SetSaveFormat</span></span>](iconvertersession-setsaveformat.md)
  
[<span data-ttu-id="881ad-138">IConverterSession::SetTextWrapping</span><span class="sxs-lookup"><span data-stu-id="881ad-138">IConverterSession::SetTextWrapping</span></span>](iconvertersession-settextwrapping.md)

