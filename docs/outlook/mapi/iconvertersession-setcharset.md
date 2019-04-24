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
# <a name="iconvertersessionsetcharset"></a><span data-ttu-id="f3896-103">IConverterSession::SetCharSet</span><span class="sxs-lookup"><span data-stu-id="f3896-103">IConverterSession::SetCharSet</span></span>

  
  
<span data-ttu-id="f3896-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f3896-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f3896-105">指定 mapi 到 mime 转换器在将 mapi 邮件转换为 mime 流时使用的一组可选字符集。</span><span class="sxs-lookup"><span data-stu-id="f3896-105">Specifies an optional character set that the MAPI to MIME converter use when converting a MAPI message to a MIME stream.</span></span>
  
```cpp
HRESULT SetCharset( 
     BOOL fApply, 
     HCHARSET hcharset, 
     CSETAPPLYTYPE csetapplytype); 
```

## <a name="parameters"></a><span data-ttu-id="f3896-106">参数</span><span class="sxs-lookup"><span data-stu-id="f3896-106">Parameters</span></span>

 <span data-ttu-id="f3896-107">_fApply_</span><span class="sxs-lookup"><span data-stu-id="f3896-107">_fApply_</span></span>
  
> <span data-ttu-id="f3896-108">实时指示是否对转换使用特定的字符集。</span><span class="sxs-lookup"><span data-stu-id="f3896-108">[in] Indicates whether to use a specific character set for the conversion.</span></span> <span data-ttu-id="f3896-109">将此参数设置为**true**可在后续转换中应用字符集。</span><span class="sxs-lookup"><span data-stu-id="f3896-109">Set this parameter to **true** to apply the character set in subsequent conversions.</span></span> <span data-ttu-id="f3896-110">如果您不再希望应用任何特定的字符集, 并返回到后续邮件的默认设置, 请将此参数设置为**false** 。</span><span class="sxs-lookup"><span data-stu-id="f3896-110">Set this parameter to **false** if you no longer want to apply any specific character set and return to the defaults for subsequent messages.</span></span> 
    
 <span data-ttu-id="f3896-111">_hcharset_</span><span class="sxs-lookup"><span data-stu-id="f3896-111">_hcharset_</span></span>
  
