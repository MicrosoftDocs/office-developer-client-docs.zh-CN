---
title: ISocialProviderDefaultSiteUrls
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 322ea2e9-d6c9-48f9-a927-7162346d16a4
description: 返回一个字符串数组, 这些字符串指定 Outlook Social Connector (.osc) 提供程序的网站 url。
ms.openlocfilehash: 34d779d5eb42b81a14c5236685104e9ef4fe36f2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32285854"
---
# <a name="isocialproviderdefaultsiteurls"></a><span data-ttu-id="ee90b-103">ISocialProvider::DefaultSiteUrls</span><span class="sxs-lookup"><span data-stu-id="ee90b-103">ISocialProvider::DefaultSiteUrls</span></span>

<span data-ttu-id="ee90b-104">返回一个字符串数组, 这些字符串指定 Outlook Social Connector (.osc) 提供程序的网站 url。</span><span class="sxs-lookup"><span data-stu-id="ee90b-104">Returns an array of strings that specify site URLs for the Outlook Social Connector (OSC) provider.</span></span>
  
```cpp
[propget] HRESULT _stdcall DefaultSiteUrls([out, retval] SAFEARRAY(BSTR)* siteUrls);
```

## <a name="property-value"></a><span data-ttu-id="ee90b-105">属性值</span><span class="sxs-lookup"><span data-stu-id="ee90b-105">Property value</span></span>

<span data-ttu-id="ee90b-106">指向结构的指针, 该结构指定代表 .osc 提供程序的网站 url 的字符串数组。</span><span class="sxs-lookup"><span data-stu-id="ee90b-106">A pointer to a structure that specifies an array of strings that represent site URLs for the OSC provider.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="ee90b-107">注解</span><span class="sxs-lookup"><span data-stu-id="ee90b-107">Remarks</span></span>

<span data-ttu-id="ee90b-108">提供程序可支持多个网站 url。</span><span class="sxs-lookup"><span data-stu-id="ee90b-108">A provider can support multiple site URLs.</span></span> <span data-ttu-id="ee90b-109">.osc 将[ISocialSession:: SiteUrl](isocialsession-siteurl.md)属性设置为通知提供程序所选的网站 URL。</span><span class="sxs-lookup"><span data-stu-id="ee90b-109">The OSC sets the [ISocialSession::SiteUrl](isocialsession-siteurl.md) property to inform the provider of the selected site URL.</span></span> 
  
<span data-ttu-id="ee90b-110">.osc 使用数组的第一个元素作为默认网站 URL。</span><span class="sxs-lookup"><span data-stu-id="ee90b-110">The OSC uses the first element of the array as the default site URL.</span></span> <span data-ttu-id="ee90b-111">提供程序可以返回网站 URL 数组中的其他元素, 但 .osc 不使用它们。</span><span class="sxs-lookup"><span data-stu-id="ee90b-111">A provider can return additional elements in the site URL array, but the OSC does not use them.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="ee90b-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ee90b-112">See also</span></span>

- [<span data-ttu-id="ee90b-113">ISocialProvider : IUnknown</span><span class="sxs-lookup"><span data-stu-id="ee90b-113">ISocialProvider : IUnknown</span></span>](isocialprovideriunknown.md)

