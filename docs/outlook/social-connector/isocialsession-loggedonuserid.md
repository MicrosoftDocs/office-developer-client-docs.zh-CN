---
title: ISocialSessionLoggedOnUserID
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 54377ab4-8c69-4d7a-b9b7-278241823c8d
description: 返回一个字符串, 表示当前登录的用户的社交网络用户 ID。
ms.openlocfilehash: edb61569829f7690c2284a083d2cbd5cfe2d32a8
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32285284"
---
# <a name="isocialsessionloggedonuserid"></a><span data-ttu-id="a19c1-103">ISocialSession::LoggedOnUserID</span><span class="sxs-lookup"><span data-stu-id="a19c1-103">ISocialSession::LoggedOnUserID</span></span>

<span data-ttu-id="a19c1-104">返回一个字符串, 表示当前登录的用户的社交网络用户 ID。</span><span class="sxs-lookup"><span data-stu-id="a19c1-104">Returns a string that represents the social network user ID of the user who is currently logged on.</span></span> 
  
```cpp
[propget] HRESULT _stdcall LoggedOnUserID([out, retval] BSTR* result);
```

## <a name="property-value"></a><span data-ttu-id="a19c1-105">属性值</span><span class="sxs-lookup"><span data-stu-id="a19c1-105">Property value</span></span>

<span data-ttu-id="a19c1-106">一个包含已登录用户的社交网络用户 ID 的字符串。</span><span class="sxs-lookup"><span data-stu-id="a19c1-106">A string that contains the social network user ID of the logged-on user.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a19c1-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a19c1-107">See also</span></span>

- [<span data-ttu-id="a19c1-108">ISocialSession::LoggedOnUserName</span><span class="sxs-lookup"><span data-stu-id="a19c1-108">ISocialSession::LoggedOnUserName</span></span>](isocialsession-loggedonusername.md)  
- [<span data-ttu-id="a19c1-109">ISocialSession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="a19c1-109">ISocialSession : IUnknown</span></span>](isocialsessioniunknown.md)

