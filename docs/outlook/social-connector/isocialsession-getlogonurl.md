---
title: ISocialSessionGetLogonUrl
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: d61bab07-acb3-433b-8783-c3fe110a5582
description: 获取一个字符串，表示用于 web 身份验证过程中显示给用户的基于浏览器的表单的 URL。
ms.openlocfilehash: 343919f194b238fc519bb8f6d808b44a8ab6e7b9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779228"
---
# <a name="isocialsessiongetlogonurl"></a><span data-ttu-id="4c15c-103">ISocialSession::GetLogonUrl</span><span class="sxs-lookup"><span data-stu-id="4c15c-103">ISocialSession::GetLogonUrl</span></span>

<span data-ttu-id="4c15c-104">获取一个字符串，表示用于 web 身份验证过程中显示给用户的基于浏览器的表单的 URL。</span><span class="sxs-lookup"><span data-stu-id="4c15c-104">Gets a string that represents a URL that is used for presenting a browser-based form to the user during web authentication.</span></span>
  
```cpp
HRESULT _stdcall GetLogonUrl([out, retval] BSTR* url);
```

## <a name="parameters"></a><span data-ttu-id="4c15c-105">参数</span><span class="sxs-lookup"><span data-stu-id="4c15c-105">Parameters</span></span>

<span data-ttu-id="4c15c-106">_url_</span><span class="sxs-lookup"><span data-stu-id="4c15c-106">_url_</span></span>
  
> <span data-ttu-id="4c15c-107">[输出]一个字符串，包含 web 身份验证中使用的格式的 URL。</span><span class="sxs-lookup"><span data-stu-id="4c15c-107">[out] A string that contains a URL for the form used in web authentication.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="4c15c-108">备注</span><span class="sxs-lookup"><span data-stu-id="4c15c-108">Remarks</span></span>

<span data-ttu-id="4c15c-109">向用户显示窗体后，则[ISocialSession::LogonWeb](isocialsession-logonweb.md)方法_connectIn_参数调用与为空字符串。</span><span class="sxs-lookup"><span data-stu-id="4c15c-109">After the form is presented to the user, the [ISocialSession::LogonWeb](isocialsession-logonweb.md) method is called with an empty string for the  _connectIn_ parameter.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="4c15c-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4c15c-110">See also</span></span>

- [<span data-ttu-id="4c15c-111">ISocialSession: IUnknown</span><span class="sxs-lookup"><span data-stu-id="4c15c-111">ISocialSession : IUnknown</span></span>](isocialsessioniunknown.md)

