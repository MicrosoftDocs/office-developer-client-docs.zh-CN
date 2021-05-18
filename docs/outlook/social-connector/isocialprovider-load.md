---
title: ISocialProviderLoad
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 6356f7bf-e3a1-4294-ad6e-df77bdd0356c
description: 初始化 OSC Outlook提供程序 (社交) 连接器。
ms.openlocfilehash: 73d14f66785417e80448f622256d0b9cb059b83c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32285756"
---
# <a name="isocialproviderload"></a>ISocialProvider::Load

初始化 OSC Outlook提供程序 (社交) 连接器。
  
```cpp
HRESULT _stdcall Load([in] BSTR socialProviderInterfaceVersion, [in] BSTR languageTag);
```

## <a name="parameters"></a>参数

_socialProviderInterfaceVersion_
  
> [in]OSC 期望的 OSC 提供程序接口的版本。
    
_languageTag_
  
> [in]Internet 工程任务组 (IETF) 语言标记，由[[RFC4646]](https://www.ietf.org/rfc/rfc4646.txt)和[[RFC4647]](https://www.ietf.org/rfc/rfc4647.txt)定义，表示当前 Outlook 用户界面语言。
    
## <a name="remarks"></a>备注

_socialProviderInterfaceVersion_ 参数的版本格式为 _X_。_xxxx，_ 其中 _X_ 是主要版本 _，xxxx_ 是 OSC 的次要版本。 For Office 2013， check for the major version being 15. 
  
## <a name="see-also"></a>另请参阅

- [ISocialProvider : IUnknown](isocialprovideriunknown.md)

