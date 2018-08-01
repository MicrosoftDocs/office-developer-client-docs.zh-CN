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
ms.openlocfilehash: e6880a32e30b8f208ce5ba0a2d30e635ff464461
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775279"
---
# <a name="iconvertersessionsetadrbook"></a><span data-ttu-id="d4d25-103">IConverterSession::SetAdrBook</span><span class="sxs-lookup"><span data-stu-id="d4d25-103">IConverterSession::SetAdrBook</span></span>

  
  
<span data-ttu-id="d4d25-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="d4d25-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="d4d25-105">指定到 MIME 转换器 MAPI 解析不明确的地址，将 MAPI 邮件转换为 MIME 流时使用可选 MAPI 通讯簿。</span><span class="sxs-lookup"><span data-stu-id="d4d25-105">Specifies an optional MAPI Address Book that the MAPI to MIME converter uses to resolve ambiguous addresses when converting a MAPI message to a MIME stream.</span></span>
  
```cpp
HRESULT IConverterSession::SetAdrBook( 
LPADRBOOK pab); 
```

## <a name="parameters"></a><span data-ttu-id="d4d25-106">参数</span><span class="sxs-lookup"><span data-stu-id="d4d25-106">Parameters</span></span>

 <span data-ttu-id="d4d25-107">_pab_</span><span class="sxs-lookup"><span data-stu-id="d4d25-107">_pab_</span></span>
  
> <span data-ttu-id="d4d25-108">[in]指向[IAddrBook: IMAPIProp](iaddrbookimapiprop.md)接口用于与 MIME 转换 MAPI。</span><span class="sxs-lookup"><span data-stu-id="d4d25-108">[in] Pointer to an [IAddrBook : IMAPIProp](iaddrbookimapiprop.md) interface to be used in the MAPI to MIME conversion.</span></span> <span data-ttu-id="d4d25-109">将此参数设置为**null** ，当不再需要通讯簿中;这释放接口并将转换器重置为不使用任何通讯簿。</span><span class="sxs-lookup"><span data-stu-id="d4d25-109">Set this parameter to **null** when you no longer need the Address Book; this releases the interface and resets the converter to not using any Address Book.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="d4d25-110">返回值</span><span class="sxs-lookup"><span data-stu-id="d4d25-110">Return value</span></span>

<span data-ttu-id="d4d25-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="d4d25-111">S_OK</span></span>
  
> <span data-ttu-id="d4d25-112">成功函数调用。</span><span class="sxs-lookup"><span data-stu-id="d4d25-112">The function call is successful.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="d4d25-113">说明</span><span class="sxs-lookup"><span data-stu-id="d4d25-113">Remarks</span></span>

<span data-ttu-id="d4d25-114">转换 MAPI 邮件 MIME 流通常不需要登录到 MAPI 配置文件。</span><span class="sxs-lookup"><span data-stu-id="d4d25-114">Converting a MAPI message to MIME stream generally does not require logging on to a MAPI profile.</span></span> <span data-ttu-id="d4d25-115">但是，指定转换的 MAPI 通讯簿需要登录到一个配置文件来获取通讯簿。</span><span class="sxs-lookup"><span data-stu-id="d4d25-115">However, specifying a MAPI Address Book for conversion requires logging on to a profile to obtain the Address Book.</span></span>
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="d4d25-116">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="d4d25-116">MFCMAPI reference</span></span>

<span data-ttu-id="d4d25-117">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="d4d25-117">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="d4d25-118">**文件**</span><span class="sxs-lookup"><span data-stu-id="d4d25-118">**File**</span></span>|<span data-ttu-id="d4d25-119">**函数**</span><span class="sxs-lookup"><span data-stu-id="d4d25-119">**Function**</span></span>|<span data-ttu-id="d4d25-120">**Comment**</span><span class="sxs-lookup"><span data-stu-id="d4d25-120">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d4d25-121">MapiMime.cpp</span><span class="sxs-lookup"><span data-stu-id="d4d25-121">MapiMime.cpp</span></span>  <br/> |<span data-ttu-id="d4d25-122">ImportEMLToIMessage</span><span class="sxs-lookup"><span data-stu-id="d4d25-122">ImportEMLToIMessage</span></span>  <br/> |<span data-ttu-id="d4d25-123">MFCMAPI 使用 MimeToMAPI 将 EML 文件转换为 MAPI 邮件。</span><span class="sxs-lookup"><span data-stu-id="d4d25-123">MFCMAPI uses MimeToMAPI to convert an EML file to a MAPI message.</span></span>  <br/> |
|<span data-ttu-id="d4d25-124">MapiMime.cpp</span><span class="sxs-lookup"><span data-stu-id="d4d25-124">MapiMime.cpp</span></span>  <br/> |<span data-ttu-id="d4d25-125">ExportIMessageToEML</span><span class="sxs-lookup"><span data-stu-id="d4d25-125">ExportIMessageToEML</span></span>  <br/> |<span data-ttu-id="d4d25-126">MFCMAPI 使用 MAPIToMIMEStm 将转换为 EML 文件的 MAPI 邮件。</span><span class="sxs-lookup"><span data-stu-id="d4d25-126">MFCMAPI uses MAPIToMIMEStm to convert a MAPI message to an EML file.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="d4d25-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d4d25-127">See also</span></span>



[<span data-ttu-id="d4d25-128">IConverterSession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="d4d25-128">IConverterSession : IUnknown</span></span>](iconvertersessioniunknown.md)
  
[<span data-ttu-id="d4d25-129">IConverterSession::MAPIToMIMEStm</span><span class="sxs-lookup"><span data-stu-id="d4d25-129">IConverterSession::MAPIToMIMEStm</span></span>](iconvertersession-mapitomimestm.md)
  
[<span data-ttu-id="d4d25-130">IConverterSession::MIMEToMAPI</span><span class="sxs-lookup"><span data-stu-id="d4d25-130">IConverterSession::MIMEToMAPI</span></span>](iconvertersession-mimetomapi.md)
  
[<span data-ttu-id="d4d25-131">IConverterSession::SetCharSet</span><span class="sxs-lookup"><span data-stu-id="d4d25-131">IConverterSession::SetCharSet</span></span>](iconvertersession-setcharset.md)
  
[<span data-ttu-id="d4d25-132">IConverterSession::SetEncoding</span><span class="sxs-lookup"><span data-stu-id="d4d25-132">IConverterSession::SetEncoding</span></span>](iconvertersession-setencoding.md)
  
[<span data-ttu-id="d4d25-133">IConverterSession::SetSaveFormat</span><span class="sxs-lookup"><span data-stu-id="d4d25-133">IConverterSession::SetSaveFormat</span></span>](iconvertersession-setsaveformat.md)
  
[<span data-ttu-id="d4d25-134">IConverterSession::SetTextWrapping</span><span class="sxs-lookup"><span data-stu-id="d4d25-134">IConverterSession::SetTextWrapping</span></span>](iconvertersession-settextwrapping.md)

