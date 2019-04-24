---
title: ISocialProviderLoad
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 6356f7bf-e3a1-4294-ad6e-df77bdd0356c
description: 初始化 Outlook Social Connector (.osc) 提供程序。
ms.openlocfilehash: 73d14f66785417e80448f622256d0b9cb059b83c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32285756"
---
# <a name="isocialproviderload"></a>ISocialProvider::Load

初始化 Outlook Social Connector (.osc) 提供程序。
  
```cpp
HRESULT _stdcall Load([in] BSTR socialProviderInterfaceVersion, [in] BSTR languageTag);
```

## <a name="parameters"></a>参数

_socialProviderInterfaceVersion_
  
> 实时.osc 所需的 .osc 提供程序接口的版本。
    
_languageTag_
  
> 实时由[[RFC4646]](https://www.ietf.org/rfc/rfc4646.txt)和[[RFC4647]](https://www.ietf.org/rfc/rfc4647.txt)定义的 Internet 工程任务组 (IETF) 语言标记, 代表当前的 Outlook 用户界面语言。
    
## <a name="remarks"></a>注解

_socialProviderInterfaceVersion_参数的版本格式是_X_。_xxxx_, 其中_X_是主要版本, _xxxx_是 .osc 的次要版本。 对于 Office 2013, 请检查主要版本是否为15。 
  
## <a name="see-also"></a>另请参阅

- [ISocialProvider : IUnknown](isocialprovideriunknown.md)

