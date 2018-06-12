---
title: ISocialSessionGetLogonUrl
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: d61bab07-acb3-433b-8783-c3fe110a5582
description: 获取一个字符串，表示用于 web 身份验证过程中显示给用户的基于浏览器的表单的 URL。
ms.openlocfilehash: 343919f194b238fc519bb8f6d808b44a8ab6e7b9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779228"
---
# <a name="isocialsessiongetlogonurl"></a>ISocialSession::GetLogonUrl

获取一个字符串，表示用于 web 身份验证过程中显示给用户的基于浏览器的表单的 URL。
  
```cpp
HRESULT _stdcall GetLogonUrl([out, retval] BSTR* url);
```

## <a name="parameters"></a>参数

_url_
  
> [输出]一个字符串，包含 web 身份验证中使用的格式的 URL。
    
## <a name="remarks"></a>备注

向用户显示窗体后，则[ISocialSession::LogonWeb](isocialsession-logonweb.md)方法_connectIn_参数调用与为空字符串。 
  
## <a name="see-also"></a>另请参阅

- [ISocialSession: IUnknown](isocialsessioniunknown.md)

