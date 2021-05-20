---
title: ISocialPersonGetDetails
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 9ca3172a-82a3-4483-b0aa-4e848930f6ed
description: 获取一个字符串，代表人员的详细信息，例如名字、姓氏和个人资料图片的 URL。
ms.openlocfilehash: 05cc2565ccd0688c7b8f4eccd6d8f42353d8743e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427330"
---
# <a name="isocialpersongetdetails"></a>ISocialPerson::GetDetails

获取一个字符串，代表人员的详细信息，例如名字、姓氏和个人资料图片的 URL。 
  
```cpp
HRESULT _stdcall GetDetails([out, retval] BSTR* details);
```

## <a name="parameters"></a>参数

_details_
  
> [out]一个 XML 字符串值，表示人员的详细信息。
    
## <a name="remarks"></a>备注

返回 _的详细信息_ XML 字符串必须符合 **person** 的架构定义，如 Outlook Social Connector (OSC) 扩展的架构中定义。
  
如果 OSC 提供程序支持社交网络上好友的缓存或混合同步，OSC 将调用 **GetDetails。** 当 OSC 最初获取已登录用户的好友活动时，它会调用[ISocialPerson：：GetFriendsAndColleagues，](isocialperson-getfriendsandcolleagues.md)将好友的信息存储在特定于社交网络的联系人文件夹中，位于登录用户的默认 Outlook 商店中。 随后，OSC 不会调用 **GetFriendsAndColleagues** 或 **GetDetails，** 除非缓存的刷新间隔已过期。 有关 OSC 如何在联系人文件夹中缓存好友信息的信息，请参阅 [同步好友和活动](synchronizing-friends-and-activities.md)。
  
## <a name="see-also"></a>另请参阅

- [ISocialPerson : IUnknown](isocialpersoniunknown.md)

