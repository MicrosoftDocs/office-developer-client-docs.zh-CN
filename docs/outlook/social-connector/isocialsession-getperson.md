---
title: ISocialSessionGetPerson
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 2d0a2945-54d7-417f-b5c6-2647c70263cf
description: 获取基于用户 Id 参数 ISocialPerson 接口。
ms.openlocfilehash: 5769f4c41bb97f45ab722f1b3a3febe24c8a7ab2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779231"
---
# <a name="isocialsessiongetperson"></a>ISocialSession::GetPerson

获取基于_用户 Id_参数[ISocialPerson](isocialpersoniunknown.md)接口。 
  
```cpp
HRESULT _stdcall GetPerson([in] BSTR userId, [out, retval] ISocialPerson** result);
```

## <a name="parameters"></a>参数

_userId_
  
> [in]一个字符串，包含用户 ID 或 SMTP 地址的联系人。
    
_result_
  
> [输出]**ISocialPerson**接口。 
    
## <a name="remarks"></a>说明

_UserID_参数必须为该用户的 ID 或 SMTP 地址。 
  
## <a name="see-also"></a>另请参阅

- [ISocialSession : IUnknown](isocialsessioniunknown.md)