> <span data-ttu-id="f3896-112">实时在 Windows Mail mimeole 中定义的字符集的句柄。</span><span class="sxs-lookup"><span data-stu-id="f3896-112">[in] A handle to a character set as defined in mimeole.h of Windows Mail.</span></span> <span data-ttu-id="f3896-113">指定**null**以指定不希望应用任何特定的字符集。</span><span class="sxs-lookup"><span data-stu-id="f3896-113">Specify **null** to specify that you do not want to apply any specific character set.</span></span> <span data-ttu-id="f3896-114">对于非**null**值, 请使用函数 (如[MimeOleGetCodePageCharset](https://msdn.microsoft.com/library/ms714746%28VS.85%29.aspx) ) 获取字符集的句柄。</span><span class="sxs-lookup"><span data-stu-id="f3896-114">For non- **null** values, use a function such as [MimeOleGetCodePageCharset](https://msdn.microsoft.com/library/ms714746%28VS.85%29.aspx) to obtain a handle to the character set.</span></span> 
    
 <span data-ttu-id="f3896-115">_csetapplytype_</span><span class="sxs-lookup"><span data-stu-id="f3896-115">_csetapplytype_</span></span>
  
> <span data-ttu-id="f3896-116">实时指示如何应用字符集以转换邮件, 如 mimeole 中的 Windows Mail 中所定义。</span><span class="sxs-lookup"><span data-stu-id="f3896-116">[in] Indicates how to apply a character set to convert a message, as defined in mimeole.h of Windows Mail.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="f3896-117">返回值</span><span class="sxs-lookup"><span data-stu-id="f3896-117">Return value</span></span>

<span data-ttu-id="f3896-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="f3896-118">S_OK</span></span>
  
> <span data-ttu-id="f3896-119">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="f3896-119">The function call is successful.</span></span>
    
## <a name="mfcmapi-reference"></a><span data-ttu-id="f3896-120">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="f3896-120">MFCMAPI reference</span></span>

<span data-ttu-id="f3896-121">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="f3896-121">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="f3896-122">**文件**</span><span class="sxs-lookup"><span data-stu-id="f3896-122">**File**</span></span>|<span data-ttu-id="f3896-123">**函数**</span><span class="sxs-lookup"><span data-stu-id="f3896-123">**Function**</span></span>|<span data-ttu-id="f3896-124">**备注**</span><span class="sxs-lookup"><span data-stu-id="f3896-124">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f3896-125">MapiMime</span><span class="sxs-lookup"><span data-stu-id="f3896-125">MapiMime.cpp</span></span>  <br/> |<span data-ttu-id="f3896-126">ImportEMLToIMessage</span><span class="sxs-lookup"><span data-stu-id="f3896-126">ImportEMLToIMessage</span></span>  <br/> |<span data-ttu-id="f3896-127">MFCMAPI 使用 MimeToMAPI 将 .eml 文件转换为 MAPI 邮件。</span><span class="sxs-lookup"><span data-stu-id="f3896-127">MFCMAPI uses MimeToMAPI to convert an EML file to a MAPI message.</span></span>  <br/> |
|<span data-ttu-id="f3896-128">MapiMime</span><span class="sxs-lookup"><span data-stu-id="f3896-128">MapiMime.cpp</span></span>  <br/> |<span data-ttu-id="f3896-129">ExportIMessageToEML</span><span class="sxs-lookup"><span data-stu-id="f3896-129">ExportIMessageToEML</span></span>  <br/> |<span data-ttu-id="f3896-130">MFCMAPI 使用 MAPIToMIMEStm 将 MAPI 邮件转换为 .eml 文件。</span><span class="sxs-lookup"><span data-stu-id="f3896-130">MFCMAPI uses MAPIToMIMEStm to convert a MAPI message to an EML file.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="f3896-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f3896-131">See also</span></span>



[<span data-ttu-id="f3896-132">IConverterSession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="f3896-132">IConverterSession : IUnknown</span></span>](iconvertersessioniunknown.md)
  
[<span data-ttu-id="f3896-133">IConverterSession::MAPIToMIMEStm</span><span class="sxs-lookup"><span data-stu-id="f3896-133">IConverterSession::MAPIToMIMEStm</span></span>](iconvertersession-mapitomimestm.md)
  
[<span data-ttu-id="f3896-134">IConverterSession::MIMEToMAPI</span><span class="sxs-lookup"><span data-stu-id="f3896-134">IConverterSession::MIMEToMAPI</span></span>](iconvertersession-mimetomapi.md)
  
[<span data-ttu-id="f3896-135">IConverterSession::SetAdrBook</span><span class="sxs-lookup"><span data-stu-id="f3896-135">IConverterSession::SetAdrBook</span></span>](iconvertersession-setadrbook.md)
  
[<span data-ttu-id="f3896-136">IConverterSession::SetEncoding</span><span class="sxs-lookup"><span data-stu-id="f3896-136">IConverterSession::SetEncoding</span></span>](iconvertersession-setencoding.md)
  
[<span data-ttu-id="f3896-137">IConverterSession::SetSaveFormat</span><span class="sxs-lookup"><span data-stu-id="f3896-137">IConverterSession::SetSaveFormat</span></span>](iconvertersession-setsaveformat.md)
  
[<span data-ttu-id="f3896-138">IConverterSession::SetTextWrapping</span><span class="sxs-lookup"><span data-stu-id="f3896-138">IConverterSession::SetTextWrapping</span></span>](iconvertersession-settextwrapping.md)

