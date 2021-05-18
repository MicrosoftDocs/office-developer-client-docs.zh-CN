---
title: 关于将 TZDEFINITION 保存到流以提交到二进制属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 0dec535d-d48f-39a5-97d5-0bd109134b3b
description: 时区属性 PidLidAppointmentTimeZoneDefinitionEndDisplay、PidLidAppointmentTimeZoneDefinitionRecur 和 PidLidAppointmentTimeZoneDefinitionStartDisplay 是二进制命名属性，其中每个属性都包含映射到 TZDEFINITION 结构的持久格式的流。
ms.openlocfilehash: f94b751a55aa852c962eebe5d46968e9e622e315
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316973"
---
# <a name="about-persisting-tzdefinition-to-a-stream-to-commit-to-a-binary-property"></a>关于将 TZDEFINITION 保存到流以提交到二进制属性

时区属性[PidLidAppointmentTimeZoneDefinitionEndDisplay、PidLidAppointmentTimeZoneDefinitionRecur](https://msdn.microsoft.com/library/7b6193cb-612b-408e-b9bc-285df313e2cc%28Office.15%29.aspx)和[PidLidAppointmentTimeZoneDefinitionStartDisplay](https://msdn.microsoft.com/library/08239670-3211-420c-99d7-0056ed967cb8%28Office.15%29.aspx)是二进制命名属性，其中每个属性都包含映射到[TZDEFINITION](tzdefinition.md)结构的持久格式的流。 [](https://msdn.microsoft.com/library/52fd57a0-9e34-4452-9ecd-2acb454446c9%28Office.15%29.aspx) 
  
本主题介绍将 **TZDEFINITION** 持久化到流以提交到三个二进制属性之一时可以使用的一种小尾格式。 在分析器中使用相同的尾数格式解释从这些属性之一获取的流值。 
  
```cpp
BYTE  bMajorVersion;    // breaking change
BYTE  bMinorVersion;    // extensibility
WORD  cbHeader;         // size of following data until TZREG sub structure
WORD  wFlags;
if (TZDEFINITION_FLAG_VALID_GUID)
   GUID  guid;                // guid
if (TZDEFINITION_FLAG_VALID_KEYNAME)     
    WORD   cchKeyName;        // does not include null char
    WCHAR  rgchKeyName;       // not null terminated
    WORD  cRules;             // number of rules
// for each rule
   BYTE        bMajorVersion;         // breaking change
   BYTE        bMinorVersion;         // extensibility
   WORD        cbRule;                // size of following data
   WORD        wFlags;                // flags
   SYSTEMTIME  stStart;               // GMT when this rule starts
// Following are the fields of the TZREG sub structure
   long        lBias;                // offset from GMT
   long        lStandardBias;        // offset from bias during standard time
   long        lDaylightBias;        // offset from bias during daylight time
   SYSTEMTIME  stStandardDate;       // time to switch to standard time
   SYSTEMTIME  stDaylightDate;       // time to switch to daylight time
```

主版本号用于进行重大更改。 不熟悉主版本号的客户端应该将该属性视为不存在。 编写结构的客户端应指定常量 **TZ_BIN_VERSION_MAJOR。** 
  
次要版本号用于扩展性。 不熟悉次要版本号的客户端应读取他们理解的数据，并跳过可能附加到每个规则或整个流的数据。 编写结构的客户端应指定常量 **TZ_BIN_VERSION_MINOR。** 
  
如果分析程序无法理解标头的主要版本，则它不应读取结构的其余部分，并像缺少数据一样运行。 如果分析程序无法理解标头的次要版本，则它应当使用 **cbHeader** 忽略它无法理解的部分，并提前读取它理解的流部分。 
  
**wFlags 的值** 始终为 **TZDEFINITION_FLAG_VALID_KEYNAME**。 键名称的最大大小为 **MAX_PATH**。 
  
如果分析程序无法识别规则的主要版本，客户端应忽略该规则，并使用 **cbRule** 前进到下一个规则。 如果分析程序无法识别规则的次要版本，则客户端只应分析它理解的规则部分。 
  
将 **TZDEFINITION** 结构持久化到流时，分析程序不应尝试编写它无法理解的任何信息。 
  
最大规则数为 1024。
  
请注意， [此处保留 TZREG](tzreg.md) 结构的方式与单独保留时不同，因此不能使用相同的代码进行分析。 
  
## <a name="see-also"></a>另请参阅

- [（Outlook 导出的 Api） 的常量](constants-outlook-exported-apis.md)
- [分析二进制属性读取 TZDEFINITION 结构的流](how-to-parse-stream-from-binary-property-to-read-tzdefinition-structure.md)
- [从约会中读取时区属性](how-to-read-time-zone-properties-from-an-appointment.md)

