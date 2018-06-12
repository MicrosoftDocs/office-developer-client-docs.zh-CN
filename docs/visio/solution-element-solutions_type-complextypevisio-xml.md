---
title: Solution 元素 （Solutions_Type 复杂类型） (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 46bf34be-761e-9d44-ab06-83d4c8932cab
description: 指定 XML 存储在绘图中的解决方案的一个的实例。
ms.openlocfilehash: 06cefcbf9b0191a9dded5548a457c4a0e50a33ca
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781409"
---
# <a name="solution-element-solutionstype-complextype-visio-xml"></a>Solution 元素 （Solutions_Type 复杂类型） (Visio XML)

指定 XML 存储在绘图中的解决方案的一个的实例。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[Solution_Type](solution_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |solutions.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="Solution"  type="Solution_Type" minOccurs="0" maxOccurs="unbounded" ></xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[解决方案](solutions-elementvisio-xml.md) <br/> |[Solutions_Type](solutions_type-complextypevisio-xml.md) <br/> |存储在文档中存储的解决方案的属性。  <br/> |
   
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Rel](rel-element-solution_type-complextypevisio-xml.md) <br/> |[Rel_Type](rel_type-complextypevisio-xml.md) <br/> |解决方案与此解决方案关联的 XML 中指定到部件的关系。  <br/> |
   
### <a name="attributes"></a>属性

|**属性**|**类型**|**必需**|**说明**|**可能的值**|
|:-----|:-----|:-----|:-----|:-----|
|名称  <br/> |xsd: string  <br/> |必需  <br/> |解决方案的名称。  <br/> |Xsd: string 类型的值。  <br/> |
   

