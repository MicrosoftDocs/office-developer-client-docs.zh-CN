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
# <a name="isocialprovidersocialnetworkguid"></a>ISocialProvider::SocialNetworkGuid

返回一个 GUID 值，该值代表社交网络的唯一标识符。
  
```cpp
[propget] HRESULT _stdcall SocialNetworkGuid([out, retval] GUID* guid);
```

## <a name="property-value"></a>属性值

一个指向 GUID 值，该值代表社交网络的唯一标识符。
  
## <a name="remarks"></a>备注

GUID 必须变，并且必须未更改，即使该提供程序版本更改。
  
## <a name="see-also"></a>另请参阅

- [ISocialProvider: IUnknown](isocialprovideriunknown.md)

