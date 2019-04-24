---
title: ISocialSession2LogonCached
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 8cac444b-0e81-44ff-a7a0-87793b533e26
description: 使用缓存凭据登录到社交网络网站。
ms.openlocfilehash: b79c692c01022dd10ecb8d4085f0aedb28a810c5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32336503"
---
# <a name="isocialsession2logoncached"></a>ISocialSession2::LogonCached

使用缓存凭据登录到社交网络网站。
  
```cpp
HRESULT _stdcall LogonCached([in] BSTR connectIn, [in] BSTR userName, [in] BSTR password,  [out] BSTR connectOut);
```

## <a name="parameters"></a>参数

_connectIn_
  
> 实时一个字符串, 可以为空或包含登录凭据, 具体取决于 .osc 调用**LogonCached**的上下文。
    
_userName_
  
> 实时一个包含用户名的字符串。
    
_口令_
  
> 实时一个包含用户密码的字符串。
    
_connectOut_
  
> 排除包含凭据的不透明字符串。
    
## <a name="remarks"></a>注解

仅当[ISocialProvider:: GetCapabilities](isocialprovider-getcapabilities.md)返回的**功能**XML 中的**useLogonCached**设置为**true**时, 才会调用此方法进行身份验证。
  
Outlook Social Connector (.osc) 调用**LogonCached**, 并为_connectIn_和非空_用户名_和_密码_字符串传递一个空字符串。 提供程序使用_用户名_和_密码_登录到社交网络, 如果身份验证成功, 则向 .osc 返回一个不透明的_connectOut_参数。 如果身份验证失败, 则提供程序将向 .osc 返回 OSC_E_LOGON_FAILURE 错误。 
  
_connectOut_参数是一个对 .osc 的不透明字符串, 并在由 .osc 登录社交网络的后续尝试中传递给_connectIn_参数。 提供程序应将任何凭据放在_connectOut_字符串中, 提供程序希望您的 .osc 在各连接之间存储。 .osc 不会解释_connectOut_中的字符串, 在将其存储在 Windows 注册表中之前, 出于安全目的对字符串进行加密。
  
## <a name="see-also"></a>另请参阅

- [ISocialSession2 : IUnknown](isocialsession2iunknown.md)

