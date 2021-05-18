---
title: ISocialProviderDefaultSiteUrls
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 322ea2e9-d6c9-48f9-a927-7162346d16a4
description: 返回一个字符串数组，该数组指定 OSC Outlook连接器 (网站) URL。
ms.openlocfilehash: 34d779d5eb42b81a14c5236685104e9ef4fe36f2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413771"
---
# <a name="isocialproviderdefaultsiteurls"></a><span data-ttu-id="b03ce-103">ISocialProvider::DefaultSiteUrls</span><span class="sxs-lookup"><span data-stu-id="b03ce-103">ISocialProvider::DefaultSiteUrls</span></span>

<span data-ttu-id="b03ce-104">返回一个字符串数组，该数组指定 OSC Outlook连接器 (网站) URL。</span><span class="sxs-lookup"><span data-stu-id="b03ce-104">Returns an array of strings that specify site URLs for the Outlook Social Connector (OSC) provider.</span></span>
  
```cpp
[propget] HRESULT _stdcall DefaultSiteUrls([out, retval] SAFEARRAY(BSTR)* siteUrls);
```

## <a name="property-value"></a><span data-ttu-id="b03ce-105">属性值</span><span class="sxs-lookup"><span data-stu-id="b03ce-105">Property value</span></span>

<span data-ttu-id="b03ce-106">指向指定字符串数组的结构的指针，该数组表示 OSC 提供程序的网站 URL。</span><span class="sxs-lookup"><span data-stu-id="b03ce-106">A pointer to a structure that specifies an array of strings that represent site URLs for the OSC provider.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="b03ce-107">备注</span><span class="sxs-lookup"><span data-stu-id="b03ce-107">Remarks</span></span>

<span data-ttu-id="b03ce-108">提供程序可以支持多个网站 URL。</span><span class="sxs-lookup"><span data-stu-id="b03ce-108">A provider can support multiple site URLs.</span></span> <span data-ttu-id="b03ce-109">OSC 设置 [ISocialSession：：SiteUrl](isocialsession-siteurl.md) 属性以通知提供程序所选网站 URL。</span><span class="sxs-lookup"><span data-stu-id="b03ce-109">The OSC sets the [ISocialSession::SiteUrl](isocialsession-siteurl.md) property to inform the provider of the selected site URL.</span></span> 
  
<span data-ttu-id="b03ce-110">OSC 使用数组的第一个元素作为默认网站 URL。</span><span class="sxs-lookup"><span data-stu-id="b03ce-110">The OSC uses the first element of the array as the default site URL.</span></span> <span data-ttu-id="b03ce-111">提供程序可以在网站 URL 数组中返回其他元素，但 OSC 不会使用它们。</span><span class="sxs-lookup"><span data-stu-id="b03ce-111">A provider can return additional elements in the site URL array, but the OSC does not use them.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="b03ce-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b03ce-112">See also</span></span>

- [<span data-ttu-id="b03ce-113">ISocialProvider : IUnknown</span><span class="sxs-lookup"><span data-stu-id="b03ce-113">ISocialProvider : IUnknown</span></span>](isocialprovideriunknown.md)

