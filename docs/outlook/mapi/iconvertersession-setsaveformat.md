---
title: IConverterSessionSetSaveFormat
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
ms.assetid: e5308a94-5191-2109-a881-b4f4a7ff1c61
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f24ad938fdb8c3ac234e1d78f2668139840c8b8f
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22568215"
---
# <a name="iconvertersessionsetsaveformat"></a><span data-ttu-id="2194e-103">IConverterSession::SetSaveFormat</span><span class="sxs-lookup"><span data-stu-id="2194e-103">IConverterSession::SetSaveFormat</span></span>

<span data-ttu-id="2194e-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2194e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2194e-105">在其中转换器将返回 MIME 流[IConverterSession::MAPIToMIMEStm](iconvertersession-mapitomimestm.md)中的格式设置。</span><span class="sxs-lookup"><span data-stu-id="2194e-105">Sets the format in which the converter will return a MIME stream in [IConverterSession::MAPIToMIMEStm](iconvertersession-mapitomimestm.md).</span></span>
  
```cpp
HRESULT IConverterSession::SetSaveFormat ( 
     MIMESAVETYPE mstSaveFormat 
);
```

## <a name="parameters"></a><span data-ttu-id="2194e-106">参数</span><span class="sxs-lookup"><span data-stu-id="2194e-106">Parameters</span></span>

<span data-ttu-id="2194e-107">_mstSaveFormat_</span><span class="sxs-lookup"><span data-stu-id="2194e-107">_mstSaveFormat_</span></span>
  
> <span data-ttu-id="2194e-108">[in]保存格式用于 MIME 流。</span><span class="sxs-lookup"><span data-stu-id="2194e-108">[in] The save format to be used for a MIME stream.</span></span> <span data-ttu-id="2194e-109">有关详细信息，请参阅枚举类型[MIMESAVETYPE](http://msdn.microsoft.com/en-us/library/ms715128%28VS.85%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="2194e-109">For more information, see the enum type [MIMESAVETYPE](http://msdn.microsoft.com/en-us/library/ms715128%28VS.85%29.aspx).</span></span>
    
  - <span data-ttu-id="2194e-110">**SAVE_RFC1521**： 使用 MIME，这是默认值。</span><span class="sxs-lookup"><span data-stu-id="2194e-110">**SAVE_RFC1521**: Use MIME, which is the default.</span></span>      
  - <span data-ttu-id="2194e-111">**SAVE_RFC822**： 使用 uuencode。</span><span class="sxs-lookup"><span data-stu-id="2194e-111">**SAVE_RFC822**: Use uuencode.</span></span>
    
## <a name="return-values"></a><span data-ttu-id="2194e-112">返回值</span><span class="sxs-lookup"><span data-stu-id="2194e-112">Return values</span></span>

<span data-ttu-id="2194e-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="2194e-113">S_OK</span></span>
  
> <span data-ttu-id="2194e-114">呼叫成功。</span><span class="sxs-lookup"><span data-stu-id="2194e-114">The call was successful.</span></span>
    
## <a name="mfcmapi-reference"></a><span data-ttu-id="2194e-115">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="2194e-115">MFCMAPI reference</span></span>

<span data-ttu-id="2194e-116">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="2194e-116">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="2194e-117">**文件**</span><span class="sxs-lookup"><span data-stu-id="2194e-117">**File**</span></span>|<span data-ttu-id="2194e-118">**函数**</span><span class="sxs-lookup"><span data-stu-id="2194e-118">**Function**</span></span>|<span data-ttu-id="2194e-119">**Comment**</span><span class="sxs-lookup"><span data-stu-id="2194e-119">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2194e-120">MapiMime.cpp</span><span class="sxs-lookup"><span data-stu-id="2194e-120">MapiMime.cpp</span></span>  <br/> |<span data-ttu-id="2194e-121">ImportEMLToIMessage</span><span class="sxs-lookup"><span data-stu-id="2194e-121">ImportEMLToIMessage</span></span>  <br/> |<span data-ttu-id="2194e-122">MFCMAPI 使用 MimeToMAPI 将 EML 文件转换为 MAPI 邮件。</span><span class="sxs-lookup"><span data-stu-id="2194e-122">MFCMAPI uses MimeToMAPI to convert an EML file to a MAPI message.</span></span>  <br/> |
|<span data-ttu-id="2194e-123">MapiMime.cpp</span><span class="sxs-lookup"><span data-stu-id="2194e-123">MapiMime.cpp</span></span>  <br/> |<span data-ttu-id="2194e-124">ExportIMessageToEML</span><span class="sxs-lookup"><span data-stu-id="2194e-124">ExportIMessageToEML</span></span>  <br/> |<span data-ttu-id="2194e-125">MFCMAPI 使用 MAPIToMIMEStm 将转换为 EML 文件的 MAPI 邮件。</span><span class="sxs-lookup"><span data-stu-id="2194e-125">MFCMAPI uses MAPIToMIMEStm to convert a MAPI message to an EML file.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="2194e-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2194e-126">See also</span></span>

- [<span data-ttu-id="2194e-127">IConverterSession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="2194e-127">IConverterSession : IUnknown</span></span>](iconvertersessioniunknown.md)
- [<span data-ttu-id="2194e-128">IConverterSession::MAPIToMIMEStm</span><span class="sxs-lookup"><span data-stu-id="2194e-128">IConverterSession::MAPIToMIMEStm</span></span>](iconvertersession-mapitomimestm.md)
- [<span data-ttu-id="2194e-129">IConverterSession::MIMEToMAPI</span><span class="sxs-lookup"><span data-stu-id="2194e-129">IConverterSession::MIMEToMAPI</span></span>](iconvertersession-mimetomapi.md)
- [<span data-ttu-id="2194e-130">IConverterSession::SetAdrBook</span><span class="sxs-lookup"><span data-stu-id="2194e-130">IConverterSession::SetAdrBook</span></span>](iconvertersession-setadrbook.md)
- [<span data-ttu-id="2194e-131">IConverterSession::SetCharSet</span><span class="sxs-lookup"><span data-stu-id="2194e-131">IConverterSession::SetCharSet</span></span>](iconvertersession-setcharset.md)
- [<span data-ttu-id="2194e-132">IConverterSession::SetEncoding</span><span class="sxs-lookup"><span data-stu-id="2194e-132">IConverterSession::SetEncoding</span></span>](iconvertersession-setencoding.md)
- [<span data-ttu-id="2194e-133">IConverterSession::SetTextWrapping</span><span class="sxs-lookup"><span data-stu-id="2194e-133">IConverterSession::SetTextWrapping</span></span>](iconvertersession-settextwrapping.md)
- [<span data-ttu-id="2194e-134">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="2194e-134">MAPI Constants</span></span>](mapi-constants.md)

