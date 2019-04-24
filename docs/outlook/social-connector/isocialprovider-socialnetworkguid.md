---
title: ISocialProviderSocialNetworkGuid
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 3c07f71d-b906-4a7f-b20a-4a7f558dbf11
description: 返回表示社交网络的唯一标识符的 GUID。
ms.openlocfilehash: fc96799ada773cc7260e156d3e2ab8423b73884b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32285510"
---
# <a name="isocialprovidersocialnetworkguid"></a><span data-ttu-id="66878-103">ISocialProvider::SocialNetworkGuid</span><span class="sxs-lookup"><span data-stu-id="66878-103">ISocialProvider::SocialNetworkGuid</span></span>

<span data-ttu-id="66878-104">返回表示社交网络的唯一标识符的 GUID。</span><span class="sxs-lookup"><span data-stu-id="66878-104">Returns a GUID that represents a unique identifier for the social network.</span></span>
  
```cpp
[propget] HRESULT _stdcall SocialNetworkGuid([out, retval] GUID* guid);
```

## <a name="property-value"></a><span data-ttu-id="66878-105">属性值</span><span class="sxs-lookup"><span data-stu-id="66878-105">Property value</span></span>

<span data-ttu-id="66878-106">指向表示社交网络的唯一标识符的 GUID 值的指针。</span><span class="sxs-lookup"><span data-stu-id="66878-106">A pointer to a GUID value that represents a unique identifier for the social network.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="66878-107">注解</span><span class="sxs-lookup"><span data-stu-id="66878-107">Remarks</span></span>

<span data-ttu-id="66878-108">GUID 必须是不可变的, 并且不得更改, 即使提供程序版本发生更改也是如此。</span><span class="sxs-lookup"><span data-stu-id="66878-108">The GUID must be immutable and must not change even if the provider version changes.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="66878-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="66878-109">See also</span></span>

- [<span data-ttu-id="66878-110">ISocialProvider : IUnknown</span><span class="sxs-lookup"><span data-stu-id="66878-110">ISocialProvider : IUnknown</span></span>](isocialprovideriunknown.md)

