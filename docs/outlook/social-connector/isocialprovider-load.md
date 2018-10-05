---
title: ISocialProviderLoad
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 6356f7bf-e3a1-4294-ad6e-df77bdd0356c
description: 初始化 Outlook Social Connector (OSC) 提供程序。
ms.openlocfilehash: 73d14f66785417e80448f622256d0b9cb059b83c
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25385828"
---
# <a name="isocialproviderload"></a>ISocialProvider::Load

初始化 Outlook Social Connector (OSC) 提供程序。
  
```cpp
HRESULT _stdcall Load([in] BSTR socialProviderInterfaceVersion, [in] BSTR languageTag);
```

## <a name="parameters"></a>参数

_socialProviderInterfaceVersion_
  
> [in]所需的 OSC OSC 提供程序接口的版本。
    
_languageTag_
  
> [in]Internet 工程任务组 (IETF) 语言标记，由[[RFC4646]](https://www.ietf.org/rfc/rfc4646.txt)和[[RFC4647]](https://www.ietf.org/rfc/rfc4647.txt)，值，该值代表当前 Outlook 用户界面语言。
    
## <a name="remarks"></a>说明

_SocialProviderInterfaceVersion_参数的版本格式为_X_。_格式_，其中_X_是主要版本和_格式_是 OSC 的次要版本。 Office 2013 的检查正在 15 的主要版本。 
  
## <a name="see-also"></a>另请参阅

- [ISocialProvider : IUnknown](isocialprovideriunknown.md)

