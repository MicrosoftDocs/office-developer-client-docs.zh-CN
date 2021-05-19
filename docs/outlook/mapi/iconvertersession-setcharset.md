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
ms.openlocfilehash: 14b2904e57852c564395f4b27c9d5270afd1454a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32336657"
---
# <a name="iconvertersessionsetcharset"></a><span data-ttu-id="a9713-103">IConverterSession::SetCharSet</span><span class="sxs-lookup"><span data-stu-id="a9713-103">IConverterSession::SetCharSet</span></span>

  
  
<span data-ttu-id="a9713-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a9713-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a9713-105">指定 MAPI 到 MIME 转换器在将 MAPI 邮件转换为 MIME 流时使用的可选字符集。</span><span class="sxs-lookup"><span data-stu-id="a9713-105">Specifies an optional character set that the MAPI to MIME converter use when converting a MAPI message to a MIME stream.</span></span>
  
```cpp
HRESULT SetCharset( 
     BOOL fApply, 
     HCHARSET hcharset, 
     CSETAPPLYTYPE csetapplytype); 
```

## <a name="parameters"></a><span data-ttu-id="a9713-106">参数</span><span class="sxs-lookup"><span data-stu-id="a9713-106">Parameters</span></span>

 <span data-ttu-id="a9713-107">_fApply_</span><span class="sxs-lookup"><span data-stu-id="a9713-107">_fApply_</span></span>
  
> <span data-ttu-id="a9713-108">[in]指示是否对转换使用特定字符集。</span><span class="sxs-lookup"><span data-stu-id="a9713-108">[in] Indicates whether to use a specific character set for the conversion.</span></span> <span data-ttu-id="a9713-109">将此参数 **设置为 true** 以在后续转换中应用字符集。</span><span class="sxs-lookup"><span data-stu-id="a9713-109">Set this parameter to **true** to apply the character set in subsequent conversions.</span></span> <span data-ttu-id="a9713-110">如果不想再应用任何特定字符集并返回到后续邮件的默认值，则此参数设置为 **false。**</span><span class="sxs-lookup"><span data-stu-id="a9713-110">Set this parameter to **false** if you no longer want to apply any specific character set and return to the defaults for subsequent messages.</span></span> 
    
 <span data-ttu-id="a9713-111">_hcharset_</span><span class="sxs-lookup"><span data-stu-id="a9713-111">_hcharset_</span></span>
  
