---
title: 表单配置文件 [属性] 部分
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: f31a08ce-3a56-4c90-9502-5bcb09d8d80f
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: f25d6b2db00f5629a9bf88499f9f4e080422ac29
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22585645"
---
# <a name="form-configuration-file-properties-section"></a>表单配置文件 [属性] 部分

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
**属性**部分列出的窗体使用并发布; 属性的完整集合即，它会在创建其自定义消息的 MAPI 客户端应用程序的属性可显示列筛选内容表，设置搜索结果文件夹时使用，依此类推。 此属性列表中的每个条目引用后续 **[属性。** _字符串_**]** 部分如下所示。 
  
 **[属性]**
  
 **属性。** _字符串_ =  _字符串_
  
格式 [**属性。** _字符串_]部分是： 
  
 **[属性。** _字符串_**]**
  
 **类型** =  _整数_
  
 **NmidPropset** =  _guid_
  
 **NmidString** =  _字符串_
  
 **NmidInteger** =  _整数_
  
 **DisplayName** =  _字符串_
  
 **Flags** =  _整数_
  
 **SpecialType** = 0 | 1 
  
 **1>** =  _字符串_
  
每个 **[属性。** _字符串_**]** 部分介绍单个属性。 该**类型**条目指定 MAPI 属性类型，例如 3 (PT_I4) 的属性。 **NmidPropset**条目是可选的。**NmidString**条目或**NmidInteger**条目，以及**NmidPropset**条目提供属性的名称。 **NmidString**提供属性的名称，而**NmidInteger**提供属性的标识符。 **NmidString**和**NmidInteger**互斥。 
  
如果设置， **NmidPropset**应包含的属性集; 名称如果不存在， **NmidPropset**设置为默认的基于以下规则： 如果**NmidInteger**存在且其值为小于 0x8000， **NmidPropset**将设置为 PS_MAPI。 如果**NmidInteger**的值设置为一个整数值大于 0x8000，或不存在， **NmidPropset**设置为 PS_PUBLIC_STRINGS。 
  
**DisplayName**条目包含属性的标签。 **SpecialType**条目，是否存在且非零值指示此属性是一个特殊的属性。 目前，仅特殊属性类型定义为**SpecialType** = 1，这表示字符串枚举属性。 如果**SpecialType**设置为 1， **1>** 条目引用 **[1>。** _字符串_**]** 部分。 
  
以下是**属性**部分的示例和 **[属性。** _字符串_**]** 部分。 
  
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

对后续的前一示例引用中的**1>** 条目 **[1>。** _字符串_**]** 部分描述特定类型的枚举。 此类枚举将关联中的第一个属性 **[属性。** _字符串_**]** 部分，包含一个整数属性，称为索引。 此类枚举还包含一组显示索引对可以假定的可能值。 指定枚举的属性类型是不必要的因为根据定义**1>** 条目始终 PT_I4 类型。 格式为 **[1>。** _字符串_**]** 部分是： 
  
 **[1>。** _字符串_**]**
  
 **NmidPropset** =  _guid_
  
 **NmidString** =  _字符串_
  
 **NmidInteger** =  _整数_
  
 **EnumCount** =  _整数_
  
 **Val。** _整数_**.显示** =  _字符串_
  
 **Val。** _整数_**.索引** =  _整数_
  
以下是名为火灾危险的低、 中型和高的可能值是枚举属性定义示例属性。
  
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

 **[1>。** _字符串_**]** 部分可用于应用程序通过两种用途： 加快使用而非字符串索引筛选属性并由不同的顺序比字符串值的字母顺序排序。 例如，排序能根据低-中的高顺序而不是高-中低顺序。 
  

