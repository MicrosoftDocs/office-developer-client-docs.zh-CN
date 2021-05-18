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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407870"
---
# <a name="isocialprovidersocialnetworkguid"></a><span data-ttu-id="55b40-103">ISocialProvider::SocialNetworkGuid</span><span class="sxs-lookup"><span data-stu-id="55b40-103">ISocialProvider::SocialNetworkGuid</span></span>

<span data-ttu-id="55b40-104">返回表示社交网络的唯一标识符的 GUID。</span><span class="sxs-lookup"><span data-stu-id="55b40-104">Returns a GUID that represents a unique identifier for the social network.</span></span>
  
```cpp
[propget] HRESULT _stdcall SocialNetworkGuid([out, retval] GUID* guid);
```

## <a name="property-value"></a><span data-ttu-id="55b40-105">属性值</span><span class="sxs-lookup"><span data-stu-id="55b40-105">Property value</span></span>

<span data-ttu-id="55b40-106">指向表示社交网络的唯一标识符的 GUID 值的指针。</span><span class="sxs-lookup"><span data-stu-id="55b40-106">A pointer to a GUID value that represents a unique identifier for the social network.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="55b40-107">备注</span><span class="sxs-lookup"><span data-stu-id="55b40-107">Remarks</span></span>

<span data-ttu-id="55b40-108">GUID 必须是不可变的，并且即使提供程序版本发生更改，也不得更改。</span><span class="sxs-lookup"><span data-stu-id="55b40-108">The GUID must be immutable and must not change even if the provider version changes.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="55b40-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="55b40-109">See also</span></span>

- [<span data-ttu-id="55b40-110">ISocialProvider : IUnknown</span><span class="sxs-lookup"><span data-stu-id="55b40-110">ISocialProvider : IUnknown</span></span>](isocialprovideriunknown.md)

