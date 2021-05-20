---
title: 'RuleSet 元素 (RuleSets_Type complexType)  (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 5ca63b8a-782e-211f-be7a-8e177b61d8fc
description: 表示一组图表验证规则。
ms.openlocfilehash: c6fc8df6d9c84f44496d69207dfb9cfb878659e3
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34541636"
---
# <a name="ruleset-element-rulesets_type-complextype-visio-xml"></a>RuleSet 元素 (RuleSets_Type complexType)  (Visio XML) 

表示一组图表验证规则。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[RuleSet_Type](ruleset_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |validation.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="RuleSet" type="RuleSet_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[RuleSets](rulesets-element-validation_type-complextypevisio-xml.md) <br/> |[RuleSets_Type](rulesets_type-complextypevisio-xml.md) <br/> |包括文档中每个验证规则集 **RuleSet** 元素。  <br/> |
   
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Rule](rule-element-ruleset_type-complextypevisio-xml.md) <br/> |[Rule_Type](rule_type-complextypevisio-xml.md) <br/> |代表图表有效性规则集中的一个有效性规则。  <br/> |
|[RuleSetFlags](rulesetflags-element-ruleset_type-complextypevisio-xml.md) <br/> |[RuleSetFlags_Type](rulesetflags_type-complextypevisio-xml.md) <br/> |指定规则集属性。  <br/> |
   
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|说明  <br/> |xsd：string  <br/> |可选  <br/> |指定在用户界面中显示用于验证说明的说明规则集。 默认值为空字符串。  <br/> |xsd：string 类型的值。  <br/> |
|已启用  <br/> |xsd：boolean  <br/> |可选  <br/> |指定在触发当前文档的验证规则集是否检查指定验证规则中的规则。 默认值为 True。  <br/> |xsd：boolean 类型的值。  <br/> |
|ID  <br/> |xsd：unsignedInt  <br/> |必需  <br/> |指定验证规则的唯一规则集。  <br/> |xsd：unsignedInt 类型的值。  <br/> |
|名称  <br/> |xsd：string  <br/> |可选  <br/> |指定验证策略的本地规则集。 默认为 NameU 属性值。  <br/> |xsd：string 类型的值。  <br/> |
|NameU  <br/> |xsd：string  <br/> |必需  <br/> |指定验证规则的通用规则集。  <br/> |xsd：string 类型的值。  <br/> |
   

