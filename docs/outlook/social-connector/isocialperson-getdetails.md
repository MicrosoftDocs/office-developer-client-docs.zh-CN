---
title: ISocialPersonGetDetails
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 9ca3172a-82a3-4483-b0aa-4e848930f6ed
description: 获取一个字符串, 表示人员的详细信息, 如名字、姓氏和指向个人资料图片的 URL。
ms.openlocfilehash: 05cc2565ccd0688c7b8f4eccd6d8f42353d8743e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32286141"
---
# <a name="isocialpersongetdetails"></a>ISocialPerson::GetDetails

获取一个字符串, 表示人员的详细信息, 如名字、姓氏和指向个人资料图片的 URL。 
  
```cpp
HRESULT _stdcall GetDetails([out, retval] BSTR* details);
```

## <a name="parameters"></a>参数

_details_
  
> 排除一个 XML 字符串值, 表示人员的详细信息。
    
## <a name="remarks"></a>注解

返回的_详细信息_XML 字符串必须符合**人员**的架构定义, 如 Outlook Social Connector (.osc) 提供程序扩展性的架构中所定义。
  
如果 .osc 提供商支持社交网络上的友元缓存或混合同步, 则 .osc 调用**GetDetails** 。 当 .osc 最初获得登录用户的朋友活动时, 它会调用[ISocialPerson:: GetFriendsAndColleagues](isocialperson-getfriendsandcolleagues.md), 并将朋友的信息存储在登录用户的默认 Outlook 存储区中的 "联系人" 文件夹中, 并将其存储在特定于社交网络的 "联系人" 文件夹中。. 随后, 如果缓存的刷新间隔已过期, 则 .osc 不会调用**GetFriendsAndColleagues**或**GetDetails** 。 有关 .osc 如何将朋友的信息缓存在联系人文件夹中的详细信息, 请参阅[同步好友和活动](synchronizing-friends-and-activities.md)。
  
## <a name="see-also"></a>另请参阅

- [ISocialPerson : IUnknown](isocialpersoniunknown.md)

