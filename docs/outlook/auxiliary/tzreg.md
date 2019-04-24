---
title: TZREG
manager: soliver
ms.date: 12/07/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: a353e1a3-0187-20af-b9ba-43438f6024d5
description: 定义夏时制的开始时间、何时返回标准时间以及夏时制转换的小时数。
ms.openlocfilehash: 136ff6ad0c1a9bc2ad61ef7ba698d66d645165d8
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32307838"
---
# <a name="tzreg"></a>TZREG

定义夏时制的开始时间、何时返回标准时间以及夏时制转换的小时数。
  
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

## <a name="members"></a>成员

_lBias_
  
> 格林威治标准时间 (GMT) 的偏移量。
    
_lStandardBias_
  
> 标准时间内偏置的偏移量。
    
_lDaylightBias_
  
> 夏时制中偏移偏差。
    
_stStandardDate_
  
> 切换到标准时间的时间。
    
_stDaylightDate_
  
> 切换到夏时制的时间。
    
## <a name="remarks"></a>注解

此结构类似于**TIME_ZONE_INFORMATION**。 这是旧版客户端用来存储定期会议的时区信息的结构。
  
## <a name="see-also"></a>另请参阅

- [有关重定基址日历以编程方式为夏时制](about-rebasing-calendars-programmatically-for-daylight-saving-time.md)  
- [HrCreateApptRebaser](hrcreateapptrebaser.md)  
- [TZRULE](tzrule.md)

