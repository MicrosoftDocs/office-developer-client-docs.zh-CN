---
title: TZRULE
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 75ed353c-7d3e-e148-4057-715e82a0f32c
description: 指定有关夏令时何时开始以及该时区规则首先生效的年份的时区规则的信息。
ms.openlocfilehash: 71ede7c0061a058c2dd85c7b9b36c42583a6bb84
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328614"
---
# <a name="tzrule"></a>TZRULE

指定有关夏令时何时开始以及该时区规则首先生效的年份的时区规则的信息。 
  
## <a name="quick-info"></a>快速信息

```cpp
typedef struct { 
    WORD        wFlags;  
    SYSTEMTIME  stStart; 
    TZREG       TZReg; 
} TZRULE;
```

## <a name="members"></a>成员

_wFlags_
  
> 为此成员设置的标志标识此时区规则的特定详细信息。 可能的标志如下所示：
    
   - **TZRULE_FLAG_EFFECTIVE_TZREG** — 将规则标识为当前应该使用的规则。 只能将一个规则标记为有效规则。 所有其他规则仅供比较。 
    
   - **TZRULE_FLAG_RECUR_CURRENT_TZREG** - 在定期会议中，将规则标识为 [与 PidLidTimeZoneStruct 中的规则匹配](https://msdn.microsoft.com/library/2acf0036-2f3e-4f90-8614-7aa667860f74%28Office.15%29.aspx)。 这可用于检测旧客户端是否已对 **PidLidTimeZoneStruct** 进行了重大修改，否则，不会知道新的、更完整的属性。 
    
_stStart_
  
> 以协调世界时 (UTC) 时区规则开始的时间。
    
_TZReg_
  
> 时区规则的时区信息。
    
## <a name="remarks"></a>备注

此结构通过提供指示时区规则何时生效的其他信息来扩充[TZREG。](tzreg.md) 
  
## <a name="see-also"></a>另请参阅

- [有关重定基址日历以编程方式为夏时制](about-rebasing-calendars-programmatically-for-daylight-saving-time.md) 
- [（Outlook 导出的 Api） 的常量](constants-outlook-exported-apis.md)
- [HrCreateApptRebaser](hrcreateapptrebaser.md)
- [TZDEFINITION](tzdefinition.md)

