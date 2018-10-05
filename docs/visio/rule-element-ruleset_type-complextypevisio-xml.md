---
title: Rule 元素 （RuleSet_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: fcd22f3a-c8e8-1133-160c-fe26e612a15d
description: 代表图表有效性规则集中的一个有效性规则。
ms.openlocfilehash: 92d52456164b89ff2aad31fa8d8f02f818c8bd1c
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25395908"
---
# <a name="rule-element-rulesettype-complextype-visio-xml"></a>Rule 元素 （RuleSet_Type 复杂类型） (Visio XML)

代表图表有效性规则集中的一个有效性规则。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[Rule_Type](rule_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |validation.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="Rule" type="Rule_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[规则集](ruleset-element-rulesets_type-complextypevisio-xml.md) <br/> |[RuleSet_Type](ruleset_type-complextypevisio-xml.md) <br/> |代表一个图表验证规则集。  <br/> |
   
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[RuleFilter](rulefilter-element-rule_type-complextypevisio-xml.md) <br/> |[RuleFilter_Type](rulefilter_type-complextypevisio-xml.md) <br/> |指定确定是否应将有效性规则应用于目标对象的逻辑表达式。  <br/> |
|[RuleTest](ruletest-element-rule_type-complextypevisio-xml.md) <br/> |[RuleTest_Type](ruletest_type-complextypevisio-xml.md) <br/> |指定确定目标对象是否满足有效性规则的逻辑表达式。  <br/> |
   
### <a name="attributes"></a>Attributes

|**属性**|**类型**|**必需**|**说明**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|Category  <br/> |xsd: string  <br/> |可选  <br/> |指定**类别**列中的问题窗口中显示的文本。 默认值为空字符串。  <br/> |Xsd: string 类型的值。  <br/> |
|说明  <br/> |xsd: string  <br/> |可选  <br/> |指定在用户界面中显示的有效性规则的说明。 默认值为"Unknown"。  <br/> |Xsd: string 类型的值。  <br/> |
|ID  <br/> |xsd:unsignedInt  <br/> |必需  <br/> |指定的有效性规则的唯一标识符。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
|忽略  <br/> |化  <br/> |可选  <br/> |指定是否当前忽略有效性规则。 默认值为 False。  <br/> |化类型的值。  <br/> |
|NameU  <br/> |xsd: string  <br/> |必需  <br/> |指定的有效性规则的通用名称。  <br/> |Xsd: string 类型的值。  <br/> |
|RuleTarget  <br/> |xsd:int  <br/> |可选  <br/> |指定的有效性规则应用于的对象的类型。  <br/> |Xsd:int 类型的值。  <br/> |
   

