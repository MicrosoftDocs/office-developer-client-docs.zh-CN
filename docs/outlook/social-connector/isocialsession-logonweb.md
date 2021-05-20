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
  
> [in]一个 **为空** 的字符串、Web 上登录表单的 URL 或包含登录凭据的字符串，具体取决于调用此方法时登录进程中的上下文。
    
_connectOut_
  
> [out]包含登录凭据的字符串。
    
## <a name="remarks"></a>备注

OSC Outlook连接器 (OSC) 仅在提供程序指示其支持基于表单的身份验证时调用 **LogonWeb** 方法。 提供程序通过针对功能在 XML 中将 **useLogonWebAuth** 设置为 **true** 来指示它需要基于表单 **的身份验证**。 如果提供程序将 **useLogonWebAuth** 设置为 **false，** 则 OSC 将使用基本身份验证并调用 [ISocialSession：：Logon](isocialsession-logon.md) 方法。 
  
使用基于表单的身份验证登录到社交网络网站涉及按特定顺序调用 **LogonWeb** 和 [ISocialSession：：GetLogonUrl](isocialsession-getlogonurl.md) 方法： 
  
1. OSC 第一 **次调用 LogonWeb，** 将 **null** 传递给  _connectIn_ 参数。 
    
2. 提供程序向 OSC OSC_E_AUTH_ERROR错误。
    
3. OSC 接下来调用 **GetLogonUrl**。
    
4. 提供程序将相应的 URL 返回到 **GetLogonUrl** 方法中的登录页。 
    
5. OSC 使用 **GetLogonUrl** 返回的 URL 显示基于表单的登录页。 
    
6. 然后，OSC 再次调用 **LogonWeb，** 将 URL 传递到  _connectIn_ 参数中的登录表单。 
    
7. 如果身份验证成功，提供程序会向 OSC 返回  _connectOut_ 参数中的登录凭据。 如果身份验证失败，提供程序会向 OSC OSC_E_AUTH_ERROR错误。 
    
如果 OSC 提供程序支持使用缓存凭据登录，则它会在功能 **XML** 中将 **useLogonCached** 指定为 **true。** 提供程序应该将任何登录凭据放在提供程序希望 OSC 跨连接存储的  _connectOut_ 字符串中。 OSC 不会解释  _connectOut_ 字符串。 在 OSC 验证 **useLogonCached** 为 **true** 后，OSC 会先对字符串进行加密，然后再将其存储在 Windows注册表中。 OSC 在后续尝试通过调用 [ISocialSession2：：LogonCached](isocialsession2-logoncached.md)登录到社交网络时，将此字符串传递给 _connectIn_ 参数。 
  
有关错误代码信息，请参阅 [Outlook Social Connector 提供程序错误代码](outlook-social-connector-provider-error-codes.md)。
  
## <a name="see-also"></a>另请参阅

- [ISocialSession : IUnknown](isocialsessioniunknown.md)
- [基于表单的身份验证](forms-based-authentication.md)

