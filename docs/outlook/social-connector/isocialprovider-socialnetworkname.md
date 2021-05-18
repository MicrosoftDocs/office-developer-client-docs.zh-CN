---
title: ISocialProviderSocialNetworkName
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 96f32db2-d654-4e72-88d1-ef955e3ff42b
description: 返回一个代表社交网络名称的字符串。
ms.openlocfilehash: 5a6240fa6e609eec8498456fe56c83a761fadab0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406876"
---
# <a name="isocialprovidersocialnetworkname"></a><span data-ttu-id="76f4a-103">ISocialProvider::SocialNetworkName</span><span class="sxs-lookup"><span data-stu-id="76f4a-103">ISocialProvider::SocialNetworkName</span></span>

<span data-ttu-id="76f4a-104">返回一个代表社交网络名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="76f4a-104">Returns a string that represents the social network name.</span></span> 
  
```cpp
[propget] HRESULT _stdcall SocialNetworkName([out, retval] BSTR* networkName);
```

## <a name="property-value"></a><span data-ttu-id="76f4a-105">属性值</span><span class="sxs-lookup"><span data-stu-id="76f4a-105">Property value</span></span>

<span data-ttu-id="76f4a-106">包含社交网络名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="76f4a-106">A string that contains the social network name.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="76f4a-107">备注</span><span class="sxs-lookup"><span data-stu-id="76f4a-107">Remarks</span></span>

<span data-ttu-id="76f4a-108">OutlookSOCIAL Connector (OSC) 提供商应本地化社交网络名称。</span><span class="sxs-lookup"><span data-stu-id="76f4a-108">Outlook Social Connector (OSC) providers should localize the social network name.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="76f4a-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="76f4a-109">See also</span></span>

- [<span data-ttu-id="76f4a-110">ISocialProvider : IUnknown</span><span class="sxs-lookup"><span data-stu-id="76f4a-110">ISocialProvider : IUnknown</span></span>](isocialprovideriunknown.md)

