---
title: ISocialSessionUnFollowPerson
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 66c83041-ee83-41d5-b9dc-a4dc4c670f82
description: 删除由 userID 参数标识为社交网络上的友元的人员。
ms.openlocfilehash: c276a9e5af18f7e4a3afbaa66d366d55de460a58
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418433"
---
# <a name="isocialsessionunfollowperson"></a>ISocialSession::UnFollowPerson

删除由_userID_参数标识为社交网络上的友元的人员。 
  
```cpp
HRESULT _stdcall UnFollowPerson([in] BSTR userID);
```

## <a name="parameters"></a>参数

_userID_
  
> 实时包含人员的社交网络用户 ID 的字符串。
    
## <a name="remarks"></a>说明

_userID_参数必须是社交网络上的人员的有效用户 ID。 
  
如果 Outlook Social Connector (.osc) 提供程序将**doNotFollowPerson**中的**功能**设置为**true** , 则在传入的用户 ID 与网络上的用户不匹配的情况下, 提供程序必须返回 OSC_E_NOT_FOUND 错误。 如果提供程序在**功能**中将**doNotFollowPerson**设置为**false** , 则提供程序应返回 OSC_E_FAIL 错误。 有关错误代码信息，请参阅 [Outlook Social Connector 提供程序错误代码](outlook-social-connector-provider-error-codes.md)。
  
## <a name="see-also"></a>另请参阅

- [ISocialSession : IUnknown](isocialsessioniunknown.md)

