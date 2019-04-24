---
title: 表单配置文件 [Properties] 部分
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: f31a08ce-3a56-4c90-9502-5bcb09d8d80f
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 86d2257b821622094ff8d5ad3a5d7b1bfc74942b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328103"
---
# <a name="form-configuration-file-properties-section"></a>表单配置文件 [Properties] 部分

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
**[Properties]** 部分列出了表单使用和发布的完整属性集;即, 它在自定义邮件中创建的属性, MAPI 客户端应用程序可以在显示列、筛选内容表、设置搜索结果文件夹等时使用这些属性。 此属性列表中的每个条目都引用一个后续的 **[属性。** _string_**** "一节, 如下所示。 
  
 **属性**
  
 **财产.** _字符串_ =  _字符串_
  
[属性的格式 **。** _string_]部分为: 
  
 **财产.** _string_**]**
  
 **类型** =  _integer_
  
 **NmidPropset** =  _guid_
  
 **NmidString** =  _字符串_
  
 **NmidInteger** =  _整数_
  
 **DisplayName** =  _字符串_
  
 **Flags** =  _integer_
  
 **SpecialType** = 0 | 1 
  
 **Enum1** =  _字符串_
  
每个 **[属性。** _string_**]** 部分介绍了单个属性。 **类型**条目指定了该属性的 MAPI 属性类型 (例如, 3 (PT_I4))。 **NmidPropset**条目是可选的;**NmidString**项或**NmidInteger**项一起使用时, **NmidPropset**项将提供属性的名称。 **NmidString**提供属性的名称, 而**NmidInteger**将提供属性的标识符。 **NmidString**和**NmidInteger**是相互排斥的。 
  
如果设置, 则**NmidPropset**应包含属性集的名称;如果不存在, 则根据以下规则将**NmidPropset**设置为默认值: 如果存在**NmidInteger**且其值小于 0x8000, 则将**NmidPropset**设置为 PS_MAPI。 如果**NmidInteger**的值设置为大于0x8000 的整数, 或者如果不存在, 则**NmidPropset**设置为 PS_PUBLIC_STRINGS。 
  
**DisplayName**项包含属性的标签。 **SpecialType**条目 (如果存在) 和非零表示此属性是特殊属性。 目前, 唯一定义的特殊属性类型是**SpecialType** = 1, 它表示字符串枚举属性。 如果将**SpecialType**设置为 1, 则**Enum1**项将引用 **[Enum1。** _string_**]** 部分。 
  
以下是 **[properties]** 节和 **[properties** ] 的示例。 _string_**]** 部分。 
  
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

前面的示例中的**Enum1**条目引用了随后的 **[Enum1。** _string_**** "一节描述特定类型的枚举。 这样的枚举将关联 **[属性**中的第一个属性。 _string_**** 包含 integer 属性 (称为 index) 的节。 此类枚举还包含显示索引对可以假设的可能值的列表。 为枚举指定属性类型是不必要的, 因为根据定义, **Enum1**条目始终具有 PT_I4 类型。 **[Enum1.** _string_**]** 部分为: 
  
 **[Enum1。** _string_**]**
  
 **NmidPropset** =  _guid_
  
 **NmidString** =  _字符串_
  
 **NmidInteger** =  _整数_
  
 **EnumCount** =  _整数_
  
 **初始值.** _integer_**.显示** =  _字符串_
  
 **初始值.** _integer_**.索引** =  _integer_
  
以下是名为火灾危险的枚举属性的示例属性定义, 其可能值为低、中和高。
  
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

 **[Enum1。** _string_**]** 可由应用程序用于两个部分: 通过使用索引而不是字符串来加快对属性的筛选, 并按与字符串值的字母数字顺序不同的顺序进行排序。 例如, 可以根据低标准高订单 (而不是高中低订单) 执行排序。 
  

