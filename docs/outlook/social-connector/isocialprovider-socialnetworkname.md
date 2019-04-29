---
title: ISocialProviderSocialNetworkName
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 96f32db2-d654-4e72-88d1-ef955e3ff42b
description: 返回一个字符串, 表示社交网络名称。
ms.openlocfilehash: 5a6240fa6e609eec8498456fe56c83a761fadab0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406876"
---
# <a name="isocialprovidersocialnetworkname"></a>ISocialProvider::SocialNetworkName

返回一个字符串, 表示社交网络名称。 
  
```cpp
[propget] HRESULT _stdcall SocialNetworkName([out, retval] BSTR* networkName);
```

## <a name="property-value"></a>属性值

包含社交网络名称的字符串。
  
## <a name="remarks"></a>说明

Outlook social Connector (.osc) 提供程序应本地化社交网络名称。
  
## <a name="see-also"></a>另请参阅

- [ISocialProvider : IUnknown](isocialprovideriunknown.md)

