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
# <a name="isocialproviderdefaultsiteurls"></a>ISocialProvider::DefaultSiteUrls

返回一个字符串数组，该数组指定 OSC Outlook连接器 (网站) URL。
  
```cpp
[propget] HRESULT _stdcall DefaultSiteUrls([out, retval] SAFEARRAY(BSTR)* siteUrls);
```

## <a name="property-value"></a>属性值

指向指定字符串数组的结构的指针，该数组表示 OSC 提供程序的网站 URL。
  
## <a name="remarks"></a>备注

提供程序可以支持多个网站 URL。 OSC 设置 [ISocialSession：：SiteUrl](isocialsession-siteurl.md) 属性以通知提供程序所选网站 URL。 
  
OSC 使用数组的第一个元素作为默认网站 URL。 提供程序可以在网站 URL 数组中返回其他元素，但 OSC 不会使用它们。 
  
## <a name="see-also"></a>另请参阅

- [ISocialProvider : IUnknown](isocialprovideriunknown.md)

