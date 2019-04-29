---
title: ISocialSessionLoggedOnUserName
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: c0e7b788-3198-499c-ae21-b2032f929ed9
description: 返回一个字符串, 表示登录时使用的用户名。
ms.openlocfilehash: 6f0d2c68b1af9e7c96f2cd86dc798518e432c7cf
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437292"
---
# <a name="isocialsessionloggedonusername"></a><span data-ttu-id="aff22-103">ISocialSession::LoggedOnUserName</span><span class="sxs-lookup"><span data-stu-id="aff22-103">ISocialSession::LoggedOnUserName</span></span>

<span data-ttu-id="aff22-104">返回一个字符串, 表示登录时使用的用户名。</span><span class="sxs-lookup"><span data-stu-id="aff22-104">Returns a string that represents the user name that is used when logging on.</span></span>
  
```cpp
[propget] HRESULT _stdcall LoggedOnUserName([out, retval] BSTR* result);
```

## <a name="property-value"></a><span data-ttu-id="aff22-105">属性值</span><span class="sxs-lookup"><span data-stu-id="aff22-105">Property value</span></span>

<span data-ttu-id="aff22-106">一个字符串, 表示登录用户的用户名。</span><span class="sxs-lookup"><span data-stu-id="aff22-106">A string that represents the user name of the logged-on user.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="aff22-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aff22-107">See also</span></span>

- [<span data-ttu-id="aff22-108">ISocialSession::LoggedOnUserID</span><span class="sxs-lookup"><span data-stu-id="aff22-108">ISocialSession::LoggedOnUserID</span></span>](isocialsession-loggedonuserid.md)  
- [<span data-ttu-id="aff22-109">ISocialSession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="aff22-109">ISocialSession : IUnknown</span></span>](isocialsessioniunknown.md)

