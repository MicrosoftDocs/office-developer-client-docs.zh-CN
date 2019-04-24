---
title: ISocialProfileAreFriendsOrColleagues
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: a0b586cd-65f6-4792-851c-4d36eaeec56d
description: 确定指定的用户是否为朋友。
ms.openlocfilehash: 183e47bea70ed378947afb6a1d0e5561fb9307f9
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331666"
---
# <a name="isocialprofilearefriendsorcolleagues"></a>ISocialProfile::AreFriendsOrColleagues

确定指定的用户是否为朋友。
  
```cpp
HRESULT _stdcall AreFriendsOrColleagues(SAFEARRAY(BSTR) userIds, [out, retval] SAFEARRAY(VARIANT_BOOL)* results);
```

## <a name="parameters"></a>参数

_userIds_
  
> 实时一个结构, 指定与社交网络上的一组人员相对应的用户 ID 值的数组。
    
_引起_
  
> 排除指向指定布尔值数组的结构的指针, 指示_userIds_数组中的相应人员是否为友元。 
    
## <a name="remarks"></a>注解

对于_userIds_参数的输入数组中表示的每个人员, 此方法设置_结果_参数的输出数组中对应的元素。 **如果为 true** , 则表示此人为朋友, **false**表示该人员不是朋友。 
  
## <a name="see-also"></a>另请参阅

- [ISocialProfile : ISocialPerson](isocialprofileisocialperson.md)

