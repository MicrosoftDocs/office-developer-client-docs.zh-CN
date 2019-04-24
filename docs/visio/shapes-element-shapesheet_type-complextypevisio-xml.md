---
title: Shapes 元素 (ShapeSheet_Type 复杂类型) ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 85aa7df3-d9bd-acb3-61b3-2bd5fa256435
description: 包含 Shape 元素的集合。
ms.openlocfilehash: d4de4436079ec6290b52dd74bf3ee015c5b0d3f5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348249"
---
# <a name="shapes-element-shapesheettype-complextype-visio-xml"></a>Shapes 元素 (ShapeSheet_Type 复杂类型) ("Visio XML")

包含 Shape 元素的集合。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[Shapes_Type](shapes_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15  <br/> |
|**文档部件** <br/> |页面 # .xml、master # .xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="Shapes" type="Shapes_Type" minOccurs="0" maxOccurs="1" >
</xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果架构定义了具体要求, 如**sequence**、 **minOccurs**、 **maxOccurs**和**choice**, 请参阅 "定义" 部分。 
  
### <a name="parent-elements"></a>父元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Shape](shape-element-shapes_type-complextypevisio-xml.md) <br/> |[ShapeSheet_Type](shapesheet_type-complextypevisio-xml.md) <br/> |指定与形状关联的属性的集合。  <br/> |
   
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Shape](shape-element-shapes_type-complextypevisio-xml.md) <br/> |[ShapeSheet_Type](shapesheet_type-complextypevisio-xml.md) <br/> |包含用于定义**主控**形状、**页面**或组形状元素中的形状的元素。  <br/> |
   
### <a name="attributes"></a>Attributes

无。
  