> <span data-ttu-id="a9713-112">[in]字符集的句柄，如 mimeole.h 中定义的Windows Mail。</span><span class="sxs-lookup"><span data-stu-id="a9713-112">[in] A handle to a character set as defined in mimeole.h of Windows Mail.</span></span> <span data-ttu-id="a9713-113">指定 **null** 以指定您不希望应用任何特定字符集。</span><span class="sxs-lookup"><span data-stu-id="a9713-113">Specify **null** to specify that you do not want to apply any specific character set.</span></span> <span data-ttu-id="a9713-114">对于非 **null** 值，请使用函数（如 [MimeOleGetCodePageCharset）](https://msdn.microsoft.com/library/ms714746%28VS.85%29.aspx) 获取字符集的句柄。</span><span class="sxs-lookup"><span data-stu-id="a9713-114">For non- **null** values, use a function such as [MimeOleGetCodePageCharset](https://msdn.microsoft.com/library/ms714746%28VS.85%29.aspx) to obtain a handle to the character set.</span></span> 
    
 <span data-ttu-id="a9713-115">_csetapplytype_</span><span class="sxs-lookup"><span data-stu-id="a9713-115">_csetapplytype_</span></span>
  
> <span data-ttu-id="a9713-116">[in]指示如何应用字符集来转换邮件，如 mimeole.h of Windows Mail。</span><span class="sxs-lookup"><span data-stu-id="a9713-116">[in] Indicates how to apply a character set to convert a message, as defined in mimeole.h of Windows Mail.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="a9713-117">返回值</span><span class="sxs-lookup"><span data-stu-id="a9713-117">Return value</span></span>

<span data-ttu-id="a9713-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="a9713-118">S_OK</span></span>
  
> <span data-ttu-id="a9713-119">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="a9713-119">The function call is successful.</span></span>
    
## <a name="mfcmapi-reference"></a><span data-ttu-id="a9713-120">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="a9713-120">MFCMAPI reference</span></span>

<span data-ttu-id="a9713-121">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="a9713-121">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="a9713-122">**文件**</span><span class="sxs-lookup"><span data-stu-id="a9713-122">**File**</span></span>|<span data-ttu-id="a9713-123">**函数**</span><span class="sxs-lookup"><span data-stu-id="a9713-123">**Function**</span></span>|<span data-ttu-id="a9713-124">**备注**</span><span class="sxs-lookup"><span data-stu-id="a9713-124">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a9713-125">MapiMime.cpp</span><span class="sxs-lookup"><span data-stu-id="a9713-125">MapiMime.cpp</span></span>  <br/> |<span data-ttu-id="a9713-126">ImportEMLToIMessage</span><span class="sxs-lookup"><span data-stu-id="a9713-126">ImportEMLToIMessage</span></span>  <br/> |<span data-ttu-id="a9713-127">MFCMAPI 使用 MimeToMAPI 将 EML 文件转换为 MAPI 邮件。</span><span class="sxs-lookup"><span data-stu-id="a9713-127">MFCMAPI uses MimeToMAPI to convert an EML file to a MAPI message.</span></span>  <br/> |
|<span data-ttu-id="a9713-128">MapiMime.cpp</span><span class="sxs-lookup"><span data-stu-id="a9713-128">MapiMime.cpp</span></span>  <br/> |<span data-ttu-id="a9713-129">ExportIMessageToEML</span><span class="sxs-lookup"><span data-stu-id="a9713-129">ExportIMessageToEML</span></span>  <br/> |<span data-ttu-id="a9713-130">MFCMAPI 使用 MAPIToMIMEStm 将 MAPI 邮件转换为 EML 文件。</span><span class="sxs-lookup"><span data-stu-id="a9713-130">MFCMAPI uses MAPIToMIMEStm to convert a MAPI message to an EML file.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="a9713-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a9713-131">See also</span></span>



[<span data-ttu-id="a9713-132">IConverterSession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="a9713-132">IConverterSession : IUnknown</span></span>](iconvertersessioniunknown.md)
  
[<span data-ttu-id="a9713-133">IConverterSession::MAPIToMIMEStm</span><span class="sxs-lookup"><span data-stu-id="a9713-133">IConverterSession::MAPIToMIMEStm</span></span>](iconvertersession-mapitomimestm.md)
  
[<span data-ttu-id="a9713-134">IConverterSession::MIMEToMAPI</span><span class="sxs-lookup"><span data-stu-id="a9713-134">IConverterSession::MIMEToMAPI</span></span>](iconvertersession-mimetomapi.md)
  
[<span data-ttu-id="a9713-135">IConverterSession::SetAdrBook</span><span class="sxs-lookup"><span data-stu-id="a9713-135">IConverterSession::SetAdrBook</span></span>](iconvertersession-setadrbook.md)
  
[<span data-ttu-id="a9713-136">IConverterSession::SetEncoding</span><span class="sxs-lookup"><span data-stu-id="a9713-136">IConverterSession::SetEncoding</span></span>](iconvertersession-setencoding.md)
  
[<span data-ttu-id="a9713-137">IConverterSession::SetSaveFormat</span><span class="sxs-lookup"><span data-stu-id="a9713-137">IConverterSession::SetSaveFormat</span></span>](iconvertersession-setsaveformat.md)
  
[<span data-ttu-id="a9713-138">IConverterSession::SetTextWrapping</span><span class="sxs-lookup"><span data-stu-id="a9713-138">IConverterSession::SetTextWrapping</span></span>](iconvertersession-settextwrapping.md)

