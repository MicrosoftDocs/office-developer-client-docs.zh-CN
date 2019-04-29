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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413771"
---
# <a name="isocialproviderdefaultsiteurls"></a>ISocialProvider::DefaultSiteUrls

返回一个字符串数组, 这些字符串指定 Outlook Social Connector (.osc) 提供程序的网站 url。
  
```cpp
[propget] HRESULT _stdcall DefaultSiteUrls([out, retval] SAFEARRAY(BSTR)* siteUrls);
```

## <a name="property-value"></a>属性值

指向结构的指针, 该结构指定代表 .osc 提供程序的网站 url 的字符串数组。
  
## <a name="remarks"></a>说明

提供程序可支持多个网站 url。 .osc 将[ISocialSession:: SiteUrl](isocialsession-siteurl.md)属性设置为通知提供程序所选的网站 URL。 
  
.osc 使用数组的第一个元素作为默认网站 URL。 提供程序可以返回网站 URL 数组中的其他元素, 但 .osc 不使用它们。 
  
## <a name="see-also"></a>另请参阅

- [ISocialProvider : IUnknown](isocialprovideriunknown.md)

