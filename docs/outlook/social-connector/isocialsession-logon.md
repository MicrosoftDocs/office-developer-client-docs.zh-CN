---
title: ISocialSessionLogon
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 8b3c9a23-6378-4054-ad1c-193fc15c473c
description: 登录到社交网络站点使用指定的用户名和密码。
ms.openlocfilehash: d7a79767f3726f9748ea48839f1e190af2e9ec74
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779236"
---
# <a name="isocialsessionlogon"></a><span data-ttu-id="a4bd0-103">ISocialSession::Logon</span><span class="sxs-lookup"><span data-stu-id="a4bd0-103">ISocialSession::Logon</span></span>

<span data-ttu-id="a4bd0-104">登录到社交网络站点使用指定的用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="a4bd0-104">Logs on to the social network site by using the specified user name and password.</span></span>
  
```cpp
HRESULT _stdcall Logon([in] BSTR username, [in] BSTR password);
```

## <a name="parameters"></a><span data-ttu-id="a4bd0-105">参数</span><span class="sxs-lookup"><span data-stu-id="a4bd0-105">Parameters</span></span>

<span data-ttu-id="a4bd0-106">_用户名_</span><span class="sxs-lookup"><span data-stu-id="a4bd0-106">_username_</span></span>
  
> <span data-ttu-id="a4bd0-107">[in]一个字符串，包含要登录的用户名称。</span><span class="sxs-lookup"><span data-stu-id="a4bd0-107">[in] A string that contains the user name to log on.</span></span>
    
<span data-ttu-id="a4bd0-108">_密码_</span><span class="sxs-lookup"><span data-stu-id="a4bd0-108">_password_</span></span>
  
> <span data-ttu-id="a4bd0-109">[in]一个字符串，包含要登录的密码。</span><span class="sxs-lookup"><span data-stu-id="a4bd0-109">[in] A string that contains the password to log on.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="a4bd0-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a4bd0-110">See also</span></span>

- [<span data-ttu-id="a4bd0-111">ISocialSession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="a4bd0-111">ISocialSession : IUnknown</span></span>](isocialsessioniunknown.md)

