---
title: ISocialSession2LogonCached
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 8cac444b-0e81-44ff-a7a0-87793b533e26
description: 使用缓存的凭据登录到社交网络网站。
ms.openlocfilehash: b79c692c01022dd10ecb8d4085f0aedb28a810c5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436620"
---
# <a name="isocialsession2logoncached"></a>ISocialSession2::LogonCached

使用缓存的凭据登录到社交网络网站。
  
```cpp
HRESULT _stdcall LogonCached([in] BSTR connectIn, [in] BSTR userName, [in] BSTR password,  [out] BSTR connectOut);
```

## <a name="parameters"></a>参数

_connectIn_
  
> [in]一个可为空或包含登录凭据的字符串，具体取决于 OSC 调用 **LogonCached** 的上下文。
    
_userName_
  
> [in]包含用户名的字符串。
    
_password_
  
> [in]包含用户密码的字符串。
    
_connectOut_
  
> [out]包含凭据的不透明字符串。
    
## <a name="remarks"></a>备注

只有在 [ISocialProvider：：GetCapabilities](isocialprovider-getcapabilities.md)返回的功能 **XML** 中 **useLogonCached** 设置为 **true** 时，才对身份验证调用此方法。
  
OSC Outlook Social Connector (调用 **LogonCached**) ，并传递 _connectIn_ 的空字符串和非空 _的 userName_ 和 _密码_ 字符串。 提供程序使用  _userName_ 和  _密码_ 登录社交网络，如果身份验证成功，则向 OSC 返回不透明  _的 connectOut_ 参数。 如果身份验证失败，提供程序将OSC_E_LOGON_FAILURE错误返回到 OSC。 
  
_connectOut_ 参数是 OSC 的不透明字符串，在 OSC 随后尝试登录社交网络时将传递给 _connectIn_ 参数。 提供程序应在  _connectOut_ 字符串中放置提供程序希望 OSC 跨连接存储的任何凭据。 OSC 不会在 _connectOut_ 中解释字符串，并出于安全目的对字符串进行加密，然后再将其存储在Windows注册表中。
  
## <a name="see-also"></a>另请参阅

- [ISocialSession2 : IUnknown](isocialsession2iunknown.md)

