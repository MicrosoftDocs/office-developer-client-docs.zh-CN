---
title: RuleSet 元素 （RuleSets_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 5ca63b8a-782e-211f-be7a-8e177b61d8fc
description: 代表一个图表验证规则集。
ms.openlocfilehash: ae8fc52dd665e51f38c7eeae2f12ff778937d565
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781200"
---
# <a name="ruleset-element-rulesetstype-complextype-visio-xml"></a>RuleSet 元素 （RuleSets_Type 复杂类型） (Visio XML)

代表一个图表验证规则集。
  
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

如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[规则集](rulesets-element-validation_type-complextypevisio-xml.md) <br/> |[RuleSets_Type](rulesets_type-complextypevisio-xml.md) <br/> |包括文档中设置每个有效性规则的**规则集**元素。  <br/> |
   
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Rule](rule-element-ruleset_type-complextypevisio-xml.md) <br/> |[Rule_Type](rule_type-complextypevisio-xml.md) <br/> |代表图表有效性规则集中的一个有效性规则。  <br/> |
|[RuleSetFlags](rulesetflags-element-ruleset_type-complextypevisio-xml.md) <br/> |[RuleSetFlags_Type](rulesetflags_type-complextypevisio-xml.md) <br/> |指定规则设置属性。  <br/> |
   
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**说明**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|说明  <br/> |xsd: string  <br/> |可选  <br/> |指定在验证规则集的用户界面中显示的说明。 默认值为空字符串。  <br/> |Xsd: string 类型的值。  <br/> |
|已启用  <br/> |化  <br/> |可选  <br/> |指定验证触发为当前文档时是否检查中指定的有效性规则集的规则。 默认值为 True。  <br/> |化类型的值。  <br/> |
|ID  <br/> |xsd:unsignedInt  <br/> |必需  <br/> |指定有效性规则集的唯一的标识符。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
|名称  <br/> |xsd: string  <br/> |可选  <br/> |指定有效性规则集的本地的名称。 默认值为 NameU 属性值。  <br/> |Xsd: string 类型的值。  <br/> |
|NameU  <br/> |xsd: string  <br/> |必需  <br/> |指定有效性规则集的通用的名称。  <br/> |Xsd: string 类型的值。  <br/> |
   

