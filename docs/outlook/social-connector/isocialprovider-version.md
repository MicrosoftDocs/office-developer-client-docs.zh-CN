---
title: ISocialProviderVersion
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: dfc92878-ab8b-4721-aee8-997c56a8e45b
description: 返回一个 string 类型的值, 该值代表此社交网络提供程序的版本号。
ms.openlocfilehash: 0749b8fb83a11328233442b79e1f9de50076effe
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438272"
---
# <a name="isocialproviderversion"></a>ISocialProvider::Version

返回一个 string 类型的值, 该值代表此社交网络提供程序的版本号。 
  
```cpp
[propget] HRESULT _stdcall Version([out, retval] BSTR* Version);
```

## <a name="property-value"></a>属性值

一个包含提供程序版本号的字符串。
  
## <a name="remarks"></a>说明

版本字符串应使用_MajorVersion_。 _MinorVersion_格式 (例如, 1.4730)。 
  
## <a name="see-also"></a>另请参阅

- [ISocialProvider : IUnknown](isocialprovideriunknown.md)

