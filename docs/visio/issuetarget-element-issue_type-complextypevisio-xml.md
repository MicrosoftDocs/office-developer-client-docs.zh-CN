---
title: IssueTarget 元素 (Issue_Type 复杂类型) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: bd9a5d5f-16fe-29b4-5af0-913b14d2be16
description: 根据父验证问题的目标, 指定页面或页面和形状, 与父验证问题相关联。 如果父验证问题的目标是文档, 则 IssueTarget 指定不是一个页面, 也不是一个形状。
ms.openlocfilehash: 74005bfb6035e32b7b34fdd5a8a5737813a562a0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32332520"
---
# <a name="issuetarget-element-issuetype-complextype-visio-xml"></a>IssueTarget 元素 (Issue_Type 复杂类型) ("Visio XML")

根据父验证问题的目标, 指定页面或页面和形状, 与父验证问题相关联。 如果父验证问题的目标是文档, 则**IssueTarget**指定不是一个页面, 也不是一个形状。 
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[IssueTarget_Type](issuetarget_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15  <br/> |
|**文档部件** <br/> |验证 .xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="IssueTarget" type="IssueTarget_Type" minOccurs="0" maxOccurs="1" >
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
|PageID  <br/> |xsd: unsignedInt  <br/> |必需  <br/> |指定与父验证问题关联的页面的唯一标识符。 如果目标是文档, 则 PageID 值可以为0xffffffff。  <br/> |xsd: unsignedInt 类型的值。  <br/> |
|ShapeID  <br/> |xsd: unsignedInt  <br/> |必需  <br/> |指定与父验证问题相关联的形状的唯一标识符。 如果目标是文档或页面, 则 ShapeID 值可以为0xffffffff。  <br/> |xsd: unsignedInt 类型的值。  <br/> |
   

