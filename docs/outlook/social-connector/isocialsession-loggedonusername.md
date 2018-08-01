---
title: ISocialSessionLoggedOnUserName
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: c0e7b788-3198-499c-ae21-b2032f929ed9
description: 返回一个字符串，表示在登录时使用的用户名。
ms.openlocfilehash: 02485ad2a510a81c64406ea6ec9a0f85c0e4d2f9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779356"
---
# <a name="isocialsessionloggedonusername"></a>ISocialSession::LoggedOnUserName

返回一个字符串，表示在登录时使用的用户名。
  
```cpp
[propget] HRESULT _stdcall LoggedOnUserName([out, retval] BSTR* result);
```

## <a name="property-value"></a>属性值

一个字符串值，该值代表登录用户的用户名。
  
## <a name="see-also"></a>另请参阅

- [ISocialSession::LoggedOnUserID](isocialsession-loggedonuserid.md)  
- [ISocialSession : IUnknown](isocialsessioniunknown.md)

