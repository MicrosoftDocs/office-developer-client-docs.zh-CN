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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435409"
---
# <a name="smapiformpropenumval"></a>SMAPIFormPropEnumVal

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
地图枚举的整数值显示名称该值的整数值。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiform.h  <br/> |
   
```cpp
typedef struct _SMAPIFormPropEnumVal
{
  LPSTR pszDisplayName;
  ULONG nVal;
} SMAPIFormPropEnumVal;

```

## <a name="members"></a>Members

 **pszDisplayName**
  
> 字符串，包含显示名称 **nVal** 成员中指定的值的字符串。 
    
 **nVal**
  
> **pszDisplayName** 显示名称指向的枚举值。 
    
## <a name="remarks"></a>备注

当用户从表单显示名称时，会使用与表单关联的 [IMAPIProp](imapipropiunknown.md) 接口实现来存储名称的相应枚举值。 
  
## <a name="see-also"></a>另请参阅



[SMAPIFormProp](smapiformprop.md)
  
[SPropValue](spropvalue.md)


[MAPI 结构](mapi-structures.md)

