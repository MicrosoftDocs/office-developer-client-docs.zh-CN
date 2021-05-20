---
title: 'RuleSetFlags 元素 (RuleSet_Type COMPLEXType)  (Visio XML) '
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: c18d3a84-2088-13f7-7b14-1f4c129537b4
description: 指定规则集属性。
ms.openlocfilehash: 03b94abb2d9bbe1f611671a4ac37053747a486fb
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34541594"
---
# <a name="rulesetflags-element-ruleset_type-complextype-visio-xml"></a>RuleSetFlags 元素 (RuleSet_Type COMPLEXType)  (Visio XML) 

指定规则集属性。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[RuleSetFlags_Type](rulesetflags_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |validation.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="RuleSetFlags" type="RuleSetFlags_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了特定要求，如 **sequence** **、minOccurs、maxOccurs** 和 **choice，** 请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[RuleSet](ruleset-element-rulesets_type-complextypevisio-xml.md) <br/> |[RuleSet_Type](ruleset_type-complextypevisio-xml.md) <br/> |表示一组图表验证规则。  <br/> |
   
### <a name="child-elements"></a>子元素

无。
  
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|Hidden  <br/> |xsd：boolean  <br/> |可选  <br/> |指定该规则集是否出现在"要检查的规则"列表中。  <br/> |xsd：boolean 类型的值。  <br/> |
   

