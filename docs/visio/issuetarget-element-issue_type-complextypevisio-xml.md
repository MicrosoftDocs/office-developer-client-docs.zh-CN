---
title: IssueTarget 元素 （Issue_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: bd9a5d5f-16fe-29b4-5af0-913b14d2be16
description: 根据目标对象的父验证问题，指定是页上，或同时页及其与父验证问题关联的形状。 如果父验证问题目标为文档、 IssueTarget 指定的页和形状都不。
ms.openlocfilehash: 72789782a37b29daa48cd01adb0b8eda4ebf73ac
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780519"
---
# <a name="issuetarget-element-issuetype-complextype-visio-xml"></a>IssueTarget 元素 （Issue_Type 复杂类型） (Visio XML)

根据目标对象的父验证问题，指定是页上，或同时页及其与父验证问题关联的形状。 如果父验证问题目标为文档、 **IssueTarget**指定的页和形状都不。 
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[IssueTarget_Type](issuetarget_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |validation.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="IssueTarget" type="IssueTarget_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[问题](issue-element-issues_type-complextypevisio-xml.md) <br/> |[Issue_Type](issue_type-complextypevisio-xml.md) <br/> |代表文档中的一个验证问题。  <br/> |
   
### <a name="child-elements"></a>子元素

无。
  
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**说明**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|PageID  <br/> |xsd:unsignedInt  <br/> |必需  <br/> |指定的页面的父验证问题与相关联的唯一标识符。 如果目标是文档，则 PageID 值可以是 0xFFFFFFFF。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
|ShapeID  <br/> |xsd:unsignedInt  <br/> |必需  <br/> |指定与父验证问题关联的形状的唯一标识符。 如果目标是文档或页面，ShapeID 值可以是 0xFFFFFFFF。  <br/> |Xsd:unsignedInt 类型的值。  <br/> |
   

