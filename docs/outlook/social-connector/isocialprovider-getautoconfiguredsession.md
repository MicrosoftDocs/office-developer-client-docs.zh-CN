---
title: ISocialProviderGetAutoConfiguredSession
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: d8d41ced-c2bb-482e-b0bc-1b46c82121bd
description: 获取自动配置的 ISocialSession 界面。
ms.openlocfilehash: 7108a7e42e9b54e069d8d420283c1ebad3367830
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779243"
---
# <a name="isocialprovidergetautoconfiguredsession"></a>ISocialProvider::GetAutoConfiguredSession

获取自动配置的 [ISocialSession](isocialsessioniunknown.md) 界面。 
  
```cpp
HRESULT _stdcall GetAutoConfiguredSession([out, retval] ISocialSession** session);
```

## <a name="parameters"></a>参数

_Session_
  
> [out] **ISocialSession** 界面。 
    
## <a name="remarks"></a>说明

返回的 **ISocialSession** 界面会根据特定于提供程序的方法自动登录到网络。 
  
如果社交网络不支持自动配置，提供程序应返回 OSC_E_NOT_IMPLEMENTED 错误。 有关错误代码信息，请参阅 [Outlook Social Connector 提供程序错误代码](outlook-social-connector-provider-error-codes.md)。
  
## <a name="see-also"></a>另请参阅

- [ISocialProvider : IUnknown](isocialprovideriunknown.md)

