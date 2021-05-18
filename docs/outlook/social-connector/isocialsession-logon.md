---
title: ISocialSessionLogon
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 8b3c9a23-6378-4054-ad1c-193fc15c473c
description: 使用指定的用户名和密码登录到社交网络网站。
ms.openlocfilehash: 7915097e456d6fafa713901f8074e6531bfaa001
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32361038"
---
# <a name="isocialsessionlogon"></a><span data-ttu-id="38530-103">ISocialSession::Logon</span><span class="sxs-lookup"><span data-stu-id="38530-103">ISocialSession::Logon</span></span>

<span data-ttu-id="38530-104">使用指定的用户名和密码登录到社交网络网站。</span><span class="sxs-lookup"><span data-stu-id="38530-104">Logs on to the social network site by using the specified user name and password.</span></span>
  
```cpp
HRESULT _stdcall Logon([in] BSTR username, [in] BSTR password);
```

## <a name="parameters"></a><span data-ttu-id="38530-105">参数</span><span class="sxs-lookup"><span data-stu-id="38530-105">Parameters</span></span>

<span data-ttu-id="38530-106">_username_</span><span class="sxs-lookup"><span data-stu-id="38530-106">_username_</span></span>
  
> <span data-ttu-id="38530-107">[in]包含要登录的用户名的字符串。</span><span class="sxs-lookup"><span data-stu-id="38530-107">[in] A string that contains the user name to log on.</span></span>
    
<span data-ttu-id="38530-108">_password_</span><span class="sxs-lookup"><span data-stu-id="38530-108">_password_</span></span>
  
> <span data-ttu-id="38530-109">[in]包含要登录的密码的字符串。</span><span class="sxs-lookup"><span data-stu-id="38530-109">[in] A string that contains the password to log on.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="38530-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="38530-110">See also</span></span>

- [<span data-ttu-id="38530-111">ISocialSession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="38530-111">ISocialSession : IUnknown</span></span>](isocialsessioniunknown.md)

