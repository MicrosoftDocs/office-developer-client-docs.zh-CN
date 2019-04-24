---
title: ISocialSessionGetPerson
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 2d0a2945-54d7-417f-b5c6-2647c70263cf
description: 获取基于 userID 参数的 ISocialPerson 接口。
ms.openlocfilehash: b54e39b3712fb57d89d03787f1e5fa0ff50ff84a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32285328"
---
# <a name="isocialsessiongetperson"></a>ISocialSession::GetPerson

获取基于_userID_参数的[ISocialPerson](isocialpersoniunknown.md)接口。 
  
```cpp
HRESULT _stdcall GetPerson([in] BSTR userId, [out, retval] ISocialPerson** result);
```

## <a name="parameters"></a>参数

_userId_
  
> 实时包含人员的用户 ID 或 SMTP 地址的字符串。
    
_result_
  
> 排除一个**ISocialPerson**接口。 
    
## <a name="remarks"></a>注解

_userID_参数必须为用户 ID 或 SMTP 地址。 
  
## <a name="see-also"></a>另请参阅

- [ISocialSession : IUnknown](isocialsessioniunknown.md)

