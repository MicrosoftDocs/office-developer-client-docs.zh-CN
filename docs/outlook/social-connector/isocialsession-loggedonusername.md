---
title: ISocialSessionLoggedOnUserName
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: c0e7b788-3198-499c-ae21-b2032f929ed9
description: 返回一个字符串，表示在登录时使用的用户名。
ms.openlocfilehash: 02485ad2a510a81c64406ea6ec9a0f85c0e4d2f9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779356"
---
# <a name="isocialsessionloggedonusername"></a><span data-ttu-id="08a38-103">ISocialSession::LoggedOnUserName</span><span class="sxs-lookup"><span data-stu-id="08a38-103">ISocialSession::LoggedOnUserName</span></span>

<span data-ttu-id="08a38-104">返回一个字符串，表示在登录时使用的用户名。</span><span class="sxs-lookup"><span data-stu-id="08a38-104">Returns a string that represents the user name that is used when logging on.</span></span>
  
```cpp
[propget] HRESULT _stdcall LoggedOnUserName([out, retval] BSTR* result);
```

## <a name="property-value"></a><span data-ttu-id="08a38-105">属性值</span><span class="sxs-lookup"><span data-stu-id="08a38-105">Property value</span></span>

<span data-ttu-id="08a38-106">一个字符串值，该值代表登录用户的用户名。</span><span class="sxs-lookup"><span data-stu-id="08a38-106">A string that represents the user name of the logged-on user.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="08a38-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="08a38-107">See also</span></span>

- [<span data-ttu-id="08a38-108">ISocialSession::LoggedOnUserID</span><span class="sxs-lookup"><span data-stu-id="08a38-108">ISocialSession::LoggedOnUserID</span></span>](isocialsession-loggedonuserid.md)  
- [<span data-ttu-id="08a38-109">ISocialSession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="08a38-109">ISocialSession : IUnknown</span></span>](isocialsessioniunknown.md)

