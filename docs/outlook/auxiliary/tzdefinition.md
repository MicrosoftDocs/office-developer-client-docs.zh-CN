---
title: TZDEFINITION
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 0ae21571-2299-6407-807c-428668bb6798
description: 表示包括夏令时的所有历史、当前和将来的时区班次规则在内的整个时区。
ms.openlocfilehash: 5f7000ecc1fa602b330670c2ee1c39f673a11a65
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429339"
---
# <a name="tzdefinition"></a>TZDEFINITION

表示包括夏令时的所有历史、当前和将来的时区班次规则在内的整个时区。
  
## <a name="quick-info"></a>快速信息

```cpp
typedef struct { 
    WORD     wFlags;  
    LPWSTR   pwszKeyName; 
    WORD     cRules; 
    TZRULE*  rgRules; 
} TZDEFINITION;
```

## <a name="members"></a>成员

_wFlags_
  
> 指示表示注册表中时区Windows名称有效。 由于每个时区应始终由键名称标识，因此此成员的值应始终为 **TZDEFINITION_FLAG_VALID_KEYNAME。**
    
_pwszKeyName_
  
> 注册表中此时区的项Windows名称。 此名称不得本地化。 它的最大大小为 **MAX_PATH**，这是在 Windows Sdk (SDK) 头文件 windows.h 中定义的。 
    
_cRules_
  
> 此定义的时区规则数。 最大规则数为 **TZ_MAX_RULES**。 
    
_rgRules_
  
> 描述何时发生班次的规则数组。
    
## <a name="remarks"></a>备注

rgRules 中必须至少有  *一个规则*  。 *rgRules* 中的第一个规则被视为第二个规则启动之前使用的规则，而不管第一个规则上的 *stStart* 是什么。 
  
规则应按从旧到新排序。 规则之间不允许重叠，因此当新规则启动时，以前的规则被视为结束。
  
## <a name="see-also"></a>另请参阅

- [（Outlook 导出的 Api） 的常量](constants-outlook-exported-apis.md)
- [有关重定基址日历以编程方式为夏时制](about-rebasing-calendars-programmatically-for-daylight-saving-time.md)  
- [HrCreateApptRebaser](hrcreateapptrebaser.md)

