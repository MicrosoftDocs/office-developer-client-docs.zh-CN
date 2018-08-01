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
ms.openlocfilehash: a13d4e54900989c692add85add6853a1b511f448
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775289"
---
# <a name="iconvertersessionsetencoding"></a><span data-ttu-id="9b085-103">IConverterSession::SetEncoding</span><span class="sxs-lookup"><span data-stu-id="9b085-103">IConverterSession::SetEncoding</span></span>

<span data-ttu-id="9b085-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="9b085-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="9b085-105">初始化转换期间使用的编码。</span><span class="sxs-lookup"><span data-stu-id="9b085-105">Initializes the encoding to be used during conversion.</span></span>
  
```cpp
HRESULT IConverterSession:: SetEncoding ( 
     ENCODINGTYPE et 
);
```

## <a name="parameters"></a><span data-ttu-id="9b085-106">参数</span><span class="sxs-lookup"><span data-stu-id="9b085-106">Parameters</span></span>

<span data-ttu-id="9b085-107">_et_</span><span class="sxs-lookup"><span data-stu-id="9b085-107">_et_</span></span>
  
> <span data-ttu-id="9b085-108">一个[ENCODINGTYPE](http://msdn.microsoft.com/en-us/library/aa374936%28VS.85%29.aspx)值。</span><span class="sxs-lookup"><span data-stu-id="9b085-108">An [ENCODINGTYPE](http://msdn.microsoft.com/en-us/library/aa374936%28VS.85%29.aspx) value.</span></span> <span data-ttu-id="9b085-109">支持仅以下值：</span><span class="sxs-lookup"><span data-stu-id="9b085-109">Only the following values are supported:</span></span> 
    
   - <span data-ttu-id="9b085-110">IET_BASE64</span><span class="sxs-lookup"><span data-stu-id="9b085-110">IET_BASE64</span></span>
   - <span data-ttu-id="9b085-111">IET_UUENCODE</span><span class="sxs-lookup"><span data-stu-id="9b085-111">IET_UUENCODE</span></span>
   - <span data-ttu-id="9b085-112">IET_QP</span><span class="sxs-lookup"><span data-stu-id="9b085-112">IET_QP</span></span>
   - <span data-ttu-id="9b085-113">IET_7BIT</span><span class="sxs-lookup"><span data-stu-id="9b085-113">IET_7BIT</span></span>
   - <span data-ttu-id="9b085-114">IET_8BIT</span><span class="sxs-lookup"><span data-stu-id="9b085-114">IET_8BIT</span></span>
    
## <a name="return-value"></a><span data-ttu-id="9b085-115">返回值</span><span class="sxs-lookup"><span data-stu-id="9b085-115">Return value</span></span>

<span data-ttu-id="9b085-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="9b085-116">E_INVALIDARG</span></span>
  
> <span data-ttu-id="9b085-117">传递的编码类型无效。</span><span class="sxs-lookup"><span data-stu-id="9b085-117">The encoding type passed was invalid.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="9b085-118">说明</span><span class="sxs-lookup"><span data-stu-id="9b085-118">Remarks</span></span>

<span data-ttu-id="9b085-119">使用[IConverterSession::MAPIToMIMEStm](iconvertersession-mapitomimestm.md)执行转换之前调用**SetEncoding** 。</span><span class="sxs-lookup"><span data-stu-id="9b085-119">Call **SetEncoding** before using [IConverterSession::MAPIToMIMEStm](iconvertersession-mapitomimestm.md) to perform conversion.</span></span> 
  
<span data-ttu-id="9b085-120">使用**SetEncoding**设置的最外面的消息正文将的邮件项目的编码。</span><span class="sxs-lookup"><span data-stu-id="9b085-120">Use **SetEncoding** to set the encoding for only the outermost message body of a mail item.</span></span> <span data-ttu-id="9b085-121">Microsoft Outlook 2010 和 Microsoft Outlook 2013 中选择的任何单个附件的编码。</span><span class="sxs-lookup"><span data-stu-id="9b085-121">Microsoft Outlook 2010 and Microsoft Outlook 2013 choose the encoding for any individual attachments.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="9b085-122">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="9b085-122">MFCMAPI reference</span></span>

<span data-ttu-id="9b085-123">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="9b085-123">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="9b085-124">**文件**</span><span class="sxs-lookup"><span data-stu-id="9b085-124">**File**</span></span>|<span data-ttu-id="9b085-125">**函数**</span><span class="sxs-lookup"><span data-stu-id="9b085-125">**Function**</span></span>|<span data-ttu-id="9b085-126">**Comment**</span><span class="sxs-lookup"><span data-stu-id="9b085-126">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9b085-127">MapiMime.cpp</span><span class="sxs-lookup"><span data-stu-id="9b085-127">MapiMime.cpp</span></span>  <br/> |<span data-ttu-id="9b085-128">ImportEMLToIMessage</span><span class="sxs-lookup"><span data-stu-id="9b085-128">ImportEMLToIMessage</span></span>  <br/> |<span data-ttu-id="9b085-129">MFCMAPI 使用 MimeToMAPI 将 EML 文件转换为 MAPI 邮件。</span><span class="sxs-lookup"><span data-stu-id="9b085-129">MFCMAPI uses MimeToMAPI to convert an EML file to a MAPI message.</span></span>  <br/> |
|<span data-ttu-id="9b085-130">MapiMime.cpp</span><span class="sxs-lookup"><span data-stu-id="9b085-130">MapiMime.cpp</span></span>  <br/> |<span data-ttu-id="9b085-131">ExportIMessageToEML</span><span class="sxs-lookup"><span data-stu-id="9b085-131">ExportIMessageToEML</span></span>  <br/> |<span data-ttu-id="9b085-132">MFCMAPI 使用 MAPIToMIMEStm 将转换为 EML 文件的 MAPI 邮件。</span><span class="sxs-lookup"><span data-stu-id="9b085-132">MFCMAPI uses MAPIToMIMEStm to convert a MAPI message to an EML file.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="9b085-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9b085-133">See also</span></span>

- [<span data-ttu-id="9b085-134">IConverterSession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="9b085-134">IConverterSession : IUnknown</span></span>](iconvertersessioniunknown.md)
- [<span data-ttu-id="9b085-135">IConverterSession::MAPIToMIMEStm</span><span class="sxs-lookup"><span data-stu-id="9b085-135">IConverterSession::MAPIToMIMEStm</span></span>](iconvertersession-mapitomimestm.md)
- [<span data-ttu-id="9b085-136">IConverterSession::MIMEToMAPI</span><span class="sxs-lookup"><span data-stu-id="9b085-136">IConverterSession::MIMEToMAPI</span></span>](iconvertersession-mimetomapi.md)
- [<span data-ttu-id="9b085-137">IConverterSession::SetAdrBook</span><span class="sxs-lookup"><span data-stu-id="9b085-137">IConverterSession::SetAdrBook</span></span>](iconvertersession-setadrbook.md)
- [<span data-ttu-id="9b085-138">IConverterSession::SetCharSet</span><span class="sxs-lookup"><span data-stu-id="9b085-138">IConverterSession::SetCharSet</span></span>](iconvertersession-setcharset.md)
- [<span data-ttu-id="9b085-139">IConverterSession::SetSaveFormat</span><span class="sxs-lookup"><span data-stu-id="9b085-139">IConverterSession::SetSaveFormat</span></span>](iconvertersession-setsaveformat.md)
- [<span data-ttu-id="9b085-140">IConverterSession::SetTextWrapping</span><span class="sxs-lookup"><span data-stu-id="9b085-140">IConverterSession::SetTextWrapping</span></span>](iconvertersession-settextwrapping.md)
- [<span data-ttu-id="9b085-141">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="9b085-141">MAPI Constants</span></span>](mapi-constants.md)

