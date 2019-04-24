---
title: 验证元素 ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: db6292c7-9f4c-c287-803b-64fa41c0a269
description: 存储有关文档图表验证的信息。
ms.openlocfilehash: 7e40cd3a79922b56800cbb566a0d88de23829cc0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329079"
---
# <a name="validation-element-visio-xml"></a>验证元素 ("Visio XML")

存储有关文档图表验证的信息。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[Validation_Type](validation_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15  <br/> |
|**文档部件** <br/> |验证 .xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="Validation" type="Validation_Type" > </xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。 
  
### <a name="parent-elements"></a>父元素

无。
  
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Issues](issues-element-validation_type-complextypevisio-xml.md) <br/> |[Issues_Type](issues_type-complextypevisio-xml.md) <br/> |包含文档的所有**问题**元素。  <br/> |
|[RuleSets](rulesets-element-validation_type-complextypevisio-xml.md) <br/> |[RuleSets_Type](rulesets_type-complextypevisio-xml.md) <br/> |为文档中的每个有效性规则集包含一个**规则集**元素。  <br/> |
|[ValidationProperties](validationproperties-element-validation_type-complextypevisio-xml.md) <br/> |[ValidationProperties_Type](validationproperties_type-complextypevisio-xml.md) <br/> |封装与文档的验证相关的属性。  <br/> |
   
### <a name="attributes"></a>Attributes

无。
  

