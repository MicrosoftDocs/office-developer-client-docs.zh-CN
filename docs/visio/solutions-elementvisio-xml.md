---
title: 解决方案元素 (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 75e53ad0-3ca3-11a1-9107-63ec15601c13
description: 指定文档中存储的解决方案的属性。
ms.openlocfilehash: 65f6d3a34a62cd5e7b63ca0f6518a6e839b48360
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25400216"
---
# <a name="solutions-element-visio-xml"></a>解决方案元素 (Visio XML)

指定文档中存储的解决方案的属性。
  
## <a name="element-information"></a>元素信息

|||
|:-----|:-----|
|**元素类型** <br/> |[Solutions_Type](solutions_type-complextypevisio-xml.md) <br/> |
|**命名空间** <br/> |https://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**架构文件** <br/> |VisioSchema15.xsd  <br/> |
|**文档部件** <br/> |solutions.xml  <br/> |
   
## <a name="definition"></a>定义

```XML
< xs:element name="Solutions" type="Solutions_Type" ></xs:element >
```

## <a name="elements-and-attributes"></a>元素和属性

如果此架构定义了具体要求，如**sequence**， **minOccurs**、 **maxOccurs**和**choice**，请参阅定义部分。 
  
### <a name="parent-elements"></a>父元素

无。
  
### <a name="child-elements"></a>子元素

|**元素**|**类型**|**说明**|
|:-----|:-----|:-----|
|[Solution](solution-element-solutions_type-complextypevisio-xml.md) <br/> |[Solution_Type](solution_type-complextypevisio-xml.md) <br/> |指定 XML 存储在绘图中的解决方案的一个的实例。  <br/> |
   
### <a name="attributes"></a>Attributes

无。
  

