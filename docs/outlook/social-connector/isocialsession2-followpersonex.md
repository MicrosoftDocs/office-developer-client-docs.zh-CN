---
title: ISocialSession2FollowPersonEx
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 17b4af7f-7967-422b-996c-792705c93ad3
description: 将 emailAddresses 和 displayName 参数标识的人添加为社交网络上登录的用户的好友。
ms.openlocfilehash: b44b442ba928b48411e5b1fc8a0c8b76477022ae
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429829"
---
# <a name="isocialsession2followpersonex"></a>ISocialSession2::FollowPersonEx

将  _emailAddresses_ 和  _displayName_ 参数标识的人添加为社交网络上登录的用户的好友。 
  
```cpp
HRESULT _stdcall FollowPersonEx([in] SAFEARRAY(BSTR) emailAddresses, [in] BSTR displayName);
```

## <a name="parameters"></a>参数

_emailAddresses_
  
> [in]包含社交网络上某个人的一个或多个有效 SMTP 地址的数组。
    
_displayName_
  
> [in]包含要添加显示名称好友的联系人的字符串。
    
## <a name="remarks"></a>备注

如果 Outlook Social Connector (OSC) 在 **emailAddresses** 参数的数组中提供的 SMTP 地址多于 SMTP 地址，则 OSC 提供程序可以假定第一个元素是主 SMTP 地址。 
  
如果提供程序在功能 **XML** 中将 **followPerson** 元素设置为 **true，**_并且 emailAddresses_ 的所有元素都不匹配网络用户，则提供程序必须返回 OSC_E_NOT_FOUND 错误。 如果提供程序在功能中将 **followPerson** 设置为 **false，** 则提供程序应返回OSC_E_FAIL错误。 
  
如果 **FollowPersonEx** 方法成功，则提供程序可以使用  _displayName_ 参数中的字符串寻址任何后续好友确认电子邮件中的人员，而不是通过 SMTP 地址寻址该人员。 另一方面，提供程序必须能够处理为  _displayName_ 参数传递空字符串的 OSC。 
  
如果提供程序实现 [ISocialSession2](isocialsession2iunknown.md) 接口，并且在功能 XML 中将 **followPerson** 设置为 **true，** 则 OSC 将调用 **FollowPersonEx** 而不是 [ISocialSession：：FollowPerson](isocialsession-followperson.md)。 如果提供程序将 **followPerson** 设置为 **true，** 但不实现 **ISocialSession2** 接口，或者 **FollowPersonEx** 返回 OSC_E_NOTIMPL 错误，OSC 将调用 **ISocialSession：：FollowPerson**。
  
## <a name="see-also"></a>另请参阅

- [ISocialSession2 : IUnknown](isocialsession2iunknown.md)

