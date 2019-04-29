---
title: ISocialSessionLogonWeb
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: f4217030-5fd1-4ec4-a83f-752717fbb787
description: 使用基于表单的身份验证登录到社交网络网站。
ms.openlocfilehash: 7ef7af8c1c2cdb783bdecd71b29635468e19dc6a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33430334"
---
# <a name="isocialsessionlogonweb"></a>ISocialSession::LogonWeb

使用基于表单的身份验证登录到社交网络网站。
  
```cpp
HRESULT _stdcall LogonWeb([in] BSTR connectIn, [out] BSTR* connectOut);
```

## <a name="parameters"></a>参数

_connectIn_
  
> 实时一个字符串, 为**null**、web 上的登录表单的 URL 或包含登录凭据的字符串, 具体取决于调用此方法时登录过程中的上下文。
    
_connectOut_
  
> 排除包含登录凭据的字符串。
    
## <a name="remarks"></a>说明

仅当提供程序指示它支持基于表单的身份验证时, Outlook Social Connector (.osc) 才会调用**LogonWeb**方法。 提供程序指示它需要基于表单的身份验证, 具体方法是在 XML 中将**useLogonWebAuth**设置为**true** 。 **** 如果提供程序将**useLogonWebAuth**设置为**false**, 则 .osc 将使用基本身份验证, 并调用[ISocialSession:: Logon](isocialsession-logon.md)方法。 
  
使用基于表单的身份验证登录到社交网络网站需要按特定顺序调用**LogonWeb**和[ISocialSession:: GetLogonUrl](isocialsession-getlogonurl.md)方法: 
  
1. .osc 调用**LogonWeb**第一次, 将**null**传递给_connectIn_参数。 
    
2. 提供程序将向 .osc 引发 OSC_E_AUTH_ERROR 错误。
    
3. .osc 接下来调用**GetLogonUrl**。
    
4. 提供程序将相应的 URL 返回到**GetLogonUrl**方法中的登录页。 
    
5. .osc 使用**GetLogonUrl**返回的 URL 来显示基于表单的登录页。 
    
6. 然后, 您的 .osc 再次调用**LogonWeb** , 并将 URL 传递给_connectIn_参数中的登录表单。 
    
7. 如果身份验证成功, 则提供程序将_connectOut_参数中的登录凭据返回到 .osc。 如果身份验证失败, 则提供程序将向 .osc 引发 OSC_E_AUTH_ERROR 错误。 
    
如果 .osc 提供程序支持使用缓存凭据登录, 则在**功能**XML 中将**useLogonCached**指定为**true** 。 提供程序应将任何登录凭据放在提供程序希望您的 .osc 在连接中存储的_connectOut_字符串中。 .osc 不会解释_connectOut_字符串。 在 .osc 验证**useLogonCached**为**true**后, 在将其存储在 Windows 注册表中之前, .osc 会对字符串进行加密, 以确保安全性。 在后续尝试通过调用[ISocialSession2:: LogonCached](isocialsession2-logoncached.md)登录社交网络时, .osc 将此字符串传递给_connectIn_参数。 
  
有关错误代码信息，请参阅 [Outlook Social Connector 提供程序错误代码](outlook-social-connector-provider-error-codes.md)。
  
## <a name="see-also"></a>另请参阅

- [ISocialSession : IUnknown](isocialsessioniunknown.md)
- [基于表单的身份验证](forms-based-authentication.md)

