---
title: ISocialProviderSocialNetworkName
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 96f32db2-d654-4e72-88d1-ef955e3ff42b
description: 返回 string 类型的值，该值代表社交网络名称。
ms.openlocfilehash: 78424db0940b2c23914355b2b20ba5bc531ad3ca
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779225"
---
# <a name="isocialprovidersocialnetworkname"></a><span data-ttu-id="63b97-103">ISocialProvider::SocialNetworkName</span><span class="sxs-lookup"><span data-stu-id="63b97-103">ISocialProvider::SocialNetworkName</span></span>

<span data-ttu-id="63b97-104">返回 string 类型的值，该值代表社交网络名称。</span><span class="sxs-lookup"><span data-stu-id="63b97-104">Returns a string that represents the social network name.</span></span> 
  
```cpp
[propget] HRESULT _stdcall SocialNetworkName([out, retval] BSTR* networkName);
```

## <a name="property-value"></a><span data-ttu-id="63b97-105">属性值</span><span class="sxs-lookup"><span data-stu-id="63b97-105">Property value</span></span>

<span data-ttu-id="63b97-106">一个字符串，包含社交网络的名称。</span><span class="sxs-lookup"><span data-stu-id="63b97-106">A string that contains the social network name.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="63b97-107">说明</span><span class="sxs-lookup"><span data-stu-id="63b97-107">Remarks</span></span>

<span data-ttu-id="63b97-108">Outlook Social Connector (OSC) 提供程序应本地化社交网络名称。</span><span class="sxs-lookup"><span data-stu-id="63b97-108">Outlook Social Connector (OSC) providers should localize the social network name.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="63b97-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="63b97-109">See also</span></span>

- [<span data-ttu-id="63b97-110">ISocialProvider : IUnknown</span><span class="sxs-lookup"><span data-stu-id="63b97-110">ISocialProvider : IUnknown</span></span>](isocialprovideriunknown.md)

