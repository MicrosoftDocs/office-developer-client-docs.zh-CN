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
ms.openlocfilehash: bae750e7e940bc1417b3d225c9c81129e9da77b4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778823"
---
# <a name="smapiformpropenumval"></a>SMAPIFormPropEnumVal

  
  
**适用于**： Outlook 
  
将枚举的整数值映射到该值的显示名称。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiform.h  <br/> |
   
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
  
> 显示名称指向**pszDisplayName**成员的一个枚举值。 
    
## <a name="remarks"></a>说明

当用户选择窗体中的显示名称时，使用该[IMAPIProp](imapipropiunknown.md)接口实现与表单关联的存储该名称的相应的枚举值。 
  
## <a name="see-also"></a>另请参阅



[SMAPIFormProp](smapiformprop.md)
  
[SPropValue](spropvalue.md)


[MAPI 结构](mapi-structures.md)

