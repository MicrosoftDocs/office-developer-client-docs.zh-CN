---
title: FILETIME
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.FILETIME
api_type:
- COM
ms.assetid: 4af8e79a-697e-44a1-8576-fdc57726e9ef
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d58a216a41ff8fe93387ce6d9d1d6aa16f36f224
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22583251"
---
# <a name="filetime"></a>FILETIME

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含无符号的 64 位日期和文件的时间值。 此值表示自 1601 年 1 月 1 日启动以来的 100 纳秒的单位数。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
   
```cpp
typedef struct _FILETIME
{
  DWORD dwLowDateTime;
  DWORD dwHighDateTime;
} FILETIME, FAR *LPFILETIME;

```

## <a name="members"></a>Members

 **dwLowDateTime**
  
> 低序位 32 位的文件时间值。 
    
 **dwHighDateTime**
  
> 高阶 32 位的文件时间值。
    
## <a name="remarks"></a>注解

PT_SYSTIME 类型的属性具有其值**FILETIME**结构。 这种属性**值**在其定义[SPropValue](spropvalue.md)结构中成员的具有**FILETIME**数据类型。 
  
在_Win32 程序员参考_和 MAPI 头文件 Mapidefs.h **FILETIME**结构的定义。 MAPI 定义有条件地以确保它被定义 Win32 定义不可用时的结构。 
  
## <a name="see-also"></a>另请参阅



[SPropValue](spropvalue.md)


[MAPI 结构](mapi-structures.md)

