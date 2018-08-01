---
title: TZRULE
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 75ed353c-7d3e-e148-4057-715e82a0f32c
description: 指定的时区规则时夏时制开始，以及该所在的时区规则首先会生效的年份的信息。
ms.openlocfilehash: 77d56d238d959992bfadd2d8c143391ca6fa4d5b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774461"
---
# <a name="tzrule"></a>TZRULE

指定的时区规则时夏时制开始，以及该所在的时区规则首先会生效的年份的信息。 
  
## <a name="quick-info"></a>快速信息

```cpp
typedef struct { 
    WORD        wFlags;  
    SYSTEMTIME  stStart; 
    TZREG       TZReg; 
} TZRULE;
```

## <a name="members"></a>Members

_wFlags_
  
> 为此成员的标志确定具体的详细信息，此所在的时区规则。 可能的标志如下所示：
    
   - **TZRULE_FLAG_EFFECTIVE_TZREG** — 标识为，应当前使用的规则。 只有一个规则可以标记为有效的规则。 所有其他规则只是为了比较。 
    
   - **TZRULE_FLAG_RECUR_CURRENT_TZREG** — 在定期会议标识为匹配[PidLidTimeZoneStruct](http://msdn.microsoft.com/library/2acf0036-2f3e-4f90-8614-7aa667860f74%28Office.15%29.aspx)中的规则的规则。 这可以用于检测是否**PidLidTimeZoneStruct**已修改显著旧客户端，否则不知道的新的、 更完整属性将为。 
    
_stStart_
  
> 以协调世界时 (UTC) 时区规则启动的时间。
    
_TZReg_
  
> 所在的时区规则的时区信息。
    
## <a name="remarks"></a>说明

此结构补充[TZREG](tzreg.md)提供了指示时所在的时区规则才会生效的其他信息。 
  
## <a name="see-also"></a>另请参阅

- [有关重定基址日历以编程方式为夏时制](about-rebasing-calendars-programmatically-for-daylight-saving-time.md) 
- [（Outlook 导出的 Api） 的常量](constants-outlook-exported-apis.md)
- [HrCreateApptRebaser](hrcreateapptrebaser.md)
- [TZDEFINITION](tzdefinition.md)

