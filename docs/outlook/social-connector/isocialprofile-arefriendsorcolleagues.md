---
title: ISocialProfileAreFriendsOrColleagues
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: a0b586cd-65f6-4792-851c-4d36eaeec56d
description: 确定指定的用户是否朋友。
ms.openlocfilehash: 17e7864dc60bf99df2028e5f6c57f0619d880a8e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779214"
---
# <a name="isocialprofilearefriendsorcolleagues"></a>ISocialProfile::AreFriendsOrColleagues

确定指定的用户是否朋友。
  
```cpp
HRESULT _stdcall AreFriendsOrColleagues(SAFEARRAY(BSTR) userIds, [out, retval] SAFEARRAY(VARIANT_BOOL)* results);
```

## <a name="parameters"></a>参数

_userIds_
  
> [in]一个指定的对应一封社交网络上的用户 ID 值的数组的结构。
    
_结果_
  
> [输出]一个指向指定布尔值，指示_userIds_数组中的相应人员是否朋友数组的结构。 
    
## <a name="remarks"></a>说明

对于表示_userIds_参数的输入数组中每个用户，此方法设置输出_结果_参数数组中对应的元素。 **true**指示人员朋友，并且该人员不朋友**false**指示。 
  
## <a name="see-also"></a>另请参阅

- [ISocialProfile : ISocialPerson](isocialprofileisocialperson.md)

