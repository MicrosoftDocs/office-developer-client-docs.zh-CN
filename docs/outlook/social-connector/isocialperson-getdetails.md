---
title: ISocialPersonGetDetails
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 9ca3172a-82a3-4483-b0aa-4e848930f6ed
description: 获取一个字符串，表示详细信息的人员，如名字、 姓氏和一个 URL 为配置文件图片。
ms.openlocfilehash: 158ce9b5c6a97ffff0325427ed07c74f518941d8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779208"
---
# <a name="isocialpersongetdetails"></a>ISocialPerson::GetDetails

获取一个字符串，表示详细信息的人员，如名字、 姓氏和一个 URL 为配置文件图片。 
  
```cpp
HRESULT _stdcall GetDetails([out, retval] BSTR* details);
```

## <a name="parameters"></a>参数

_详细信息_
  
> [输出]XML 字符串值，该值代表的人员的详细信息。
    
## <a name="remarks"></a>说明

Outlook Social Connector (OSC) 提供程序扩展性的架构中定义，返回的_详细信息_的 XML 字符串必须符合**人**，架构定义。
  
OSC 社交网络上调用**GetDetails**如果 OSC 提供程序支持缓存或朋友混合同步。 当 OSC 最初获取在用户登录朋友的活动时，它调用[ISocialPerson::GetFriendsAndColleagues](isocialperson-getfriendsandcolleagues.md)，并将朋友的信息存储中特定于登录的用户的默认 Outlook 存储区中的社交网络联系人文件夹. 随后 OSC 不调用**GetFriendsAndColleagues**或**GetDetails**除非缓存刷新间隔时间已过期。 有关如何 OSC 缓存联系人文件夹中的朋友的信息的详细信息，请参阅[同步朋友和活动](synchronizing-friends-and-activities.md)。
  
## <a name="see-also"></a>另请参阅

- [ISocialPerson : IUnknown](isocialpersoniunknown.md)

