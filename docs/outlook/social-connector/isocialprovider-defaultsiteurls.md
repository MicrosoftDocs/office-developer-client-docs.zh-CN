---
title: ISocialProviderDefaultSiteUrls
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 322ea2e9-d6c9-48f9-a927-7162346d16a4
description: 返回一个 Outlook Social Connector (OSC) 提供程序指定网站 Url 的字符串数组。
ms.openlocfilehash: a2b2e0397c7c67476ac8067a53e2acbd4eddf270
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779211"
---
# <a name="isocialproviderdefaultsiteurls"></a><span data-ttu-id="c68c8-103">ISocialProvider::DefaultSiteUrls</span><span class="sxs-lookup"><span data-stu-id="c68c8-103">ISocialProvider::DefaultSiteUrls</span></span>

<span data-ttu-id="c68c8-104">返回一个 Outlook Social Connector (OSC) 提供程序指定网站 Url 的字符串数组。</span><span class="sxs-lookup"><span data-stu-id="c68c8-104">Returns an array of strings that specify site URLs for the Outlook Social Connector (OSC) provider.</span></span>
  
```cpp
[propget] HRESULT _stdcall DefaultSiteUrls([out, retval] SAFEARRAY(BSTR)* siteUrls);
```

## <a name="property-value"></a><span data-ttu-id="c68c8-105">属性值</span><span class="sxs-lookup"><span data-stu-id="c68c8-105">Property value</span></span>

<span data-ttu-id="c68c8-106">一个指向结构，它指定一个表示 OSC 提供程序网站 Url 的字符串数组。</span><span class="sxs-lookup"><span data-stu-id="c68c8-106">A pointer to a structure that specifies an array of strings that represent site URLs for the OSC provider.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="c68c8-107">说明</span><span class="sxs-lookup"><span data-stu-id="c68c8-107">Remarks</span></span>

<span data-ttu-id="c68c8-108">提供程序可以支持多个网站 Url。</span><span class="sxs-lookup"><span data-stu-id="c68c8-108">A provider can support multiple site URLs.</span></span> <span data-ttu-id="c68c8-109">OSC 设置[ISocialSession::SiteUrl](isocialsession-siteurl.md)属性，告知所选的网站 url 的提供程序。</span><span class="sxs-lookup"><span data-stu-id="c68c8-109">The OSC sets the [ISocialSession::SiteUrl](isocialsession-siteurl.md) property to inform the provider of the selected site URL.</span></span> 
  
<span data-ttu-id="c68c8-110">OSC 用作默认网站 URL 的第一个元素的数组。</span><span class="sxs-lookup"><span data-stu-id="c68c8-110">The OSC uses the first element of the array as the default site URL.</span></span> <span data-ttu-id="c68c8-111">在网站的 URL 数组中，提供可以返回其他元素，但 OSC 不使用它们。</span><span class="sxs-lookup"><span data-stu-id="c68c8-111">A provider can return additional elements in the site URL array, but the OSC does not use them.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="c68c8-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c68c8-112">See also</span></span>

- [<span data-ttu-id="c68c8-113">ISocialProvider : IUnknown</span><span class="sxs-lookup"><span data-stu-id="c68c8-113">ISocialProvider : IUnknown</span></span>](isocialprovideriunknown.md)

