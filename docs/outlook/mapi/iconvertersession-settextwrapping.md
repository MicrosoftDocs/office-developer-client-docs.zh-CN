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
ms.openlocfilehash: a8a6546c38c629c193c1978998c95918943fe5c7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32336629"
---
# <a name="iconvertersessionsettextwrapping"></a><span data-ttu-id="e5b90-103">IConverterSession::SetTextWrapping</span><span class="sxs-lookup"><span data-stu-id="e5b90-103">IConverterSession::SetTextWrapping</span></span>

  
  
<span data-ttu-id="e5b90-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e5b90-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e5b90-105">设置转换器将在[IConverterSession:: MAPIToMIMEStm](iconvertersession-mapitomimestm.md)中返回的 MIME 流的文本换行宽度。</span><span class="sxs-lookup"><span data-stu-id="e5b90-105">Sets the text wrapping width for a MIME stream that the converter will return in [IConverterSession::MAPIToMIMEStm](iconvertersession-mapitomimestm.md).</span></span>
  
```cpp
HRESULT IConverterSession::SetTextWrapping ( 
    BOOL    fWrapText, 
    ULONG   ulWrapWidth 
);
```

## <a name="parameters"></a><span data-ttu-id="e5b90-106">参数</span><span class="sxs-lookup"><span data-stu-id="e5b90-106">Parameters</span></span>

 <span data-ttu-id="e5b90-107">*fWrapText*</span><span class="sxs-lookup"><span data-stu-id="e5b90-107">*fWrapText*</span></span> 
  
> <span data-ttu-id="e5b90-108">实时是否环绕文本。</span><span class="sxs-lookup"><span data-stu-id="e5b90-108">[in] Whether to wrap text or not.</span></span>
    
 <span data-ttu-id="e5b90-109">*ulWrapWidth*</span><span class="sxs-lookup"><span data-stu-id="e5b90-109">*ulWrapWidth*</span></span> 
  
> <span data-ttu-id="e5b90-110">实时要使用的文字环绕宽度。</span><span class="sxs-lookup"><span data-stu-id="e5b90-110">[in] The text wrapping width to use.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="e5b90-111">返回值</span><span class="sxs-lookup"><span data-stu-id="e5b90-111">Return value</span></span>

<span data-ttu-id="e5b90-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="e5b90-112">S_OK</span></span>
  
> <span data-ttu-id="e5b90-113">调用成功。</span><span class="sxs-lookup"><span data-stu-id="e5b90-113">The call was successful.</span></span>
    
## <a name="mfcmapi-reference"></a><span data-ttu-id="e5b90-114">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="e5b90-114">MFCMAPI reference</span></span>

<span data-ttu-id="e5b90-115">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="e5b90-115">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="e5b90-116">**文件**</span><span class="sxs-lookup"><span data-stu-id="e5b90-116">**File**</span></span>|<span data-ttu-id="e5b90-117">**函数**</span><span class="sxs-lookup"><span data-stu-id="e5b90-117">**Function**</span></span>|<span data-ttu-id="e5b90-118">**备注**</span><span class="sxs-lookup"><span data-stu-id="e5b90-118">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e5b90-119">MapiMime</span><span class="sxs-lookup"><span data-stu-id="e5b90-119">MapiMime.cpp</span></span>  <br/> |<span data-ttu-id="e5b90-120">ImportEMLToIMessage</span><span class="sxs-lookup"><span data-stu-id="e5b90-120">ImportEMLToIMessage</span></span>  <br/> |<span data-ttu-id="e5b90-121">MFCMAPI 使用 MimeToMAPI 将 .eml 文件转换为 MAPI 邮件。</span><span class="sxs-lookup"><span data-stu-id="e5b90-121">MFCMAPI uses MimeToMAPI to convert an EML file to a MAPI message.</span></span>  <br/> |
|<span data-ttu-id="e5b90-122">MapiMime</span><span class="sxs-lookup"><span data-stu-id="e5b90-122">MapiMime.cpp</span></span>  <br/> |<span data-ttu-id="e5b90-123">ExportIMessageToEML</span><span class="sxs-lookup"><span data-stu-id="e5b90-123">ExportIMessageToEML</span></span>  <br/> |<span data-ttu-id="e5b90-124">MFCMAPI 使用 MAPIToMIMEStm 将 MAPI 邮件转换为 .eml 文件。</span><span class="sxs-lookup"><span data-stu-id="e5b90-124">MFCMAPI uses MAPIToMIMEStm to convert a MAPI message to an EML file.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="e5b90-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e5b90-125">See also</span></span>



[<span data-ttu-id="e5b90-126">IConverterSession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="e5b90-126">IConverterSession : IUnknown</span></span>](iconvertersessioniunknown.md)
  
[<span data-ttu-id="e5b90-127">IConverterSession::MAPIToMIMEStm</span><span class="sxs-lookup"><span data-stu-id="e5b90-127">IConverterSession::MAPIToMIMEStm</span></span>](iconvertersession-mapitomimestm.md)
  
[<span data-ttu-id="e5b90-128">IConverterSession::MIMEToMAPI</span><span class="sxs-lookup"><span data-stu-id="e5b90-128">IConverterSession::MIMEToMAPI</span></span>](iconvertersession-mimetomapi.md)
  
[<span data-ttu-id="e5b90-129">IConverterSession::SetAdrBook</span><span class="sxs-lookup"><span data-stu-id="e5b90-129">IConverterSession::SetAdrBook</span></span>](iconvertersession-setadrbook.md)
  
[<span data-ttu-id="e5b90-130">IConverterSession::SetCharSet</span><span class="sxs-lookup"><span data-stu-id="e5b90-130">IConverterSession::SetCharSet</span></span>](iconvertersession-setcharset.md)
  
[<span data-ttu-id="e5b90-131">IConverterSession::SetEncoding</span><span class="sxs-lookup"><span data-stu-id="e5b90-131">IConverterSession::SetEncoding</span></span>](iconvertersession-setencoding.md)
  
[<span data-ttu-id="e5b90-132">IConverterSession::SetSaveFormat</span><span class="sxs-lookup"><span data-stu-id="e5b90-132">IConverterSession::SetSaveFormat</span></span>](iconvertersession-setsaveformat.md)


[<span data-ttu-id="e5b90-133">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="e5b90-133">MAPI Constants</span></span>](mapi-constants.md)

