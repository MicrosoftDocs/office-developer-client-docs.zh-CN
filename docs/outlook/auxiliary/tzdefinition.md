---
title: TZDEFINITION
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 0ae21571-2299-6407-807c-428668bb6798
description: 代表包括夏时制的所有历史、 当前和将来的时区 shift 规则整个所在的时区。
ms.openlocfilehash: f436216f5da882ea8ac144e6bd384e51e31abb8e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774473"
---
# <a name="tzdefinition"></a>TZDEFINITION

代表包括夏时制的所有历史、 当前和将来的时区 shift 规则整个所在的时区。
  
## <a name="quick-info"></a>快速信息

```cpp
typedef struct { 
    WORD     wFlags;  
    LPWSTR   pwszKeyName; 
    WORD     cRules; 
    TZRULE*  rgRules; 
} TZDEFINITION;
```

## <a name="members"></a>Members

_wFlags_
  
> 指示键名值，该值代表在 Windows 注册表中的时区有效。 因为每个时区始终应由项的名称，此成员应始终具有值**TZDEFINITION_FLAG_VALID_KEYNAME**。
    
_pwszKeyName_
  
> 此时区在 Windows 注册表中项的名称。 此名称必须不进行本地化。 它具有**MAX_PATH**，在 Windows 软件开发工具包 (SDK) 标头文件 windows.h 中定义的最大大小。 
    
_cRules_
  
> 为此定义的时区规则的数目。 规则的最大数目是**TZ_MAX_RULES**。 
    
_rgRules_
  
> 规则描述引进发生的数组。
    
## <a name="remarks"></a>说明

*RgRules*中必须有至少一个规则。 考虑为要使用直到开始的第二个规则的规则，无论*stStart*上的第一个规则， *rgRules*中的第一个规则。 
  
到最新，应从最早排序规则。 允许规则，以便将前一个规则视为结束时开始一个新规则之间没有重叠。
  
## <a name="see-also"></a>另请参阅

- [（Outlook 导出的 Api） 的常量](constants-outlook-exported-apis.md)
- [有关重定基址日历以编程方式为夏时制](about-rebasing-calendars-programmatically-for-daylight-saving-time.md)  
- [HrCreateApptRebaser](hrcreateapptrebaser.md)

