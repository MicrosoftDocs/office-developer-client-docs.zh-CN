---
title: ISocialProviderGetSession
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 371b48c5-6d77-4d2d-890c-bb234c7eaabc
description: 获取 ISocialSession 接口。
ms.openlocfilehash: 59e6f61e1954f64d875c6336b211dcb530100252
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779237"
---
# <a name="isocialprovidergetsession"></a>ISocialProvider::GetSession

获取[ISocialSession](isocialsessioniunknown.md)接口。 
  
```cpp
HRESULT _stdcall GetSession([out, retval] ISocialSession** session);
```

## <a name="parameters"></a>参数

_会话_
  
> [输出]**ISocialSession**接口。 
    
## <a name="remarks"></a>备注

Outlook Social Connector (OSC) 使用**ISocialSession**接口登录到社交网络。 
  
## <a name="see-also"></a>另请参阅

- [ISocialProvider: IUnknown](isocialprovideriunknown.md)

