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
# <a name="isocialprovidersocialnetworkname"></a>ISocialProvider::SocialNetworkName

返回 string 类型的值，该值代表社交网络名称。 
  
```cpp
[propget] HRESULT _stdcall SocialNetworkName([out, retval] BSTR* networkName);
```

## <a name="property-value"></a>属性值

一个字符串，包含社交网络的名称。
  
## <a name="remarks"></a>备注

Outlook Social Connector (OSC) 提供程序应本地化社交网络名称。
  
## <a name="see-also"></a>另请参阅

- [ISocialProvider: IUnknown](isocialprovideriunknown.md)

