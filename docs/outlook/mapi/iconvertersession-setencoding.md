---
title: IConverterSessionSetEncoding
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
ms.assetid: a9624d3f-a636-0267-5cbd-de0db42f9c22
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5a81e04d112e0adf201dcacf03673daac77a04ab
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32341298"
---
# <a name="iconvertersessionsetencoding"></a><span data-ttu-id="2c9b6-103">IConverterSession::SetEncoding</span><span class="sxs-lookup"><span data-stu-id="2c9b6-103">IConverterSession::SetEncoding</span></span>

<span data-ttu-id="2c9b6-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2c9b6-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2c9b6-105">初始化在转换期间使用的编码。</span><span class="sxs-lookup"><span data-stu-id="2c9b6-105">Initializes the encoding to be used during conversion.</span></span>
  
```cpp
HRESULT IConverterSession:: SetEncoding ( 
     ENCODINGTYPE et 
);
```

## <a name="parameters"></a><span data-ttu-id="2c9b6-106">参数</span><span class="sxs-lookup"><span data-stu-id="2c9b6-106">Parameters</span></span>

<span data-ttu-id="2c9b6-107">_et_</span><span class="sxs-lookup"><span data-stu-id="2c9b6-107">_et_</span></span>
  
> <span data-ttu-id="2c9b6-108">[ENCODINGTYPE](https://msdn.microsoft.com/library/aa374936%28VS.85%29.aspx)值。</span><span class="sxs-lookup"><span data-stu-id="2c9b6-108">An [ENCODINGTYPE](https://msdn.microsoft.com/library/aa374936%28VS.85%29.aspx) value.</span></span> <span data-ttu-id="2c9b6-109">仅支持以下值：</span><span class="sxs-lookup"><span data-stu-id="2c9b6-109">Only the following values are supported:</span></span> 
    
   - <span data-ttu-id="2c9b6-110">IET_BASE64</span><span class="sxs-lookup"><span data-stu-id="2c9b6-110">IET_BASE64</span></span>
   - <span data-ttu-id="2c9b6-111">IET_UUENCODE</span><span class="sxs-lookup"><span data-stu-id="2c9b6-111">IET_UUENCODE</span></span>
   - <span data-ttu-id="2c9b6-112">IET_QP</span><span class="sxs-lookup"><span data-stu-id="2c9b6-112">IET_QP</span></span>
   - <span data-ttu-id="2c9b6-113">IET_7BIT</span><span class="sxs-lookup"><span data-stu-id="2c9b6-113">IET_7BIT</span></span>
   - <span data-ttu-id="2c9b6-114">IET_8BIT</span><span class="sxs-lookup"><span data-stu-id="2c9b6-114">IET_8BIT</span></span>
    
## <a name="return-value"></a><span data-ttu-id="2c9b6-115">返回值</span><span class="sxs-lookup"><span data-stu-id="2c9b6-115">Return value</span></span>

<span data-ttu-id="2c9b6-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="2c9b6-116">E_INVALIDARG</span></span>
  
> <span data-ttu-id="2c9b6-117">传递的编码类型无效。</span><span class="sxs-lookup"><span data-stu-id="2c9b6-117">The encoding type passed was invalid.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="2c9b6-118">备注</span><span class="sxs-lookup"><span data-stu-id="2c9b6-118">Remarks</span></span>

<span data-ttu-id="2c9b6-119">在使用 [IConverterSession：：MAPIToMIMEStm](iconvertersession-mapitomimestm.md)执行转换之前，先调用 **SetEncoding。**</span><span class="sxs-lookup"><span data-stu-id="2c9b6-119">Call **SetEncoding** before using [IConverterSession::MAPIToMIMEStm](iconvertersession-mapitomimestm.md) to perform conversion.</span></span> 
  
<span data-ttu-id="2c9b6-120">使用 **SetEncoding** 可以仅设置邮件项目最外部的邮件正文的编码。</span><span class="sxs-lookup"><span data-stu-id="2c9b6-120">Use **SetEncoding** to set the encoding for only the outermost message body of a mail item.</span></span> <span data-ttu-id="2c9b6-121">Microsoft Outlook 2010和 Microsoft Outlook 2013 选择任何单个附件的编码。</span><span class="sxs-lookup"><span data-stu-id="2c9b6-121">Microsoft Outlook 2010 and Microsoft Outlook 2013 choose the encoding for any individual attachments.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="2c9b6-122">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="2c9b6-122">MFCMAPI reference</span></span>

<span data-ttu-id="2c9b6-123">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="2c9b6-123">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="2c9b6-124">**文件**</span><span class="sxs-lookup"><span data-stu-id="2c9b6-124">**File**</span></span>|<span data-ttu-id="2c9b6-125">**函数**</span><span class="sxs-lookup"><span data-stu-id="2c9b6-125">**Function**</span></span>|<span data-ttu-id="2c9b6-126">**备注**</span><span class="sxs-lookup"><span data-stu-id="2c9b6-126">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2c9b6-127">MapiMime.cpp</span><span class="sxs-lookup"><span data-stu-id="2c9b6-127">MapiMime.cpp</span></span>  <br/> |<span data-ttu-id="2c9b6-128">ImportEMLToIMessage</span><span class="sxs-lookup"><span data-stu-id="2c9b6-128">ImportEMLToIMessage</span></span>  <br/> |<span data-ttu-id="2c9b6-129">MFCMAPI 使用 MimeToMAPI 将 EML 文件转换为 MAPI 邮件。</span><span class="sxs-lookup"><span data-stu-id="2c9b6-129">MFCMAPI uses MimeToMAPI to convert an EML file to a MAPI message.</span></span>  <br/> |
|<span data-ttu-id="2c9b6-130">MapiMime.cpp</span><span class="sxs-lookup"><span data-stu-id="2c9b6-130">MapiMime.cpp</span></span>  <br/> |<span data-ttu-id="2c9b6-131">ExportIMessageToEML</span><span class="sxs-lookup"><span data-stu-id="2c9b6-131">ExportIMessageToEML</span></span>  <br/> |<span data-ttu-id="2c9b6-132">MFCMAPI 使用 MAPIToMIMEStm 将 MAPI 邮件转换为 EML 文件。</span><span class="sxs-lookup"><span data-stu-id="2c9b6-132">MFCMAPI uses MAPIToMIMEStm to convert a MAPI message to an EML file.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="2c9b6-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2c9b6-133">See also</span></span>

- [<span data-ttu-id="2c9b6-134">IConverterSession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="2c9b6-134">IConverterSession : IUnknown</span></span>](iconvertersessioniunknown.md)
- [<span data-ttu-id="2c9b6-135">IConverterSession::MAPIToMIMEStm</span><span class="sxs-lookup"><span data-stu-id="2c9b6-135">IConverterSession::MAPIToMIMEStm</span></span>](iconvertersession-mapitomimestm.md)
- [<span data-ttu-id="2c9b6-136">IConverterSession::MIMEToMAPI</span><span class="sxs-lookup"><span data-stu-id="2c9b6-136">IConverterSession::MIMEToMAPI</span></span>](iconvertersession-mimetomapi.md)
- [<span data-ttu-id="2c9b6-137">IConverterSession::SetAdrBook</span><span class="sxs-lookup"><span data-stu-id="2c9b6-137">IConverterSession::SetAdrBook</span></span>](iconvertersession-setadrbook.md)
- [<span data-ttu-id="2c9b6-138">IConverterSession::SetCharSet</span><span class="sxs-lookup"><span data-stu-id="2c9b6-138">IConverterSession::SetCharSet</span></span>](iconvertersession-setcharset.md)
- [<span data-ttu-id="2c9b6-139">IConverterSession::SetSaveFormat</span><span class="sxs-lookup"><span data-stu-id="2c9b6-139">IConverterSession::SetSaveFormat</span></span>](iconvertersession-setsaveformat.md)
- [<span data-ttu-id="2c9b6-140">IConverterSession::SetTextWrapping</span><span class="sxs-lookup"><span data-stu-id="2c9b6-140">IConverterSession::SetTextWrapping</span></span>](iconvertersession-settextwrapping.md)
- [<span data-ttu-id="2c9b6-141">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="2c9b6-141">MAPI Constants</span></span>](mapi-constants.md)

