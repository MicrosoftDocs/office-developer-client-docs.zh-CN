---
title: ISocialSession2LogonCached
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 8cac444b-0e81-44ff-a7a0-87793b533e26
description: 登录到社交网络站点使用缓存的凭据。
ms.openlocfilehash: 098ccd2cd3a55affed683886ce1e297ed725475b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779248"
---
# <a name="isocialsession2logoncached"></a>ISocialSession2::LogonCached

登录到社交网络站点使用缓存的凭据。
  
```cpp
HRESULT _stdcall LogonCached([in] BSTR connectIn, [in] BSTR userName, [in] BSTR password,  [out] BSTR connectOut);
```

## <a name="parameters"></a>参数

_connectIn_
  
> [in]一个字符串，可以为空或包含的登录凭据，具体取决于在其中 OSC 调用**LogonCached**的上下文。
    
_userName_
  
> [in]一个字符串，包含用户的名称。
    
_密码_
  
> [in]一个字符串，包含用户的密码。
    
_connectOut_
  
> [输出]不透明字符串，其中包含凭据。
    
## <a name="remarks"></a>说明

只有当**useLogonCached**设置为**true**的**功能**返回[ISocialProvider::GetCapabilities](isocialprovider-getcapabilities.md)XML 中，将身份验证调用此方法。
  
Outlook Social Connector (OSC) 调用**LogonCached**，并传递空字符串作为_connectIn_和非空_用户名_和_密码_字符串。 提供程序使用_用户名_和_密码_登录到社交网络，并返回不透明_connectOut_参数为 OSC 身份验证成功。 如果身份验证失败，提供程序将返回到 OSC OSC_E_LOGON_FAILURE 错误。 
  
_ConnectOut_参数 OSC，不透明字符串并且通过传递给_connectIn_参数在以后尝试登录到社交网络 OSC。 提供程序应该将提供程序希望 OSC 跨连接存储在_connectOut_字符串中的任何凭据。 OSC 不解释_connectOut_中的字符串，并将其存储在 Windows 注册表中之前加密出于安全目的的字符串。
  
## <a name="see-also"></a>另请参阅

- [ISocialSession2 : IUnknown](isocialsession2iunknown.md)

