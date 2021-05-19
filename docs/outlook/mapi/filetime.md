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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409501"
---
# <a name="filetime"></a>FILETIME

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
保留文件的未签名 64 位日期和时间值。 此值表示自 1601 年 1 月 1 日开始以来 100 纳秒单位的数量。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
   
```cpp
typedef struct _FILETIME
{
  DWORD dwLowDateTime;
  DWORD dwHighDateTime;
} FILETIME, FAR *LPFILETIME;

```

## <a name="members"></a>Members

 **dwLowDateTime**
  
> 文件时间值的低顺序 32 位。 
    
 **dwHighDateTime**
  
> 文件时间值的 32 位高顺序值。
    
## <a name="remarks"></a>备注

类型为 PT_SYSTIME其值具有 **FILETIME** 结构。 此类属性具有 **FILETIME** 数据类型在 [SPropValue](spropvalue.md)结构中的定义中为 **Value** 成员定义。 
  
**FILETIME** 结构的定义位于 _Win32 程序员_ 参考和 MAPI 头文件 Mapidefs.h 中。 MAPI 有条件地定义结构，以确保它在 Win32 定义不可用时定义。 
  
## <a name="see-also"></a>另请参阅



[SPropValue](spropvalue.md)


[MAPI 结构](mapi-structures.md)

