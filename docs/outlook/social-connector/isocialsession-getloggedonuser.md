---
title: ISocialSessionGetLoggedOnUser
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: bd6bdaf6-52d5-4308-9c3d-869f6e1a6608
description: 获取一个 ISocialProfile 接口, 该接口表示已登录的用户。
ms.openlocfilehash: 6c15d9d016f7445f8887f7d0fc87a1f36fb99b94
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439903"
---
# <a name="isocialsessiongetloggedonuser"></a>ISocialSession::GetLoggedOnUser

获取一个[ISocialProfile](isocialprofileisocialperson.md)接口, 该接口表示已登录的用户。 
  
```cpp
HRESULT _stdcall GetLoggedOnUser([out, retval] ISocialProfile** result);
```

## <a name="parameters"></a>参数

_result_
  
> 排除一个**ISocialProfile**接口。 
    
## <a name="see-also"></a>另请参阅

- [ISocialSession : IUnknown](isocialsessioniunknown.md)

