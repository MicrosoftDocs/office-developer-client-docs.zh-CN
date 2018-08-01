---
title: ISocialSessionGetNetworkIdentifier
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 534e404f-54c6-4d2b-a8d0-d2ee990a972f
description: 获取一个字符串，表示对于给定的社交网络连接的唯一的社交网络标识符。
ms.openlocfilehash: eb618ba8e8bb37278c1fdb09d984fba141a9d686
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779355"
---
# <a name="isocialsessiongetnetworkidentifier"></a>ISocialSession::GetNetworkIdentifier

获取一个字符串，表示对于给定的社交网络连接的唯一的社交网络标识符。 
  
```cpp
HRESULT _stdcall GetNetworkIdentifier([out, retval] BSTR* networkIdentifier);
```

## <a name="parameters"></a>参数

_networkIdentifier_
  
> [输出]一个字符串，包含一个唯一的社交网络的标识符。
    
## <a name="remarks"></a>说明

一个唯一的网络标识符是一个字符串，标识 Outlook Social Connector (OSC) 提供程序社交网络。 此方法还可以返回 E_NOTIMPL。
  
## <a name="see-also"></a>另请参阅

- [ISocialSession : IUnknown](isocialsessioniunknown.md)

