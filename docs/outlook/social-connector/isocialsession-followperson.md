---
title: ISocialSessionFollowPerson
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: de7f56e2-c131-4955-b945-0a72043e0f5a
description: 添加为朋友社交网络登录用户的电子邮件地址参数标识的人员。
ms.openlocfilehash: 6dc289801c99f2f3bf1647e9c98c072d2f53d066
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779233"
---
# <a name="isocialsessionfollowperson"></a>ISocialSession::FollowPerson

添加为朋友社交网络登录用户的_电子邮件地址_参数标识的人员。 
  
```cpp
HRESULT _stdcall FollowPerson([in] BSTR emailAddress);
```

## <a name="parameters"></a>参数

_emailAddress_
  
> [in]一个字符串，包含某个人的电子邮件地址。
    
## <a name="remarks"></a>说明

_EmailAddress_参数必须为有效的 SMTP 地址。 如果 Outlook Social Connector (OSC) 提供程序已经**followPerson**方法为**true**设置式**功能**，并且_电子邮件地址_的参数与网络上的用户不匹配，则提供程序必须返回 OSC_E_NOT_FOUND错误。 如果提供程序已将**followPerson**设置为**false** ，在**功能**中，提供程序应返回 OSC_E_FAIL 错误。
  
OSC 提供程序实现[ISocialSession2](isocialsession2iunknown.md)接口和已在**功能**中**followPerson**设为**true** ，如果将而不是**ISocialSession::FollowPerson 调用[ISocialSession2::FollowPersonEx](isocialsession2-followpersonex.md)**. 只要提供程序具有设置**OSC 提供程序未实现**ISocialSession2**接口，或者**ISocialSession2::FollowPersonEx**返回 OSC_E_NOTIMPL 错误，如果将调用**ISocialSession::FollowPerson**followPerson**作为**true** **功能**。 有关错误代码信息，请参阅 [Outlook Social Connector 提供程序错误代码](outlook-social-connector-provider-error-codes.md)。
  
在决定是否要实现**ISocalSession::FollowPerson**或**ISocialSession2::FollowPersonEx**，您应考虑您的提供商所需的其他方法在**ISocialSession2**，以及是否可以使用_djsplayName_中**FollowPersonEx**参数。
  
## <a name="see-also"></a>另请参阅

- [ISocialSession : IUnknown](isocialsessioniunknown.md)

