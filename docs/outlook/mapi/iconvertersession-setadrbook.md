---
title: IConverterSessionSetAdrBook
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IConverterSession.SetAdrBook
api_type:
- COM
ms.assetid: d276ab19-17f4-01c7-4b44-b578e631b5fe
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7645208e6a0256957deb3a71ba3e04ad125a6b61
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429192"
---
# <a name="iconvertersessionsetadrbook"></a><span data-ttu-id="639b3-103">IConverterSession::SetAdrBook</span><span class="sxs-lookup"><span data-stu-id="639b3-103">IConverterSession::SetAdrBook</span></span>

  
  
<span data-ttu-id="639b3-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="639b3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="639b3-105">指定 mapi 到 mime 转换器在将 MAPI 邮件转换为 MIME 流时用于解析不明确地址的可选 MAPI 通讯簿。</span><span class="sxs-lookup"><span data-stu-id="639b3-105">Specifies an optional MAPI Address Book that the MAPI to MIME converter uses to resolve ambiguous addresses when converting a MAPI message to a MIME stream.</span></span>
  
```cpp
HRESULT IConverterSession::SetAdrBook( 
LPADRBOOK pab); 
```

## <a name="parameters"></a><span data-ttu-id="639b3-106">参数</span><span class="sxs-lookup"><span data-stu-id="639b3-106">Parameters</span></span>

 <span data-ttu-id="639b3-107">_.pab_</span><span class="sxs-lookup"><span data-stu-id="639b3-107">_pab_</span></span>
  
> <span data-ttu-id="639b3-108">实时指向要在 MAPI 到 MIME 转换中使用的[IAddrBook: IMAPIProp](iaddrbookimapiprop.md)接口的指针。</span><span class="sxs-lookup"><span data-stu-id="639b3-108">[in] Pointer to an [IAddrBook : IMAPIProp](iaddrbookimapiprop.md) interface to be used in the MAPI to MIME conversion.</span></span> <span data-ttu-id="639b3-109">当不再需要通讯簿时, 将此参数设置为**null** ;这将释放接口, 并将转换器重置为不使用任何通讯簿。</span><span class="sxs-lookup"><span data-stu-id="639b3-109">Set this parameter to **null** when you no longer need the Address Book; this releases the interface and resets the converter to not using any Address Book.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="639b3-110">返回值</span><span class="sxs-lookup"><span data-stu-id="639b3-110">Return value</span></span>

<span data-ttu-id="639b3-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="639b3-111">S_OK</span></span>
  
> <span data-ttu-id="639b3-112">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="639b3-112">The function call is successful.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="639b3-113">说明</span><span class="sxs-lookup"><span data-stu-id="639b3-113">Remarks</span></span>

<span data-ttu-id="639b3-114">将 MAPI 邮件转换为 MIME 流通常不需要登录 MAPI 配置文件。</span><span class="sxs-lookup"><span data-stu-id="639b3-114">Converting a MAPI message to MIME stream generally does not require logging on to a MAPI profile.</span></span> <span data-ttu-id="639b3-115">但是, 指定要转换的 MAPI 通讯簿需要登录到配置文件才能获取通讯簿。</span><span class="sxs-lookup"><span data-stu-id="639b3-115">However, specifying a MAPI Address Book for conversion requires logging on to a profile to obtain the Address Book.</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="639b3-116">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="639b3-116">MFCMAPI reference</span></span>

<span data-ttu-id="639b3-117">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="639b3-117">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="639b3-118">**文件**</span><span class="sxs-lookup"><span data-stu-id="639b3-118">**File**</span></span>|<span data-ttu-id="639b3-119">**函数**</span><span class="sxs-lookup"><span data-stu-id="639b3-119">**Function**</span></span>|<span data-ttu-id="639b3-120">**备注**</span><span class="sxs-lookup"><span data-stu-id="639b3-120">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="639b3-121">MapiMime</span><span class="sxs-lookup"><span data-stu-id="639b3-121">MapiMime.cpp</span></span>  <br/> |<span data-ttu-id="639b3-122">ImportEMLToIMessage</span><span class="sxs-lookup"><span data-stu-id="639b3-122">ImportEMLToIMessage</span></span>  <br/> |<span data-ttu-id="639b3-123">MFCMAPI 使用 MimeToMAPI 将 .eml 文件转换为 MAPI 邮件。</span><span class="sxs-lookup"><span data-stu-id="639b3-123">MFCMAPI uses MimeToMAPI to convert an EML file to a MAPI message.</span></span>  <br/> |
|<span data-ttu-id="639b3-124">MapiMime</span><span class="sxs-lookup"><span data-stu-id="639b3-124">MapiMime.cpp</span></span>  <br/> |<span data-ttu-id="639b3-125">ExportIMessageToEML</span><span class="sxs-lookup"><span data-stu-id="639b3-125">ExportIMessageToEML</span></span>  <br/> |<span data-ttu-id="639b3-126">MFCMAPI 使用 MAPIToMIMEStm 将 MAPI 邮件转换为 .eml 文件。</span><span class="sxs-lookup"><span data-stu-id="639b3-126">MFCMAPI uses MAPIToMIMEStm to convert a MAPI message to an EML file.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="639b3-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="639b3-127">See also</span></span>



[<span data-ttu-id="639b3-128">IConverterSession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="639b3-128">IConverterSession : IUnknown</span></span>](iconvertersessioniunknown.md)
  
[<span data-ttu-id="639b3-129">IConverterSession::MAPIToMIMEStm</span><span class="sxs-lookup"><span data-stu-id="639b3-129">IConverterSession::MAPIToMIMEStm</span></span>](iconvertersession-mapitomimestm.md)
  
[<span data-ttu-id="639b3-130">IConverterSession::MIMEToMAPI</span><span class="sxs-lookup"><span data-stu-id="639b3-130">IConverterSession::MIMEToMAPI</span></span>](iconvertersession-mimetomapi.md)
  
[<span data-ttu-id="639b3-131">IConverterSession::SetCharSet</span><span class="sxs-lookup"><span data-stu-id="639b3-131">IConverterSession::SetCharSet</span></span>](iconvertersession-setcharset.md)
  
[<span data-ttu-id="639b3-132">IConverterSession::SetEncoding</span><span class="sxs-lookup"><span data-stu-id="639b3-132">IConverterSession::SetEncoding</span></span>](iconvertersession-setencoding.md)
  
[<span data-ttu-id="639b3-133">IConverterSession::SetSaveFormat</span><span class="sxs-lookup"><span data-stu-id="639b3-133">IConverterSession::SetSaveFormat</span></span>](iconvertersession-setsaveformat.md)
  
[<span data-ttu-id="639b3-134">IConverterSession::SetTextWrapping</span><span class="sxs-lookup"><span data-stu-id="639b3-134">IConverterSession::SetTextWrapping</span></span>](iconvertersession-settextwrapping.md)

