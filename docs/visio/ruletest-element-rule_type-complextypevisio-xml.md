---
title: 'RuleTest 元素 (Rule_Type COMPLEXType)  (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 0cb95b34-3ce0-07a5-5d57-8ac9b0570b9a
description: 指定逻辑表达式，该表达式确定目标对象是否满足验证规则。
ms.openlocfilehash: bb1f0cf9b3f712903f6e45d6d09f96607089f920
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34541517"
---
# <a name="ruletest-element-rule_type-complextype-visio-xml"></a>RuleTest 元素 (Rule_Type COMPLEXType)  (Visio XML) 

指定逻辑表达式，该表达式确定目标对象是否满足验证规则。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[RuleTest_Type](ruletest_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |validation.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="RuleTest" type="RuleTest_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Rule](rule-element-ruleset_type-complextypevisio-xml.md) <br/> |[Rule_Type](rule_type-complextypevisio-xml.md) <br/> |代表图表有效性规则集中的一个有效性规则。  <br/> |
   
### <a name="child-elements"></a>子元素

无。
  
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|公式  <br/> |xsd：string  <br/> |可选  <br/> |表示元素的公式。  <br/> |xsd：string 的值。  <br/> |
   

