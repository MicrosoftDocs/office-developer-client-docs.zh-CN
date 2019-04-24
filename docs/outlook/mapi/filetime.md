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
ms.openlocfilehash: 00355546717ca61492750cb1dd113d20114b0695
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32334809"
---
# <a name="filetime"></a>FILETIME

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
保留文件的无符号64位日期和时间值。 此值表示自1601年1月1日开始起的100毫微秒单位的数量。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
   
```cpp
typedef struct _FILETIME
{
  DWORD dwLowDateTime;
  DWORD dwHighDateTime;
} FILETIME, FAR *LPFILETIME;

```

## <a name="members"></a>Members

 **dwLowDateTime**
  
> 文件时间值的低序位32位。 
    
 **dwHighDateTime**
  
> 文件时间值的高序位32位。
    
## <a name="remarks"></a>注解

PT_SYSTIME 类型的属性具有其值的**FILETIME**结构。 此类属性的**值**成员在[SPropValue](spropvalue.md)结构中的定义中有一个**FILETIME**数据类型。 
  
**FILETIME**结构的定义位于_Win32 程序员参考_和 MAPI 头文件 mapidefs.h 中。 MAPI 定义有条件的结构, 以确保在 Win32 定义不可用时定义它。 
  
## <a name="see-also"></a>另请参阅



[SPropValue](spropvalue.md)


[MAPI 结构](mapi-structures.md)

