---
title: ISocialProviderVersion
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: dfc92878-ab8b-4721-aee8-997c56a8e45b
description: 返回一个字符串，表示为此社交网络提供程序的版本号。
ms.openlocfilehash: 5c82df2dc4c052b1a06bcecb16defbb4dee38b18
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779226"
---
# <a name="isocialproviderversion"></a>ISocialProvider::Version

返回一个字符串，表示为此社交网络提供程序的版本号。 
  
```cpp
[propget] HRESULT _stdcall Version([out, retval] BSTR* Version);
```

## <a name="property-value"></a>属性值

一个字符串，包含提供程序的版本号。
  
## <a name="remarks"></a>说明

版本字符串应使用_MajorVersion_。 _MinorVersion_格式 (例如，1.4730)。 
  
## <a name="see-also"></a>另请参阅

- [ISocialProvider : IUnknown](isocialprovideriunknown.md)

