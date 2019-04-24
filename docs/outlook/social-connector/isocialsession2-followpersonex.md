---
title: ISocialSession2FollowPersonEx
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 17b4af7f-7967-422b-996c-792705c93ad3
description: 将由 emailAddresses 和 displayName 参数标识的人员添加为社交网络上登录用户的友元。
ms.openlocfilehash: b44b442ba928b48411e5b1fc8a0c8b76477022ae
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339653"
---
# <a name="isocialsession2followpersonex"></a>ISocialSession2::FollowPersonEx

将由_emailAddresses_和_displayName_参数标识的人员添加为社交网络上登录用户的友元。 
  
```cpp
HRESULT _stdcall FollowPersonEx([in] SAFEARRAY(BSTR) emailAddresses, [in] BSTR displayName);
```

## <a name="parameters"></a>参数

_emailAddresses_
  
> 实时包含社交网络中某个人的一个或多个有效 SMTP 地址的数组。
    
_displayName_
  
> 实时包含要作为好友添加的人员的显示名称的字符串。
    
## <a name="remarks"></a>注解

如果 Outlook Social Connector (.osc) 在**emailAddresses**参数的数组中提供了多个 SMTP 地址, 则 .osc 提供程序可以假定第一个元素是主 SMTP 地址。 
  
如果提供程序在**功能**XML 中将**followPerson**元素设置为**true** , 并且_emailAddresses_中的任何元素与网络上的用户都不匹配, 则提供程序必须返回 OSC_E_NOT_FOUND 错误。 如果提供程序在**功能**中将**followPerson**设置为**false** , 则提供程序应返回 OSC_E_FAIL 错误。 
  
如果**FollowPersonEx**方法成功, 则提供程序可以使用_displayName_参数中的字符串来处理任何后续的友元确认电子邮件中的人员, 而不是通过 SMTP 地址寻址人员。 另一方面, 提供程序必须能够处理在为_displayName_参数传递空字符串的 .osc。 
  
如果提供程序实现[ISocialSession2](isocialsession2iunknown.md)接口, 并在功能 XML 中将**followPerson**设置为**true** , 则 .osc 调用**FollowPersonEx**而不是[ISocialSession:: followPerson](isocialsession-followperson.md)。 如果提供程序将**followPerson**设置为**true** , 但未实现**ISocialSession2**接口, 或**FollowPersonEx**返回 OSC_E_NOTIMPL 错误, 则 .osc 调用**ISocialSession:: followPerson**。
  
## <a name="see-also"></a>另请参阅

- [ISocialSession2 : IUnknown](isocialsession2iunknown.md)

