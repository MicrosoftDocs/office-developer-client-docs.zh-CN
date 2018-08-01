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
# <a name="isocialproviderdefaultsiteurls"></a>ISocialProvider::DefaultSiteUrls

返回一个 Outlook Social Connector (OSC) 提供程序指定网站 Url 的字符串数组。
  
```cpp
[propget] HRESULT _stdcall DefaultSiteUrls([out, retval] SAFEARRAY(BSTR)* siteUrls);
```

## <a name="property-value"></a>属性值

一个指向结构，它指定一个表示 OSC 提供程序网站 Url 的字符串数组。
  
## <a name="remarks"></a>说明

提供程序可以支持多个网站 Url。 OSC 设置[ISocialSession::SiteUrl](isocialsession-siteurl.md)属性，告知所选的网站 url 的提供程序。 
  
OSC 用作默认网站 URL 的第一个元素的数组。 在网站的 URL 数组中，提供可以返回其他元素，但 OSC 不使用它们。 
  
## <a name="see-also"></a>另请参阅

- [ISocialProvider : IUnknown](isocialprovideriunknown.md)

