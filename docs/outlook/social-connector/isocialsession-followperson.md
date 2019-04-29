---
title: ISocialSessionFollowPerson
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: de7f56e2-c131-4955-b945-0a72043e0f5a
description: 将 emailAddress 参数标识的人员添加为社交网络上已登录用户的友元。
ms.openlocfilehash: 849085bd40788039a96ac159fd76a5e252395916
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423256"
---
# <a name="isocialsessionfollowperson"></a>ISocialSession::FollowPerson

将_emailAddress_参数标识的人员添加为社交网络上已登录用户的友元。 
  
```cpp
HRESULT _stdcall FollowPerson([in] BSTR emailAddress);
```

## <a name="parameters"></a>参数

_emailAddress_
  
> 实时包含某人的电子邮件地址的字符串。
    
## <a name="remarks"></a>说明

_emailAddress_参数必须是有效的 SMTP 地址。 如果 Outlook Social Connector (.osc) 提供程序在**功能**中将**followPerson**方法设置为**true** , 并且_emailAddress_的参数与网络上的用户不匹配, 则该提供程序必须返回 OSC_E_NOT_FOUND误差. 如果提供程序在**功能**中将**followPerson**设置为**false** , 则提供程序应返回 OSC_E_FAIL 错误。
  
如果提供程序实现了[ISocialSession2](isocialsession2iunknown.md)接口, 并在**功能**中将**followPerson**设置为**true** , 则该 .osc 将调用[ISocialSession2:: FollowPersonEx](isocialsession2-followpersonex.md)而不是**ISocialSession:: followPerson**. 如果提供程序未实现**ISocialSession2**接口, 或者**ISocialSession2:: FollowPersonEx**返回 OSC_E_NOTIMPL 错误, 则在提供程序已设置**** **的情况下, .osc 将调用 ISocialSession:: FollowPerson****功能**中的 followPerson 为**true** 。 有关错误代码信息，请参阅 [Outlook Social Connector 提供程序错误代码](outlook-social-connector-provider-error-codes.md)。
  
在决定是否实现**ISocalSession:: FollowPerson**或**ISocialSession2:: FollowPersonEx**时, 应考虑提供程序中的其他方法是否需要**ISocialSession2**中的其他方法, 以及是否可以使用__ **FollowPersonEx**中的 djsplayName 参数。
  
## <a name="see-also"></a>另请参阅

- [ISocialSession : IUnknown](isocialsessioniunknown.md)

