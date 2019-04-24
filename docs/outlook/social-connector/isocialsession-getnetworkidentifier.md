---
title: ISocialSessionGetNetworkIdentifier
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 534e404f-54c6-4d2b-a8d0-d2ee990a972f
description: 获取一个字符串, 表示给定的社交网络连接的唯一社交网络标识符。
ms.openlocfilehash: 3051abd6dcccec878e8c53332980731772d543eb
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32285335"
---
# <a name="isocialsessiongetnetworkidentifier"></a>ISocialSession::GetNetworkIdentifier

获取一个字符串, 表示给定的社交网络连接的唯一社交网络标识符。 
  
```cpp
HRESULT _stdcall GetNetworkIdentifier([out, retval] BSTR* networkIdentifier);
```

## <a name="parameters"></a>参数

_networkIdentifier_
  
> 排除包含唯一社交网络标识符的字符串。
    
## <a name="remarks"></a>注解

唯一的网络标识符是一个标识 Outlook social Connector (.osc) 提供商社交网络的字符串。 此方法还可以返回 E_NOTIMPL。
  
## <a name="see-also"></a>另请参阅

- [ISocialSession : IUnknown](isocialsessioniunknown.md)

