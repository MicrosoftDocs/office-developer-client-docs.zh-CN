---
title: SMAPIFormPropEnumVal
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SMAPIFormPropEnumVal
api_type:
- COM
ms.assetid: 694d40e9-cff2-435e-ad90-446044c306d2
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 353bc574ca5987d71faf4841744de30a3d6c3f19
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32309490"
---
# <a name="smapiformpropenumval"></a>SMAPIFormPropEnumVal

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将枚举整数值映射到该值的显示名称。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiform  <br/> |
   
```cpp
typedef struct _SMAPIFormPropEnumVal
{
  LPSTR pszDisplayName;
  ULONG nVal;
} SMAPIFormPropEnumVal;

```

## <a name="members"></a>Members

 **pszDisplayName**
  
> 包含**nVal**成员中指定的值的显示名称的字符串。 
    
 **nVal**
  
> 由**pszDisplayName**成员指向的显示名称的枚举值。 
    
## <a name="remarks"></a>注解

当用户从窗体中选择显示名称时, 将使用与表单相关联的[IMAPIProp](imapipropiunknown.md)接口实现来存储该名称对应的枚举值。 
  
## <a name="see-also"></a>另请参阅



[SMAPIFormProp](smapiformprop.md)
  
[SPropValue](spropvalue.md)


[MAPI 结构](mapi-structures.md)

