---
title: ISocialProfileAreFriendsOrColleagues
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: a0b586cd-65f6-4792-851c-4d36eaeec56d
description: 确定指定用户是否是好友。
ms.openlocfilehash: 183e47bea70ed378947afb6a1d0e5561fb9307f9
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412560"
---
# <a name="isocialprofilearefriendsorcolleagues"></a>ISocialProfile::AreFriendsOrColleagues

确定指定用户是否是好友。
  
```cpp
HRESULT _stdcall AreFriendsOrColleagues(SAFEARRAY(BSTR) userIds, [out, retval] SAFEARRAY(VARIANT_BOOL)* results);
```

## <a name="parameters"></a>参数

_userIds_
  
> [in]一种结构，用于指定对应于社交网络上一组人员的用户 ID 值的数组。
    
_results_
  
> [out]指向指定布尔值数组的结构的指针，指示  _userIds_ 数组中的相应人员是否是好友。 
    
## <a name="remarks"></a>备注

对于  _userIds_ 参数的输入数组中表示的每个人，此方法设置 results 参数的输出数组中的  _相应_ 元素。 **true** 表示该人员是好友 **，false** 表示该人员不是好友。 
  
## <a name="see-also"></a>另请参阅

- [ISocialProfile : ISocialPerson](isocialprofileisocialperson.md)

