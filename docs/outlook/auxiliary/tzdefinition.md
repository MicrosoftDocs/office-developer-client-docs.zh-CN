---
title: TZDEFINITION
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 0ae21571-2299-6407-807c-428668bb6798
description: 表示包含所有历史、当前和未来时区班次规则的时区的完整时区 (夏时制)。
ms.openlocfilehash: 5f7000ecc1fa602b330670c2ee1c39f673a11a65
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429339"
---
# <a name="tzdefinition"></a>TZDEFINITION

表示包含所有历史、当前和未来时区班次规则的时区的完整时区 (夏时制)。
  
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
  
> 指示表示 Windows 注册表中的时区的键名称有效。 由于每个时区应始终按键名称进行标识, 因此此成员的值应始终为**TZDEFINITION_FLAG_VALID_KEYNAME**。
    
_pwszKeyName_
  
> Windows 注册表中此时区的键的名称。 此名称不得本地化。 它的最大大小为**MAX_PATH**, 在 windows 软件开发工具包 (SDK) 头文件 windows .h 中进行了定义。 
    
_cRules_
  
> 此定义的时区规则数。 最大规则数为**TZ_MAX_RULES**。 
    
_rgRules_
  
> 描述班次发生时间的规则数组。
    
## <a name="remarks"></a>说明

*rgRules*中必须至少有一个规则。 在第二个规则启动前, *rgRules*中的第一个规则被视为要使用的规则, 而不考虑第一个规则上的*stStart* 。 
  
应从最旧到最新对规则进行排序。 规则之间不允许重叠, 因此在新规则开始时, 之前的规则将被认为是结束。
  
## <a name="see-also"></a>另请参阅

- [（Outlook 导出的 Api） 的常量](constants-outlook-exported-apis.md)
- [有关重定基址日历以编程方式为夏时制](about-rebasing-calendars-programmatically-for-daylight-saving-time.md)  
- [HrCreateApptRebaser](hrcreateapptrebaser.md)

