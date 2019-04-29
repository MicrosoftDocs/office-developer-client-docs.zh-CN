---
title: ISocialSessionGetLogonUrl
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: d61bab07-acb3-433b-8783-c3fe110a5582
description: 获取一个字符串, 表示用于在 web 身份验证期间向用户呈现基于浏览器的表单的 URL。
ms.openlocfilehash: 83867282922ea136b9673609cc2ba2f1a206f6ab
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427911"
---
# <a name="isocialsessiongetlogonurl"></a><span data-ttu-id="571c0-103">ISocialSession::GetLogonUrl</span><span class="sxs-lookup"><span data-stu-id="571c0-103">ISocialSession::GetLogonUrl</span></span>

<span data-ttu-id="571c0-104">获取一个字符串, 表示用于在 web 身份验证期间向用户呈现基于浏览器的表单的 URL。</span><span class="sxs-lookup"><span data-stu-id="571c0-104">Gets a string that represents a URL that is used for presenting a browser-based form to the user during web authentication.</span></span>
  
```cpp
HRESULT _stdcall GetLogonUrl([out, retval] BSTR* url);
```

## <a name="parameters"></a><span data-ttu-id="571c0-105">参数</span><span class="sxs-lookup"><span data-stu-id="571c0-105">Parameters</span></span>

<span data-ttu-id="571c0-106">_url_</span><span class="sxs-lookup"><span data-stu-id="571c0-106">_url_</span></span>
  
> <span data-ttu-id="571c0-107">排除包含用于 web 身份验证的表单的 URL 的字符串。</span><span class="sxs-lookup"><span data-stu-id="571c0-107">[out] A string that contains a URL for the form used in web authentication.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="571c0-108">说明</span><span class="sxs-lookup"><span data-stu-id="571c0-108">Remarks</span></span>

<span data-ttu-id="571c0-109">将窗体呈现给用户后, 将调用[ISocialSession:: LogonWeb](isocialsession-logonweb.md)方法, 并将空字符串用于_connectIn_参数。</span><span class="sxs-lookup"><span data-stu-id="571c0-109">After the form is presented to the user, the [ISocialSession::LogonWeb](isocialsession-logonweb.md) method is called with an empty string for the  _connectIn_ parameter.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="571c0-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="571c0-110">See also</span></span>

- [<span data-ttu-id="571c0-111">ISocialSession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="571c0-111">ISocialSession : IUnknown</span></span>](isocialsessioniunknown.md)

