---
title: 规则集元素 (RuleSets_Type 复杂类型) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 5ca63b8a-782e-211f-be7a-8e177b61d8fc
description: 表示一组图表有效性规则。
ms.openlocfilehash: 1231e8cdb3c8781dc47f470c0477b4585b1331c6
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32318912"
---
# <a name="ruleset-element-rulesetstype-complextype-visio-xml"></a>规则集元素 (RuleSets_Type 复杂类型) ("Visio XML")

表示一组图表有效性规则。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[RuleSet_Type](ruleset_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15  <br/> |
|**文档部件** <br/> |验证 .xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="RuleSet" type="RuleSet_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[RuleSets](rulesets-element-validation_type-complextypevisio-xml.md) <br/> |[RuleSets_Type](rulesets_type-complextypevisio-xml.md) <br/> |为文档中的每个有效性规则集包含一个**规则集**元素。  <br/> |
   
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Rule](rule-element-ruleset_type-complextypevisio-xml.md) <br/> |[Rule_Type](rule_type-complextypevisio-xml.md) <br/> |代表图表有效性规则集中的一个有效性规则。  <br/> |
|[RuleSetFlags](rulesetflags-element-ruleset_type-complextypevisio-xml.md) <br/> |[RuleSetFlags_Type](rulesetflags_type-complextypevisio-xml.md) <br/> |指定规则集属性。  <br/> |
   
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|说明  <br/> |xsd: string  <br/> |可选  <br/> |指定在验证规则集的用户界面中显示的说明。 默认值为空字符串。  <br/> |xsd: string 类型的值。  <br/> |
|已启用  <br/> |xsd: boolean  <br/> |可选  <br/> |指定在为当前文档触发验证时是否检查指定的验证规则集中的规则。 默认值为 True。  <br/> |xsd: boolean 类型的值。  <br/> |
|ID  <br/> |xsd: unsignedInt  <br/> |必需  <br/> |指定验证规则集的唯一标识符。  <br/> |xsd: unsignedInt 类型的值。  <br/> |
|名称  <br/> |xsd: string  <br/> |可选  <br/> |指定验证规则集的本地名称。 默认值为 NameU 属性值。  <br/> |xsd: string 类型的值。  <br/> |
|NameU  <br/> |xsd: string  <br/> |必需  <br/> |指定验证规则集的通用名称。  <br/> |xsd: string 类型的值。  <br/> |
   

