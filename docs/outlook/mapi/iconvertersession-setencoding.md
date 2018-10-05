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
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25382419"
---
# <a name="iconvertersessionsetencoding"></a><span data-ttu-id="ad00b-103">IConverterSession::SetEncoding</span><span class="sxs-lookup"><span data-stu-id="ad00b-103">IConverterSession::SetEncoding</span></span>

<span data-ttu-id="ad00b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ad00b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ad00b-105">初始化转换期间使用的编码。</span><span class="sxs-lookup"><span data-stu-id="ad00b-105">Initializes the encoding to be used during conversion.</span></span>
  
```cpp
HRESULT IConverterSession:: SetEncoding ( 
     ENCODINGTYPE et 
);
```

## <a name="parameters"></a><span data-ttu-id="ad00b-106">参数</span><span class="sxs-lookup"><span data-stu-id="ad00b-106">Parameters</span></span>

<span data-ttu-id="ad00b-107">_et_</span><span class="sxs-lookup"><span data-stu-id="ad00b-107">_et_</span></span>
  
> <span data-ttu-id="ad00b-108">一个[ENCODINGTYPE](https://msdn.microsoft.com/library/aa374936%28VS.85%29.aspx)值。</span><span class="sxs-lookup"><span data-stu-id="ad00b-108">An [ENCODINGTYPE](https://msdn.microsoft.com/library/aa374936%28VS.85%29.aspx) value.</span></span> <span data-ttu-id="ad00b-109">支持仅以下值：</span><span class="sxs-lookup"><span data-stu-id="ad00b-109">Only the following values are supported:</span></span> 
    
   - <span data-ttu-id="ad00b-110">IET_BASE64</span><span class="sxs-lookup"><span data-stu-id="ad00b-110">IET_BASE64</span></span>
   - <span data-ttu-id="ad00b-111">IET_UUENCODE</span><span class="sxs-lookup"><span data-stu-id="ad00b-111">IET_UUENCODE</span></span>
   - <span data-ttu-id="ad00b-112">IET_QP</span><span class="sxs-lookup"><span data-stu-id="ad00b-112">IET_QP</span></span>
   - <span data-ttu-id="ad00b-113">IET_7BIT</span><span class="sxs-lookup"><span data-stu-id="ad00b-113">IET_7BIT</span></span>
   - <span data-ttu-id="ad00b-114">IET_8BIT</span><span class="sxs-lookup"><span data-stu-id="ad00b-114">IET_8BIT</span></span>
    
## <a name="return-value"></a><span data-ttu-id="ad00b-115">返回值</span><span class="sxs-lookup"><span data-stu-id="ad00b-115">Return value</span></span>

<span data-ttu-id="ad00b-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="ad00b-116">E_INVALIDARG</span></span>
  
> <span data-ttu-id="ad00b-117">传递的编码类型无效。</span><span class="sxs-lookup"><span data-stu-id="ad00b-117">The encoding type passed was invalid.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="ad00b-118">说明</span><span class="sxs-lookup"><span data-stu-id="ad00b-118">Remarks</span></span>

<span data-ttu-id="ad00b-119">使用[IConverterSession::MAPIToMIMEStm](iconvertersession-mapitomimestm.md)执行转换之前调用**SetEncoding** 。</span><span class="sxs-lookup"><span data-stu-id="ad00b-119">Call **SetEncoding** before using [IConverterSession::MAPIToMIMEStm](iconvertersession-mapitomimestm.md) to perform conversion.</span></span> 
  
<span data-ttu-id="ad00b-120">使用**SetEncoding**设置的最外面的消息正文将的邮件项目的编码。</span><span class="sxs-lookup"><span data-stu-id="ad00b-120">Use **SetEncoding** to set the encoding for only the outermost message body of a mail item.</span></span> <span data-ttu-id="ad00b-121">Microsoft Outlook 2010 和 Microsoft Outlook 2013 中选择的任何单个附件的编码。</span><span class="sxs-lookup"><span data-stu-id="ad00b-121">Microsoft Outlook 2010 and Microsoft Outlook 2013 choose the encoding for any individual attachments.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="ad00b-122">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="ad00b-122">MFCMAPI reference</span></span>

<span data-ttu-id="ad00b-123">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="ad00b-123">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="ad00b-124">**文件**</span><span class="sxs-lookup"><span data-stu-id="ad00b-124">**File**</span></span>|<span data-ttu-id="ad00b-125">**函数**</span><span class="sxs-lookup"><span data-stu-id="ad00b-125">**Function**</span></span>|<span data-ttu-id="ad00b-126">**备注**</span><span class="sxs-lookup"><span data-stu-id="ad00b-126">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ad00b-127">MapiMime.cpp</span><span class="sxs-lookup"><span data-stu-id="ad00b-127">MapiMime.cpp</span></span>  <br/> |<span data-ttu-id="ad00b-128">ImportEMLToIMessage</span><span class="sxs-lookup"><span data-stu-id="ad00b-128">ImportEMLToIMessage</span></span>  <br/> |<span data-ttu-id="ad00b-129">MFCMAPI 使用 MimeToMAPI 将 EML 文件转换为 MAPI 邮件。</span><span class="sxs-lookup"><span data-stu-id="ad00b-129">MFCMAPI uses MimeToMAPI to convert an EML file to a MAPI message.</span></span>  <br/> |
|<span data-ttu-id="ad00b-130">MapiMime.cpp</span><span class="sxs-lookup"><span data-stu-id="ad00b-130">MapiMime.cpp</span></span>  <br/> |<span data-ttu-id="ad00b-131">ExportIMessageToEML</span><span class="sxs-lookup"><span data-stu-id="ad00b-131">ExportIMessageToEML</span></span>  <br/> |<span data-ttu-id="ad00b-132">MFCMAPI 使用 MAPIToMIMEStm 将转换为 EML 文件的 MAPI 邮件。</span><span class="sxs-lookup"><span data-stu-id="ad00b-132">MFCMAPI uses MAPIToMIMEStm to convert a MAPI message to an EML file.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="ad00b-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ad00b-133">See also</span></span>

- [<span data-ttu-id="ad00b-134">IConverterSession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="ad00b-134">IConverterSession : IUnknown</span></span>](iconvertersessioniunknown.md)
- [<span data-ttu-id="ad00b-135">IConverterSession::MAPIToMIMEStm</span><span class="sxs-lookup"><span data-stu-id="ad00b-135">IConverterSession::MAPIToMIMEStm</span></span>](iconvertersession-mapitomimestm.md)
- [<span data-ttu-id="ad00b-136">IConverterSession::MIMEToMAPI</span><span class="sxs-lookup"><span data-stu-id="ad00b-136">IConverterSession::MIMEToMAPI</span></span>](iconvertersession-mimetomapi.md)
- [<span data-ttu-id="ad00b-137">IConverterSession::SetAdrBook</span><span class="sxs-lookup"><span data-stu-id="ad00b-137">IConverterSession::SetAdrBook</span></span>](iconvertersession-setadrbook.md)
- [<span data-ttu-id="ad00b-138">IConverterSession::SetCharSet</span><span class="sxs-lookup"><span data-stu-id="ad00b-138">IConverterSession::SetCharSet</span></span>](iconvertersession-setcharset.md)
- [<span data-ttu-id="ad00b-139">IConverterSession::SetSaveFormat</span><span class="sxs-lookup"><span data-stu-id="ad00b-139">IConverterSession::SetSaveFormat</span></span>](iconvertersession-setsaveformat.md)
- [<span data-ttu-id="ad00b-140">IConverterSession::SetTextWrapping</span><span class="sxs-lookup"><span data-stu-id="ad00b-140">IConverterSession::SetTextWrapping</span></span>](iconvertersession-settextwrapping.md)
- [<span data-ttu-id="ad00b-141">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="ad00b-141">MAPI Constants</span></span>](mapi-constants.md)

