---
title: ISocialSessionLogonWeb
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: f4217030-5fd1-4ec4-a83f-752717fbb787
description: 登录到使用基于表单的身份验证的社交网络站点。
ms.openlocfilehash: 4af0301d5b619ce7f9ff54b97f54b4b00408a564
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779241"
---
# <a name="isocialsessionlogonweb"></a>ISocialSession::LogonWeb

登录到使用基于表单的身份验证的社交网络站点。
  
```cpp
HRESULT _stdcall LogonWeb([in] BSTR connectIn, [out] BSTR* connectOut);
```

## <a name="parameters"></a>参数

_connectIn_
  
> [in]一个字符串，为**null**，向 web 或一个包含登录凭据，具体取决于在登录过程时调用此方法的上下文字符串上登录表单的 URL。
    
_connectOut_
  
> [输出]一个字符串，包含登录凭据。
    
## <a name="remarks"></a>说明

Outlook Social Connector (OSC) 提供程序指示它支持基于表单的身份验证时，才调用**LogonWeb**方法。 提供程序指示它通过设置为**true** **功能**的 XML **useLogonWebAuth**需要基于表单的身份验证。 如果提供程序将**useLogonWebAuth**设置为**false**，则 OSC 使用基本身份验证，并调用[ISocialSession::Logon](isocialsession-logon.md)方法。 
  
登录到社交网络站点使用基于表单的身份验证涉及的特定顺序调用**LogonWeb**和[ISocialSession::GetLogonUrl](isocialsession-getlogonurl.md)方法： 
  
1. OSC 调用**LogonWeb**首次给_connectIn_参数传递**null** 。 
    
2. 提供程序将引发到 OSC OSC_E_AUTH_ERROR 错误。
    
3. OSC 接下来将调用**GetLogonUrl**。
    
4. 提供程序返回**GetLogonUrl**方法中的登录页面的相应 URL。 
    
5. OSC 使用**GetLogonUrl**返回的 URL 来显示基于表单的登录页。 
    
6. OSC 然后调用**LogonWeb**第二次，将 URL 传递给_connectIn_参数中的登录窗体。 
    
7. 如果身份验证成功，提供程序返回_connectOut_参数中具有到 OSC 登录凭据。 如果身份验证失败，提供程序将引发到 OSC OSC_E_AUTH_ERROR 错误。 
    
如果 OSC 提供程序支持使用缓存的凭据登录，它指定**useLogonCached**为**true**的**功能**XML 中。 提供程序应该将提供程序希望 OSC 跨连接存储在_connectOut_字符串中的任何登录凭据。 OSC 不解释_connectOut_字符串。 OSC 验证该**useLogonCached**为**true**后，OSC 将其存储在 Windows 注册表之前对加密的安全的字符串。 OSC 将_connectIn_参数传递到此字符串上调用[ISocialSession2::LogonCached](isocialsession2-logoncached.md)登录到社交网络上的后续尝试。 
  
有关错误代码信息，请参阅 [Outlook Social Connector 提供程序错误代码](outlook-social-connector-provider-error-codes.md)。
  
## <a name="see-also"></a>另请参阅

- [ISocialSession : IUnknown](isocialsessioniunknown.md)
- [基于表单的身份验证](forms-based-authentication.md)

