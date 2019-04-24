---
title: RuleInfo 元素 (Issue_Type 复杂类型) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: aec47b43-adbe-3344-fbac-29554f244c99
description: 指定与父验证问题相关的验证规则的相关信息。
ms.openlocfilehash: f0cf726f0c5d6943ef72669aa92f361a7367459c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356985"
---
# <a name="ruleinfo-element-issuetype-complextype-visio-xml"></a>RuleInfo 元素 (Issue_Type 复杂类型) ("Visio XML")

指定与父验证问题相关的验证规则的相关信息。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[RuleInfo_Type](ruleinfo_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15  <br/> |
|**文档部件** <br/> |验证 .xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="RuleInfo" type="RuleInfo_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[问题](issue-element-issues_type-complextypevisio-xml.md) <br/> |[Issue_Type](issue_type-complextypevisio-xml.md) <br/> |代表文档中的一个验证问题。  <br/> |
   
### <a name="child-elements"></a>子元素

无。
  
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**描述**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|RuleID  <br/> |xsd: unsignedInt  <br/> |必需  <br/> |指定父问题所适用的验证规则的唯一标识符。  <br/> |xsd: unsignedInt 类型的值。  <br/> |
|RuleSetID  <br/> |xsd: unsignedInt  <br/> |必需  <br/> |指定父问题所适用的验证规则集的唯一标识符。  <br/> |xsd: unsignedInt 类型的值。  <br/> |
   

