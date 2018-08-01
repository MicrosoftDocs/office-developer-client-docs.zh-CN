---
title: TZREG
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: a353e1a3-0187-20af-b9ba-43438f6024d5
description: 定义夏时制时间启动时，返回到标准时间发生时，和多少个小时夏 shift 是。
ms.openlocfilehash: 85812ab053d77c07f9360b6bf3a1faaf72cae573
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774463"
---
# <a name="tzreg"></a>TZREG

定义夏时制时间启动时，返回到标准时间发生时，和多少个小时夏 shift 是。
  
## <a name="quick-info"></a>快速信息

```cpp
typedef struct RenTimeZone { 
    long        lBias;  
    long        lStandardBias; 
    long        lDaylightBias; 
    SYSTEMTIME  stStandardDate; 
    SYSTEMTIME  stDaylightDate; 
} TZREG; 

```

## <a name="members"></a>Members

_lBias_
  
> 从格林威治标准时间 (GMT) 偏移量。
    
_lStandardBias_
  
> 从标准时间的偏向的偏移量。
    
_lDaylightBias_
  
> 从偏向期间夏时制的偏移量。
    
_stStandardDate_
  
> 要切换到标准时间的时间。
    
_stDaylightDate_
  
> 要切换到夏时制的时间。
    
## <a name="remarks"></a>说明

类似于**TIME_ZONE_INFORMATION**此结构。 这是旧客户端用于存储所在的时区定期会议信息的结构。
  
## <a name="see-also"></a>另请参阅

- [有关重定基址日历以编程方式为夏时制](about-rebasing-calendars-programmatically-for-daylight-saving-time.md)  
- [HrCreateApptRebaser](hrcreateapptrebaser.md)  
- [TZRULE](tzrule.md)

