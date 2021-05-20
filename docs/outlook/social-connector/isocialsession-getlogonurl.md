---
title: ISocialSessionGetLogonUrl
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: d61bab07-acb3-433b-8783-c3fe110a5582
description: 获取一个字符串，代表在 Web 身份验证期间用于向用户显示基于浏览器的表单的 URL。
ms.openlocfilehash: 83867282922ea136b9673609cc2ba2f1a206f6ab
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427911"
---
# <a name="isocialsessiongetlogonurl"></a><span data-ttu-id="34c5c-103">ISocialSession::GetLogonUrl</span><span class="sxs-lookup"><span data-stu-id="34c5c-103">ISocialSession::GetLogonUrl</span></span>

<span data-ttu-id="34c5c-104">获取一个字符串，代表在 Web 身份验证期间用于向用户显示基于浏览器的表单的 URL。</span><span class="sxs-lookup"><span data-stu-id="34c5c-104">Gets a string that represents a URL that is used for presenting a browser-based form to the user during web authentication.</span></span>
  
```cpp
HRESULT _stdcall GetLogonUrl([out, retval] BSTR* url);
```

## <a name="parameters"></a><span data-ttu-id="34c5c-105">参数</span><span class="sxs-lookup"><span data-stu-id="34c5c-105">Parameters</span></span>

<span data-ttu-id="34c5c-106">_url_</span><span class="sxs-lookup"><span data-stu-id="34c5c-106">_url_</span></span>
  
> <span data-ttu-id="34c5c-107">[out]一个字符串，包含用于 Web 身份验证的表单的 URL。</span><span class="sxs-lookup"><span data-stu-id="34c5c-107">[out] A string that contains a URL for the form used in web authentication.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="34c5c-108">备注</span><span class="sxs-lookup"><span data-stu-id="34c5c-108">Remarks</span></span>

<span data-ttu-id="34c5c-109">向用户显示表单后，使用 _connectIn_ 参数的空字符串调用 [ISocialSession：：LogonWeb](isocialsession-logonweb.md)方法。</span><span class="sxs-lookup"><span data-stu-id="34c5c-109">After the form is presented to the user, the [ISocialSession::LogonWeb](isocialsession-logonweb.md) method is called with an empty string for the  _connectIn_ parameter.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="34c5c-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="34c5c-110">See also</span></span>

- [<span data-ttu-id="34c5c-111">ISocialSession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="34c5c-111">ISocialSession : IUnknown</span></span>](isocialsessioniunknown.md)

