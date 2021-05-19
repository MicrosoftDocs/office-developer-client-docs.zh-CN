---
title: 表单配置文件 [Properties] 节
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: f31a08ce-3a56-4c90-9502-5bcb09d8d80f
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 86d2257b821622094ff8d5ad3a5d7b1bfc74942b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421289"
---
# <a name="form-configuration-file-properties-section"></a>表单配置文件 [Properties] 节

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
**[Properties]** 节列出了表单使用和发布的完整属性集;即，它在自定义邮件中创建的属性，MAPI 客户端应用程序可在显示列、筛选内容表、设置搜索结果文件夹等时使用这些属性。 此属性列表中的每个条目引用一个后续 **[Property。** _string_ **]** 部分，如下所示。 
  
 **[Properties]**
  
 **属性。** _string_  =  _string_
  
[ **属性的格式。** _string_]section 为： 
  
 **[属性。** _string_ **]**
  
 **类型**  =  _integer_
  
 **NmidPropset**  =  _guid_
  
 **NmidString**  =  _string_
  
 **NmidInteger**  =  _integer_
  
 **DisplayName**  =  _string_
  
 **Flags**  =  _integer_
  
 **SpecialType** = 0|1 
  
 **Enum1**  =  _string_
  
每个 **[属性。** _string_ **]** 节描述单个属性。 **Type** 条目指定属性的 MAPI 属性类型， (PT_I4) 3 个属性类型。 **NmidPropset** 项是可选的;**NmidPropset** 条目与 **NmidString** 条目或 **NmidInteger** 条目一起提供属性的名称。 **NmidString** 提供属性的名称， **而 NmidInteger** 提供属性的标识符。 **NmidString** 和 **NmidInteger** 相互排斥。 
  
如果设置， **则 NmidPropset** 应包含属性集的名称;如果不存在，则根据以下规则将 **NmidPropset** 设置为默认值：如果存在 **NmidInteger** 且其值小于 0x8000，则 **NmidPropset** 设置为 PS_MAPI。 如果 **NmidInteger** 的值设置为大于 0x8000 的整数，或者如果不存在， **则 NmidPropset** 设置为 PS_PUBLIC_STRINGS。 
  
**DisplayName** 条目包含属性的标签。 **SpecialType** 项（如果存在）和非零值表示此属性是特殊属性。 目前，唯一定义的特殊属性类型是 **SpecialType** = 1，它指示字符串枚举属性。 如果 **SpecialType** 设置为 1，Enum1 条目将引用 **[Enum1。**  _string_ **]** section. 
  
下面是 **[Properties] 部分** 和 **[Properties** 的示例。 _string_ **]** section. 
  
```cpp
[Properties]
Property.1 = Fire Hazard
Property.2 = Safe
[Property.Fire Hazard]
Type = 1
NmidPropSet = {E47F4480-8400-101B-934D-04021C007002]
NmidString = FireHazard
DisplayName = Fire Hazard
SpecialType = 1
Enum1 = HazardEnum

```

前 **一示例引用的 Enum1** 条目引用后续 **[Enum1。** _string_ **]** 描述特定类型枚举的部分。 此类枚举将关联 [Property] 中的第一 **个属性。** _string_ **]** section with an integer property， called the index. 此类枚举还包含显示索引对可以假定的可能值的列表。 不必为枚举指定属性类型，因为根据定义 **，Enum1** 项始终具有PT_I4类型。 **[Enum1 的格式。** _string_ **]** section is： 
  
 **[Enum1。** _string_ **]**
  
 **NmidPropset**  =  _guid_
  
 **NmidString**  =  _string_
  
 **NmidInteger**  =  _integer_
  
 **EnumCount**  =  _integer_
  
 **Val.** _整数_ **。显示**  =   _字符串_
  
 **Val.** _整数_ **。索引**  =   _整数_
  
下面是名为 Fire Hazard 的枚举属性的示例属性定义，其可能值为 Low、Medium 和 High。
  
```cpp
[Properties]
Property1 = Fire Hazard
[Enum1.HazardEnum]
IdxNmidPropset={E47F4480-8400-101B-934D-04021C007002]
IdxNmidString=FireHazardEnum
EnumCount = 3
Val.1.Display = Low
Val.1.Index = 1
Val.2.Display = Medium
Val.2.Index = 2
Val.3.Display = High
Val.3.Index = 3

```

 **[Enum1。** _string_ **]** sections can be used by applications for two purposes： to speed up the filtering of properties by using the index instead of the string and to sort by a different order than the alphanumeric order of the string values. 例如，可以基于低-中-高顺序而不是基于高-中-低顺序进行排序。 
  

