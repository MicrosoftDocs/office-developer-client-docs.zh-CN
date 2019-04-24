---
title: ISocialSessionGetLoggedOnUser
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: bd6bdaf6-52d5-4308-9c3d-869f6e1a6608
description: 获取一个 ISocialProfile 接口, 该接口表示已登录的用户。
ms.openlocfilehash: 6c15d9d016f7445f8887f7d0fc87a1f36fb99b94
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32285390"
---
# <a name="isocialsessiongetloggedonuser"></a><span data-ttu-id="3f98c-103">ISocialSession::GetLoggedOnUser</span><span class="sxs-lookup"><span data-stu-id="3f98c-103">ISocialSession::GetLoggedOnUser</span></span>

<span data-ttu-id="3f98c-104">获取一个[ISocialProfile](isocialprofileisocialperson.md)接口, 该接口表示已登录的用户。</span><span class="sxs-lookup"><span data-stu-id="3f98c-104">Gets an [ISocialProfile](isocialprofileisocialperson.md) interface that represents the logged-on user.</span></span> 
  
```cpp
HRESULT _stdcall GetLoggedOnUser([out, retval] ISocialProfile** result);
```

## <a name="parameters"></a><span data-ttu-id="3f98c-105">参数</span><span class="sxs-lookup"><span data-stu-id="3f98c-105">Parameters</span></span>

<span data-ttu-id="3f98c-106">_result_</span><span class="sxs-lookup"><span data-stu-id="3f98c-106">_result_</span></span>
  
> <span data-ttu-id="3f98c-107">排除一个**ISocialProfile**接口。</span><span class="sxs-lookup"><span data-stu-id="3f98c-107">[out] An **ISocialProfile** interface.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="3f98c-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3f98c-108">See also</span></span>

- [<span data-ttu-id="3f98c-109">ISocialSession : IUnknown</span><span class="sxs-lookup"><span data-stu-id="3f98c-109">ISocialSession : IUnknown</span></span>](isocialsessioniunknown.md)

