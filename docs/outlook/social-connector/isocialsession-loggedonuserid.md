---
title: ISocialSessionLoggedOnUserID
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 54377ab4-8c69-4d7a-b9b7-278241823c8d
description: 返回一个字符串, 表示当前登录的用户的社交网络用户 ID。
ms.openlocfilehash: edb61569829f7690c2284a083d2cbd5cfe2d32a8
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32285284"
---
# <a name="isocialsessionloggedonuserid"></a>ISocialSession::LoggedOnUserID

返回一个字符串, 表示当前登录的用户的社交网络用户 ID。 
  
```cpp
[propget] HRESULT _stdcall LoggedOnUserID([out, retval] BSTR* result);
```

## <a name="property-value"></a>属性值

一个包含已登录用户的社交网络用户 ID 的字符串。
  
## <a name="see-also"></a>另请参阅

- [ISocialSession::LoggedOnUserName](isocialsession-loggedonusername.md)  
- [ISocialSession : IUnknown](isocialsessioniunknown.md)

