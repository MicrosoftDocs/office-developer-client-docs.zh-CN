---
title: ISocialProviderSocialNetworkGuid
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 3c07f71d-b906-4a7f-b20a-4a7f558dbf11
description: 返回一个 GUID 值，该值代表社交网络的唯一标识符。
ms.openlocfilehash: 5ff10d51fab03c3bca3eead52848088f2cd80bba
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779240"
---
# <a name="isocialprovidersocialnetworkguid"></a><span data-ttu-id="09f3a-103">ISocialProvider::SocialNetworkGuid</span><span class="sxs-lookup"><span data-stu-id="09f3a-103">ISocialProvider::SocialNetworkGuid</span></span>

<span data-ttu-id="09f3a-104">返回一个 GUID 值，该值代表社交网络的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="09f3a-104">Returns a GUID that represents a unique identifier for the social network.</span></span>
  
```cpp
[propget] HRESULT _stdcall SocialNetworkGuid([out, retval] GUID* guid);
```

## <a name="property-value"></a><span data-ttu-id="09f3a-105">属性值</span><span class="sxs-lookup"><span data-stu-id="09f3a-105">Property value</span></span>

<span data-ttu-id="09f3a-106">一个指向 GUID 值，该值代表社交网络的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="09f3a-106">A pointer to a GUID value that represents a unique identifier for the social network.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="09f3a-107">备注</span><span class="sxs-lookup"><span data-stu-id="09f3a-107">Remarks</span></span>

<span data-ttu-id="09f3a-108">GUID 必须变，并且必须未更改，即使该提供程序版本更改。</span><span class="sxs-lookup"><span data-stu-id="09f3a-108">The GUID must be immutable and must not change even if the provider version changes.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="09f3a-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="09f3a-109">See also</span></span>

- [<span data-ttu-id="09f3a-110">ISocialProvider: IUnknown</span><span class="sxs-lookup"><span data-stu-id="09f3a-110">ISocialProvider : IUnknown</span></span>](isocialprovideriunknown.md)

